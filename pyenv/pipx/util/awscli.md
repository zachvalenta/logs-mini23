```sh
$ pipx install awscli

installed package awscli 1.46.0, installed using Python 3.12.1
These apps are now globally available
- aws
- aws.cmd
- aws_bash_completer
- aws_completer
- aws_zsh_completer.sh
done! ✨ 🌟 ✨
```

# err

just installed aws cli using pipx:

$ aws
zsh: /Users/zach/.local/bin/aws: bad interpreter: /Users/zach/Library/Application: no such file or directory

# explanation

cause

aws is a pipx-generated script with this shebang:

```sh
#!/Users/zach/Library/Application Support/pipx/venvs/awscli/bin/python
```

Because the interpreter path contains a space (Application Support), macOS tries to run:

```sh
/Users/zach/Library/Application
```

and fails with:

```sh
bad interpreter: /Users/zach/Library/Application: no such file or directory
```

fix option A: move pipx home to a no-space path

Recommended.

```sh
export PIPX_HOME="$HOME/.local/pipx"
export PIPX_BIN_DIR="$HOME/.local/bin"
```

Add those to your shell config, then reinstall awscli:

```sh
pipx uninstall awscli
pipx install awscli
hash -r
aws --version
```

fix option B: reinstall just this app using env vars once

```sh
PIPX_HOME="$HOME/.local/pipx" PIPX_BIN_DIR="$HOME/.local/bin" pipx uninstall awscli
PIPX_HOME="$HOME/.local/pipx" PIPX_BIN_DIR="$HOME/.local/bin" pipx install awscli
hash -r
aws --version
```

verify

After reinstall:

```sh
head -n 1 ~/.local/bin/aws
```

Should look like:

```sh
#!/Users/zach/.local/pipx/venvs/awscli/bin/python
```

No spaces in the interpreter path.

# but why

why doesn't this happen with other pipx installs then?

# bc

why

 Because your other pipx apps are using a different launcher style.

 For example, bpython, csvcut, llm, etc. have this:

 ```sh
   #!/bin/sh
   '''exec' "/Users/zach/Library/Application Support/pipx/venvs/llm/bin/python" "$0" "$@"
   ' '''
 ```

 So the actual shebang is just:

 ```sh
   #!/bin/sh
 ```

 Then the shell runs the Python path with quotes, so Application Support is fine.

 But aws has this:

 ```sh
   #!/Users/zach/Library/Application Support/pipx/venvs/awscli/bin/python
 ```

 The OS parses shebangs before any shell is involved, and shebang interpreter paths cannot contain unescaped spaces. It splits at the space and tries:

 ```sh
   /Users/zach/Library/Application
 ```

 Hence:

 ```sh
   bad interpreter: /Users/zach/Library/Application: no such file or directory
 ```

 why aws is different

 Likely because awscli ships/installs its executable as a script file, while many other packages expose commands via Python console_scripts entry points. The generated console_scripts wrappers are smart enough to use the /bin/sh
 trampoline when the Python interpreter path contains spaces.

 awscli ends up with a direct rewritten shebang instead, which breaks under pipx's macOS default venv location:

 ```sh
   ~/Library/Application Support/pipx/venvs/...
 ```

 practical takeaway

 This is not really a zsh issue. It is the combination of:

 - pipx venv path contains a space
 - awscli launcher uses direct Python shebang
 - macOS shebang parsing does not tolerate that space

 Best durable fix is still moving pipx venvs somewhere without spaces, e.g.:

 ```sh
   PIPX_HOME="$HOME/.local/pipx"
   PIPX_BIN_DIR="$HOME/.local/bin"
 ```


 would this get fixed if I just used pip to install vs. pipx?


 short answer

 Maybe, but only if the target install path has no spaces.

 specifics

 If you used pip install --user awscli, the script would likely land at:

 ```sh
   ~/.local/bin/aws
 ```

 and its shebang would point to your Python interpreter, e.g.:

 ```sh
   #!/usr/local/bin/python3
 ```

 or:

 ```sh
   #!/opt/homebrew/bin/python3
 ```

 Those paths usually do not contain spaces, so yes, it would probably avoid this exact error.

 But if you used pip inside a virtualenv located under:

 ```sh
   ~/Library/Application Support/...
 ```

 you could hit the same problem, because the generated aws script might still get a shebang with a space-containing interpreter path.

 tradeoff

 I would not switch to pip just for this. pipx is the right tool for CLI apps because it isolates dependencies per app.

 Better options:

 1. Move pipx venvs to a no-space path:
    ```sh
      export PIPX_HOME="$HOME/.local/pipx"
      export PIPX_BIN_DIR="$HOME/.local/bin"
      pipx reinstall awscli
    ```
 2. Use AWS's official installer:
    ```sh
      brew install awscli
    ```
    or the AWS bundled installer.
 3. Use pip install --user awscli if you want the quick path, but it is less isolated and can pollute/conflict with your user Python environment.

# brew?

is the official installer actually homebrew, bc not mentioned in docs https://github.com/aws/aws-cli

# sure

answer

 zjv, no: Homebrew is not the official AWS installer.

 The official AWS CLI v2 installer is the AWS-provided macOS package from awscli.amazonaws.com, e.g. conceptually:

 ```sh
   curl "https://awscli.amazonaws.com/AWSCLIV2.pkg" -o "AWSCLIV2.pkg"
   sudo installer -pkg AWSCLIV2.pkg -target /
 ```

 Homebrew:

 ```sh
   brew install awscli
 ```

 is a common/convenient install route, but it is maintained through Homebrew packaging, not the official AWS install path. The fact that the AWS docs/GitHub README do not mention Homebrew is a good signal that AWS does not present it
 as the official installer.

 important wrinkle

 Your pipx install is:

 ```txt
   awscli 1.46.0
 ```

 That is AWS CLI v1 from PyPI.

 AWS CLI v2 is the current recommended major version and is distributed via AWS's bundled installers, not normal pip install awscli.

 So your realistic options are:

 1. Official AWS path: use AWSCLIV2.pkg
 2. Homebrew path: brew install awscli, convenient but not official
 3. pipx path: keep AWS CLI v1, but fix PIPX_HOME so paths have no spaces

 If you want least fiddling and current AWS CLI v2, I would use the AWS pkg installer or Homebrew.
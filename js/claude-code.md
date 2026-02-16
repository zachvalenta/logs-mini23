# 🛜 INSTALL

## init

```sh
$ npm install -g @anthropic-ai/claude-code

added 3 packages in 2s
2 packages are looking for funding
  run `npm fund` for details
npm notice
npm notice New major version of npm available! 10.9.2 -> 11.3.0
npm notice Changelog: https://github.com/npm/cli/releases/tag/v11.3.0
npm notice To update run: npm install -g npm@11.3.0
npm notice
```

## version bump

```sh
$ claude update
Current version: 0.2.74
Checking for updates...
New version available: 1.0.31 (current: 0.2.74)
Installing update...
Using global installation update method...
Successfully updated from 0.2.74 to version 1.0.31
```

# 🫟 MESS

## ✅ doc

Your take (which seems right!):

```sh
Homebrew has Node/npm installed (at /opt/homebrew/bin)
- NVM has Node/npm installed (at ~/.config/nvm/versions/node/v22.13.1/bin)
- When you run npm install -g, it installs to whichever npm is first in PATH
- The symlink at /opt/homebrew/bin/claude exists because you ran npm install -g when Homebrew's npm was in PATH
```

* can you add an 'install' header to my CC notes documenting this mess
* there are a bunch of coreutils-esque commands we used to debug this - type, command - that I've never used before. my default is just running `which`. I have a header for 'path'. Can you flesh out how to use these commands to debug path issues.
* In the same path header, can you document the Homebrew / NPM interplay that occured here. Might be some overlap to the notes you're adding to the CC install header, but that's ok. Let's just add links btw the CC install header, Homebrew, and path.

## ✅ no SSoT

* per GPT:
```sh
You actually have two Claudes:

claude via NVM: /Users/zach/.config/nvm/versions/node/v22.13.1/bin/claude
claude via Homebrew prefix: /opt/homebrew/bin/claude -> ../lib/node_modules/@anthropic-ai/claude-code/cli.js
```
* I never want to have two installs of the same app/binary. So we've got to pick a single install
* Again, per GPT:
```sh
If you want the most boring setup: make brew come first and delete the NVM-installed claude:
```

## ✅ find SSoT

Given that Anthropic is pushing their native installer and I'll probably be swimming against the current (and get annoying prompts to switch to the native install), I'm leaning towards switching to the native installer.

My questions/concerns with doing that:

* If I didn't install the Homebrew version of CC myself, I'm worried about uninstalling. Although, unlike Homebrew installing its own versions of Python, Ruby, et. al. - CC is not a primitive for other tools. So in theory it should be safe to get it out of there.
* I was fine w/ CC auto-updating before this mess. Now, I want some mechanism to version control changes in CC versions. I want to have a working version of CC, attempt upgrade, and if things go fubar at least I have something under version control and can do a simple git diff btw version-that-worked and new-version-that-is-blowing-up.

So basically I'd choose whatever install method that leads to less of this foolishness.

## ✅ settings weirdness

I have no idea what this means:

```json
"skipDangerousModePermissionPrompt": true
```

and have no idea how it came into my settings during this mess, but I have doubts/concerns.

Your take:

```sh
Current state: Has skipDangerousModePermissionPrompt: true

When it changed: November 23, 2025 (file timestamp)

Most likely cause: Claude Code 1.0.x introduced this setting and auto-added it when you first ran the updated version. The 0.2.74 → 1.0.31 jump is a MAJOR version bump — they probably migrated settings automatically.
```

This just happened today (2026.02.13) in my settings. Where are you getting this file timestamp?

# 🧺 REMEDIATION

* got rid of - hopefully - both the NVM and brew versions of CC
```sh
npm uninstall -g @anthropic-ai/claude-code
brew uninstall claude-code
```

```sh
  # 2. Install native (check CC docs for latest installer)
  # 3. Log it: echo "$(date) - native installer v1.0.31" >> ~/Documents/denv/logs/js/claude-code.log

  # 4. Remove claude() wrapper from .zshrc

```

couple more items:

* Can you provide the cmds to uninstall both the Homebrew and NPM versions?
* `echo "$(date) - native installer v1.0.31" >> ~/Documents/denv/logs/js/claude-code.log` -> this logs the initial install, but doesn't allow me to control and version subsequent updates. Assume there's 1) config to opt out of auto-update 2) mechanism to update the native install and thus version control. Can you figure out what those are?

## drop brew CC
## drop NPM CC
## install & version native
## drop zsh.rc wrapper
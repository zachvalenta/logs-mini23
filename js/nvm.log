$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 16563  100 16563    0     0   106k      0 --:--:-- --:--:-- --:--:--  109k
=> Downloading nvm from git to '/Users/zach/.config/nvm'
=> Cloning into '/Users/zach/.config/nvm'...
remote: Enumerating objects: 381, done.
remote: Counting objects: 100% (381/381), done.
remote: Compressing objects: 100% (324/324), done.
remote: Total 381 (delta 43), reused 179 (delta 29), pack-reused 0 (from 0)
Receiving objects: 100% (381/381), 383.70 KiB | 6.73 MiB/s, done.
Resolving deltas: 100% (43/43), done.
* (HEAD detached at FETCH_HEAD)
  master
=> Compressing and cleaning up git repository
=> Appending nvm source string to /Users/zach/.zshrc
=> Appending bash_completion source string to /Users/zach/.zshrc
=> Close and reopen your terminal to start using nvm or run the following to use it now:
export NVM_DIR="$HOME/.config/nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

$ command -v nvm
nvm

$ nvm install --lts
Installing latest LTS version.
Downloading and installing node v22.13.1...
Downloading https://nodejs.org/dist/v22.13.1/node-v22.13.1-darwin-arm64.tar.xz...
########################################################################################################################################################################################################### 100.0%
Computing checksum with shasum -a 256
Checksums matched!
Now using node v22.13.1 (npm v10.9.2)
Creating default alias: default -> lts/* (-> v22.13.1)

$ nvm current # v22.13.1
$ nvm ls      # -> v22.13.1, default -> lts/* (-> v22.13.1), unstable -> N/A (default)
$ which node  # /Users/zach/.config/nvm/versions/node/v22.13.1/bin/node
$ which npm   # /Users/zach/.config/nvm/versions/node/v22.13.1/bin/npm

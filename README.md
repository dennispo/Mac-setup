# Mac-setup

## Must have
- (Homebrew)[https://brew.sh]
  _Xcode Command Line Tools_ will be installed as part of Homebrew.
  Installation: ```/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"```
  After the install, register the command via:
  ```
  echo >> ~/.zprofile
  echo 'eval "$(/opt/homebrew/bin/brew shellenv zsh)"' >> ~/.zprofile
  eval "$(/opt/homebrew/bin/brew shellenv zsh)"
  ```
- (iterm2)[https://iterm2.com]
  Installation by downloading from (https://iterm2.com/downloads.html)[https://iterm2.com/downloads.html]
  Move to `Applications` folder after downloading.
  Peferred profile settings are at `./iterm2/Default.json`
- (oh-my-zsh)[https://ohmyz.sh]
  Installation: `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`


# Mac-setup

## Must have
### [Homebrew](https://brew.sh)
  _Xcode Command Line Tools_ will be installed as part of Homebrew.

  Installation:
  ```
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```

  After the install, register the environment via:
  ```
  echo >> ~/.zprofile
  echo 'eval "$(/opt/homebrew/bin/brew shellenv zsh)"' >> ~/.zprofile
  eval "$(/opt/homebrew/bin/brew shellenv zsh)"
  ```

### [iterm2](https://iterm2.com)
  Installation by downloading from <https://iterm2.com/downloads.html>
  Move to `Applications` folder after downloading.
  Peferred profile settings are at `./iterm2/Default.json`

### [oh-my-zsh](https://ohmyz.sh)
  Installation:
  ```
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

  My preferred plugins are:
  ```plugins=(git common-aliases docker docker-compose iterm2 macos sudo themes urltools)```

### [Powerline fonts](https://github.com/powerline/fonts)
  Installation:
  ```
  git clone https://github.com/powerline/fonts.git --depth=1
  cd fonts
  ./install.sh
  cd ..
  rm -rf fonts
  ```

### [Github SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
Generate keys pair:
```
ssh-keygen -t ed25519 -C "dennispo@gmail.com"
```

First, check to see if your ~/.ssh/config file exists in the default location.
```
$ open ~/.ssh/config
> The file /Users/YOU/.ssh/config does not exist.
```

If the file doesn't exist, create the file.
```
touch ~/.ssh/config
```

Open your ~/.ssh/config file, then modify the file to contain the following lines. If your SSH key file has a different name or path than the example code, modify the filename or path to match your current setup.
``` Text
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

Add your SSH private key to the ssh-agent and store your passphrase in the keychain. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.
```
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

Last, add the SSH public key to your account on GitHub. For more information, ([Adding a new SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)):

Copy the contents of public key to the clipboard:
```
pbcopy < ~/.ssh/id_ed25519.pub
```

Goto [Github.com > Profile > Settings > SSH and GPG keys](https://github.com/settings/keys) and add a new SHH key.
### Docker + Compose
Installation:
```
brew update
brew install docker docker-compose
```

## Development environment

### [IntelliJ IDEA](https://lp.jetbrains.com)
Download proper DMG from the web site

### [VSCode](https://code.visualstudio.com)
Download proper DMG from the web site

### [Simple Python Version Management: pyenv](https://github.com/pyenv/pyenv)
Installation of the manager:
```
brew update
brew install openssl readline sqlite3 xz tcl-tk@8 libb2 zstd zlib pkgconfig pyenv
```
```
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init - zsh)"' >> ~/.zshrc
```

### [Claude Code](https://claude.com/product/claude-code)
Installation:
```
curl -fsSL https://claude.ai/install.sh | bash
```
Setup:
```
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc
```

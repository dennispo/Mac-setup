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

### Docker + Compose
Installation:
```
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

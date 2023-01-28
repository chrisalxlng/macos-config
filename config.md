# macOS Configuration (Monterey, last updated: December 2022)

## App Store

- Install Magnet

## System Preferences

### General

- Change Accent Color

### Dock

- Remove most applications from Dock
- Position -> "Left"
- Automatic Hide
- Smaller Dock
- "Minimize windows using" -> "Scale effect"
- "Show recent applications in Dock" off
- "Show indicators for open applications" on
- Battery -> "Show Percentage"

### Notifications

- Off, except Headphones & Find My

### Siri

- Disable

### Trackpad

- Disable Notification Center
- Disable Look Up & Data Detectors

### Keyboard

- Text
    - disable "Autocorrect"
    - disable "Capitalise word automatically"
    - disable "Add full stop with double-space"
    - disable "Use smart quotes and dashes"
    - use " for double quotes
    - use ' for single quotes
    
### Spotlight

- Disable Spotlight except for Applications and System Preferences

### Mission Control

- Hot Corners: disable all

### Finder

- General
    - "New Finder windows show" -> home folder
    - Disable "Open folders in tabs instead of new windows"
- Tags
    - Remove all
- Sidebar
    - activate all Favorites
- Advanced
    - Show all Filename Extensions
    - Remove Items from Bin after 30 Days
- Customize Toolbar
    - AirDrop
    - View
    - Sort by
    - More
    - Search
- View
    - Enable path bar
    - Enabale status bar

### Security and Privacy

- Use Apple Watch for Unlocking Mac
- Add Browser to "Screen Recording"

### Extensions

- Remove everything unncessary from Share Menu

### Storage

- Remove all unnecessary apps

### Trackpad

- Speed: 9/10

### Accessibility
- Scroll Speed: 6/8

## System Preferences (Terminal)

- Change computer name
    - `sudo scutil --set ComputerName "newname"`
    - `sudo scutil --set LocalHostName "newname"`
    - `sudo scutil --set HostName "newname"`
- Take screenshots as jpg (usually smaller size) and not png
    - `defaults write com.apple.screencapture type jpg`
- Make dock appear quicker
    - `defaults write com.apple.dock autohide-delay -float 0; defaults write com.apple.dock autohide-time-modifier -float 0.6`
- Do not open previous previewed files (e.g. PDFs) when opening a new one
    - `defaults write com.apple.Preview ApplePersistenceIgnoreState YES`
- Restart everything modified
    - `killall Terminal`
    - `killall Dock`
    - `killall Finder`

## Homebrew

### Installation

- `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
- `echo 'eval $(/opt/homebrew/bin/brew shellenv)' >> /Users/YOUR USER NAME/.zprofile`
- `eval $(/opt/homebrew/bin/brew shellenv)`
- `brew update`

### GUI apps

```
brew install --cask \
  google-chrome  \
  firefox \
  visual-studio-code \
  docker \
  discord \
  signal \
  whatsapp \
  figma
```

### Terminal apps

```
brew install \
  git \
  nvm \
  pnpm \
  yarn
```

## GUI apps

### Google Chrome

- Preferences
    - Enable dark mode
    - Never save passwords
    - Always show bookmarks
- Chrome Developer Tools
    - Enable dark mode
    - Network -> only "Fetch/XHR"
- Chrome Extensions
    - [React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en)
    - [Live color picker](https://chrome.google.com/webstore/detail/live-color-picker/ocfboephblnapfbccjigejhblhkpgflj)
    
### Visual Studio Code

- Log into GitHub and enable Settings Sync

## Terminal apps

### Git

- Set global name and email
    - `git config --global user.name "Your Name"`
    - `git config --global user.email "you@your-domain.com"`
- Improved log
    - `git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"`
    - Now use: `git lg`
- Print global git configuration
    - `git config --list`
    
### NVM

- Complete installation
    - `mkdir ~/.nvm`
    - `echo "export NVM_DIR=~/.nvm\nsource \$(brew --prefix nvm)/nvm.sh" >> .zshrc`
    - `source ~/.zshrc`
- Check if nvm installation was successful
    - `nvm -v`
- Install latest LTS version
    - [Find latest LTS version](https://nodejs.org/en/)
    - `nvm install <latest LTS version>`
- Check if node installation was successful
    - `node -v && npm -v`
- Update npm to its latest version
    - `npm install -g npm@latest`
- Set defaults for npm
    - `npm config set init-author-name="your name"`
    - `npm config set init-author-email="you@example.com"`
- List all Node installations
    - `nvm list`
- *Optional:* Install other Node versions
    - `nvm install <version> --reinstall-packages-from=$(nvm current)`
    - Use specific version: `nvm use <version>`
    - Make specific version default: `nvm alias default <version>`

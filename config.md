# macOS Configuration (Monterey, last updated: April 2023)

## App Store

- Install Magnet

## Safari Installations

- Install Arc browser

## Arc

### Manage Flags

1. Navigate to `arc://flags`
2. Enable `#high-efficiency-mode-available`
3. Enable `#enable-parallel-downloading`
4. Relaunch Arc
5. Navigate to `arc://settings`
6. Enable `Performance` > `Memory Saver`

### Manage Spaces & Profiles

- Setup

## System Preferences

### Appearance

- Dark mode
- Change accent color to "Purple"

### Dock

- Remove most applications from dock
- Position -> "Left"
- Automatic hide
- Smaller dock
- "Minimize windows using" -> "Scale effect"
- "Show recent applications in Dock" off
- "Show indicators for open applications" on

### Control Center

- Battery -> "Show Percentage in Menu Bar"

### Notifications

- Off, except Arc & Find My

### Spotlight & Siri

- Disable Siri

### Trackpad

- Disable "Notification Center" gesture
- Disable "Look Up & Data Detectors" gesture
- Cursor speed: 9/10

### Keyboard

- Text
    - Disable "Autocorrect"
    - Disable "Capitalise word automatically"
    - Disable "Add full stop with double-space"
    - Disable "Use smart quotes and dashes"
    - Use " for double quotes
    - Use ' for single quotes
- Shortcuts
    - Disable `Spotlight`
    
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
  visual-studio-code \
  docker \
  raycast
```

### Terminal apps

```
brew install \
  git \
  nvm \
  yarn
```

## Terminal apps

### Git

- Set global name and email
    - `git config --global user.name "Your Name"`
    - `git config --global user.email "you@your-domain.com"`
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

## GUI apps
    
### Visual Studio Code

- Log into GitHub and enable Settings Sync

### Raycast

- Disable all built-in extensions except `Calendar`, `Clipboard History`, `File Search` & `System`
- Install `Color Picker` extension for menu bar color picker
    - Disable all commands except menu bar command
- Add alias for `Screenshot`
- Configure `Calendar` extension
    - Show Events in Menu Bar: `5 minutes before`
    - Select desired calendars

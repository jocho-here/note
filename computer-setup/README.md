# tools-configuration
### Slack
### fliqlo
### Docker
### Homebrew
### Rectangle

### Postico
- Export favorites to the new computer

### Postman
- username: `mkc.k2580@gmail.com`

### Sublime
- `ln -s "/Applications/myapp/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime`
- Sublime license in the Documents
- To enable key repeats, run `defaults write com.sublimetext.2 ApplePressAndHoldEnabled -bool false` in terminal
- Install Sublime Package Control
    - Install Pretty JSON
- Copy settings from the previous computer
    - 'Preferences' -> 'Key Bindings'
    - 'Preferences' -> 'Settings'

### zsh
- `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
- Then, remove the original `~/.oh-my-zsh` and replace it with `git clone https://github.com/mgjo5899/oh-my-zsh`
- Set up the upstream `git remote add upstream https://github.com/robbyrussell/oh-my-zsh`
- Copy over `~/.zshrc` and `~/.zshenv`

### tmux
- `brew install tmux`
- Copy over ~/.tmux.conf

### Neovim
- `brew install neovim`
- `alias vim="nvim"`
- Copy over `~/.config/nvim/`
- Set up Simple plugin
    - [https://github.com/junegunn/vim-plug](https://github.com/junegunn/vim-plug)

### NVM
- Use the script to install, not Homebrew
- With this, install node and npm

### Pyenv
- `brew install pyenv`
- With this, install other Python versions

### htop
- `brew install htop`

### Quick Look Markdown
- Check out [github page](https://github.com/toland/qlmarkdown)
- `brew update`
- `brew install --cask qlmarkdown`
- `qlmanage -r`

### hushlogin
- `touch ~/.hushlogin`

### Change the computer name
- [https://www.wikihow.com/Change-Your-Computer%27s-Name-on-a-Mac](https://www.wikihow.com/Change-Your-Computer%27s-Name-on-a-Mac)

### Set Zoom with control
- System Preferences -> Accessibility -> Zoom -> "Use scroll gesture..."

### iTerm
- Export the profile as a JSON file and import it from the new computer
- Closely follow other settings by having iterms pulled up on the new and old computers side-by-side

### Git
- `git` and it should download git and Mac OS command line tool as well
- `git config --global user.email "mgjo5899@gmail.com"`
- `git config --global user.name "mgjo5899"`

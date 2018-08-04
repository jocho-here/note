# tools-configuration


## General Tools
### Sublime
- `ln -s "/Applications/myapp/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/sublime`

### Postman

### zsh
- `sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
- Then, remove the original `~/.oh-my-zsh` and replace it with `git clone https://github.com/mgjo5899/oh-my-zsh`
- Set theunraveler as the theme in `~/.zshrc`
- **Need to save .zshrc in gist**

### tmux
- `brew install tmux`
- Set up ~/.tmux.conf
- add `unsetopt share_history` in `~/.zshrc` so tmux panes don't share history with panes

### Neovim
- `alias vim="nvim"`
- Set up `~/.config/nvim/init.vim` and `~/.config/nvim/colors/dracula.vim`

### Python Virtual Environment
- python3: `python3 -m venv <directory>`
- python2: virtualenv

### Docker
- For ubuntu, follow the [guide](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04)


## Mac OS specific
### hushlogin
- `touch .hushlogin`

### Change the computer name
- [https://www.wikihow.com/Change-Your-Computer%27s-Name-on-a-Mac](https://www.wikihow.com/Change-Your-Computer%27s-Name-on-a-Mac)

### Set Zoom with control
- System Preferences -> Accessibility -> Zoom -> "Use scroll gesture..."

### iterm
- Set up word/line deletion: [ref](https://coderwall.com/p/ds2dha/word-line-deletion-and-navigation-shortcuts-in-iterm2)
- Set up line jumps: [ref](https://stackoverflow.com/questions/6205157/iterm-2-how-to-set-keyboard-shortcuts-to-jump-to-beginning-end-of-line)
- Set up word jumps: [ref](https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x)
- Set up font
    - menlo
    - regular
- Make it transparent
- Make it the menu bar black
    - Preference -> Window -> Uncheck "Show line under title bar when..."
    - Preference -> Profiles -> Make Tab Color to black

### Homebrew

### Python 3
- `brew install python3`
- `export PYTHONDONTWRITEBYTECODE=1`

### Spectacle

### Development directory
- `mkdir ~/Project`

### Git
- `git` and it should download git and Mac OS command line tool as well
- `git config --global user.email "mgjo5899@gmail.com"`

### NPM
- `brew install node`

### MySQL
- `brew install mysql`
- Sequel Pro
    - Use MySQL version 5.7

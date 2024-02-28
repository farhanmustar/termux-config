# Install
* install latest termux from fdroid, (google play have older version only).
# Config
* edit ~/.termux/termux.properties.
    * enable ctrl + space fix.
* use exkeymo to generate new keyboard layout to map capslock -> escape
* install unexpected keyboard for on-screen keyboard.

# Vim Config
* Compile vim-ctrlspace engine using go or use prebuild in this repo.
```bash
cd ~/.config/nvim/plugged/vim-ctrlspace/go
go build -o file_engine_termux ./file_engine.go
mv ./file_engine_termux ../bin/
```

# Initial Setup
* Setup storage access, run following command and click allow on screen popup.
```bash
termux-setup-storage
```

* Allow termux app to run in app background in settings.
* Some android can also lock the app in the running app list or from drawer.

# Notes:
* list all pkg and its description
```bash
for pkg in $(apt-cache pkgnames | sort); do printf "$pkg - $(apt-cache show $pkg | grep -m 1 "Description:"  | cut -c 14-)\n"; done
```

* Root is not accessible in termux. use PREFIX env variable.
```bash
cd $PREFIX/etc
```

* there is no .bashrc in home folder, instead edit it here.
```bash
vim $PREFIX/etc/bash.bashrc

# add following line inside it to use our dotfiles
export PATH=$PREFIX/etc/alternatives/:$PATH
source $HOME/.bash_aliases
source $HOME/.profile
```

* use termux-services and termux:boot to run service similar to supervisord
   1. [termux-services](https://wiki.termux.com/wiki/Termux-services) 
   2. [termux:boot](https://wiki.termux.com/wiki/Termux:Boot) 

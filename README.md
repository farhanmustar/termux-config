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

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

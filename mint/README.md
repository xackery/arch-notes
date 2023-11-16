1. sudo apt install nala (undo history, apt wrapper)
1. sudo nala install neovim waterfox wine
1. sudo nala remove hexchat
1. download [waterfox](https://www.waterfox.net/download/)
    1. tar -xvf waterfox-*.tar.bz2
    1. cd waterfox
    1. ./waterfox (verify it works)
    1. sudo mv waterfox /usr/local/src/
    1. cd /usr/local/bin
    1. ln -s /usr/local/src/waterfox/waterfox waterfox
    1. Right click start button,  edit menu, add item
    1. link to /usr/local/bin/waterfox for executable, for icon use /usr/local/src/waterfox/browser/chrome/icons/default/default128.png
1. download [golang](https://go.dev/dl/), grab the linux zip
    1. tar xzf go*.tar.gz
    1. mv go go-1.21.4 (or whatever your version is)
    1. sudo mv go-1.21.4 /usr/local/src/
    1. sudo ln -s go-1.21.4 go
    1. sudo ln -s /usr/local/src/go/bin/go /usr/local/bin/go
    1. sudo ln -s /usr/local/src/go/bin/gofmt /usr/local/bin/gofmt
    1. mkdir -p ~/.bin
    1. nano ~/.bashrc
    1. on bottom of bashrc, add `export PATH=$PATH:$HOME/.bin`
    1. on bottom of bashrc, add `export GOBIN=$HOME/.bin`
    1. source ~/.bashrc
    1. go env and verify all paths set proper (GOPATH, GOBIN, GOROOT)
    1. if you want to update go, repeat steps and tweak the symolinks to the new version
1. download vscode
    1. when asked for a keyring, don't put a password
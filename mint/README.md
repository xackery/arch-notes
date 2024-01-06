1. sudo mkdir /src
1. sudo chown -R $USER /src
1. sudo chgrp -R $USER /src
1. sudo apt install nala (undo history, apt wrapper)
1. sudo nala install neovim wine libc6-dev
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
1. download aseprite
    1. cd /src
    1. git clone git@github.com:nilsve/docker-aseprite-linux.git (if permission denied, generate a ssh key)
        1. ssh-keygen -f ~/.ssh/github (don't put a password)
        1. cat ~/.ssh/github.pub (copy to clipboard)
        1. log in to github, click profile pic, settings, ssh keys, add new, paste
    1. cd docker-aseprite-linux
1. download docker
    1. as per [this guide](https://docs.docker.com/desktop/install/ubuntu/), run:
        https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository
        You can run this, because mint doesn't natively support the command:
        ```
        # Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  jammy stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
        ```

now run `sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`
and finally `sudo usermod -aG docker $USER`
`newgrp docker`
now try `docker run hello-world`
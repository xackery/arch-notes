## Live CD Stuff

If install text is too small (retina), 
run `setfont ter-132b`

`ip a` make sure an address was found. if not, may need to configure dhcp yourself.

Once you have internet, 

`archinstall` is the guided installer. Set up each step. Copying network config is needed

## Package Managers

### YAY

Yay is handy for non-essential stuff. Avoid it for kernal/core stuff
```sh
git clone https://aur.archlinux.org/yay-git.git
ls -la
cd yay-git
makepkg -si
yay -S name-of-package (for installing a package)
```

### Flatpak

Flatpak has pretty wide support and is handy with how it sandboxes it's install, but you have to manually alias commands or run annoying flatpak run com.domain.appname commands
`sudo pacman -S flatpak`

### Source AUR Building

General idea is search for a `package aur` term, and you'll see a git url. Clicking copies it to clipboard.

Basically, you build it via:
```
mkdir -p ~/src/aur
cd ~/src/aur
git clone <url paste>
cd <package name>
makepkg -si
```

### Dark Mode

With awesomewm, dark mode is basically achieved by:
`sudo pacman -S lxappearance`

lxappearance handles qt, which a lot of arch stuff tends to use.
- `gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'` can help too


### Fonts
Default awesome font on arch sucks, especiall on retina. There's countless fonts out there, but my favorite (especially on retina) is [Fira Code Retina](https://aur.archlinux.org/packages/ttf-firacode)
```
cd ~/src/aur
git clone https://aur.archlinux.org/ttf-firacode.git
cd ttf-firacode
makepkg -si
```
- Go into lxappearance and set the font to Fira Code Retina.
- for alacritty font:
  - `mkdir -p ~/.config/alacritty``
  - `cp /usr/share/doc/alacritty/example/alacritty.yml ~/.config/alacritty/alacritty.yml``
  - edit it namely: adding:
```yaml
font:
    normal:
        family: Fira Code Retina
```

If discord fonts have [] blocks and other invalid stuff,
`sudo pacman -S noto-fonts-extra` is the fix


I'm running a macbook pro mid 2014, so [this guide](https://wiki.archlinux.org/title/MacBookPro11,x) was helpful, but a lot of parts outdated.

### WIFI
- I had to plug in a thunderbolt to ethernet to get internet initially, then used macbook guide above to install broadcom-wl-dkms
- then I installed networkmanager and networkmanager-applet

### Graphics
- I had to install nvidia-470xx-dkms


### AwesomeWM

[my awesome-wm config is being trackeed elsewhere](https://github.com/xackery/awesome-wm)
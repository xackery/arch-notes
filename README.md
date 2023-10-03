If install text is too small (retina), run `setfont ter-132b`

`archinstall` is the guided installer. Set up each step. Copying network config is needed

Yay is handy for non-essential stuff. Avoid it for kernal/core stuff
```sh
git clone https://aur.archlinux.org/yay-git.git
ls -la
cd yay-git
makepkg -si
yay -S name-of-package (for installing a package)
```

Flatpak is handy but the alias headache can be annoying for awesomewm integration


General idea is search for a `package aur` term, and you'll see a git url. Clicking copies it to clipboard.

Basically, you build it via:
```
mkdir -p ~/src/aur
cd ~/src/aur
git clone <url paste>
cd <package name>
makepkg -si
```

---dark mode--
With awesomewm, dark mode is basically achieved by:
`sudo pacman -S lxappearance`

lxappearance handles qt, which a lot of arch stuff tends to use.
- `gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'` can help too


-- fonts --
There's countless founts out there, but my favorite (especially on retina) is [Fira Code Retina](https://aur.archlinux.org/packages/ttf-firacode)
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

[my awesome-wm config is being trackeed elsewhere](https://github.com/xackery/awesome-wm)

I'm running a macbook pro mid 2014, so [this guide](https://wiki.archlinux.org/title/MacBookPro11,x) was helpful, but a lot of parts outdated.

-- wifi --
- I had to plug in a thunderbolt to ethernet to get internet initially, then used macbook guide above to install broadcom-wl-dkms
- then I installed networkmanager and networkmanager-applet

-- graphics card --
- I had to install nvidia-470xx-dkms


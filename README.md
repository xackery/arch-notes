If install text is too small, run `setfont ter-132b`
`archinstall` is the guided installer. Set up each step.

Once you're booted in, either run `startx` or from cli do your operations
- `sudo pacman -Syu` update all packages
- `sudo pacman -S code` install vscode
- `sudo pacman -S alacritty`

Yay AUR helper
```sh
git clone https://aur.archlinux.org/yay-git.git
ls -la
cd yay-git
makepkg -si
yay -S name-of-package (for installing a package)
```

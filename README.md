If install text is too small, run `setfont ter-132b`
`archinstall` is the guided installer. Set up each step.

Once you're booted in, either run `startx` or from cli do your operations
- `sudo pacman -Syu` update all packages
- `sudo pacman -S code lxqt-policykit` install vscode
- `sudo pacman -S alacritty`
- `pacman -S git nitrogen picom polkit`
Yay AUR helper
```sh
git clone https://aur.archlinux.org/yay-git.git
ls -la
cd yay-git
makepkg -si
yay -S name-of-package (for installing a package)
```
- `sudo yay -S yin-yang`
- `gsettings set org.gnome.desktop.interface color-scheme 'prefer-dark'`
- In vscode, go to Edit, Preferences, Settings, and search for "title bar style" and set it to custom. Restart, and the top bar will go dark.
- `xdg-mime default code.desktop text/plain` Set code as default editor

- [steps for remaining dark theme tweaks](https://unix.stackexchange.com/questions/683823/dark-theme-for-applications-launched-within-awesome-window-manager)

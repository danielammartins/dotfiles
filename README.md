Work in Progress

-  **OS:** Manjaro
-  **DE:** Plasma
-  **WM:** KWin w/ Krohnkite
-  **Terminal:** Konsole
-  **Terminal Font:** Noto Sans
-  **System Font:** Noto Sans
-  **Bar/Panel:** Latte-Dock
-  **File Manager:** Dolphin
-  **Browser:** Firefox
-  **Music Player:** Spotify

Firefox CSS is based on [minimal-functional-fox](https://github.com/mut-ex/minimal-functional-fox) with a few custom tweaks

Latte layout is custom and requires adicional widgets:
-  Virtual Desktop Bar
-  Latte Spacer
-  macOS BS Inline Battery
-  Better Inline Clock

## :pushpin: Dependencies

-  [Latte-Dock](https://github.com/KDE/latte-dock) (git version)
-  [wpgtk](https://github.com/deviantfero/wpgtk) & [pywal](https://github.com/dylanaraps/pywal)
-  [qt5-styleplugins](https://github.com/qt/qtstyleplugins) ([AUR](https://aur.archlinux.org/packages/qt5-styleplugins/), can also be installed with `pacman`)

## :paperclip: Recommendations

-  [Spicetify-cli](https://github.com/khanhas/spicetify-cli) (make sure to install [Dribbblish](https://github.com/morpheusthewhite/spicetify-themes/tree/master/Dribbblish) as well.) (Spotify has to be either from the AUR or Flatpak)
-  VS Code Extension - [Wal Theme](https://marketplace.visualstudio.com/items?itemName=dlasagno.wal-theme) (uses pywall to get theme's colors) or [Nord Native](https://marketplace.visualstudio.com/items?itemName=divanvisagie.nord-native-theme)
-  [Krohnkite](https://store.kde.org/p/1281790/)
-  [Zathura-Pywal](https://github.com/GideonWolfe/Zathura-Pywal)
-  [betterdiscordctl](https://github.com/bb010g/betterdiscordctl) & [pywal-discord](https://github.com/FilipLitwora/pywal-discord)

## :hammer_and_wrench: Setup

**Global Theme:** Breeze Dark 

**Install the dependencies:**

- ```bash
  # both yay and pacman work
  yay -S latte-dock-git wpgtk-git qt5-styleplugins python-pywal
  ```
<details open>
<summary><strong>Clone and copy most of the stuff</strong></summary>
  
- ```bash
  git clone https://github.com/danielammartins/mydotfiles
    ```
- ```bash
  # Copy .local, .config, .themes, and .ncmpcpp to your home directory.
  cd mydotfiles/ && cp -r {.local,.config,.themes} ~/
  ```
   
</details>

To remove title bars and add active/inactive frame colors, follow [this guide](https://github.com/esjeon/krohnkite#removing-title-bars)

Import the Latter layout from /misc
<details open>
  <summary><strong>Extract Icons</strong></summary>
  
   - ```bash
     cd ~/.local/share/icons/
     ```
   - ```bash
     tar -Jxvf Foggy-Mountain.tar.xz 
     ```
   - ```bash
   	 # Delete leftover archives
     rm -r ~/.local/share/icons/{Foggy-Mountain.tar.xz}
     ```
     
</details>

<details open>
  <summary><strong>wpgtk</strong></summary>

1. Add wallpapers and import color schemes:

- ```bash
  # Assuming you're in KDE-Dotfiles directory
  # Add wallpapers
  wpg -a walls/ngf28mu50oy51.png
  ```
- ```bash
  # Assuming you're in KDE-Dotfiles directory
  # Import color schemes
  wpg -i foggy-mountain_01.jpg colorschemes/foggy-mountain.json

2. Add templates:

- ```bash
  # Backups are automatically made just in case something goes wrong.
  wpg -ta ~/.config/kdeglobals
  wpg -ta ~/.local/share/konsole/wpgtk.colorscheme
  wpg -ta ~/.local/share/plasma/desktoptheme/CullaX/colors
  ```

3. Add variables/keywords to the templates:

- ```bash
  # Identify the templates` filenames first on ~/.config/wpg/templates
  # Replace <filename>.base with yours
  # Assuming you're in KDE-dotfiles directory
  cd wpgtktemplates

  # For dark color schemes:
  cat kdeglobals-dark.base > ~/.config/wpg/templates/<your_kdeglobals>.base

  cat colors.base > ~/.config/wpg/templates/<your_cullax_colors>.base
  cat konsole.base > ~/.config/wpg/templates/<your_konsole>.base
  ```

4. Set the color scheme:

- ```bash
  wpg -s <scheme>.jpg
  # Replace <scheme> with your color scheme of choice.
  # For example
  wpg -s ngf28mu50oy51.png
  ```

</details>

If you're using `Spicetify` with `Dribbblish`, run the following:

```bash
xrdb -merge ~/.cache/wal/colors.Xresources
spicetify config color_scheme pywal
spicetify apply
```

<details open>
<summary><strong>Set Plasma theme</strong></summary>
  
 - System Settings > Plasma Style, set it to CullaX.
 - System Settings > Application Style, set it to gtk2. Click `Configure GNOME/GTK Application Style...`, set the GTK2 and GTK3 theme your theme of choice.
- System Settings > Icons, set the icon theme to your theme of choice.

To remove the titlebar buttons:
- System Settings > Application Style > Window Decorations > Titlebar Buttons, drag the buttons and drop them down to the list.

To change the titlebar size:
- System Settings > Application Style > Window Decorations, click the edit icon on `Breeze`. Change button size to whatever you want.

</details>

## :pushpin: Apps to install

**Dev**
-  [VS Code](https://aur.archlinux.org/packages/visual-studio-code-bin/)
-  Vim
-  IntelliJ
-  PyCharm
-  [Eclipse C++](https://www.eclipse.org/downloads/packages/release/kepler/sr2/eclipse-ide-cc-developers) 09.2019 (version with arduino plugin)
-  [Figma](https://aur.archlinux.org/packages/figma-linux/)
-  Filezilla

**Internet**
-  Firefox
-  Firefox Developer Edition
-  Chromium
-  Microsoft Teams
-  Zoom 

**Misc**
-  Discord
-  Slack
-  [Spotify](https://aur.archlinux.org/packages/spotify/)
-  gnome-keyring
-  qBitTorrent
-  VLC
-  Nautilus
-  Kate




## :sparkling_heart: Credits

- [owl4ce](https://github.com/owl4ce/)
- [elenapan](https://github.com/elenapan/)
- [addy-dclxvi](https://github.com/addy-dclxvi/)

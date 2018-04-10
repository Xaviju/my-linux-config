# Linux: from zero to front-end ready

## Introduction
The purpose of this repository is to keep detailed and updated instructions on what and how to install **my optimal minimum required linux system for front-end development**. It is also aimed to all the users which are interested in using linux, but feel insecure because all the myths about the Linux complexity

## Operating system

### Antergos
Antergos is a Linux distro based on [Arch Linux](https://www.archlinux.org/). The reason why is my chosen distro are:
- **Rolling release**: It comes with the latests packages. [More about rolling relase](https://en.wikipedia.org/wiki/Rolling_release)
- **Stability**: Do not crashes unexpectedly, is a very stable system.
- **Packages repo**: Is the same as Arch and basically has everything I look for.
- **Ease of installation**: The installer, [Cnchi](https://antergos.com/blog/say-hello-to-cnchi-v0-10-the-latest-and-greatest-version-of-our-installer/) is really easy.
- **preinstalled desktops**: Comes with many options for desktops ([mate](https://mate-desktop.org/es/), [KDE](https://www.kde.org/), [Cinnamon](https://blog.linuxmint.com/?p=3457), including no desktop at all.

#### How to install
1. Download the latest [Antergos ISO](https://antergos.com/try-it/) file to your computer.
1. If you are already using Linux, I would recommend [Etcher ](https://etcher.io/) to burn the ISO into a USB.
1. Reboot your system and [select the USB as booting system](https://lifehacker.com/5991848/how-to-boot-from-a-cd-or-usb-drive-on-any-pc)
1. Antergos will boot from your USB, ensure that you are connected to internet to update Antergos installer. If you are using WiFi, look for it it in the top left menu.
1. Before installing it, you can test Antergos directly for the USB.
1. Once you are ready, launch Cnchi installer.
1. Choose your language and location
1. Choose what desktop you want to install. My recommendation is to use Gnome (more about this later).
1. Choose what software your want to install by default. I tend to install:
    1. AUR: The Arch User Repository (More on this later)
    1. Bluetooth
    1. Chromium + Firefox
    1. Print support
    1. [Libreoffice](https://www.libreoffice.org/)
1. Mirrors [More about mirrors](https://unix.stackexchange.com/a/175954)
1. Erase disk and install Antergos.
1. Wait for install and reload.

### Package managers

**PACMAN** Pacman is the built-in software manager for antergos. Is the tool you'll use to download and update your system software.

[About pacman :point-right:](https://wiki.archlinux.org/index.php/Pacman)
    1. Search a package: `sudo pacman -Ss <name>`
    1. Install a package `sudo pacman -S <name>`
    1. Remove `sudo pacman -Rs <name>`
    1. Upgrade `sudo pacman -Syu`

**AUR** The Arch User Repository (AUR) is a community-driven repository for Arch users. Its a sort of pacman, but community-driven.

[About AUR (Arch User Repository) :point-right:](https://wiki.archlinux.org/index.php/Arch_User_Repository_(Espa%C3%B1ol)) `https://wiki.archlinux.org/index.php/Pacman_(Espa%C3%B1ol)`
    1. Search a package: `yaourt -Ss <name>`
    1. Install a package: `yaourt -S <name> --noconfirm`
    1. Remove a package: `yaourt -Rs <name> --noconfirm`
    1. Upgrade a package: `yaourt -Syua --noconfirm`
    1. Install through yaourt without `--noconfirm`
        1. Edit PKGBUILD? -> N
        1. Edit **{name}**.install? -> N
        1. Continue building **{name}**? -> Y
        1. Continue installing **{name}**? -> Y

### Desktop Manager: [Gnome](https://www.gnome.org/gnome-3/)
Gnome is my favourite desktop. It has the better user experience, stability and user interface. Is not as fast as other desktops, specially tiling window managers. its easy to use and has a huge community and amazing software. If you prioritize performance in your desktop over UX or UI, you should probably check [i3](https://i3wm.org/)

1. [Gnome cheat sheet](https://wiki.gnome.org/Projects/GnomeShell/CheatSheet)
1. GNOME Tweak Tool. Installed by default, allows you to edit advanced assets from your desktop, as the icons or the shell theme.
    1. Gnome Shell. The look and feel of your dektops. There are thousands out there. I use `Numix Frost`
    1. Icons. I use `Numix Squeare`. There are many icon sets (install on `~/.icons` and choose theme in the selector)
1. [GNOME extensions](https://extensions.gnome.org/) are plugins for your desktop.
    1. Extensions can be installed, activated and removed from your browser `https://wiki.gnome.org/Projects/GnomeShellIntegrationForChrome/Installation#Arch_Linux`
        1. AlternateTab `https://extensions.gnome.org/extension/15/alternatetab/`
        1. Applications menu `https://extensions.gnome.org/extension/6/applications-menu/`
        1. Dash to Dock `https://extensions.gnome.org/extension/307/dash-to-dock/`
        1. Native Window placement `https://extensions.gnome.org/extension/18/native-window-placement/`
        1. Removable Drive Menu `https://extensions.gnome.org/extension/7/removable-drive-menu/`
        1. User Themes `https://extensions.gnome.org/extension/19/user-themes/`
1. [Advanced Gnome](https://wiki.archlinux.org/index.php/GNOME)

### Terminal
1. Install [VIM editor](https://www.vim.org/)
1. [ZSH](https://wiki.archlinux.org/index.php/zsh) 
    1. Select default options when installing
    1. [Changing_your_default_shell](https://wiki.archlinux.org/index.php/Command-line_shell#Changing_your_default_shell): Set as your default shell on reload 

        ```
        chsh -s /usr/bin/zsh
        ```

1. [Antigen](https://github.com/zsh-users/antigen) . The plugin manager for ZSH 
    1. Install through `yaourt -S antigen-git`
        ```
        source /usr/share/zsh/share/antigen.zsh
        ```
    1. [Extensions](https://github.com/robbyrussell/oh-my-zsh/wiki/Plugins) `antigen bundle {pluginName}`
        1. [Oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
        1. [Themes](https://github.com/robbyrussell/oh-my-zsh/wiki/themes)
        1. [NVM](https://github.com/creationix/nvm)
        1. [Z](https://github.com/rupa/z)
    1. Log out and log in again to reload your terminal.


### GIT
1. Install Git as [Antigen](https://github.com/zsh-users/antigen) extension
1. [Configure GIT](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
1. [Generate an SSH key](https://help.github.com/articles/connecting-to-github-with-ssh/)
1. Add the SSH key to [github](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)
1. Add the SSH key to [gitlab](https://docs.gitlab.com/ee/ssh/)

### Fonts
1. How to [install fonts](https://wiki.archlinux.org/index.php/Fonts)
1. Also the Gnome fonts viewer (open the font and click on `install`)

### Browsers `sudo pacman -Ss {browser-name}`
1. Firefox Developer Edition `sudo pacman -S firefox-developer-edition`
1. Chromium `sudo pacman -S chromium`

### Code editor
1. VSCode `yaourt -S code --noconfirm`

### UI editors
1. Vectorial: [Inkscape](https://inkscape.org/es/) `pacman -S inkcape`
    1. [Inkscape Open Symbols](https://github.com/Xaviju/inkscape-open-symbols)
    1. [Inkscape SVGO](https://github.com/juanfran/svgo-inkscape)
    1. [Inkscape export layers](https://github.com/jespino/inkscape-export-layers)
    1. [Inkscape placeholders](https://github.com/Xaviju/inkscape-placeholder)
2. Bitmap: [Gimp](https://www.gimp.org/) `pacman -S gimp`

### Troubleshooting
1. [NodeJS ENOSPC](https://stackoverflow.com/questions/22475849/node-js-error-enospc)


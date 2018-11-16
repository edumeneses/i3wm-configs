# i3wm-configs
My personal config files and gude for personalize i3wm

### apps to install (over Manjaro xfce):

```
sudo pacman -Sy i3 i3status i3blocks i3lock rofi ibus xautolock glances compton lxappearance vim arandr xorg-xbacklight yaourt lshw xorg-xev gtk-chtheme qt4 arc-gtk-theme dmenu polkit-gnome gnome-keyring sysstat volumeicon parcellite gvim
```

### Install Fonts

- font Awesome (https://fontawesome.com/how-to-use/on-the-web/setup/getting-started?using=web-fonts-with-css)
- font YosemiteSanFranciscoFont (https://github.com/supermarin/YosemiteSanFranciscoFont)

### theme

Start with lxappearance and choose Dark Ark theme; then choose it in gtk-chtheme. In qt4-config, there is a dropdown menu setting to make qt take the GTK+ settings.

### Set pamac-manager to work

Under i3-wm none of the polkit and keyring are installed/loaded unless you configure it.
First install them:

```
sudo pacman -S polkit-gnome gnome-keyring
```

Then set them to start in your i3-wm config file ```~/.config/i3``` adding the line below:

```
exec --no-startup-id /usr/lib/polkit-gnome/polkit-gnome-authentication-agent-1 & eval $(gnome-keyring-daemon -s --components=pkcs11,secrets,ssh,gpg) &
```

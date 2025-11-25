# Toggle Screens

Allows you to switch all windows from screen 0 to screen 1 and vice versa.
By default, if there is one or more windows on screen 0, it moves them from 0 to 1.
If there are no windows on 0, it moves all windows from 1 to 0.

The program runs under the X11 (Xorg) environment.
It has not been fully tested under Wayland.

```bash
cp toggle-screens /usr/bin/toggle-screens
chmod 0755 /usr/local/bin/toggle-screens.sh


cp 90-toggle-screens.ini /etc/dconf/db/local.d/90-toggle-screens.ini
chmod 0644 /etc/dconf/db/local.d/00-toggle-screens

dconf update
```

Force by hand and verify
```bash
gsettings set org.gnome.settings-daemon.plugins.media-keys custom-keybindings "['/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/toggle-screens/']"
gsettings set org.gnome.settings-daemon.plugins.media-keys.custom-keybinding:/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/toggle-screens/ command '/usr/bin/toggle-screens'
gsettings set org.gnome.settings-daemon.plugins.media-keys.custom-keybinding:/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/toggle-screens/ binding '<Super>T'

gsettings get org.gnome.settings-daemon.plugins.media-keys custom-keybindings
gsettings get org.gnome.settings-daemon.plugins.media-keys.custom-keybinding:/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/toggle-screens/ command
gsettings get org.gnome.settings-daemon.plugins.media-keys.custom-keybinding:/org/gnome/settings-daemon/plugins/media-keys/custom-keybindings/toggle-screens/ binding
```

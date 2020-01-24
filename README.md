# antsy-xdm-theme

XDM theme using polybar, picom, and feh

![screenshot1](https://github.com/jeffmhubbard/antsy-xdm-theme/raw/assets/xdm-menu-1-main.png 'Login Screen')
Login Screen

![screenshot2](https://github.com/jeffmhubbard/antsy-xdm-theme/raw/assets/xdm-menu-2-choices.png 'System Menu')
System Menu

![screenshot3](https://github.com/jeffmhubbard/antsy-xdm-theme/raw/assets/xdm-menu-3-confirm.png 'Menu Confirmation')
Menu Confirmation

### About
I wanted to add restart and shutdown options to XDM screen, but wasn't happy with the solutions I found. So I came up with this...

Polybar for the menus and time. Picom (compton) for shadows and transparency on xlogin window and polybar. And feh provides random backgrounds each time XDM starts.

NOTE: Does not include backgrounds (see [here](https://github.com/jeffmhubbard/antsy-wallpaper/)).

### Requirements
- [XDM](https://www.x.org) - X Display Manger
- [polybar](https://github.com/polybar/polybar) - menu and clock
- [picom](https://github.com/yshui/picom) - transparency and shadows
- [feh](https://feh.finalrewind.org) - set background
- [Nerd Fonts](https://www.nerdfonts.com/) - fonts with glyphs

### Installation
##### Source
```sh
cp antsy/* /etc/X11/xdm
chmod 0755 /etc/X11/xdm/antsy/{Xsetup,GiveConsole}
chmod 0600 /etc/X11/xdm/antsy/polybar.ini
(restart XDM)
```

##### Source (systemd)
```sh
cp -r antsy /etc/X11/xdm/antsy
chmod 0755 /etc/X11/xdm/antsy/{Xsetup,GiveConsole}
chmod 0600 /etc/X11/xdm/antsy/polybar.ini
install -Dm0644 xdm-antsy.service /usr/lib/systemd/system/xdm-antsy.service
sudo systemctl daemon-reload
sudo systemctl disable xdm
sudo systemctl enable xdm-antsy
sudo systemctl stop xdm
(login to console)
sudo systemctl start xdm-antsy
```

##### Arch
There is a PKGBUILD in my [pkgbuilds](https://github.com/jeffmhubbard/pkgbuilds) repo for now

### License
MIT

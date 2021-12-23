# personal-xrandr
My personal settings for xrandr


```bash
xrandr --listmonitors
Monitors: 2
 0: +*HDMI3 3840/610x2160/350+0+0  HDMI3
 1: +HDMI2 1200/520x1920/320+3840+0  HDMI2
```

```bash
cat /etc/X11/xorg.conf.d/20-intel.conf
Section "Device"
        Identifier  "Intel Graphics"
        Driver      "intel"
        Option      "TearFree"    "true"
EndSection
```

```bash
cat .config/autostart/hidpi.desktop
[Desktop Entry]
Name=HiDPi
Exec=/usr/bin/xrandr --output HDMI3 --scale 1x1
Terminal=false
Type=Application
Icon=Monitor
Categories=Office;

[Desktop Entry 2]
Name=HiDPi
Exec=/usr/bin/xrandr --output HDMI2 --scale 1.25x1.25
Terminal=false
Type=Application
Icon=Monitor
Categories=Office;

```

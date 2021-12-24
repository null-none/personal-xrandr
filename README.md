# personal-xrandr.sh

xrandr is an official configuration utility to the RandR (Resize and Rotate) X Window System extension. It can be used to set the size, orientation or reflection of the outputs for a screen. For configuring multiple monitors see the Multihead page.

### Install

```bash
#!/bin/sh
sudo apt update
sudo apt install lxrandr
```

### Setup

```bash
#!/bin/sh
xrandr --listmonitors
```
```
Monitors: 2
 0: +*HDMI3 3840/610x2160/350+0+0  HDMI3
 1: +HDMI2 1200/520x1920/320+3840+0  HDMI2
```

```bash
#!/bin/sh
cat /etc/X11/xorg.conf.d/20-intel.conf
Section "Device"
        Identifier  "Intel Graphics"
        Driver      "intel"
        Option      "TearFree"    "true"
EndSection
```

```bash
#!/bin/sh
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


### Script

```bash
#!/bin/sh
xrandr --output DP1 --off --output DP2 --off --output HDMI1 --off --output HDMI2 --mode 1920x1200 --pos 3840x0 --rotate left --output HDMI3 --primary --mode 3840x2160 --pos 0x0 --rotate normal --output VIRTUAL1 --off
```

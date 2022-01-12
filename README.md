# GPD Pocket 3 Linux
Useful commads for Linux at GPD Pocket 3

![image](https://nwzimg.wezhan.net/contents/sitefiles3601/18006016/images/5214381.png)

### Screen Orientation
#### X11
```
# xrandr -o right
```
#### FB
```
# nano /etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT="quiet fbcon=rotate:1"
GRUB_CMDLINE_LINUX="fbcon=rotate:1"
GRUB_GFXMODE=1200x1920x32
# update-grub
```
#### lightdm
```
# nano /etc/lightdm/lightdm.conf
[SeatDefaults]
display-setup-script=xrandr -o right
```
#### TouchScreen & Stylus
```
# nano /etc/xorg.conf.d/99-touchsreen.conf
Section "InputClass"
  Identifier    "calibration"
  MatchProduct  "GXTP7380"
  Option        "TransformationMatrix" "0 1 0 -1 0 1 0 0 1"
EndSection
```

### Capture HDMI input
```
ffplay /dev/video3
```

### Sound 

Open a terminal and type 
```
sudo nano /etc/modprobe.d/alsa.conf
```
to create a new audio configuration file.
Type 
```
options snd-intel-dspcfg dsp_driver=1
```
into that file and hit save.

## ToDo
* GRUB Menu Orientation
* Stylus Buttons Remap

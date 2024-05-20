# iio-hyprland
A fork of okeri/iio-sway for Hyprland

Listens to iio-sensor-proxy and automatically changes Hyprland output orientation

## Installing 

:warning: Make sure [iio-sensor-proxy](https://gitlab.freedesktop.org/hadess/iio-sensor-proxy/) running :warning:

### Arch linux

`yay iio-hyprland-git`

`paru iio-hyprland-git`


### Build from scratch

```
nix-shell -p ninja meson dbus pkg-config cmake
mkdir build
meson build
cd build
ninja install

```

#### Uninstalling 
```
cd iio-hyprland

sudo make uninstall
```

## Running
`iio-hyprland [monitor to rotate, default=eDP-1]`, run `hyprctl monitors` to list available outputs.

Add `exec-once = iio-hyprland` to `~/.config/hypr/hyprland.conf`

Some users reported that specifying the monitor in hyprland.conf could be necessary. For example, on Surface Pro:

`monitor=eDP-1,preferred,auto,2,transform,0`

## Touch rotation support

Should automatically rotate all Tablets and Touch Devices from `hyprctl devices`.
Thank you to Desktop31 for fetching the `hyprctl devices` output.


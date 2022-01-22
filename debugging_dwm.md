# Debugging DWM using a virtual display

## Launch Xephyr (nested X server) in a new display (:1)

```bash
Xephyr -ac -screen 1024x2048 -br -reset -terminate 2> /dev/null :1 &
```

## Launch a terminal using same display:

Use a higher number than `1` if using multiple displays!

```bash
DISPLAY=:1 alacritty &
```

## In that terminal launch dwm

```bash
make && ./dwm
```
## Crashed? Debug the crash with gdb

```bash
gdb ./dwm
r
# crash!
bt
...
```


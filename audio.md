Getting audio to work
---------------------
Needed these steps to get a Creative X-Fi Sound Blaster to run:


Fix /etc/asound.conf adding the following lines. This enables two devices, add more if necessary (0 - builtin audio jack, 1 - the next connected USB device, ...)
*Built-in sound uses PWM, no way this will ever produce clear sound below 100KHz*

```
pcm.!default {
        type hw
        card 0
}

ctl.!default {
        type hw
        card 0
}

pcm.!default {
        type hw
        card 1
}

ctl.!default {
        type hw
        card 1
}
```

Apply the *USB Fix* inserting the following into the command line in /boot/cmdline.txt:
```
dwc_otg.speed=1
```


Install mplayer
```
sudo apt-get install mplayer
```

Play sound (Use hw=0.0 for built-in audio, hw=1.0 for USB-audio, ...)
```
mplayer -framedrop -ao alsa:device=hw=1.0 *.mp3
```

If the Raspberry runs low on power add an active USB hub with external >= 1A supply.

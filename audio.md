Getting audio to work
---------------------

Fix /etc/asound.conf adding the following lines. This enables two devices, add more if necessary (0 - builtin audio jack, 1 - the next connected USB device, ...)

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

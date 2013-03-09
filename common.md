Common tasks I don't want to g00gle each time
---------------------------------------------

Mounting Windows shares
```
mkdir /mnt/myshare
sudo mount -t cifs "//192.168.1.2/share" -o username=name,password=pass /mnt/myshare
```

Play sound to USB device
```
mplayer -framedrop -ao alsa:device=hw=1.0 -af resample=44100 *.mp3
```

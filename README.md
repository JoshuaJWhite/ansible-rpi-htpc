# ansible-rpi-htpc
configuration for raspberry pi htpc streaming client

# SD Card Imaging
Image the SD card using the installer from: https://www.raspberrypi.com/software/ using the following settings:<br>
Raspberry Pi Device="RASPBERRY PI 4"<br>
Operating System="RASPBERRY PI OS (64-BIT)"<br>
Storage=

# On Device Setup
Once the SD card is imaged boot the Raspberry Pi for the first time.

Run the default setup setting an appropriate local and
     user="htpc"

Enable ssh for config management by running,
```
sudo systemctl enable ssh
sudo systemctl start ssh
```
then remotely log in via ssh.

# Remote Device Setup
Update the system with,
```
sudo apt update
sudo apt dist-upgrade
```
and install the following to facilitate auto-config:
```
sudo apt install ansible git
```

Lastly, run ansible pull:
```
sudo ansible-pull -U https://github.com/JoshuaJWhite/ansible-rpi-htpc.git
```

# XBoxOne Controller
The XBoxOne controller in a USB wired configuration requires the following settings in steam to function:<br>
Steam Settings > Controller > External Gamepad Settings > Enable Steam Input for XBox Controllers = YES

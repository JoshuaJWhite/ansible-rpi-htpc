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

The XBoxOne controller with wireless dongle for pc requires xone be installed.
Ref: https://github.com/medusalix/xone. Follow the prompts the dependencies are already included with the ansible playbook:
```
git clone https://github.com/medusalix/xone
```

```
cd xone
sudo ./install.sh --release
```

```
sudo xone-get-firmware.sh
```

You will need to pair the xbox controller with the dongle.

# Chromium Hardware Video Decode
The following settings will need to be changed in Chromium:

In the Chromium browser url bar type:
```
chrome://flags
```

Set the following:<br>
Override software rendering list = "Enabled"<br>
GPU rasterization = "Enabled"<br>
Hardware-accelerated video decode = "Enabled"<br>
Out-of-process 2D canvas rasterization = "Enabled"

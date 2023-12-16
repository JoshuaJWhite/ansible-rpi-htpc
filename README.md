# ansible-rpi-htpc
configuration for raspberry pi htpc streaming client

Run the default setup with 
user=htpc

Enable ssh for config managment,
'''
sudo systemctl enable ssh
sudo systemctl start ssh
'''
then remotely log in.

Update the system with:
'''
sudo apt update
sudo apt dist-upgrade
'''

Install the following to facilitate auto-config:
```
sudo apt install ansible git
```

Run ansible pull:
```
sudo ansible-pull -U https://github.com/JoshuaJWhite/ansible-rpi-htpc.git
```

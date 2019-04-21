# Creating root User
```sh
adduser username
usermod -aG sudo username
su - username
```
# Ubuntu Desktop Installation
- First Update the apt packages
With Packages:
```sh
sudo apt-get install ubuntu-desktop gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal
```
Without Packages:
```sh
sudo apt-get install --no-install-recommends ubuntu-desktop gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal
```
### Lite version Desktop
[Digital Ocean Lite Desktop Guide](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-18-04)
- 
# VNC Server Installation - Ubuntu Desktop
```sh
sudo apt-get install vnc4server
```
- Add this content to ~/.vnc/xstartup
```sh 
vim ~/.vnc/xstartup
```
```sh
#!/bin/sh

# Uncomment the following two lines for normal desktop:
# unset SESSION_MANAGER
# exec /etc/X11/xinit/xinitrc

[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
xsetroot -solid grey
vncconfig -iconic &
x-terminal-emulator -geometry 80x24+10+10 -ls -title "$VNCDESKTOP Desktop" &
x-window-manager &

gnome-panel &
gnome-settings-daemon &
metacity &
nautilus &
```
# CRON TAB for vncstartup
```sh
crontab -e
```
Add this line at the bottom of the file
```sh
@reboot /usr/bin/vncserver :1
```
# adding Google Repo
```sh
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
sudo sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
sudo apt-get update
sudo apt-get install google-chrome-stable
```


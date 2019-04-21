# Crreating root User
-adduser username
-usermod -aG sudo username
-su - username
# Ubuntu Desktop Installation
- First Update the apt packages
With Packages:
sudo apt-get install ubuntu-desktop gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal
Without Packages:
sudo apt-get install --no-install-recommends ubuntu-desktop gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal
# VNC Server Installation - Ubuntu Desktop
sudo apt-get install vnc4server

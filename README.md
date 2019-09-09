# i3-EndeavourOS
## joekamprad: setup for i3 under [EndeavourOS](https://endeavouros.com)
## setup for i3-Wm on EndeavourOS running on a thinkpad with fingerprint reader:

Main shortcuts:

* [mod]+**enter** = open terminal (xfce4-terminal)
* [mod]+**w** =  open Browser (firefox)
* **F9** =  app menu (rofi)
* **F4** =  close focused app

# Tiling mode is tabbed: 
so each new window will open fullscreen as a tab, you can change between window-tabs with mouse or shortcut:
* [mod]+**Left** focus left (left arrow key)
* [mod]+**Right** focus right (right arrow key)

# i3blocks:
* pulseaudio (mousewheel volume level, rightclick open pulseaudio control)
* weather (openweather)
* tray-icons (showing kalu and network-manager)
* logout button (poweroff, logout, suspending, hibernate e.t.c.)
#
![alt text](https://raw.githubusercontent.com/killajoe/i3-EndeavourOS/master/panel.png "i3blocks")
#
![alt text](https://raw.githubusercontent.com/killajoe/i3-EndeavourOS/master/logoutmenu.png "logout-menu")

# application menu:
![alt text](https://raw.githubusercontent.com/killajoe/i3-EndeavourOS/master/appmenu.png "application-menu")





`git clone https://github.com/killajoe/i3-EndeavourOS.git`

* copy files to the right directories (.config of your user and pam files under /etc/pam.d {needed for fingerprint-gui to work})
* scripts inside ~/.config/i3/scripts must be executable ! [chmod +x] them please ;)

ad user to this groups **scanner plugdev**:

`sudo gpasswd -a username scanner plugdev`

install needed apps and programms:

`sudo pacman -S --needed - < packages-repository.txt`

`yay -S --needed - < packages-AUR.txt`

# Thermald/TLP POWERSAVING:

install needed: `yay -S --needed tlp thermald`

`sudo nano /usr/lib/systemd/system/thermald.service`

change the line:

`ExecStart=/usr/bin/thermald --no-daemon --dbus-enable`

like so:

`ExecStart=/usr/bin/thermald --no-daemon --dbus-enable --ignore-cpuid-check`

services e.t.c.:

`sudo systemctl enable thermald tlp.service tlp-sleep.service`

`sudo systemctl mask systemd-rfkill.service systemd-rfkill.socket`

reboot... 
#
![alt text](https://raw.githubusercontent.com/killajoe/i3-EndeavourOS/master/greeter.png "slick-greeter")
#
![alt text](https://raw.githubusercontent.com/killajoe/i3-EndeavourOS/master/2019-09-08-223630_1024x768_scrot.png "i3-running")

login to i3... with a fingertip

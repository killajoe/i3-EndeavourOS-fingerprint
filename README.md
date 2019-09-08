# i3-EndeavourOS
## joekamprad: setup for i3 under [EndeavourOS](https://endeavouros.com)
## setup for i3-Wm on EndeavourOS running on a thinkpad with finferprint reader:

`git clone https://github.com/killajoe/i3-EndeavourOS.git`

* copy files to the right directories (.config of your user and pam files under /etc/pam.d {needed for fingerprint-gui to work})
* scripts inside ~/.config/i3/scripts must be executable ! [chmod +x] them please ;)

ad user to this groups **scanner plugdev**:

`sudo gpasswd -a username scanner plugdev`

install needed apps and programms:

`sudo pacman -S --needed - < packages-repository.txt`

`yay -S --needed - < packages-AUR.txt`

# Thermald TLP POWERSAVING

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

login to i3... with a fingertip

# PiHole Switch Plus (Linux only)
## On-off switch for PiHole using the pihole-switch by Cosimo Matteini.


#### The first thing to do is to install the pihole-switch, it can be found underhttps://github.com/devmatteini/pihole-switch

#### If you already have pihole-switch installed and running, you can use pihole-switch-plus as follows.
#### To make the script directly executable:

    chmod +x PSP

#### To use the script to turn off a PiHole that is turned on, and turn on a PiHole that is turned off.

    PSP [PiHole-IP]

#### That's all, you can now e.g. make a menu entry and drag an icon to the taskbar. So you have a direct PiHole switch which gives you a short message about the notify-send of the system whether the PiHole was switched on or off.

### PS: Of course you have to install "notify-send" or the required package for your desktop environment!
---
# Additional installation as well as integration instructions for pihole-switch.
#### If you do not know your PiHole API yet, you can do this with the following command when you are logged in on your Pihole.

    cat /etc/pihole/setupVars.conf | grep "WEBPASSWORD=" | awk -F'=' '{for (i=2; i<=NF; i++) printf("%s\n", $i)}'
    
#### You now call your .bashrc file e.g. with nano (on your work PC).

    nano ~/.bashrc
    
#### Now you can add the following to the beginning of your .bashrc file (on your work PC):

    #PiHole API-Key
    export PIHOLE_TOKEN="[API-CODE]"

#### So that the .bashrc is read in again, a logout as well as a renewed logging in is necessary, a restart is not necessary!


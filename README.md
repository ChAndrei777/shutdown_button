# shutdown_button
For lattepanda-3-delta the SW button default action in Ubuntu 20.04.6 LTS  is to launch gnome shutdown dialog - that means you have to wait 1 minute.

the following settings allow immediate shutdown:

1. gsettings set org.gnome.settings-daemon.plugins.power power-button-action nothing

2. gsettings set org.gnome.settings-daemon.plugins.power button-power nothing

3. In folder /etc/acpi/events create a file with a name that is not already taken (sudo nano power-button-fast-shutdown) with the following Content:

event=button/power
action=/sbin/shutdown --poweroff now
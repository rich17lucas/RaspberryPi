# RaspberryPi
Stuff and nonsonse for my Raspberry Pi Projects
-----------------------------------------------
### Setup Notes - what to do after installing Raspbian
To be able to connect to Wifi, enable the the WLAN0 interface if not enabled by default.
(https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md)

Open the wpa-supplicant configuration file in a text editor (vi or Nano):

`vi /etc/wpa_supplicant/wpa_supplicant.conf`

Go to the bottom of the file and add the following:

```
network={`
    ssid="The_ESSID_from_earlier"
    psk="Your_wifi_password"
}
```

To be able to ping Windows PCs by Name:
---------------------------------------
```
sudo apt-get update
sudo apt-get install winbind
sudo apt-get install libnss-winbind
sudo vi /etc/nsswitch and append 'wins' after 'files''
```

To be able to run 'ping' without sudo
-------------------------------------
For some reason Ping would only with the latest Raspbian 
`chmod 4755 /bin/ping`

Install xrdp for remote desktop
-------------------------------
`sudo apt-get install xrdp`

Alias vi to vim 
---------------
Habit - use 'vim' all the time so save my sanity I alias vim to vi
`vi ~.bashrc`
Add `alias vim="vi"`

Change Hostname from default `raspberrypi`
----------------------------------
Launch the raspi-config utility
`sudo raspi-config`
Select *Advanced Options*, then *Hostname*
_Note any characters after period '.' are ignored - so 'rpi2.02' was treated as 'rpi2' whereas 'rpi2-01' was fine_

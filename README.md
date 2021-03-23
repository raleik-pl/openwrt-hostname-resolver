# openwrt-hostname-resolver
hostapd script for dumb ap to resolve hostname from router (dhcp server) on AP-STA-CONNECTED  
No more question marks or MACs in "Associated Stations" list!

## usage
- alter the `hostname-resolver.hostapd` file to replace "root@router" with your user/hostname if needed 
- put the `hostname-resolver.hostapd` file somewhere on your dumb ap (like in `/bin`)
- make it executable with `chmod a+x hostname-resolver.hostapd`
- put the following lines in `/etc/rc.local`, updating paths and wlan interfaces if needed:  
  `hostapd_cli -a /bin/hostname-resolver.hostapd -i wlan0 -B`  
  `hostapd_cli -a /bin/hostname-resolver.hostapd -i wlan1 -B`

the script assumes that your ap can connect to your router passwordlessly (va ssh key)

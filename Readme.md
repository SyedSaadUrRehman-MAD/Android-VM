# Setting up an Android Virtual Machine with VirtualBox
Watch this video tutorial for a visual guide: https://www.youtube.com/watch?v=MN4Kl3i699M

## Completing Android Setup:
Access Android developer options by tapping the build number in "About phone" multiple times.

## Network Setup:
Close the Android Virtual Machine.
Open VirtualBox, and go to File > Preferences > Network.
In the "Host-only Networks" tab, add a new network:

Name: vboxnet0
IP Address: 192.168.56.1
Subnet Mask: 255.255.255.0
DHCP Server: Enabled
Now, open the Android Virtual Machine settings:

Go to Settings > Network.
For "Adapter 1," select "Host-only Adapter" and choose "vboxnet0" for the "Name."
For "Adapter 2," enable the adapter, select "NAT" for "Attached to," and expand the "Advanced" settings.
Click on "Port Forwarding" and add a new entry:

Name: ADP
Protocol: TCP
Host IP: 127.0.0.1
Host Port: 5555
Guest IP: (Leave empty)
Guest Port: 5555

Save the changes in the Virtual Machine settings.

## ADB Setup:
On a Linux host, you can install ADB (Android Debug Bridge) using the following command:
sudo apt install adb
adb connect 127.0.0.1:5555


That's it! You're done with the setup. 

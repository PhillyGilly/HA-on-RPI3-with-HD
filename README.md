# HA-on-RPI3-with-HD

HA to external HD migration
1.	Make sure you have a lot of time to spare and a good supply of tea and Christmas cake!
2.	Refer to https://github.com/home-assistant/operating-system/blob/dev/Documentation/partition.md 
3.	These notes also provide a simple, non-expert guide to be followed at your own risk.
4.	Get your hands on an external USB3 drive and use tools to clear it to unformatted, unpartitioned. 
5.	Take a snapshot of your existing HA setup and download it to your PC. Make a note of your Samba-share app config and save on your PC. Have you HA login details to hand.
6.	Create a new HA installation on an SD card (I got away with 8GB)
7.	Set up the RPi3 with mouse, keyboard, HDMI monitor, and external HDD.
8.	Fire it all up and wait. Keep waiting and eventually the installation will show the HA logo on the monitor. Login using the default ID of “root”.
9.	Wait and when it looks like it has settled down. Use command “login” to exit to Linux shell. Run “fdisk -l” to find your hard-disk which will probably be /dev/sda. If it isn’t sda  it will be sdb or sdc etc. Note what it is. Now run command “datactl move /dev/sda” or whatever you noted.
10.	Wait again and eventually your RPi will reboot with HA running on the HD. Now you can login from your PC. More waiting.
11.	Eventually Switch to PC and log in to HA. Create a new user account using your old account details. Do not bother with any further set up.
12.	From the Supervisor Add-on store install Samba Share. Create a network drive map to the RPi and copy the downloaded snapshot back into the back-up sub-directory.
13.	From the Supervisor Snapshot menu restore the snapshot. Wait. Wait a bit more.
14.	Eventually HA will reappear running off the HD. And you’re finished. 

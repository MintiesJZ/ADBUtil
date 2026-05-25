# ADBUtil
### A small utility for enabling ADB over USB on the MG4 SE/Excite (2022-2025 models tested).

This utility solves the problem of not being able to enable ADB.  
Engineering mode has a HOST/OTG toggle but that doesn't enable adbd.


__I've been finding ADB is far more likely to conenct if the computer is connected to the USB-C port when the car starts__

If the car is already running, connect the computer to the USB-C port, then hold the home button on the car till the headunit reboots (approx 10 seconds, you'll see a harmless autohold fault on the dash) and it should work once the restart is complete.

The USB-C port to the right side of the 12v power socket is the OTG port. 
The USB A port will be switch to OTG mode as well, but this hasn't been tested. 

### Restarting ADB
I've included a button to restart adbd. 
That allows you to enable Wireless ADB bypassing the firewall.  

Once ADB is connected via USB run:
> adb shell setprop service.adb.tcp.port 5556

from your computer and then press the "Restart ADB" button for the change to take effect. 

On your computer you can then run:
> adb connect MG4_IP_Address:5556


### Installing APKs on the MG4
If you haven't sideloaded apps before:
1.  Open the Bluetooth Settings and select the car name
2. Hold down on the comma until the settings appear.
3. Select Android Keyboard Settings.
4. Select Languages
5. Use the search box at the top to search for "file"
6. That should give you access to the files app.

From there you can select a connected USB device with APKs on it and install as usual.

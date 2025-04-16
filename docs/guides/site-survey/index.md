# Site survey

!!! info "How can this documentation be improved?" 

    - Check that menu labels are correct. 
    - Explain how to read the signal strength in the Omni instructions.

## Line-of-sight to supernode install

### Prep

1. Make sure you have the passwords for accessing the router administration interfaces as well as the WPA password.
  - The default LiteBeam administration credentials are stored in the password manager as `Ubiquiti LiteAP/LBE admin`.

### Arrival & Site Selection

1. Arrive at Installee’s home. 
2. Introduce yourself.
3. Find a safe place to position the ladder.
4. Climb up on the roof carefully using the [ladder safety protocol](../ladder-safety.md).  
5. Look for an ideal location on the roof that would have the best line-of-site (LOS) to Tucson Mesh’s [supernode](../hardware/supernodes/index.md). You may need to use binoculars to find the mast.   
6. Once you have selected a location, check with the Installee to make sure the location works for them.

### LiteBeam

1. Plug in the LBE to the battery pack. Once it powers up, a blue light will appear on the router and it will generate a management wifi- SSID- that looks something like `LBE-5AC-Gen2`.   
2. Connect to the network by navigating to https://192.168.172.1 in your browser. You may be met with a warning due to a self-signed security certificate. Bypass this warning. This will bring you to the LiteBeam administrtion interface. 
3. Type in the admin username and password to log into the LiteBeam. 
4. Once connected, Go to `Wireless Settings` \> `SSID`, and make sure the SSID is connected to the Sector Router that makes the most sense with your location. Click and apply changes. Make sure that the WPA Password is correct. 
5. After you check these, you might have to wait a few minutes for the LiteBeam to find the Sector Router and connect.   
6. Go to Tools and Alignment or “Align Antennae”  
7. Hold the LiteBeam up to be the direction and location that you had previously chosen.  
8. You will need to find a signal that is at least \-70 or higher. Any signal lower than that will not be strong enough to move on to the install.   
9. Once you install, you will be able to make a more precise alignment of at least \-65 or higher.

*You can now move on to the install\!*

## Line-of-site to Omni-only install

1. Plug in the Omni to power pack. 
2. You will see a wifi network called `tucsonmesh-20-omni`.
3. Navigate to `http://10.69.0.20/` in your browser. This will take you to the web interface GUI for the Omni.  
4. If it asks you to change password, ignore it.  
5. Go to the WebFig tab on the top right.
6. Click through the following menu items starting with the menus on the left side of the interface: `Wireless` \> `Wifi interfaces` \> `scanner`. 
7. Make sure you change `interface` to `wlan3` before scanning.
7. To select an Omni to connect to, close out the scanner, navigate to `Wireless` \> `WiFi Interfaces`, click on `wlan4`, and edit the SSID to match the SSID of the Omni you want to connect to.  


# Ubiquiti Rocket Prism 5AC Router Configuration Guide

This is a guide for configuring the [Ubiquiti Rocket Prism 5AC](../../hardware/rocketprism.md), the device that connects a user's node to the [supernode](../../networking/supernodes/index.md).

## Materials needed 

- Rocket Prism device
- Mount of choice
- Eventually, an antenna (as the RocketPrism itself doesn't come with one)
- Hose clamp  
- Power cable  
- POE Injector
- The default administrator username and password for RocketPrism devices. This is in the password manager as `Tucson House RocketPrism 5AC Admin`.

## Overview 

To configure the Rocket Prism, you will need to take a number of steps. The broad goals of these steps are to:

- load in a Tucson Mesh configuration
- update the firmware (the operating system)  
- install/mount the device

## Download the firmware 

Start by downloading the firmware that you'll be upgrading the device to. You can grab the newest version of the firmware [here](https://ui.com/download/software/r5ac-prism). The firmware on the device may already be up to date, but it's good to have on hand for if it's not.

## Download a baseline configuration

Next, download a sample configuration file [here](./static/RocketPrism-template.cfg) that we'll use to quickly setup the device and then tweak for the new install.

## Power on the device 

1. Plug the power cable into the PoE injector and plug the other end into an outlet.  
2. Plug an ethernet cable into the port on the PoE injector labeled POE.   
3. Pull off the weather-resistant cover on the bottom and plug the other end of the ethernet cable into the port on the Rocket Prism.

## Connect to the management WiFi network 

1. Once the device powers up, some blue lights will appear on the router and it will enable a management network whose SSID looks something like `RP-5AC-Gen2:<MACADDRESS>`. Connect to this network.

## Browse to the management web interface 

1. Once connected to the wireless network, navigate to https://192.168.172.1 in your browser if your device does not automatically redirect you.
2. You may be met with a warning due to a self-signed security certificate. Bypass this warning. This will bring you to the Rocket Prism's management interface.  

## Upload the configuration file 

1. In this interface you will go through a “Please Set Up Your Device” prompt, where you will select `United States` under `Country` and `English` under `Language`.   
2. Check the Terms of Use checkbox and click `Upload Backup Configuration`. Choose the .cfg file you downloaded from the configuration generator.
3. You will see a prompt on the top-right corner of the screen saying Configuration backup file uploaded. Click `Apply` and wait a minute for the page to reload. Sometimes you will have to refresh the page to get back into the interface.  
4. The configuration you uploaded will change the username and password to access the management web interface. To log back in, use the credentials you gathered before the install. These are the credentials labeled `Tucson House RocketPrism 5AC Admin` in the password manager.

## Update the firmware if needed 

1. Click on the `System` menu item (a gear icon) in the left-hand sidebar.  
2. Click the `Upload` link next to the `Upload Firmware` label and in the file selection dialog select the firmware file you downloaded earlier. It will end in `.bin`.  
3. You will see a modal labeled `Uploading` with a progress bar.  
4. When the firmware has completed uploading, the progress modal will close and a new one will open in the upper-right-hand corner of the screen. It will be labeled `Firmware Update`. Click the `Update` button.  
5. A new modal will open showing the status. It will first show `Initializing Firmware Update` and then `Upgrading`.  
6. You may get temporarily disconnected from the management wireless network. If you get disconnected, reconnect to the management network and reload the web management interface in your browser.  
7. The `Firmware Version` should now reflect the version of the firmware you downloaded.

## Pair with UISP

Note: you can only do this step if your Rocket Prism _has internet access_ (i.e., the ethernet cable on the other side of your PoE injector is connected to something that provides internet access).

1. Click the `UISP` button in the top right.
2. Paste the URL from the password manager item `Tucson House RocketPrism - UISP Key`.
3. Login to UISP and navigate to the devices screen.
4. At the bottom, there should be a yellow device that represents your Rocket Prism and says "Pending Adoption". Adopt it into the network.

## Configure the sector for your install's needs

You're configuring a sector router. You probably have specific things to your install that you should do here, but I don't know what they are. Maybe change the network SSID (go to the Wireless tab). Or the hostname/timezone (go to the System tab). Best of luck with whatever it is, though! 

## Hardware and Mounting

TBD, but it's likely specific to your install too.

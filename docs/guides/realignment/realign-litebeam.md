# Realign your LiteBeam 

For these steps, you'll need to be on your roof. Be sure to observe the [ladder safety](../ladder-safety.md) protocols, when climbing up to your roof.

It's also helpful to have two people, both for ladder safety and later, so one person can adjust the angle of the device and the other can monitor the signal strength.

!!! info "Using the UISP mobile app" 

    These instructions use your device's web browser to access the admin interface for your LiteBeam. If you find it easier to use the UISP mobile app, you can find instructions [here](realign-litebeam-uisp-app.md).

## 1. Review related documentation

It's helpful to review these other pieces of documentation that are referenced throughout this guide. 

- [LBE-5AC-Gen2 Quick Start Guide](https://dl.ubnt.com/qsg/LBE-5AC-Gen2/LBE-5AC-Gen2_EN.html): This has images of the different parts of the LiteBeam device and has the names Ubiquiti uses for the different parts.

## 2. Connect to the LiteBeam's management network 

- Unplug the ethernet cable from the LightBeam. Wait a few seconds and plug the ethernet cable back in. This will restart the device.
- Once the LightBeam powers up, a blue light will appear on the bottom of the router's Antenna Feed and a wireless management network will become available. This network has an SSID that begins with `LBE-5AC-Gen2`, for example `LBE-5AC-Gen2:245A4CD44286`.
- Connect to this wireless network on your computer or mobile phone as you would any other WiFi network.

## 3. Log into the device's administrative interface

- Visit [https://192.168.172.1](https://192.168.172.1) in your browser. You may be met with a warning due to the self-signed SSL certificate used for the connection. Bypass this warning. 

![Certificate Warning](img/litebeam-web-browser-warning-1200x679.png)

- This will bring you to the administration interface.
- Use the admin username and password you recieved from Tucson Mesh Admin to log into the administration interface.

![Administrative Interface Login](img/litebeam-web-login-1200x679.png)

- Log in.

## 4. Connect the device to the correct network for alignment

- Once you've loaded the web administration interface, click on the `WIRELESS` icon in the left hand menu. The icon looks like a WiFi symbol. This should take you to the `Basic Wireless Settings` page.

![Basic Wireless Settings](img/litebeam-web-basic-wireless-settings-1200x679.png)

- Under `Wireless Security` click the 'show' button next to `WPA PRESHARED KEY`. Make sure that the value that it shows matches the one you were given. If you need to change it, be sure to click the `SAVE CHANGES` button.
- Remember, the BICAS supernode and the Tucson House supernode use different keys. If you are switching from one to the other, you will need to update accordingly. 
- Click the `SELECT` button below the `SSID` input and click the radio button next to the Tucson Mesh network with the strongest signal. A signal closer to zero is stronger. I.e. \-68 dBm is stronger than \-70 dBm and \-75 dBm is weaker. 

![Site Survey](img/litebeam-web-site-survey-1200x679.png)


- The network names for the Tucson House supernode are:
    - `TMTH-SW-Top-W`
    - `TMTH-SW-Middle-SW`
    - `TMTH-SW-Bottom-W`
    - `TMTH-SE-Top-S`
    - `TMTH-SE-Middle-SE`
    - `TMTH-SE-Bottom-E`
    - `TMTH-NW-Top-N`
    - `TMTH-NW-Middle-NW`
    - `TMTH-NW-Bottom-W`
    - `TMTH-NE-Top-E`
    - `TMTH-NE-Middle-NE`
    - `TMTH-NE-Bottom-N`

- The network names for the BICAS supernode are:
    - `tucsonmesh-sectortest`
    - `tucsonmesh-sectorsouth`
    - `tucsonmesh-sectoreast`

- Then click the `SELECT` button.

- After you change either the wireless network or the WPA preshared key, you might have to wait a few minutes for the LiteBeam to find the sector router and connect.

## 5. Open the alignment tool

Open the alignment tool and keep it open. You'll monitor this tool as you adjust the position of the LiteBeam.

- Click on the `TOOLS` icon in the left-hand menu. And choose `ALIGNMENT` in the menu that pops up.

![Tools Menu](img/litebeam-web-tools-menu-1200x679.png)

- This will open the `Antenna Alignment Tool`.

![Alignment Tool](img/litebeam-web-antenna-alignment-tool-1200x679.png)

## 6. Adjust the LiteBeam position

![LiteBeam Mounts](img/litebeam-mounts-labeled-450x600.jpg)

- Loosen the wingnut on the clamp around the *azimuth mount* shaft. This will allow adjusting the horizontal angle of the device.
- The shaft has small ridges and the clamp has small grooves. This makes it difficult to rotate the device around the shaft, even when the clamp is loosened. The best way to rotate the device is to gently raise the device off the shaft until it is just above the shaft. Then rotate it so the next ridge and groove are aligned.
- Adjust the angle of the device one groove at a time and watch for how the signal strength changes. The alignment tool signal strength readings will lag movements of the antenna, so make small movements and wait for the admin interface signal reading to update before adjusting the position further. 
- Keep in mind the landmarks you identified in Google Earth and consult any saved images from the app.
- Look for the position that makes the signal as strong as possible as shown in the web admin interface or UISP app. A signal closer to zero is stronger. I.e. \-68 dBm is stronger than \-70 dBm and \-75 dBm is weaker 
- Now loosen the wingnut on the side of the *elevation mount*.
- Repeat the process of adjusting the vertical angle of the device and watch how the signal strength changes. Stop at the angle with the strongest signal strength.
- Ideally you want a signal \-65 dBm or stronger, but one that is at least \-70 dBm will be workable.
- Tighten the wingnut for the *elevation mount*, then tighten the wingnut for the clamp around the *azimuth mount* shaft.


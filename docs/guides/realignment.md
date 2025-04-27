# DRAFT: Realignment

!!! info "How can this documentation be improved?" 

    - Check the menu items in LiteBeam administrative interface.
    - Add screenshots to clarify where to look in the admin interface.
    - Clarify whether it makes sense to adjust the LiteBeam horizontally or vertically first.
    - Update to reflect realignment from BICAS to Tucson House.
    - Incorporate a protocol for people to get their own login for the LiteBeam's admin interface.

This is a draft guide to help users and installers realign the [LiteBeam](../hardware/litebeam.md) device on a home rooftop with a [supernode](../networking/supernodes/index.md). Currently it reflects attempting to realign users after the supernode moved from the old BCC to [BICAS](../networking/supernodes/bicas.md). Eventually it will reflect realigning devices to point to the [Tucson House](../networking/supernodes/tucson-house.md) supernode instead.

## Overview

- Gather equipment, install software and credentials. 
- Use free GIS software to orient yourself between the home node and the supernode and check line of site.
- Climb on the roof and use the devices administrative interface to see how changing the vertical and horizontal angle of the device changes the signal strength when connecting to the supernode.

## Materials needed

- Password to log into the administration interface of the LiteBeam
- WPA password for connecting to the sector router WiFi network
- Ladder
- Laptop computer or mobile phone with WiFi capabilities and a web browser
- Google Earth
- Binoculars (optional)

## Reading

- Review the [LBE-5AC-Gen2 Quick Start Guide](https://dl.ubnt.com/qsg/LBE-5AC-Gen2/LBE-5AC-Gen2_EN.html). This has images of the different parts of the device and has the names Ubiquiti uses for the different parts.

## Before getting on the roof

- Confirm where the LightBeam is on the rooftop
- Check line of sight using Google Earth 
- Note landmarks for helping to align the supernode
- Determine which sector router to connect to
- Let anyone in the household know that their internet connection will be disrupted during the alignment process.

https://startyourownisp.com/posts/guide-to-google-earth/

## On the roof

It's helpful to have two people for this part so one person can adjust the angle of the device and the other can monitor the signal strength.

- Unplug the ethernet cable from the LightBeam. Wait a few seconds and plug the ethernet cable back in. This will restart the device.
- Once it powers up, a blue light will appear on the router and it will generate a management wireless network that has an SSID that looks something like `LBE-5AC-Gen2`.
- Connect to the wireless network on your computer or mobile phone.
- Visit [https://192.168.172.1](https://192.168.172.1) in your browser. You may be met with a warning due to a self-signed security certificate. Bypass this warning. This will bring you to the administration interface.
- Type in the admin username and password and log into the administration interface.
- Once connected, click on `Wireless Settings` \> `SSID`. Make sure the SSID is connected to the sector router that makes the most sense with your location. Make sure that the WPA Password is correct. Apply changes.
- After you check these, you might have to wait a few minutes for the LiteBeam to find the sector router and connect.
- Go to `Tools` \> `Alignment` or `Align Antennae`.
- Loosen the wingnut on the *azimuth mount* this will allow adjusting the horizontal angle of the device. Slowly adjust the angle of the device and watch for how the signal changes. The admin interface signal strength readings will lag movements of the antenna, so make small movements and wait for the admin interface signal reading to update before adjusting the position further. Keep in mind the landmarks you identified in Google Earth and consult any saved images from the app.
- Look for the position that makes the signal as strong as possible. A signal closer to zero is stronger. I.e. \-68 dBm is stronger than \-70 dBm and \-75 dBm is weaker 
- Now loosen the wingnut for the *elevation mount*.
- Repeat the process of adjusting the vertical angle of the device and watch how the signal strength changes. Stop at the angle with the strongest signal strength.
- Ideally you want a signal \-65 dBm or stronger, but one that is at least \-70 dBm will be workable.
- Tighten the wingnut for the *elevation mount*, then tighten the wingnut for the *azimuth mount*.


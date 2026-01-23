# Ubiquiti LiteBeam 5AC - Pairing with UISP

This is a guide for pairing the [Ubiquiti LiteBeam 5AC](../../hardware/litebeam.md) with Tucson Mesh's UISP instance. Doing this allows for remote monitoring and management of the LiteBeam.

!!! info "How can this documentation be improved?" 

    - Also provide instructions for adopting a device using the UISP mobile app.


## Materials needed

- A laptop. We couldn't find the `UISP` button in the mobile version of the LiteBeam web admin interface. It's easiest to just use a desktop browser.
- The UISP device adoption key. This is under `UISP Device Adoption Key` in the password manager. 
  - This is a very long string, so make sure you have access to the password manager on the computer you're using to do the pairing.
  - If you're connecting to the LBE through it's local management network, make sure you have offline access to the adoption key.
- The LiteBeam admin interface credentials.

## Find the LiteBeam's IP address

In this portion of the guide, we are walking through how you would find and connect to a LiteBeam remotely, assuming that you have a working OmniTik 5AC & LiteBeam setup. If you already have a way of accessing your LiteBeam's management interface (because you're physically nearby and can reboot it to spin up the management WiFi network or similar), skip down to [the next section](#connecting-to-the-litebeam)

To get started we first need to find the IP address of the LiteBeam on the mesh. Only Omnitiks have statically allocated IPs (based on their node number/NN), so our first goal is to identify what IP has been assigned to this Litebeam by [DHCP](https://simple.wikipedia.org/wiki/Dynamic_Host_Configuration_Protocol).

First, let's open Winbox and connect to your Omnitik device.

![Winbox Prompt](img/winbox-login-prompt.png)

Once logged in using the credentials stored in the Tucson Mesh Bitwarden, navigate to IP -> DHCP Server.

![IP - DHCP Server](img/winbox-ip-dhcpserver.png)

Then, head to the Leases tab and look for the device with an `Active Host Name` of `tucsonmesh-lbe-<NN>`. Then, to the left of that, you should find the actively assigned IP address.

![IP - DHCP Server - Leases](img/winbox-ip-dhcpserver-leases.png)

With that, we can move on to pairing the LiteBeam with UISP.

## Connect to the LiteBeam's admin interface

Using your web browser, navigate to the IP address of your LiteBeam.

If you're connecting remotely, use the IP address you found in the previous step.

If you're on-site, connect to the LiteBeam's admin network. It's name will begin with `LBE-`. Once connected, you can navigate to the address https://192.168.172.1.

You will likely get a warning about the LiteBeam's self-signed TLS certificate. Just tell your browser to continue. You'll find yourself at the login page.

![LBE Login Page](img/lbe-login-page.png)

## Pair the LiteBeam with UISP

Once you are logged in, you should notice a button that says `UISP` in the top right corner, and it likely has a flashing amber light next to it. If the light next to the icon is green, your LiteBeam is already paired with UISP. You may want to go check there and see if you can find it.

Click this button, and a small menu will drop down. Select `Change Key`.

![LBE Change Key](img/lbe-uisp-changekey.png)

In the text window that opens, fill in the `UISP Device Adoption Key` in the password manager. After clicking OK, the UISP icon should change to showing a green circle after a few moments.

![LBE UISP Configured](img/lbe-uisp-changekey-status.png)

If the light never turns green, make sure your LiteBeam can reach the internet. If it can't reach the internet, then it can't reach UISP either. After this, we need to login to UISP and adopt the new device.

## Adopt the device in UISP

If you're connected to the LBE's management WiFi network, you'll need to disconnect and connect to a network with access to the internet.

Navigate to [https://tucsonmesh.uisp.com](https://tucsonmesh.uisp.com) and log in with your credentials. On the devices page, typically at the very bottom, there should be a list of devices that are "pending adoption". In this case, we only have one:

![UISP Pending Devices](img/uisp-device-adoption-prompt.png)

Select your pending LBE and choose `Assign Site/Subscriber`.

![UISP Assign Site/Subscriber](img/uisp-device-adoption-assignsite.png)

We tend to assign devices as `Sites` as we don't use any of the "customer management"-oriented pieces of UISP. So, say you're creating a new Site and fill out the relevant information.

![UISP Site Creation](img/uisp-device-adoption-site.png)

After confirming the new site information, the new LBE should shortly then move from Pending Devices to the broader list. You did it!

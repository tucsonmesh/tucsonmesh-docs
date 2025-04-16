# MikroTik SXTsq 5 ac Router Configuration Guide

!!! info "How can this documentation be improved?" 

    - Clarify how to tell the SXT which router to bridge with, and to tell which router to be the top and which to be the bottom (receiving and sending). 
    - Check if we still need to replace instances of `nycmesh` with `tucsonmesh` in the generated config, or has this been fixed? 

This is a guide to configuring the [MikroTik SXTsq 5 ac](../../hardware/sxtsq.md), which is often used for point-to-point connections between nodes.

These instructions are based on NYC Mesh's [configuration docs for this device](https://wiki.nycmesh.net/books/3-hardware-firmware/page/mikrotik-sxtsq-5-ac).

## Materials needed

* Router
* POE injector
* AC adapter for POE injector
* Computer
* Ethernet adapter for computer
* Ethernet cable
* WinBox installed on your computer or an SCP and SSH client
* Network number

## Connect to the device

Plug one end of an ethernet cable into the port at the bottom of the SXTsq. Plug the other end of the cable into the POE injector. 

Connect the POE injector to your computer (on the injector that comes with the device, this is a short, integrated cable labeled "DATA").

Connect the AC adapter to the POE injector.

The SXTsq device will initially have an IP address of `192.168.88.1`. In order to connect to it, you will need to give your computer the IP address `192.168.88.5` with a subnet mask of `255.255.255.0`. 

Instead of manually setting the IP address of your computer, you could plug the SXTsq, and your computer to one of ethernet ports 2-5 on an OmniTIK or similar router, find the DHCP lease for the SXTsq, and connect to it that way.

## Generate a configuration file

If using the SXT instead of a LBE to connect to another Omni, go to the [Tucson Mesh Configuration Generator](https://tucsonmesh.github.io/tucsonmesh-configgen/?version=v4.8.4&device=SXTsq5AC&template=sxtsq5ac-mesh-bridge.rsc.tmpl) and create a configuration file by selecting these options in the form:

* **Version:** `v4.8.4`   
* **Device:** `SXTsq5AC`  
* **Template:** `sxtsq5ac-mesh-ospf.rsc` .   
* **network number:**  
* **If you are only installing one SXT** use the network number of the node you are installing it at. E.g. if installing an SXT at NN66, use `66` as the NN in the configuration generator.  
* **If you are installing two or more SXTs** add the network number of the place it is installed, and append the network number for the node the SXT it is connecting to. E.g. `6669` if you are installing it at NN66 and pointing it at NN69.

Click the `Download config` button, which should download a .rsc file named `sxtsq5ac-mesh-ospf.rsc`.

⚠️ If using the **template** `sxtsq5ac-mesh-ospf.rsc`, all instances of `nycmesh` in the config should already be adjusted to `tucsonmesh`. If using a different template, you may need to change all instances of `nycmesh` to `tucsonmesh` in the text file of the config by using ctrl \+ f replace all.

## Upload configuration

### Using the WinBox app

Open WinBox.

You should be able to see the SXTsq by looking in the `Neighbors` tab of WinBox.

Connect to the SXTsq by double-clicking on the **MAC Address (*important\!*)** that appears in the list. 

On the 4.0 version of WinBox, this will initiate the connection. On older versions, you may have to wait for the MAC address to populate  the `Connect To` box and then click the `Connect` button at the top. The login is `admin` and the password is blank.

You will get a prompt saying “RouterOS Default Configuration”. Click `OK` to dismiss.

Once connected, load the config you generated using the Tucson Mesh configuration generator.  
   
Navigate to the `files` tab in WinBox’s GUI and drag the .rsc config you just downloaded into the `flash` folder. 

* On the left sidebar, click `Files`. Open a File Explorer or Finder window alongside WinBox and and drop the configuration file you downloaded earlier into the `flash` folder.  
* You should see the uploaded file have `flash/` before the filename**.**  
* **⚠️ *Important\! if it doesn’t have flash before it, make sure you drop the file onto the flash folder and try again***.

Tell the router's operating system to reset the configuration using the file you just uploaded.

* On the left sidebar, click `System`, then `Reset Configuration`.   
* Check the `No Default Configuration` box.  
* Click the down arrow next to `Run After Reset` to select the file you uploaded.   
* Finally, click `Reset Configuration` and `yes`, and you will be disconnected.   
* After a couple of minutes, the LED next to the person icon on the device will turn on, indicating that the configuration has been applied.  
  * ⚠️ As of Apr 5, 2025, the LED next to the person icon didn't light up, even though the configuration was installed. If the LED doesn't light, just make sure you've given the process at least 5 minutes before moving on to the next step.

## Reconnect using WinBox

At this point you may need to close WinBox and open it again, or even power cycle the SXTsq by unplugging and plugging in the ethernet cable from the bottom of the device in order to reconnect to the SXTsq.

If the device shows up in WinBox, note its IP address. You will want to manually assign an IP address on the same subnet as the SXTsq to your computer. Note that the configuration generator assigns IP addresses to the device based on its network number using the scheme `10.69.0.[NN + 100]`. For example, if the network number is 88, the IP address of the device will be `10.69.0.188`. Give your computer an IP on the same subnet, such as `10.69.0.189` with a netmask of `255.255.255.0`.

You should then be able to connect to the device using WinBox as you did before.

## Set the SSID for bridging

Now you will need to change the SSID in WinBox by clicking the `Wireless` tab, double clicking on the row for `wlan1` in the table that appears and clicking on the `Wireless` tab of the window that pops up named `Interface <wlan1>`.  
 

* **If configuring the SXT to act as a direct bridge to another SXT:**   
  * For the SXTsq AP (i.e. the remote SXTsq that the end user's SXTsq is connecting to, i.e the top), change the SSID to `tucsonmesh-NN` where `NN` is the network number where this end of the point-to-point will be installed. Then the user's device will connect so that the SXTsq will connect as a bridge to the SXTsq on the other end of the connection. Then change the `mode` to `bridge`.    
  * For the SXTsq client (i.e the SXTsq that is installed at the end user’s home, i.e. the bottom) change the SSID to `tucsonmesh-NN` where `NN` is the network number of the AP and keep the `mode` as `station bridge`.  
* **If configuring the SXTsq to connect to a specific OmniTIK:** Change the SSID to `tucsonmesh-NN-omni` where `NN` is the network number of the remote node where the OmniTIK is located. For example, if trying to connect to the node with network number 56, set the SSID to `tucsonmesh-56-omni`.  
* **If configuring the SXT to connect to ANY omni that it can see:**  Change the SSID to `tucsonmesh-wds`. This will allow it to automatically connect to any router on the mesh network. We typically don't do this and prefer to have an SXT pair with a particular OmniTIK or other SXT.

## Check the connection

That’s it\! You should be good to go at this point. 

You can check the connections here through the `Wireless` tab on the left and see the signal strength and what connection the SXsqT is connecting to by clicking through some of the options in the `Wireless` window. There is also a `scan` option to find options of what to connect to and an `alignment` tool.   


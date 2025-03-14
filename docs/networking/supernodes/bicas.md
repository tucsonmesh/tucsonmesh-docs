# BICAS 

This supernode is located at [BICAS](https://bicas.org/), a community bicycle project located at [2001 N 7th Ave](https://maps.app.goo.gl/uK3XnBHGnFK33Zqw9).

This supernode was created in March 2025 when we moved the equipment that was at the former location of the BCC across the street.

## Hardware

- 3 [Ubiquity LiteAP](../../hardware/liteap.md) sector antennas
- Omni 50: A [MikroTik OmniTIK 5 PoE ac](../../hardware/omnitik.md) that handles NAT and handoff with login.
- Omni 51: A [MikroTik OmniTIK 5 PoE ac](../../hardware/omnitik.md) that is attached to the same mast as the secto antennas. This device powers all three sector antennas. It is connected to Omni 50 by a single ethernet cable.
- TP Link ???: Wireless router formerly at BCC, now used to provide WiFi to BICAS. The WAN Port of this device is plugged into "ether2 cust" on the Mikrotik switch that belongs to Login.

## Inside hardware connections

Login has a PoE injector that leads out to the roof through the "simply bits"  plug. We have a PoE injector that goes out to the roof through the mesh plug.

![Ports connect PoE injectors to roof](img/bicas_supernode_ports_poe_to_roof.jpg)

The black "Tucson Mesh" cable leads to our MikroTik PoE injector.

![Mikrotik PoE injector](img/bicas_supernode_microtik_poe_injector.jpg)

The other end of our mikrotik PoE injector goes into "eth2 cust" in Login's switch. Meanwhile, a patch cable goes from eth1 cust to BICAS's router.

![Login switch](img/bicas_supernode_login_switch.jpg)

This is the other end of the patch cable going from the Login switch to BICAS's router:

![BICAS router](img/bicas_supernode_bicas_router.jpg)

BICAS also has their own UPS that our equipment is connected to the battery backup side of.

![BICAS UPS](img/bicas_supernode_ups.jpg)

## TP Link internet configuration

- Internet Connection Type: Static IP
- IP Address: 204.17.35.195
- Subnet Mask: 255.255.255.248
- Default Gateway: 204.17.35.193
- Primary DNS: 1.1.1.1
- Secondary DNS: 8.8.8.8


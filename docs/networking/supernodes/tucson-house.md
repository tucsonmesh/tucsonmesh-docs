# Tucson House

This supernode will be located on the roof of [Tucson House](https://en.wikipedia.org/wiki/Tucson_House), a residential high-rise tower built in the 1960s. It is located at [1501 N Oracle Rd, Tucson, AZ 85705](https://maps.app.goo.gl/LGk427NhUyN2ciaw8).

It is slated to be installed in May 2025.

## ⚠️  This documentation requires updates

- Create pages in the hardware section and link 
- Document connections between hardware
- Update language once supernode is fully installed and live

## Hardware

- Mikrotik Cloud Core Series Router	CCR2004-16G-2S+ 
- Mikrotik Cloud Switch Series Switch 	CCS610-8P-2S+IN
- Ubiquiti rocket PRISM AC gen2 5 GHz airMAX® ac Radio BaseStation with airPrism® Active RF Filtering Technology	RP-5AC-Gen2-US
- Ubiquiti AirPRISM 5 GHz, 30x30° HD Sector Antenna 	AP-5AC-90-HD
- Ubiquiti Ethernet Surge Protector	ETH-SP-G2 
- APC Smart-UPS C 1500VA LCD RM 2U 120V with SmartConnect	SMC1500-2UC

### Information from Login's Side

> IP assignment:
> Network: 204.17.32.56/29
> Gateway: 204.17.32.57
> Usable IPs: 204.17.32.58-204.17.32.62 (inclusive)
> 
> We will hand you a 1Gbps copper handoff set to auto-negotiate.  Please advise if you need/want a different demarc configuration.

### Hardware: Mikrotik CCR2004-16G-2S+

This is the _router_ for the Tucson House supernode. It is configured as **NN-49**. Accordingly, it has a static mesh IP of `https://10.69.0.49`

If you are configuring one of these routers and it has been freshly reset or is fresh out of the box, you need to
- Connect to it over Ethernet into the `15/BOOT` port
- Manually assign your network interface to use an IP of `192.168.88.2/24` (`192.168.88.2` with a netmask of `255.255.255.0` and default gateway/route of `192.168.88.1`)
- Go to `http://192.168.88.1` or open Winbox and attempt to connect via IP or through the Neighbors tab

---

### Hardware: Mikrotik CSS610-8P-2S+IN

This is the model of _PoE Switch_ that we are using. There are two of them. They don't require any particular setup with the exception of naming them something other than Mikrotik.

If you connect directly over Ethernet with them, you can access the admin UI at `192.168.88.1` in the same fashion as above or, if it's been assigned an IP over DHCP, that IP.

- Switch 1:
    - Hostname/Identity: `tmth-css610-1`
    - Serial number: `HEB08PEFCYS`
- Switch 2:
    - Hostname/Identity: `tmth-css610-2`
    - Serial number: `HEB08R65HZ9`

---

### Hardware: RocketPrism 5AC Gen 2

Model: `RP-5AC-Gen2`

When setting up, connect to the `RP-5AC-Gen2:<MAC-ADDRESS>` WiFi AP. Navigate to `192.168.172.1`

**Further documentation here TBD**

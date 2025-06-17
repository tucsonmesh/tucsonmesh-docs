# Tucson House

This supernode will be located on the roof of [Tucson House](https://en.wikipedia.org/wiki/Tucson_House), a residential high-rise tower built in the 1960s. It is located at [1501 N Oracle Rd, Tucson, AZ 85705](https://maps.app.goo.gl/LGk427NhUyN2ciaw8).

It went live in June 2025.

!!! warning "This documentation requires updates"
    - Document connections between hardware

## Hardware

- [MikroTik Cloud Core Series Router CCR2004-16G-2S+](../../hardware/ccr2004.md): This is the _router_ for the Tucson House supernode. It is configured as **NN-49**. Accordingly, it has a static mesh IP of `https://10.69.0.49`
- [Mikrotik Cloud Switch Series Switch CCS610-8P-2S+IN](../../hardware/ccs610.md): There are two of these.
- [Ubiquiti rocket PRISM AC gen2 5 GHz airMAX® ac Radio BaseStation with airPrism® Active RF Filtering Technology RP-5AC-Gen2-US](../../hardware/rocketprism.md)
- Ubiquiti AirPRISM 5 GHz, 30x30° HD Sector Antenna	AP-5AC-90-HD
- Ubiquiti Ethernet Surge Protector	ETH-SP-G2 
- APC Smart-UPS C 1500VA LCD RM 2U 120V with SmartConnect	SMC1500-2UC

### Information from Login's Side

> IP assignment:
> Network: 204.17.32.56/29
> Gateway: 204.17.32.57
> Usable IPs: 204.17.32.58-204.17.32.62 (inclusive)
> 
> We will hand you a 1Gbps copper handoff set to auto-negotiate.  Please advise if you need/want a different demarc configuration.


## SSID naming convention

The naming convention for the SSID of the APs on Tucson House follow this convention: `TMTH-{corner}-{vertical_position}-{effective_direction}`, e.g. `TMTH-SW-Bottom-S`.

- `corner` is the corner of the building on which the radio is mounted: `NE`, `NW`, `SE`, `SW`
- `vertical_position` is the vertical slot where the radio is mounted: `Bottom`, `Middle`, `Top`
- `effective_direction` is the direction corresponding to the radio's slot: `N`, `S`, `E`, `W`, `NE`, `NW`, `SE`, `SW` 

These are all the networks available from this supernode:

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


# Ubiquiti Rocket Prism 5AC

Product page: [UISP airMAX Rocket Prism 5AC Access Point](https://store.ui.com/us/en/products/rocket-5ac-prism)

Monitoring: ?

These are the radios for the sector antennas on the [Tucson House supernode](../networking/supernodes/tucson-house.md).

## Antenna setting

In UISP the antenna setting needs to be set to `AP-5AC-90-HD` when connected to the airPRISM 3x30° HD Sector antennas ("Big Boy") as they are atop Tucson House.

## SSID naming convention

The naming convention for the SSID of the APs on Tucson House follow this convention: `TMTH-{corner}-{vertical_position}-{effective_direction}`, e.g. `TMTH-SW-Bottom-S`.

- `corner` is the corner of the building on which the radio is mounted: `NE`, `NW`, `SE`, `SW`
- `vertical_position` is the vertical slot where the radio is mounted: `Bottom`, `Middle`, `Top`
- `effective_direction` is the direction corresponding to the radio's slot: `N`, `S`, `E`, `W`, `NE`, `NW`, `SE`, `SW` 


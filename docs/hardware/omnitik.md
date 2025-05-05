# MikroTik OmniTIK 5 PoE ac

Product page: [MikroTik Routers and Wireless - Products: OmniTIK 5 PoE ac](https://mikrotik.com/product/rbomnitikpg_5hacd)

User manual: [OmniTIK series - User manuals - MikroTik Documentation](https://help.mikrotik.com/docs/spaces/UM/pages/14221325/OmniTIK+series)

Configuration guide: [MikroTik OmniTIK 5 PoE ac Router Configuration Guide](../guides/configuring-routers/omnitik.md)

Monitoring: Slack messages to \#monitoring-screams

Along with the [Ubiquity LightBeam AC Gen 2](litebeam.md), this is what most users have on their roofs.

This device runs MikroTik RouterOS, so it may be useful to consult the [RouterOS documentation](https://help.mikrotik.com/docs/). We've also started compiling documentation about common tasks in RouterOS in [RouterOS Tips](../guides/routeros-tips.md).

## Resetting

To reset the Omni's operating system (OS) to the default settings, follow these steps:

- Unplug the ethernet cable from the POE port on the Omni. This will turn off the router. 
- Hold down the reset button.
- While continuing to hold down the reset button, plug the ethernet cable back into the POE port. This powers on the router.
- Continue holding down the reset button until the LED light starts flashing, about 5 seconds.
- Release the reset button and let the router continue to boot.
- You should see the default management wireless network appear, it will look smething like `Mikrotik-F32xxxx`.

There are additional functions of the reset button that are accessed by holding down the reset button for longer than 5 seconds. See the [Buttons and Jumpers](https://help.mikrotik.com/docs/spaces/UM/pages/14221325/OmniTIK+series#OmniTIKseries-ButtonsandJumpers) section of the OmniTIK user manual for more about these other functions.

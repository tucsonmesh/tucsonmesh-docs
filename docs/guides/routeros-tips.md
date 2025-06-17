# RouterOS tips

RouterOS is the operating system that runs on MikroTik devices such as the [OmniTIK 5 PoE ac](../hardware/omnitik.md) and the [SXTsq 5 ac](../hardware/sxtsq.md).

You should really read the [official RouterOS manual](https://help.mikrotik.com/docs/spaces/ROS/pages/328059/RouterOS). This guide is intended to provide task-oriented entry points into the official documentation, especially when the examples in that documentation aren't fully clear.

## Export the configuration

Router OS has a [configuration management system](https://help.mikrotik.com/docs/spaces/ROS/pages/328155/Configuration+Management) that allows [exporting and importing configuration](https://help.mikrotik.com/docs/spaces/ROS/pages/328155/Configuration+Management#ConfigurationManagement-ConfigurationExportandImport).

To export the entire configuration, first connect to the [console](https://help.mikrotik.com/docs/spaces/ROS/pages/8978498/Console) using SSH or the console screen within Winbox.

Then, run the following is command. You might want to replace `config-export.rsc` with a file name that reflects the device name and date of the export, for example, `tucsonmesh-52-omni-20250410.rsc`:


```
/ export file=config-export.rsc
```

## We use a mixture of RouterOS 6 and RouterOS 7, but mostly RouterOS 6

We use RouterOS 6 on [OmniTIK](../hardware/omnitik.md) devices because of difficulties with WDS. NYC Mesh may have figured this out.

We use RouterOS 7 on the [CCR2004-16G-2S+](../hardware/ccr2004.md) at the [Tucson House supernode](../networking/supernodes/tucson-house.md) because RouterOS 7 has support for Wireguard.

Here is the official documentation for [migrating from RouterOS 6 to 7](https://help.mikrotik.com/docs/spaces/ROS/pages/30474256/Moving+from+ROSv6+to+v7+with+examples).

### OSPF network type behavior

One consequential difference between ROS 6 and 7 is that the `ptmp` OSPF network type in ROS 6 behaves like the `ptmp-broadcast` network type in ROS 7.

From the [documentation](https://help.mikrotik.com/docs/spaces/ROS/pages/9863229/OSPF#OSPF-DiscoveryonPTMPSubnets):

> For PTMP networks that do support broadcast, a hybrid type named "ptmp-broadcast" can be used. This network type uses multicast Hellos to discover neighbors automatically and detect bidirectional communication between neighbors. After neighbor detection "ptmp-broacast" sends unicast packets directly to the discovered neighbors. This mode is compatible with the RouterOS v6 "ptmp" type.


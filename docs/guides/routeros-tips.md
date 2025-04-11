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


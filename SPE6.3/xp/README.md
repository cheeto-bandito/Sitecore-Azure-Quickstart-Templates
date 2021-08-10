# Sitecore Powershell Extensions module for Sitecore XP0 Environment

This template deploys Sitecore Powershell Extensions module into a Sitecore XP0 (XPSingle) Environment (single all-in-one instance).

## Parameters for Sitecore Powershell Extensions

The **deploymentId**  parameter is filled in by the PowerShell script.

| Parameter                                 | Description
--------------------------------------------|------------------------------------------------
| sqlServerLogin                            | The name of the administrator account for the newly created Azure SQL server.
| sqlServerPassword                         | The password for the administrator account for Azure SQL server.
| speMsDeployPackageUrl                     | The HTTP(s) URL of a Sitecore Powershell Extensions Web Deploy package.

## Deploying as part of Sitecore deployment

In order to configure Sitecore deployment parameters to include Sitecore Powershell Extensions:

* Add the following snippet to the `modules` parameter:
```JSON
  {
    "name": "spe",
    "templateLink": "https://raw.githubusercontent.com/Sitecore/Sitecore-Azure-Quickstart-Templates/master/JSS/xp0/azuredeploy.json",
    "parameters":
    {
      "speMsDeployPackageUrl": "<URL of the WDP file for Sitecore Powershell Extensions *.scwdp>"
    }
  }
```

* Configure Bootloader module according to [MODULES.md](../../MODULES.md). 
> **Note**. The Bootloader module should be placed after the Sitecore Powershell Extensions module.
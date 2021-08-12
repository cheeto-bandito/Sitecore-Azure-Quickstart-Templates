# DEG Elision module for Sitecore XP Environment

This template deploys the DEG Elision module into a Sitecore XP Environment.

## Parameters for DEG Elision

The **deploymentId**  parameter is filled in by the PowerShell script.

| Parameter                                 | Description
--------------------------------------------|------------------------------------------------
| sqlServerLogin                            | The name of the administrator account for the newly created Azure SQL server.
| sqlServerPassword                         | The password for the administrator account for Azure SQL server.
| elisionMsDeployPackageUrl                     | The HTTP(s) URL of a DEG Elision Web Deploy package.
| elisionCDMsDeployPackageUrl                   | The HTTP(s) URL of a DEG Elision Web Deploy CD package.

## Deploying as part of Sitecore deployment

In order to configure Sitecore deployment parameters to include DEG Elision:

* Add the following snippet to the `modules` parameter:
```JSON
  {
    "name": "elision",
    "templateLink": "https://raw.githubusercontent.com/cheeto-bandito/Sitecore-Azure-Quickstart-Templates/master/Elision%2010.1.1/xp/azuredeploy.json",
    "parameters":
    {
      "jssMsDeployPackageUrl": "<URL of the WDP file for DEG Elision *.scwdp>",
      "jssCDMsDeployPackageUrl": "<URL of the CD WDP file for DEG Elision *.scwdp>"
    }
  }
```

* Configure Bootloader module according to [MODULES.md](../../MODULES.md). 
> **Note**. The Bootloader module should be placed after the DEG Elision module.
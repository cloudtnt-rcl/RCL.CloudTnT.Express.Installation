---
title: Microsoft Azure
description: Learn how to host the Credentials Web Wallet and Credentials Issuer in Microsoft Azure
parent: Hosting
has_children: false
nav_order: 1
---

# Hosting Web Applications in Microsoft Azure

In this section, you will learn how to host the Credentials Web Wallet and Credentials Issuer applications in Microsoft Azure.

## Hosting in a Microsoft Azure Web App

- It is recommended that the Web App use the NET 8 (LTS) framework in a Windows operating system 32 Bit (x86) platform.

- Download the application ``.zip`` file

    - [Credentials Web Wallet](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-webapp-v1-winx86.zip)
    - [Credentials Issuer](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/issuer-webapp-v1-winx86.zip)

- Install the ``.zip`` file in the web app following the instructions in the following link :

    - [Deploy with ZIP deploy UI in Kudu](https://learn.microsoft.com/en-us/azure/app-service/deploy-zip?tabs=cli#deploy-with-zip-deploy-ui-in-kudu)

{: .warning }
**Known Issues** : The Kudu completion indicator seems to be stuck at 50%. Wait a few minutes and refresh the page, the Kudu site can only display 300 files and will throw an error. However, the ``.zip`` file will be successfully uploaded despite this error.

{: .information }
If you try opening the application after installing the ``.zip`` file, you should get a **500 internal server error**. This will happen since the web app is not configured. You will learn how to configure the application in the configuration section. 
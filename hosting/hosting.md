---
title: Hosting
description: Learn how to host the Credentials Web Wallet and Credentials Issuer applications in a web browser.
has_children: true
nav_order: 3
---

# Web Application Hosting

The web applications are hosted in a web browser. The following hosting systems are supported :

- Cloud Hosting
- On-Premise Hosting
- Stand Alone Hosting

## Cloud Hosting

The Credentials Web Wallet and Credentials Issuer applications are built with the ASP.NET Core framework. The application is hosted in the cloud using the cloud provider's web application hosting services for ASP.NET Core applications.

## Hosting in a Microsoft Azure Web App

- It is recommended that the Web App use the NET 8 (LTS) framework in a Windows operating system 32 Bit (x86) platform.

- Download the application ``.zip`` files

    - [Credentials Web Wallet](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-webapp-v1.zip)
    - [Credentials Issuer]()

- Install the zip file in the web app following the instructions in the following link :

    - [Deploy with ZIP deploy UI in Kudu](https://learn.microsoft.com/en-us/azure/app-service/deploy-zip?tabs=cli#deploy-with-zip-deploy-ui-in-kudu)


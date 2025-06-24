---
title: Microsoft Azure
description: Learn how to host the Credentials Web Wallet and Credentials Issuer in a Linux Server
parent: Hosting
has_children: false
nav_order: 4
---

# Hosting Web Applications in Linux

In this section, you will learn how to host the Credentials Web Wallet and Credentials Issuer applications in Linux.

## Download and Extracting Application Files

- It is recommended that the application be hosted in a Linux operating system 64 Bit platform.

- Create a folder for your application files

```bash
> sudo mkdir /var/www
```

- Navigate to the folder

```bash
> cd /var/www
```

- Download and extract the application files to the folder

**Credential Web Wallet**
```bash
> wget -c https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-webapp-v1-linux64.tar.gz -O - | sudo tar -xz
```

**Credential Issuer**
```bash
> wget -c https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/issuer-webapp-v1-linux64.tar.gz -O - | sudo tar -xz 
```

## Creating a Service

The application will run as a service.

- Create the service definition file

**Credential Web Wallet**
```bash
> sudo nano /etc/systemd/system/cloudtnt-wallet.service
```

**Credential Issuer**
```bash
> sudo nano /etc/systemd/system/cloudtnt-issuer.service
```

- Add the content to the file

**Credential Web Wallet**
```bash
[Unit]
Description=Credential Web Wallet application service

[Service]
WorkingDirectory=/var/www/wallet-webapp-v1-linux64
ExecStart=/var/www/wallet-webapp-v1-linux64/RCL.CloudTnT.Express.WebApp.Wallet /var/www/wallet-webapp-v1-linux64/RCL.CloudTnT.Express.WebApp.Wallet.dll
Restart=always
RestartSec=10
KillSignal=SIGINT
SyslogIdentifier=cloudtnt-wallet
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=Production
Environment=DOTNET_NOLOGO=true
Environment=ASPNETCORE_URLS=http://127.0.0.1:5001

[Install]
WantedBy=multi-user.target
```

**Credential Issuer**
```bash
[Unit]
Description=Credential Issuer application service

[Service]
WorkingDirectory=/var/www/issuer-webapp-v1-linux64
ExecStart=/var/www/issuer-webapp-v1-linux64/RCL.CloudTnT.Express.WebApp.Issuer /var/www/issuer-webapp-v1-linux64/RCL.CloudTnT.Express.WebApp.Issuer.dll
Restart=always
RestartSec=10
KillSignal=SIGINT
SyslogIdentifier=cloudtnt-issuer
User=www-data
Environment=ASPNETCORE_ENVIRONMENT=Production
Environment=DOTNET_NOLOGO=true
Environment=ASPNETCORE_URLS=http://127.0.0.1:5002

[Install]
WantedBy=multi-user.target
```

- Save the file

- ``Enable``, ``Start`` and check the ``Status`` of the service

**Credential Web Wallet**
```bash
> sudo systemctl enable cloudtnt-wallet.service
> sudo systemctl start cloudtnt-wallet.service
> sudo systemctl status cloudtnt-wallet.service
```

**Credential Issuer**
```bash
> sudo systemctl enable issuer-wallet.service
> sudo systemctl start issuer-wallet.service
> sudo systemctl status issuer-wallet.service
```
- Ensure the service is running

- Navigate to the application at :

**Credential Web Wallet**
``http://localhost:5001``

**Credential Issuer**
``http://localhost:5002``

{: .information }
If you try viewing the service in a web browser, you should get a **500 internal server error**. This will happen since the web application is not configured. You will learn how to configure the application in the configuration section. 

## Using NGINX as a Reverse Proxy

You can use NGINX as a reverse proxy to host the web application.

- Install NGINX

```bash
> sudo apt install nginx
```

```bash
> sudo service nginx start
```

- Update NGINX configuration file

```bash
> sudo nano /etc/nginx/sites-available/default
```

**Credential Web Wallet**
```bash
server {
  listen        80;
  server_name   mywallet.com;
  location / {
      proxy_pass         http://127.0.0.1:5001/;
      proxy_http_version 1.1;
      proxy_set_header   Upgrade $http_upgrade;
      proxy_set_header   Connection $connection_upgrade;
      proxy_set_header   Host $host;
      proxy_cache_bypass $http_upgrade;
      proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
      proxy_set_header   X-Forwarded-Proto $scheme;
  }
}
```
**Credential Issuer**
```bash
server {
  listen        80;
  server_name   myissuer.com;
  location / {
      proxy_pass         http://127.0.0.1:5002/;
      proxy_http_version 1.1;
      proxy_set_header   Upgrade $http_upgrade;
      proxy_set_header   Connection $connection_upgrade;
      proxy_set_header   Host $host;
      proxy_cache_bypass $http_upgrade;
      proxy_set_header   X-Forwarded-For $proxy_add_x_forwarded_for;
      proxy_set_header   X-Forwarded-Proto $scheme;
  }
}
```

- Save the file

- Restart NGINX

```bash
> sudo service nginx restart
```
- View the site in a web browser


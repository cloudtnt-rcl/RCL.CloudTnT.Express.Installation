---
title: SQL Server
description: Set up a SQL Server database for the Credentials Web Wallet and Credentials Issuer applications.
parent: Database
has_children: false
nav_order: 1
---

# SQL Server

In this section you will learn how to set up a SQL Server database for the Credentials Web Wallet and Credentials Issuer applications. The database will be setup using a executable file. You can run the executable file either in a Windows or Linux environment.

# Windows

## Download 

- Download the executable files for creating the database tables

    - [Web Wallet Application Database Executable](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-sqlserver-v1-windows.exe)
    - [Issuer Application Database Executable](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/issuer-sqlserver-v1-windows.exe)

- Save the files to a folder on your computer, eg. ``c:/cloudtnt``

## Create the Database

In your database server, create separate databases for the applications and assign a name for the databases: eg. ``cloudtntwalletdb``, ``cloudtntissuerdb``

## Run the executable

- cd into the folder that you saved the executable file, example:

```bash
> cd c:/cloudtnt
```
Set the connection string property for your SQL Server database and run the executable using ``Powershell``:

### Example: Stand Alone PC (SQL Server Express)

**Credential Web Wallet** 
```bash
> .\wallet-sqlserver-v1-windows.exe --connection 'Data Source=YOURCOMPUTERNAME\SQLEXPRESS;Initial Catalog=cloudtntwalletdb;Integrated Security=True;Encrypt=False'
```
**Credential Issuer** 
```bash
> .\issuer-sqlserver-v1-windows.exe --connection 'Data Source=YOURCOMPUTERNAME\SQLEXPRESS;Initial Catalog=cloudtntissuerdb;Integrated Security=True;Encrypt=False'
```

### Example: Public Cloud (Azure SQL)
**Credential Web Wallet** 
```bash
> .\wallet-sqlserver-v1-windows.exe --connection 'Data Source=yoursqlserver.database.windows.net;Initial Catalog=cloudtntwalletdb;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```
**Credential Issuer** 
```bash
> .\issuer-sqlserver-v1-windows.exe --connection 'Data Source=yoursqlserver.database.windows.net;Initial Catalog=cloudtntissuerdb;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: Public Cloud (AWS RDS for SQL Server)
```bash
.\wallet-sqlserver-v1-windows.exe --connection 'Data yoursqlserver.dfrtehrder.us-east-1.rds.amazonaws.com;Initial Catalog=cloudtntwalletdb;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: Public Cloud (Google Cloud SQL for SQL Server)
```bash
.\wallet-sqlserver-v1-windows.exe --connection 'Data Source=34.56.75.195;Initial Catalog=cloudtntwalletdb;User ID=sqlserver;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: On-Premise (Microsoft SQL Server)
```bash
.\wallet-sqlserver-v1-windows.exe --connection 'Data Source=192.168.0.3;Initial Catalog=cloudtntwalletdb;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

# Linux

## Download 

- create a directory to store the binary file

```bash
> mkdir cloudtnt
```

- navigate to the directory

```bash
> cd cloudtnt
```

- Download the binary file for creating the database tables

```bash
wget -O walletdb "https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-sqlserver-v1-linux"
```

- Make the binary executable

```bash
> chmod +x walletdb
```

- Set the connection string property for your SQL Server database and run the executable :

### Example: Stand Alone (SQL Server Express)
```bash
> .\walletdb --connection 'Data Source=MYCOMPUTERNAME\SQLEXPRESS;Initial Catalog=cloudtntwalletdb;Integrated Security=True;Encrypt=False'
```

### Example: Public Cloud (Azure SQL)
```bash
> ./walletdb --connection 'Data Source=yoursqlserver.database.windows.net;Initial Catalog=cloudtntwalletdb;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=False;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```



---
title: SQL Server
description: Set up a SQL Server database for the Credentials Web Wallet and Credentials Issuer applications.
parent: Database
has_children: false
nav_order: 1
---

# SQL Server

In this section, you will learn how to set up a SQL Server database for the Credentials Web Wallet and Credentials Issuer applications. The database tables will be created using an executable file. You can run the executable file either in a Windows or Linux environment.

# Windows

## Download 

- Download the executable file for creating the database tables

    - [Credential Web Wallet Database Executable](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-sqlserver-v1-windows.exe)
    - [Credential Issuer Database Executable](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/issuer-sqlserver-v1-windows.exe)

- Save the file to a folder on your computer, eg. ``c:/cloudtnt``

## Create or use an existing database

In your SQL Server database server, use an existing database or create a new database to store the application's data.

## Run the executable file

- cd into the folder that you saved the executable file, example:

```bash
> cd c:/cloudtnt
```
Set the connection string property for your SQL Server database and run the executable using ``Powershell``:

### Example: Stand Alone PC (SQL Server Express)

**Credential Web Wallet**
```bash
> .\wallet-sqlserver-v1-windows.exe --connection 'Data Source=YOURCOMPUTERNAME\SQLEXPRESS;Initial Catalog=yourdatabase;Integrated Security=True;Encrypt=False'
```

**Credential Issuer**
```bash
> .\issuer-sqlserver-v1-windows.exe --connection 'Data Source=YOURCOMPUTERNAME\SQLEXPRESS;Initial Catalog=yourdatabase;Integrated Security=True;Encrypt=False'
```

### Example: Public Cloud (Azure SQL)

**Credential Web Wallet**
```bash
> .\wallet-sqlserver-v1-windows.exe --connection 'Data Source=yoursqlserver.database.windows.net;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

**Credential Issuer**
```bash
> .\issuer-sqlserver-v1-windows.exe --connection 'Data Source=yoursqlserver.database.windows.net;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: Public Cloud (AWS RDS for SQL Server)

**Credential Web Wallet**
```bash
.\wallet-sqlserver-v1-windows.exe --connection 'Data yoursqlserver.dfrtehrder.us-east-1.rds.amazonaws.com;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

**Credential Issuer**
```bash
.\issuer-sqlserver-v1-windows.exe --connection 'Data yoursqlserver.dfrtehrder.us-east-1.rds.amazonaws.com;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: Public Cloud (Google Cloud SQL for SQL Server)

**Credential Web Wallet**
```bash
.\wallet-sqlserver-v1-windows.exe --connection 'Data Source=34.56.75.195;Initial Catalog=yourdatabase;User ID=sqlserver;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

**Credential Issuer**
```bash
.\issuer-sqlserver-v1-windows.exe --connection 'Data Source=34.56.75.195;Initial Catalog=yourdatabase;User ID=sqlserver;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: On-Premise (Microsoft SQL Server)

**Credential Web Wallet**
```bash
.\wallet-sqlserver-v1-windows.exe --connection 'Data Source=192.168.0.3;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

**Credential Issuer**
```bash
.\issuer-sqlserver-v1-windows.exe --connection 'Data Source=192.168.0.3;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

# Linux

## Create or use an existing database

In your SQL Server database server, use an existing database or create a new database to store the application's data.

## Download the executable file

- create a directory to store the binary file

```bash
> mkdir cloudtnt
```

- navigate to the directory

```bash
> cd cloudtnt
```

- Download the binary file for creating the database tables

**Credential Web Wallet**
```bash
wget -O walletdb "https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-sqlserver-v1-linux"
```

**Credential Issuer**
```bash
wget -O issuerdb "https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/issuer-sqlserver-v1-linux"
```

## Run the executable file

- Make the binary executable

**Credential Web Wallet**
```bash
> chmod +x walletdb
```

**Credential Web Wallet**
```bash
> chmod +x issuerdb
```

- Set the connection string property for your SQL Server database and run the executable :

### Example: Stand Alone (SQL Server Express)

**Credential Web Wallet**
```bash
> .\walletdb --connection 'Data Source=MYCOMPUTERNAME\SQLEXPRESS;Initial Catalog=yourdatabase;Integrated Security=True;Encrypt=False'
```

**Credential Web Wallet**
```bash
> .\issuerdb --connection 'Data Source=MYCOMPUTERNAME\SQLEXPRESS;Initial Catalog=yourdatabase;Integrated Security=True;Encrypt=False'
```

### Example: Public Cloud (Azure SQL)

**Credential Web Wallet**
```bash
> ./walletdb --connection 'Data Source=yoursqlserver.database.windows.net;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=False;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

**Credential Issuer**
```bash
> ./issuerdb --connection 'Data Source=yoursqlserver.database.windows.net;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=False;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: Public Cloud (AWS RDS for SQL Server)

**Credential Web Wallet**
```bash
./walletdb --connection 'Data yoursqlserver.dfrtehrder.us-east-1.rds.amazonaws.com;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

**Credential Issuer**
```bash
./issuer --connection 'Data yoursqlserver.dfrtehrder.us-east-1.rds.amazonaws.com;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: Public Cloud (Google Cloud SQL for SQL Server)

**Credential Web Wallet**
```bash
./walletdb --connection 'Data Source=34.56.75.195;Initial Catalog=yourdatabase;User ID=sqlserver;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

**Credential Issuer**
```bash
./issuerdb --connection 'Data Source=34.56.75.195;Initial Catalog=yourdatabase;User ID=sqlserver;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

### Example: On-Premise (Microsoft SQL Server)

**Credential Web Wallet**
```bash
./walletdb --connection 'Data Source=192.168.0.3;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```

**Credential Issuer**
```bash
./issuerdb --connection 'Data Source=192.168.0.3;Initial Catalog=yourdatabase;User ID=yourusername;Password=yourpassword;Connect Timeout=60;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False'
```


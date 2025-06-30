---
title: PostgreSQL
description: Set up a PostgreSQL database for the Credentials Web Wallet and Credentials Issuer applications.
parent: Database
has_children: false
nav_order: 2
---

# PostgreSQL

In this section, you will learn how to set up a PostgreSQL database for the Credentials Web Wallet and Credentials Issuer applications. The database tables will be created using an executable file. You can run the executable file either in a Windows or Linux environment.

# Windows

## Download the executable file

- Download the executable file for creating the database tables

    - [Credential Web Wallet Database Executable](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-postgres-v1-windows.exe)
    - [Credential Issuer Database Executable](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/issuer-postgres-v1-windows.exe)

- Save the file to a folder on your computer, eg. ``c:/cloudtnt``

## Create or use an existing database

In your PostgreSQL database server, use an existing database or create a new database to store the application's data.

## Run the executable file

- cd into the folder that you saved the executable file, example:

```bash
> cd c:/cloudtnt
```
Set the connection string property for your PostgreSQL database and run the executable using ``Powershell``:

### Example: On-Premise (PostgreSQL)

**Credential Web Wallet**
```bash
.\wallet-sqlserver-v1-windows.exe --connection 'Host=192.168.0.70;Port=5432;Password=yourpassword;Persist Security Info=True;Username=yourusername;Database=yourdatabase'
```

**Credential Issuer**
```bash
.\issuer-sqlserver-v1-windows.exe --connection ''
```

### Example: Public Cloud (Azure PostgreSQL)

**Credential Web Wallet**
```bash
.\wallet-sqlserver-v1-windows.exe --connection ''
```

**Credential Issuer**
```bash
.\issuer-sqlserver-v1-windows.exe --connection ''
```

### Example: Public Cloud (AWS RDS for PostgreSQL)

**Credential Web Wallet**
```bash
.\wallet-sqlserver-v1-windows.exe --connection ''
```

**Credential Issuer**
```bash
.\issuer-sqlserver-v1-windows.exe --connection ''
```

### Example: Public Cloud (Google Cloud SQL for PostgreSQL)

**Credential Web Wallet**
```bash
.\wallet-sqlserver-v1-windows.exe --connection ''
```

**Credential Issuer**
```bash
.\issuer-sqlserver-v1-windows.exe --connection ''
```

# Linux

## Create or use an existing database

In your PostgreSQL database server, use an existing database or create a new database to store the application's data.

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
wget -O walletdb "https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/wallet-postgres-v1-linux"
```

**Credential Issuer**
```bash
wget -O issuerdb "https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/issuer-postgres-v1-linux"
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

### Example: On-Premise (PostgreSQL)

**Credential Web Wallet**
```bash
./walletdb --connection 'Host=192.168.0.70;Port=5432;Password=yourpassword;Persist Security Info=True;Username=yourusername;Database=yourdatabase'
```

**Credential Issuer**
```bash
./issuerdb --connection 'Host=192.168.0.70;Port=5432;Password=yourpassword;Persist Security Info=True;Username=yourusername;Database=yourdatabase'
```

### Example: Public Cloud (Azure SQL)

**Credential Web Wallet**
```bash
> ./walletdb --connection ''
```

**Credential Issuer**
```bash
> ./issuerdb --connection ''
```

### Example: Public Cloud (AWS RDS for PostgreSQL)

**Credential Web Wallet**
```bash
./walletdb --connection ''
```

**Credential Issuer**
```bash
./issuer --connection ''
```

### Example: Public Cloud (Google Cloud SQL for PostgreSQL)

**Credential Web Wallet**
```bash
./walletdb --connection ''
```

**Credential Issuer**
```bash
./issuerdb --connection ''
```
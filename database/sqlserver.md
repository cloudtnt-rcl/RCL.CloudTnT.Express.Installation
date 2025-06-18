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

Download the executable files for creating the database tables.

- [Web Wallet Application Database Executable](https://github.com/cloudtnt-rcl/RCL.CloudTnT.Express.Deployment/releases/download/V1.0/efbundle-sqlserver-v1-windows.exe)
- [Issuer Application Database Executable]()

## Create the Database

In your database server, create separate databases for the applications and assign a name for the databases: eg. ``cloudtntwalletdb``, ``cloudtntissuerdb``.

## Run the executable

Set the connection string property and run the executable using ``Powershell``

### Example: Stand Alone PC (SQL Server Express)
```bash
.\efbundle-sqlserver-v1-windows.exe --connection 'Data Source=.\\SQLEXPRESS;Initial Catalog=cloudtntwalletdb;Integrated Security=True;Encrypt=False'
```
### Example: Public Cloud (Azure SQL)

### Example: Public Cloud (AWS RDS for SQL Server)

### Example: Public Cloud (Google Cloud SQL for SQL Server)

### Example: On-Premise (Microsoft SQL Server)

# Linux


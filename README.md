# Azure Database Migration - Project

## Table of Contents
- [Project Overview](#project-overview)
- [1 - Create the Production Environment](#1---create-the-production-environment)
- [2 - Migrate to Azure SQL Database](#2---migrate-to-azure-sql-database)
- [3 - Backup & Restore Data](#3---backup--restore-data)
- [4 - Disaster Recovery Simulation](#4---disaster-recovery-simulation)
- [5 - Geo-Replication & Failover](#5---geo-replication--failover)
- [6 - Microsoft Entra Directory Integration](#6---microsoft-entra-directory-integration)
- [Future Improvements & Lessons Learnt](#future-improvements--lessons-learnt)
- [License](#license)

## Project Overview
:cloud: This project showcases how to architect and implement a cloud-based database system on Microsoft Azure.

:card_file_box: The first phase of the project focuses on: (1) the provision of a production environment via a Windows Virtual Machine (VM); (2) the creation of an Azure SQL database and corresponding database schema; and (3) ensuring that the data is securely stored by backing up the data, creating a development database, and establishing a Management Task that automates regular backups.

:exclamation: The second phase of the project focuses on: (4) mimicing data loss and restoring the development databse; (5) the creation of a synchronised replica of the primary database, simulating a failover to this replica, and then a failback to the primary region; and (6) enabling Microsoft Entra ID authentication for the production database and creating a DB Reader User.

## 1 - Create the Production Environment
- First, the project requires the provision of a Microsoft VM on [Azure](https://portal.azure.com/) - making sure that the image selected is Windows 11 Pro, and that the Remote Desktop Protocol (RDP) is enabled. Once the VM is created, an RDP file can be downloaded on the VM resource page on Azure and used to connect to the VM.

- In order to do this, make sure to download the [Microsoft Remote Desktop](https://apps.microsoft.com/detail/9wzdncrfj3ps?hl=en-US&gl=US) application first, and then double-click the RDP file and fill out the necessary admin name & password that would have been configured during the provision of the VM.
  
- After connecting to the VM, download Microsoft's [SQL Server Developer](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) and [SQL Server Management Studio (SSMS)](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16) as these will be necessary for the subsequent tasks.

- Download the newest version of the [AdventureWorks](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms#download-backup-files) sample database and then use [SSMS to restore the database](https://learn.microsoft.com/en-us/sql/relational-databases/backup-restore/quickstart-backup-restore-database?view=sql-server-ver16&tabs=ssms).

## 2 - Migrate to Azure SQL Database
- Create an SQL database on [Azure](https://portal.azure.com/) and a corresponding SQL server that uses an SQL authentication system - this will be the target database. After the SQL database has been created, make sure to populate the firewall rules with the VM IP address.

- Now, in order to connect the VM to the target database, first download [Azure Data Studio](https://learn.microsoft.com/en-us/azure-data-studio/download-azure-data-studio?tabs=win-install%2Cwin-user-install%2Credhat-install%2Cwindows-uninstall%2Credhat-uninstall). Then launch it and create a connection to the locally stored AdventureWorks sample database, as well as to the newly created SQL database on Azure. Make sure to choose *True* for the Trust Server Certificate when doing this so that the connection is encrypted and secure.

## 3 - Backup & Restore Data

## 4 - Disaster Recovery Simulation

## 5 - Geo-Replication & Failover

## 6 - Microsoft Entra Directory Integration

## Future Improvements & Lessons Learnt

## License


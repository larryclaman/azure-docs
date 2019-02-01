---
title: Quickstart - single databases in Azure SQL Database | Microsoft Docs
description: 'Learn how to quickly get started with single databases in Azure SQL Database'
services: sql-database
ms.service: sql-database
ms.subservice: single-database
ms.custom: 
ms.devlang: 
ms.topic: quickstart
author: jovanpop-msft
ms.author: jovanpop
ms.reviewer: carlr
manager: craigg
ms.date: 01/25/2019
---
# Getting started with single databases in Azure SQL Database

[A single database](sql-database-single-index.yml) in Azure SQL Database is fully managed PaaS database as a service (DbaaS) that is ideal storage engine for the modern cloud-born applications. In this section, you will learn how to quickly configure and create SQL Database.

## Quickstart overview

In this section, you will see an overview of available articles that can help you to quickly get started with single databases. The easiest way to create your first SQL Database is to use [the Azure portal](sql-database-get-started-portal.md) where you can configure necessary parameters.
After creation, you would need to [secure your database by configuring firewall rules](sql-database-get-started-portal-firewall.md). 

If you have an existing database on SQL Server that you want to migrate to Azure, you should install [Data Migration Assistant (DMA)](https://www.microsoft.com/download/details.aspx?id=53595) that will analyze your databases on SQL Server and find any issue that could block migration to Singe Database. If you don't find any issue, you can export your database as `.bacpac` file and [import it using the Azure portal or SqlPackage](sql-database-import.md).

These quickstarts enable you to quickly configure, create, and import your databases in Azure cloud.

## Automating management operations

The Azure portal enables you to easily create and modify your single database. As an alternative you can use [PowerShell](scripts/sql-database-create-and-configure-database-powershell.md), or [Azure CLI](scripts/sql-database-create-and-configure-database-cli.md) to create databases.
 You can also update your single database and scale resources using [PowerShell](scripts/sql-database-monitor-and-scale-database-powershell.md) or [Azure CLI](scripts/sql-database-monitor-and-scale-database-cli.md).

## Migrating to a single database with minimal downtime

Articles in these quickstarts enable you to quickly create or import your database to Azure using `.bacpac`. However, `.bacpac` and `.dacpack` files are designed to quickly move database across different versions of SQL Server and Azure SQL Database (single database, elastic pool, or Managed Instance) or to implement continuous integration in your DevOps pipeline. However, this method is not designed for migration of your production databases with minimal downtime, because you would need to wait to export the source database as `.bacpac` file and import it into Azure SQL Database, which would cause some downtime of your application especially if the database is bigger. If you are moving your production database, you would probably need a better way to migrate that will guarantee minimal downtime of migration. [Data Migration Service](https://docs.microsoft.com/azure/dms/tutorial-sql-server-to-azure-sql?toc=/azure/sql-database/toc.json) is a service that can migrate your database with the minimal downtime. This way, you can quickly switch your application from source to target database with the minimal downtime.

## Next steps

* Find a [high-level list of supported features in Azure SQL Database](sql-database-features.md). 
* Learn how to make your [database more secure](sql-database-security-tutorial.md). 
* Find more advanced tutorials in [how to section](sql-database-howto-single-database.md). 
* Find more sample scripts written in [PowerShell](sql-database-powershell-samples.md) and [Azure CLI](sql-database-cli-samples.md). 
* Learn more about the [Management API](sql-database-single-databases-manage.md) that you can use to configure your databases. 

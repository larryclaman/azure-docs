---
title: General Purpose tier - Azure SQL Database service | Microsoft Docs
description: Learn about the Azure SQL Database General Purpose tier
services: sql-database
ms.service: sql-database
ms.subservice: service
ms.custom: 
ms.devlang: 
ms.topic: conceptual
author: jovanpop-msft
ms.author: jovanpop-msft
ms.reviewer: carlrab
manager: craigg
ms.date: 12/04/2018
---
# General Purpose tier - Azure SQL Database

> [!NOTE]
> General Purpose tier is called Standard in DTU purchasing model. For a comparison of the vCore-based purchasing model with the DTU-based purchasing model, see [Azure SQL Database purchasing models and resources](sql-database-service-tiers.md).

Azure SQL Database is based on SQL Server Database Engine architecture adapted for the cloud environment in order to ensure 99.99% availability even in the cases of infrastructure failures. There are three architectural models that are used in Azure SQL Database:
- General Purpose 
- Business Critical
- Hyperscale

General Purpose model is based on a separation of compute and storage. This architectural model relies on high availability and reliability of Azure Premium Storage that transparently replicates database files and guarantees no data loss if underlying infrastructure failure happens.

The following figure shows four nodes in standard architectural model with the separated compute and storage layers.

![Separation of compute and storage](media/sql-database-managed-instance/general-purpose-service-tier.png)

In the General Purpose model there are two layers:

- A stateless compute layer that is running the `sqlserver.exe` process and contains only transient and cached data (for example – plan cache, buffer pool, column store pool). This stateless SQL Server node is operated by Azure Service Fabric that initializes process, controls health of the node, and performs failover to another place if necessary.
- A stateful data layer with database files (.mdf/.ldf) that are stored in Azure Premium Storage. Azure Storage guarantees that there will be no data loss of any record that is placed in any database file. Azure Storage has built-in data availability/redundancy that ensures that every record in log file or page in data file will be preserved even if SQL Server process crashes.

Whenever database engine or operating system is upgraded, some part of underlying infrastructure fails, or if some critical issue is detected in SQL Server process, Azure Service Fabric will move the stateless SQL Server process to another stateless compute node. There is a set of spare nodes that is waiting to run new compute service if a failover of the primary node happens in order to minimize failover time. Data in Azure Storage layer is not affected, and data/log files are attached to newly initialized SQL Server process. This process guarantees 99.99% availability, but it might have some performance impacts on heavy workload that is running due to transition time and the fact the new SQL Server node starts with cold cache.

## When to choose this service tier?

General Purpose service tier is a default service tier in Azure SQL Database that is designed for most of the generic workloads. If you need a fully managed database engine with 99.99% SLA with storage latency between 5 and 10 ms that matches Azure SQL IaaS in most of the cases, General Purpose tier is the option for you.

## Next steps

- Learn about [Business Critical](sql-database-service-tier-business-critical.md) and [Hyperscale](sql-database-service-tier-hyperscale.md) tiers.
- Learn about [Service Fabric](../service-fabric/service-fabric-overview.md).
- For more options for high availability and disaster recovery, see [Business Continuity](sql-database-business-continuity.md).

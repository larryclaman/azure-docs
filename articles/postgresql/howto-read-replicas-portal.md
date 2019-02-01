---
title: Manage read replicas in Azure portal for Azure Database for PostgreSQL
description: This article describes managing Azure Database for PostgreSQL read replicas in Azure portal.
author: rachel-msft
ms.author: raagyema
ms.service: postgresql
ms.topic: conceptual
ms.date: 01/23/2019
---

# How to create and manage read replicas in the Azure portal

> [!IMPORTANT]
> The read replica feature is in Public Preview.


In this article, you will learn how to create and manage read replicas in the Azure Database for PostgreSQL service using the Azure portal. To learn more about read replicas, [read the concepts documentation](concepts-read-replicas.md).

## Prerequisites
- An [Azure Database for PostgreSQL server](quickstart-create-server-database-portal.md) that will be the master server.

## Prepare the master server
This master preparation step applies to General Purpose and Memory Optimized servers only.

The **azure.replication_support** parameter must be set to REPLICA on the master server. Changing this parameter requires a server restart to take effect.

1. In the Azure portal, select the existing Azure Database for PostgreSQL server that you want to use as a master.

2. Select **Server Parameters** from the menu on the left.

3. Search for **azure.replication_support**.

   ![Azure Database for PostgreSQL - azure.replication_support](./media/howto-read-replicas-portal/azure-replication-parameter.png)

4. Set **azure.replication_support** to REPLICA. **Save** the change.

   ![Azure Database for PostgreSQL - REPLICA and save](./media/howto-read-replicas-portal/save-parameter-replica.png)

5. Once saving is complete, you will receive a notification.

   ![Azure Database for PostgreSQL - Save notification](./media/howto-read-replicas-portal/parameter-save-notification.png)

6. Restart the server to apply the change after it is saved. See [the restart documentation](howto-restart-server-portal.md) to learn how to restart a server.


## Create a read replica
Read replicas can be created using the following steps:
1.	Select the existing Azure Database for PostgreSQL server that you want to use as a master. 

2.	Select Replication from the menu, under SETTINGS.

   If you haven't set **azure.replication_support** to REPLICA on the General Purpose or Memory Optimized master and restarted the server, you will see a message instructing you to do so. Do so before proceeding with the create.

3.	Select Add Replica.

   ![Azure Database for PostgreSQL - Add replica](./media/howto-read-replicas-portal/add-replica.png)

4.	Enter a name for the replica server and select OK to confirm the creation of the replica.

   ![Azure Database for PostgreSQL - Name replica](./media/howto-read-replicas-portal/name-replica.png) 

> [!IMPORTANT]
> Read replicas are created with the same server configuration as the master. After a replica has been created, the pricing tier (except to and from Basic), compute generation, vCores, storage, and backup retention period can be changed independently from the master server.

> [!IMPORTANT]
> Before a master's server configuration is updated to new values, the replicas' configuration should be updated to equal or greater values. Attempting to do otherwise will cause an error. This ensures that the replicas are able to keep up with changes made to the master. 


Once the replica server has been created, it can be viewed from the Replication window.

![Azure Database for PostgreSQL - New replica](./media/howto-read-replicas-portal/list-replica.png)
 

## Stop replication

> [!IMPORTANT]
> Stopping replication to a server is irreversible. Once replication has stopped between a master and replica, it cannot be undone. The replica server then becomes a standalone server and now supports both read and writes. This server cannot be made into a replica again.

To stop replication between a master and a replica from the Azure portal, use the following steps:
1.	In the Azure portal, select your master Azure Database for PostgreSQL server.

2.	Select Replication from the menu, under SETTINGS.

3.	Select the replica server you wish to stop replication for.

   ![Azure Database for PostgreSQL - Select replica](./media/howto-read-replicas-portal/select-replica.png)
 
4.	Select Stop replication.

   ![Azure Database for PostgreSQL - Select stop replication](./media/howto-read-replicas-portal/select-stop-replication.png)
 
5.	Confirm you want to stop replication by clicking OK.

   ![Azure Database for PostgreSQL - Confirm stop replication](./media/howto-read-replicas-portal/confirm-stop-replication.png)
 

## Delete a master

> [!IMPORTANT]
> Deleting a master server stops replication to all replica servers. Replica servers become standalone servers that now support both read and writes.
Deleting a master follows the same steps as for a standalone Azure Database for PostgreSQL server. To delete a server from the Azure portal, do the following:

1.	In the Azure portal, select your master Azure Database for PostgreSQL server.

2.	From the Overview, select Delete.

   ![Azure Database for PostgreSQL - Delete server](./media/howto-read-replicas-portal/delete-server.png)
 
3.	Type the name of the master server and select Delete to confirm deletion of the master server.

   ![Azure Database for PostgreSQL - Confirm delete](./media/howto-read-replicas-portal/confirm-delete.png)
 

## Delete a replica
To delete a read replica you, can follow the same steps as with deleting a master server above. First open the Overview page of the replica then select Delete.

   ![Azure Database for PostgreSQL - Delete replica](./media/howto-read-replicas-portal/delete-replica.png)
 
Alternatively, you can delete it from the Replication window.
1.	In the Azure portal, select your master Azure Database for PostgreSQL server.

2.	Select Replication from the menu, under SETTINGS.

3.	Select the replica server you wish to delete. 

   ![Azure Database for PostgreSQL - Select replica](./media/howto-read-replicas-portal/select-replica.png)
 
4.	Select Delete replica.

   ![Azure Database for PostgreSQL - Select delete replica](./media/howto-read-replicas-portal/select-delete-replica.png)
 
5.	Type the name of the replica and select Delete to confirm deletion of the replica.

   ![Azure Database for PostgreSQL - Confirm delete replica](./media/howto-read-replicas-portal/confirm-delete-replica.png)
 

## Monitor a replica
### Max Lag Across Replicas
The **Max lag across replicas** metric shows the lag time between the master and the most lagging replica. 

1.	In the Azure portal, select the **master** Azure Database for PostgreSQL server.

2.	Select Metrics. In the metrics window, select **Max Lag Across Replicas**.

    ![Azure Database for PostgreSQL - Monitor max lag across replicas](./media/howto-read-replicas-portal/select-max-lag.png)
 
3.	Select **Max** as your Aggregation. 

### Replica Lag
The **Replica Lag** metric shows the time since the last replayed transaction on this replica. If there are no transactions occurring on your master, the metric reflects this time lag.

1.	In the Azure portal, select a **replica** Azure Database for PostgreSQL server.

2.	Select Metrics. In the metrics window, select **Replica Lag**.

   ![Azure Database for PostgreSQL - Monitor replica lag](./media/howto-read-replicas-portal/select-replica-lag.png)
 
3.	Select **Max** as your Aggregation. 
 
## Next steps
- Learn more about [read replicas in Azure Database for PostgreSQL](concepts-read-replicas.md).
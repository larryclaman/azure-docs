---
title: Azure Instant Restore Capability
description: Azure Instant Restore Capability and FAQs for VM backup stack, Resource Manager deployment model
services: backup
author: sogup
manager: vijayts
ms.service: backup
ms.topic: conceptual
ms.date: 01/10/2019
ms.author: sogup
---

# Get improved backup and restore performance with Azure Backup Instant Restore capability

> [!NOTE]
> Based on feedback from users we are renaming **VM backup stack V2** to **Instant Restore** to reduce confusion with Azure Stack functionality.

The new model for Instant Restore provides the following feature enhancements:

* Ability to use snapshots taken as part of a backup job that is available for recovery without waiting for data transfer to the vault to finish. It reduces the wait time for snapshots to copy to the vault before triggering restore.
* Reduces backup and restore times by retaining snapshots along with the disk(s) for seven days.
* Supports disk sizes up to 4 TB.
* Supports Standard SSD disks.
* Ability to use an unmanaged VM's original storage accounts (per disk), when restoring. This ability exists even when the VM has disks that are distributed across storage accounts. It speeds up restore operations for a wide variety of VM configurations.


## What's new in this feature

Currently, the backup job consists of two phases:

1.	Taking a VM snapshot.
2.	Transferring a VM snapshot to the Azure Recovery Services vault.

A recovery point is considered created only after phases 1 and 2 are completed. As a part of this upgrade, a recovery point is created as soon as the snapshot is finished and this recovery point of snapshot type can be used to perform a restore using the same restore flow. You can identify this recovery point in the Azure portal by using “snapshot” as the recovery point type, and after the snapshot is transferred to the vault, the recovery point type changes to “snapshot and vault.”

![Backup job in VM backup stack Resource Manager deployment model--storage and vault](./media/backup-azure-vms/instant-rp-flow.png)

Snapshots are retained for seven days. This feature allows restores operation from these snapshots there by cutting down the restore times. It reduces the time that is required to transform and copy data back from the vault to the user's storage account for unmanaged disk scenarios while for managed disk users, it creates managed disks out of the backup data.

## Feature considerations

* Snapshots are stored along with the disks to boost recovery point creation and to speed up restore operations. As a result, you'll see storage costs that correspond to snapshots taken during this period.
* Incremental snapshots are stored as page blobs. All the users using unmanaged disks are charged for the snapshots stored in their local storage account. Since the restore point collections used by Managed VM backups use blob snapshots at the underlying storage level, for managed disks you will see costs corresponding to blob snapshot pricing and they are incremental.
* For premium storage accounts, the snapshots taken for instant recovery points count towards the 10-TB limit of allocated space.

## Cost impact

The incremental snapshots are stored in VM’s storage account, which are used for instant recovery. Incremental snapshot means the space occupied by a snapshot is equal to the space occupied by pages that are written after the snapshot was created. Billing is still for the per GB used space occupied by the snapshot and the price per GB is same as mentioned in the [pricing page](https://azure.microsoft.com/pricing/details/managed-disks/).


## Upgrading to Instant Restore

If you use the Azure portal, you will see a notification on the vault dashboard. This notification relates to large-disk support and backup and restore speed improvements.

![Backup job in VM backup stack Resource Manager deployment model--support notification](./media/backup-azure-vms/instant-rp-banner.png)

To open a screen for upgrading to Instant Restore, select the banner.

![Backup job in VM backup stack Resource Manager deployment model--upgrade](./media/backup-azure-vms/instant-rp.png)

Alternatively you can go to **Properties** page of the vault to get the **Upgrade** option under **VM backup stack**.

![Backup job in VM backup stack -- Properties page](./media/backup-azure-vms/instant-restore-capability-properties.png)


## Upgrade to Instant Restore using PowerShell

If you wish to self-serve and upgrade to Instant Restore, run the following cmdlets from an elevated PowerShell terminal:

1.	Sign in to your Azure account:

    ```
    PS C:> Connect-AzureRmAccount
    ```

2.	Select the subscription that you want to register:

    ```
    PS C:>  Get-AzureRmSubscription –SubscriptionName "Subscription Name" | Select-AzureRmSubscription
    ```

3.	Register this subscription:

    ```
    PS C:>  Register-AzureRmProviderFeature -FeatureName "InstantBackupandRecovery" –ProviderNamespace Microsoft.RecoveryServices
    ```

## Upgrade to Instant Restore using CLI

Run the following commands from a shell:

1.	Sign in to your Azure account:

    ```
    az login
    ```

2.	Select the subscription that you want to register:

    ```
    az account set --subscription "Subscription Name"
    ```

3.	Register this subscription:

    ```
    az feature register --namespace Microsoft.RecoveryServices --name InstantBackupandRecovery
    ```

## Verify that the upgrade is successful

### PowerShell
From an elevated PowerShell terminal, run the following cmdlet:

```
Get-AzureRmProviderFeature -FeatureName "InstantBackupandRecovery" -ProviderNamespace Microsoft.RecoveryServices
```

### CLI
From a shell, run the following command:

```
az feature show --namespace Microsoft.RecoveryServices --name InstantBackupandRecovery
```

If it says "Registered," then your subscription is upgraded to Instant Restore.

## Frequently asked questions

### What are the cost implications of Instant restore?
Snapshots are stored along with the disks to speed up recovery point creation and restore operations. As a result, you'll see storage costs that correspond to the snapshot retention selected as a part of VM backup policy.

### In Premium Storage accounts, do the snapshots taken for instant recovery point occupy the 10-TB snapshot limit?
Yes, for premium storage accounts the snapshots taken for instant recovery point occupy 10-TB of allocated snapshot space.

### How does the snapshot retention work during the five-day period?
Each day a new snapshot is taken, then there are five individual incremental snapshots. The size of the snapshot depends on the data churn, which is in most cases around 2%-7%.

### Is an instant restore snapshot an incremental snapshot or full snapshot?
Snapshots taken as a part of instant restore capability are incremental snapshots.

### How can I calculate the approximate cost increase due to instant restore feature?
It depends on the churn of the VM. In a steady state, you can assume the increase in cost is = Snapshot retention period * daily churn per VM * storage cost per GB.

### If the recovery type for a restore point is “Snapshot and vault” and I perform a restore operation, which recovery type will be used?
If the recovery type is “snapshot and vault”, restore will be automatically done from the local snapshot, which will be much faster compared to the restore done from the vault.

### What happens if I select retention period of restore point (Tier 2) less than the snapshot (Tier1) retention period?
The new model does not allow deleting the restore point (Tier2) unless the snapshot (Tier1) is deleted. Currently we support seven days retention period for snapshot (Tier1) deletion, so the restore point (Tier2) retention period for less than seven days is not honored. We recommend scheduling restore point (Tier2) retention period greater than seven days.

### Why is my snapshot existing even after the set retention period in backup policy?
If the recovery point has snapshot and that is the latest RP available, it is retained until the time there is a next successful backup. This is as per the designed GC policy today that mandates at least one latest RP to be always present in case all backups further on fail due to an issue in the VM. In normal scenarios, RPs are cleaned up in maximum of 48 hours after their expiry.

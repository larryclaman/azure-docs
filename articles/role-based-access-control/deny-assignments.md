---
title: Understand deny assignments in Azure RBAC | Microsoft Docs
description: Learn about deny assignments in role-based access control (RBAC) for resources in Azure.
services: active-directory
documentationcenter: ''
author: rolyon
manager: mtillman

ms.assetid: 
ms.service: role-based-access-control
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: identity
ms.date: 11/30/2018
ms.author: rolyon
ms.reviewer: bagovind
ms.custom: 
---
# Understand deny assignments

Similar to a role assignment, a *deny assignment* attaches a set of deny actions to a user, group, or service principal at a particular scope for the purpose of denying access. Deny assignments block users from performing specific actions even if a role assignment grants them access. Some resource providers in Azure now include deny assignments. Currently, deny assignments are **read-only** and can only be set by Azure.

In some ways, deny assignments are different than role assignments. Deny assignments can exclude principals and prevent inheritance to child scopes. Deny assignments also apply to [classic subscription administrator](rbac-and-directory-admin-roles.md) assignments.

This article describes how deny assignments are defined.

## Deny assignment properties

 A deny assignment has the following properties:

> [!div class="mx-tableFixed"]
> | Property | Required | Type | Description |
> | --- | --- | --- | --- |
> | `DenyAssignmentName` | Yes | String | The display name of the deny assignment. Names must be unique for a given scope. |
> | `Description` | No | String | The description of the deny assignment. |
> | `Permissions.Actions` | At least one Actions or one DataActions | String[] | An array of strings that specify the management operations to which the deny assignment blocks access. |
> | `Permissions.NotActions` | No | String[] | An array of strings that specify the management operations to exclude from the deny assignment. |
> | `Permissions.DataActions` | At least one Actions or one DataActions | String[] | An array of strings that specify the data operations to which the deny assignment blocks access. |
> | `Permissions.NotDataActions` | No | String[] | An array of strings that specify the data operations to exclude from the deny assignment. |
> | `Scope` | No | String | A string that specifies the scope that the deny assignment applies to. |
> | `DoNotApplyToChildScopes` | No | Boolean | Specifies whether the deny assignment applies to child scopes. Default value is false. |
> | `Principals[i].Id` | Yes | String[] | An array of Azure AD principal object IDs (user, group, service principal, or managed identity) to which the deny assignment applies. Set to an empty GUID `00000000-0000-0000-0000-000000000000` to represent all principals. |
> | `Principals[i].Type` | No | String[] | An array of object types represented by Principals[i].Id. Set to `SystemDefined` to represent all principals. |
> | `ExcludePrincipals[i].Id` | No | String[] | An array of Azure AD principal object IDs (user, group, service principal, or managed identity) to which the deny assignment does not apply. |
> | `ExcludePrincipals[i].Type` | No | String[] | An array of object types represented by ExcludePrincipals[i].Id. |
> | `IsSystemProtected` | No | Boolean | Specifies whether this deny assignment was created by Azure and cannot be edited or deleted. Currently, all deny assignments are system protected. |

## System-Defined Principal

To support deny assignments, the **System-Defined Principal** has been introduced. This principal represents all users, groups, service principals, and managed identities in an Azure AD directory. If the principal ID is a zero GUID `00000000-0000-0000-0000-000000000000` and the principal type is `SystemDefined`, the principal represents all principals. `SystemDefined` can be combined with `ExcludePrincipals` to deny all principals except some users. `SystemDefined` has the following constraints:

- Can be used only in `Principals` and cannot be used in `ExcludePrincipals`.
- `Principals[i].Type` must be set to `SystemDefined`.

## Next steps

* [List deny assignments using RBAC and the REST API](deny-assignments-rest.md)
* [Understand role definitions](role-definitions.md)

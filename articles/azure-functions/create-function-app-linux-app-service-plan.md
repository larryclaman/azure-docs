---
title: Create a function app on Linux in an Azure App Service plan 
description: Learn how to create a function app that runs on Linux in an App Service plan using the Azure CLI.
services: functions 
keywords: 
author: ggailey777
ms.author: glenga
ms.date: 11/28/2018
ms.topic: conceptual
ms.service: azure-functions
ms.custom: mvc
ms.devlang: azure-cli
manager: jeconnoc
---

# Create a function app on Linux in an Azure App Service plan (preview)

Azure Functions lets you host your functions on Linux in a default Azure App Service container. This article walks you through how to use the Azure CLI to create a Linux-hosted function app in Azure that runs in an [App Service plan](functions-scale.md#app-service-plan). You can also [bring your own custom container](functions-create-function-linux-custom-image.md). Linux hosting is currently in preview.

In an App Service plan, you are responsible for scaling your function app. To take advantage of the serverless capabilities of Azure Functions, you can also host your functions on Linux in a [Consumption plan](functions-scale.md#consumption-plan).

You can follow the steps below using a Mac, Windows, or Linux computer.

## Prerequisites

To complete this quickstart, you need:

+ An active Azure subscription.

[!INCLUDE [quickstarts-free-trial-note](../../includes/quickstarts-free-trial-note.md)]

[!INCLUDE [cloud-shell-try-it.md](../../includes/cloud-shell-try-it.md)]

If you choose to install and use the CLI locally, this topic requires the Azure CLI version 2.0.21 or later. Run `az --version` to find the version you have. If you need to install or upgrade, see [Install Azure CLI 2.0]( /cli/azure/install-azure-cli). 

[!INCLUDE [functions-create-resource-group](../../includes/functions-create-resource-group.md)]

[!INCLUDE [functions-create-storage-account](../../includes/functions-create-storage-account.md)]

## Create a Linux App Service plan

[!INCLUDE [app-service-plan-no-h](../../includes/app-service-web-create-app-service-plan-linux-no-h.md)]

## Create a function app on Linux

You must have a function app to host the execution of your functions on Linux. The function app provides an environment for execution of your function code. It lets you group functions as a logic unit for easier management, deployment, and sharing of resources. Create a function app by using the [az functionapp create](/cli/azure/functionapp#az-functionapp-create) command with a Linux App Service plan.

In the following command, substitute a unique function app name where you see the `<app_name>` placeholder and the storage account name for  `<storage_name>`. The `<app_name>` is used as the default DNS domain for the function app, and so the name needs to be unique across all apps in Azure. You should also set the `<language>` runtime for your function app, from `dotnet` (C#), `node` (JavaScript), or `python`.

```azurecli-interactive
az functionapp create --resource-group myResourceGroup --plan myAppServicePlan \
--name <app_name> --storage-account  <storage_name> --runtime <language>
```

After the function app has been created and deployed, the Azure CLI shows information similar to the following example:

```json
{
  "availabilityState": "Normal",
  "clientAffinityEnabled": true,
  "clientCertEnabled": false,
  "cloningInfo": null,
  "containerSize": 1536,
  "dailyMemoryTimeQuota": 0,
  "defaultHostName": "quickstart.azurewebsites.net",
  "enabled": true,
  "enabledHostNames": [
    "quickstart.azurewebsites.net",
    "quickstart.scm.azurewebsites.net"
  ],
   ....
    // Remaining output has been truncated for readability.
}
```

Because `myAppServicePlan` is a Linux plan, the built-in docker image is used to create the container that runs the function app on Linux.

[!INCLUDE [functions-cleanup-resources](../../includes/functions-cleanup-resources-simple.md)]

## Next Steps

This article shows you how to create a Linux hosted function app in Azure. You can now [deploy a function project](https://docs.microsoft.com/cli/azure/functionapp/deployment/source?view=azure-cli-latest) to this function app. You can use the Azure Functions Core Tools to [create a Functions project](functions-run-local.md#create-a-local-functions-project) on your local computer and deploy it to your new Linux function app.  

> [!div class="nextstepaction"] 
> [Code and test Azure Functions locally](functions-run-local.md)

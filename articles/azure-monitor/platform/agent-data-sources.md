---
title: Configure agent data sources in Log Analytics | Microsoft Docs
description: Data sources define the log data that Log Analytics collects from agents and other connected sources.  This article describes the concept of how Log Analytics uses data sources, explains the details of how to configure them, and provides a summary of the different data sources available.
services: log-analytics
documentationcenter: ''
author: bwren
manager: carmonm
editor: tysonn
ms.assetid: 67710115-c861-40f8-a377-57c7fa6909b4
ms.service: log-analytics
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: infrastructure-services
ms.date: 01/07/2018
ms.author: bwren
---

# Agent data sources in Log Analytics
The data that Log Analytics collects from agents is defined by the data sources that you configure.  The data from agents is stored as [log data](data-collection.md) with a set of records.  Each data source creates records of a particular type with each type having its own set of properties.

![Log data collection](media/agent-data-sources/overview.png)

## Summary of data sources
The following table lists the agent data sources that are currently available in Log Analytics.  Each has a link to a separate article providing detail for that data source.   It also provides information on their method and frequency of collection. 


| Data source | Platform | Microsoft monitoring agent | Operations Manager agent | Azure storage | Operations Manager required? | Operations Manager agent data sent via management group | Collection frequency |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [Custom logs](data-sources-custom-logs.md) | Windows |&#8226; |  | |  |  | on arrival |
| [Custom logs](data-sources-custom-logs.md) | Linux   |&#8226; |  | |  |  | on arrival |
| [IIS logs](data-sources-iis-logs.md) | Windows |&#8226; |&#8226; |&#8226; |  |  |depends on Log File Rollover setting |
| [Performance counters](data-sources-performance-counters.md) | Windows |&#8226; |&#8226; |  |  |  |as scheduled, minimum of 10 seconds |
| [Performance counters](data-sources-performance-counters.md) | Linux |&#8226; |  |  |  |  |as scheduled, minimum of 10 seconds |
| [Syslog](data-sources-syslog.md) | Linux |&#8226; |  |  |  |  |from Azure storage: 10 minutes; from agent: on arrival |
| [Windows Event logs](data-sources-windows-events.md) |Windows |&#8226; |&#8226; |&#8226; |  |&#8226; | on arrival |


## Configuring data sources
You configure data sources from the **Data** menu in **Advanced Settings** for the workspace.  Any configuration is delivered to all connected sources in your workspace.  You cannot currently exclude any agents from this configuration.

![Configure Windows events](./media/agent-data-sources/configure-events.png)

1. In the Azure portal, select **Log Analytics** > your workspace > **Advanced Settings**.
2. Select **Data**.
3. Click on the data source you want to configure.
4. Follow the link to the documentation for each data source in the above table for details on their configuration.


## Data collection
Data source configurations are delivered to agents that are directly connected to Log Analytics within a few minutes.  The specified data is collected from the agent and delivered directly to Log Analytics at intervals specific to each data source.  See the documentation for each data source for these specifics.

For System Center Operations Manager agents in a connected management group, data source configurations are translated into management packs and delivered to the management group every 5 minutes by default.  The agent downloads the management pack like any other and collects the specified data. Depending on the data source, the data will be either sent to a management server which forwards the data to the Log Analytics, or the agent will send the data to Log Analytics without going through the management server. See [Data collection details for monitoring solutions in Azure](../../azure-monitor/insights/solutions-inventory.md) for details.  You can read about details of connecting Operations Manager and Log Analytics and modifying the frequency that configuration is delivered at [Configure Integration with System Center Operations Manager](../../log-analytics/log-analytics-om-agents.md).

If the agent is unable to connect to Log Analytics or Operations Manager, it will continue to collect data that it will deliver when it establishes a connection.  Data can be lost if the amount of data reaches the maximum cache size for the client, or if the agent is not able to establish a connection within 24 hours.

## Log records
All data collected by Log Analytics is stored in the workspace as records.  Records collected by different data sources will have their own set of properties and be identified by their **Type** property.  See the documentation for each data source and solution for details on each record type.

## Next steps
* Learn about [monitoring solutions](../../azure-monitor/insights/solutions.md) that add functionality to Azure Monitor and also collect data into the workspace.
* Learn about [log queries](../../log-analytics/log-analytics-queries.md) to analyze the data collected from data sources and monitoring solutions.  
* Configure [alerts](../../monitoring-and-diagnostics/monitoring-overview-alerts.md) to proactively notify you of critical data collected from data sources and monitoring solutions.

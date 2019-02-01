---
title: Supported operating systems, container engines - Azure IoT Edge | Microsoft Docs 
description: Learn which operating systems can run the Azure IoT Edge daemon and runtime, and supported container engines for your production devices
author: kgremban
manager: philmea
ms.author: kgremban
ms.date: 12/17/2018
ms.topic: conceptual
ms.service: iot-edge
services: iot-edge
ms.custom: seodec18
---

# Azure IoT Edge supported systems

There are a variety of ways to seek support for the Azure IoT Edge product.

**Reporting bugs** – The majority of development that goes into the Azure IoT Edge product happens in the IoT Edge open-source project. Bugs can be reported on the [issues page](https://github.com/azure/iotedge/issues) of the project. Fixes rapidly make their way from the project in to product updates.

**Microsoft Customer Support team** – Users who have a [support plan](https://azure.microsoft.com/support/plans/) can engage the Microsoft Customer Support team by creating a support ticket directly from the [Azure portal](https://ms.portal.azure.com/signin/index/?feature.settingsportalinstance=mpac).

**Feature requests** – The Azure IoT Edge product tracks feature requests via the product’s [User Voice page](https://feedback.azure.com/forums/907045-azure-iot-edge).

## Operating systems
Azure IoT Edge runs on most operating systems that can run containers; however, all of these are not equally supported. Operating systems are grouped into tiers that represent the level of support users can expect.

### Tier 1
Tier 1 systems can be thought of as officially supported. This means that Microsoft:
* has these operating system in automated tests
* provides installation packages for them

Generally available
| Operating System | AMD64 | ARM32 |
| ---------------- | ----- | ----- |
| Raspbian-stretch | No | Yes|
| Ubuntu Server 16.04 | Yes | No |
| Ubuntu Server 18.04 | Yes | No |

Public preview
| Operating System | AMD64 | ARM32 |
| ---------------- | ----- | ----- |
| Windows 10 IoT Core build 17763 | Yes | No |
| Windows 10 build 17763 for Windows containers<br><br>Windows 10 build 14393 or newer for Linux containers\* | Yes | No |
| Windows Server 2019 for Windows containers<br><br>Windows Server 2016 or newer for Linux containers\* | Yes | No |

\* Microsoft provides installation packages for Linux containers on Windows devices for development and testing only. This is not a supported configuration for production use. 

### Tier 2
Tier 2 systems can be thought of as compatible with Azure IoT Edge and can be used relatively easily. This means that:
* Microsoft has done ad-hoc testing on the platforms or knows of a partner successfully running Azure IoT Edge on the platform
* Installation packages for other platforms may work on these platforms

| Operating System | AMD64 | ARM32 |
| ---------------- | ----- | ----- |
| CentOS 7.5 | Yes | Yes |
| Debian 8 | Yes | Yes |
| Debian 9 | Yes | Yes |
| RHEL 7.5 | Yes | Yes |
| Ubuntu 18.04 | Yes | Yes |
| Ubuntu 16.04 | Yes | Yes |
| Wind River 8 | Yes | No |
| Yocto | Yes | No |

## Container engines
Azure IoT Edge needs a container engine to launch modules, regardless of the operating system on which it is running. Microsoft provides a container engine, moby-engine, to fulfill this requirement. It is based on the Moby open-source project. Docker CE and Docker EE are other popular container engines. They are also based on the Moby opens-source project and are compatible with Azure IoT Edge. Microsoft provides best effort support for systems using those container engines; however, Microsoft does not have the ability to ship fixes for issues in them. For this reason, Microsoft recommends using moby-engine on production systems.


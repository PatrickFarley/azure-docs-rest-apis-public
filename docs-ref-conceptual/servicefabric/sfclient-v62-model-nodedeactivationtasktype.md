---
title: "NodeDeactivationTaskType"
ms.date: "2018-04-23"
ms.prod: "azure"
ms.service: "service-fabric"
ms.topic: "reference"
applies_to: 
  - "Azure"
  - "Windows Server 2012 R2"
  - "Windows Server 2016"
dev_langs: 
  - "rest-api"
helpviewer_keywords: 
  - "Service Fabric REST API Reference"
author: "rwike77"
ms.author: "ryanwi"
manager: "timlt"
translation.priority.mt: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pt-br"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
---
# NodeDeactivationTaskType enum

type: string

The type of the task that performed the node deactivation. Following are the possible values.

Possible values are: 

  - `Invalid` - Indicates the node deactivation task type is invalid. All Service Fabric enumerations have the invalid type. The value is zero. This value is not used.
  - `Infrastructure` - Specifies the task created by Infrastructure hosting the nodes. The value is 1.
  - `Repair` - Specifies the task that was created by the Repair Manager service. The value is 2.
  - `Client` - Specifies that the task was created by using the public API. The value is 3.


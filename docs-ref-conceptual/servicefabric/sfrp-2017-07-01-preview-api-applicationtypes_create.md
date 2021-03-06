---
title: "Create"
ms.date: "2018-05-25"
ms.prod: "azure"
ms.service: "service-fabric"
ms.topic: "reference"
applies_to: 
  - "Azure"
dev_langs: 
  - "rest-api"
helpviewer_keywords: 
  - "Service Fabric Resource Manager REST API Reference"
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
# Create
Creates or updates a Service Fabric application type name resource.

Create or update a Service Fabric application type name resource with the specified name.

## Request
| Method | Request URI |
| ------ | ----------- |
| PUT | `/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ServiceFabric/clusters/{clusterName}/applicationTypes/{applicationTypeName}?api-version=2017-07-01-preview` |


## Parameters
| Name | Type | Required | Location |
| --- | --- | --- | --- |
| [subscriptionId](#subscriptionid) | string | Yes | Path |
| [resourceGroupName](#resourcegroupname) | string | Yes | Path |
| [clusterName](#clustername) | string | Yes | Path |
| [applicationTypeName](#applicationtypename) | string | Yes | Path |
| [api-version](#api-version) | string | Yes | Query |
| [parameters](#parameters) | [ApplicationTypeResource](sfrp-2017-07-01-preview-model-applicationtyperesource.md) | Yes | Body |

____
### subscriptionId
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The customer subscription identifier.

____
### resourceGroupName
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The name of the resource group.

____
### clusterName
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The name of the cluster resource.

____
### applicationTypeName
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The name of the application type name resource.

____
### api-version
__Type__: string <br/>
__Required__: Yes<br/>
__Default__: 2017-07-01-preview <br/>
<br/>
The version of the Service Fabric resource provider API. This is a required parameter and it's value must be "2017-07-01-preview" for this specification.

____
### parameters
__Type__: [ApplicationTypeResource](sfrp-2017-07-01-preview-model-applicationtyperesource.md) <br/>
__Required__: Yes<br/>
<br/>
The application type name resource.

## Responses

| HTTP Status Code | Description | Response Schema |
| --- | --- | --- |
| 200 (OK) | The operation completed successfully.<br/> | [ApplicationTypeResource](sfrp-2017-07-01-preview-model-applicationtyperesource.md) |
| All other status codes | The detailed error response.<br/> | [ErrorModel](sfrp-2017-07-01-preview-model-errormodel.md) |

## Examples

### Put an application type

#### Request
```
PUT https://management.azure.com/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resRg/providers/Microsoft.ServiceFabric/clusters/myCluster/applicationTypes/myAppType?api-version=2017-07-01-preview
```

##### Body
```json
{
  "type": "applicationTypes",
  "location": "eastus",
  "id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/resRg/providers/Microsoft.ServiceFabric/clusters/myCluster/applicationTypes/myAppType",
  "name": "myCluster",
  "tags": {}
}
```

#### 200 Response
##### Body
```json
{
  "type": "applicationTypes",
  "location": "eastus",
  "id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/resRg/providers/Microsoft.ServiceFabric/clusters/myCluster/applicationTypes/myAppType",
  "name": "myCluster",
  "tags": {},
  "etag": "W/\"636462502174844831\"",
  "properties": {
    "provisioningState": "Succeeded"
  }
}
```


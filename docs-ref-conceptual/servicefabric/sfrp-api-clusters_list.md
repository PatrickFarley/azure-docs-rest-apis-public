---
title: "List"
ms.date: "2017-05-16"
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
# List
List cluster resource

List cluster resource


## Request
| Method | Request URI |
| ------ | ----------- |
| GET | `/subscriptions/{subscriptionId}/providers/Microsoft.ServiceFabric/clusters?api-version=2016-09-01` |


## Parameters
| Name | Type | Required | Location |
| --- | --- | --- | --- |
| [subscriptionId](#subscriptionid) | string | Yes | Path |
| [api-version](#api-version) | string | Yes | Query |

____
### subscriptionId
__Type__: string <br/>
__Required__: Yes<br/>
<br/>
The customer subscription identifier

____
### api-version
__Type__: string <br/>
__Required__: Yes<br/>
__Default__: 2016-09-01 <br/>
<br/>
The version of the API. This is a required parameter and it's value must be "2016-09-01".

## Responses

| HTTP Status Code | Description | Response Schema |
| --- | --- | --- |
| 200 (OK) | OK - Get cluster  successfully<br/> | [ClusterListResult](sfrp-model-clusterlistresult.md) |
| All other status codes | Error<br/> | [ErrorModel](sfrp-model-errormodel.md) |

## Examples

### List clusters

#### Request
```
GET https://management.azure.com/subscriptions/00000000-0000-0000-0000-000000000000/providers/Microsoft.ServiceFabric/clusters?api-version=2016-09-01
```

#### 200 Response
##### Body
```json
{
  "value": [
    {
      "type": "Microsoft.ServiceFabric/clusters",
      "location": "westus",
      "id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/demo/providers/Microsoft.ServiceFabric/clusters/demo",
      "name": "demo",
      "tags": {
        "resourceType": "Service Fabric",
        "clusterName": "demo"
      },
      "properties": {
        "provisioningState": "Succeeded",
        "clusterId": "a4e23572-8443-470e-adcb-3b7ebe6d582b",
        "clusterCodeVersion": "5.4.164.9494",
        "clusterState": "Ready",
        "managementEndpoint": "http://demo.westus.cloudapp.azure.com:19080",
        "clusterEndpoint": "https://westus.servicefabric.azure.com/runtime/clusters/a4e23572-8443-470e-adcb-3b7ebe6d582b",
        "upgradeDescription": {
          "forceRestart": true,
          "upgradeReplicaSetCheckTimeout": "10675199.02:48:05.4775807",
          "healthCheckWaitDuration": "00:05:00",
          "healthCheckStableDuration": "00:05:00",
          "healthCheckRetryTimeout": "00:45:00",
          "upgradeTimeout": "12:00:00",
          "upgradeDomainTimeout": "02:00:00",
          "healthPolicy": {
            "maxPercentUnhealthyNodes": 100,
            "maxPercentUnhealthyApplications": 100
          },
          "deltaHealthPolicy": {
            "maxPercentDeltaUnhealthyNodes": 0,
            "maxPercentUpgradeDomainDeltaUnhealthyNodes": 0,
            "maxPercentDeltaUnhealthyApplications": 0
          }
        },
        "diagnosticsStorageAccountConfig": {
          "storageAccountName": "sflogsdemo4564",
          "protectedAccountKeyName": "StorageAccountKey1",
          "blobEndpoint": "https://sflogsdemo4564.blob.core.windows.net/",
          "queueEndpoint": "https://sflogsdemo4564.queue.core.windows.net/",
          "tableEndpoint": "https://sflogsdemo4564.table.core.windows.net/"
        },
        "nodeTypes": [
          {
            "name": "Demo",
            "clientConnectionEndpointPort": 19000,
            "httpGatewayEndpointPort": 19080,
            "applicationPorts": {
              "startPort": 20000,
              "endPort": 30000
            },
            "ephemeralPorts": {
              "startPort": 49152,
              "endPort": 65534
            },
            "isPrimary": true,
            "vmInstanceCount": 5,
            "durabilityLevel": "Bronze"
          }
        ],
        "vmImage": "Windows",
        "reliabilityLevel": "Silver",
        "upgradeMode": "Automatic",
        "availableClusterVersions": [
          {
            "codeVersion": "5.4.164.9494",
            "supportExpiryUtc": "9999-12-31T23:59:59.9999999",
            "environment": "Windows"
          }
        ]
      }
    },
    {
      "type": "Microsoft.ServiceFabric/clusters",
      "location": "southcentralus",
      "id": "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/psdeployrg4/providers/Microsoft.ServiceFabric/clusters/sfclust4",
      "name": "sfclust4",
      "tags": {
        "resourceType": "Service Fabric",
        "clusterName": "sfclust4"
      },
      "properties": {
        "provisioningState": "Succeeded",
        "clusterId": "029c03b7-d94e-4c64-9dd4-b1c3bb0914c1",
        "clusterCodeVersion": "5.5.149.9494",
        "clusterState": "Ready",
        "managementEndpoint": "https://sfclust4.southcentralus.cloudapp.azure.com:19080",
        "clusterEndpoint": "https://warp-test-winfabrp-southcentralus.trafficmanager.net/runtime/clusters/029c03b7-d94e-4c64-9dd4-b1c3bb0914c1",
        "certificate": {
          "thumbprint": "68A89C30F20B2A198B0A26DF3744079D0F5AC2FC",
          "x509StoreName": "My"
        },
        "fabricSettings": [
          {
            "name": "Security",
            "parameters": [
              {
                "name": "ClusterProtectionLevel",
                "value": "EncryptAndSign"
              }
            ]
          }
        ],
        "upgradeDescription": {
          "forceRestart": true,
          "upgradeReplicaSetCheckTimeout": "10675199.02:48:05.4775807",
          "healthCheckWaitDuration": "00:05:00",
          "healthCheckStableDuration": "00:05:00",
          "healthCheckRetryTimeout": "00:45:00",
          "upgradeTimeout": "12:00:00",
          "upgradeDomainTimeout": "02:00:00",
          "healthPolicy": {
            "maxPercentUnhealthyNodes": 100,
            "maxPercentUnhealthyApplications": 100
          },
          "deltaHealthPolicy": {
            "maxPercentDeltaUnhealthyNodes": 0,
            "maxPercentUpgradeDomainDeltaUnhealthyNodes": 0,
            "maxPercentDeltaUnhealthyApplications": 0
          }
        },
        "diagnosticsStorageAccountConfig": {
          "storageAccountName": "t2vgl3f2bk6qw2",
          "protectedAccountKeyName": "StorageAccountKey1",
          "blobEndpoint": "https://t2vgl3f2bk6qw2.blob.core.windows.net/",
          "queueEndpoint": "https://t2vgl3f2bk6qw2.queue.core.windows.net/",
          "tableEndpoint": "https://t2vgl3f2bk6qw2.table.core.windows.net/"
        },
        "nodeTypes": [
          {
            "name": "nt1vm",
            "clientConnectionEndpointPort": 19000,
            "httpGatewayEndpointPort": 19080,
            "applicationPorts": {
              "startPort": 20000,
              "endPort": 30000
            },
            "ephemeralPorts": {
              "startPort": 49152,
              "endPort": 65534
            },
            "isPrimary": true,
            "vmInstanceCount": 5,
            "durabilityLevel": "Bronze"
          }
        ],
        "vmImage": "Windows",
        "reliabilityLevel": "Silver",
        "upgradeMode": "Automatic",
        "availableClusterVersions": [
          {
            "codeVersion": "5.5.67.9494",
            "supportExpiryUtc": "9999-12-31T23:59:59.9999999",
            "environment": "Windows"
          },
          {
            "codeVersion": "5.5.149.9494",
            "supportExpiryUtc": "9999-12-31T23:59:59.9999999",
            "environment": "Windows"
          }
        ]
      }
    }
  ]
}
```

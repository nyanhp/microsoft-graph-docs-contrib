---
title: "List sensors"
description: "Get a list of sensor objects and their properties."
author: "amirfeldman"
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: apiPageType
ms.date: 09/10/2024
---

# List sensors

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of [sensor](../resources/security-sensor.md) objects and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "security-identitycontainer-list-sensors-permissions"
}
-->
|Permission type|Least privileged permission|Higher privileged permissions|
|:---|:---|:---|
|Delegated (work or school account)|SecurityIdentitiesSensors.Read.All|SecurityIdentitiesSensors.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|Not supported.|
|Application|SecurityIdentitiesSensors.Read.All|SecurityIdentitiesSensors.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /security/identities/sensors
```

## Optional query parameters

This method supports the following OData query parameters to help customize the response: `$count`, `$filter`, `$skip`, `$top`. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [microsoft.graph.security.sensor](../resources/security-sensor.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_sensor"
}
-->
``` http
GET https://graph.microsoft.com/beta/security/identities/sensors
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.security.sensor)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.security.sensor",
      "id": "b3c1b5fc-828c-45fa-a1e1-10d74f6d6e9c",
      "displayName": "DC1",
      "sensorType": "domainControllerIntegrated",
      "version": "2.239.18124.58593",
      "deploymentStatus": "upToDate",
      "createdDateTime": "2023-11-16T09:41:24.2585071Z",
      "domainName": "domain1.test.local",
      "healthStatus": "healthy",
      "openHealthIssuesCount": 0,
      "settings": {
        "@odata.type": "microsoft.graph.security.sensorSettings",
        "description": "dc1 settings",
        "domainControllerDnsNames": [
            "DC1.domain1.test.local"
        ],
        "isDelayedDeploymentEnabled": true
      }
    }
  ]
}
```
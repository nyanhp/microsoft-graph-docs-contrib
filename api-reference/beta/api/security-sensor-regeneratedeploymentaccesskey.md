---
title: "sensor: regenerateDeploymentAccessKey"
description: "Generate a new deployment access key that can be used to install sensors associated with the workspace."
author: "amirfeldman"
ms.localizationpriority: medium
ms.subservice: "security"
doc_type: apiPageType
ms.date: 09/10/2024
---

# sensor: regenerateDeploymentAccessKey

Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Generate a new deployment access key that can be used to install a [sensor](../resources/security-sensor.md) associated with the workspace.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- {
  "blockType": "permissions",
  "name": "security-sensor-regeneratedeploymentaccesskey-permissions"
}
-->
|Permission type|Least privileged permission|Higher privileged permissions|
|:---|:---|:---|
|Delegated (work or school account)|SecurityIdentitiesSensors.ReadWrite.All|Not available.|
|Delegated (personal Microsoft account)|Not supported.|Not supported.|
|Application|SecurityIdentitiesSensors.ReadWrite.All|Not available.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /security/identities/sensors/regenerateDeploymentAccessKey
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this action returns a `200 OK` response code and a [microsoft.graph.security.deploymentAccessKeyType](../resources/security-deploymentaccesskeytype.md) in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "sensorthis.regeneratedeploymentaccesskey"
}
-->
``` http
POST https://graph.microsoft.com/beta/security/identities/sensors/regenerateDeploymentAccessKey
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.security.deploymentAccessKeyType"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "microsoft.graph.security.deploymentAccessKeyType",
    "sensorDeploymentAccessKey": "<Deployment access key (Secret)>"
  }
}
```
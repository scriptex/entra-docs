---
title: Configure permission classifications
description: Learn how to manage delegated permission classifications.

author: omondiatieno
manager: mwongerapk
ms.service: entra-id
ms.subservice: enterprise-apps

ms.topic: how-to
ms.date: 03/03/2025
ms.author: jomondi
ms.reviewer: phsignor, jawoods
ms.custom: no-azure-ad-ps-ref
zone_pivot_groups: enterprise-apps-all
#customer intent: As an administrator managing permissions in Microsoft Entra ID, I want to configure permission classifications, so that I can identify the impact of different permissions according to my organization's policies and risk evaluations.
---

# Configure permission classifications

In this article, you learn how to configure permissions classifications in Microsoft Entra ID. Permission classifications allow you to identify the impact that different permissions have based on your organization's policies and risk evaluations. For example, you can use permission classifications in consent policies to identify the set of permissions that users are allowed to consent to.

Three permission classifications are supported: "Low," "Medium" (preview), and "High" (preview). Currently, only delegated permissions that don't require admin consent can be classified.

The minimum permissions needed to do basic sign-in are `openid`, `profile`, `email`, and `offline_access`, which are all delegated permissions on the Microsoft Graph. With these permissions an app can read details of the signed-in user's profile, and can maintain this access even when the user is no longer using the app.

## Prerequisites

To configure permission classifications, you need:

- An Azure account with an active subscription. [Create an account for free](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).
- One of the following roles: Application Administrator, or Cloud Application Administrator

## Manage permission classifications

:::zone pivot="portal"


Follow these steps to classify permissions using the Microsoft Entra admin center:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Consent and permissions** > **Permission classifications**.
1. Choose the tab for the permission classification you'd like to update.
1. Choose **Add permissions** to classify another permission.
1. Select the API and then select one or more delegated permissions.

In this example, we classify the minimum set of permission required for single sign-on:

:::image type="content" source="media/configure-permission-classifications/permission-classifications.png" alt-text="Permission classifications":::

:::zone-end

:::zone pivot="entra-powershell"

You can use the latest [Microsoft Entra PowerShell](/powershell/entra-powershell/?preserve-view=true&view=entra-powershell) to classify permissions. Permission classifications are configured on the **ServicePrincipal** object of the API that publishes the permissions.

Run the following command to connect to Microsoft Entra PowerShell. To consent to the required scopes, sign in as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).

```powershell
Connect-Entra -scopes "Policy.ReadWrite.PermissionGrant", "Application.Read.All"
```

### List the current permission classifications using Microsoft Entra PowerShell

1. Retrieve the **ServicePrincipal** object for the API. Here we retrieve the ServicePrincipal object for the Microsoft Graph API:

   ```powershell
   $serviceprincipal = Get-EntraServicePrincipal `
       -Filter "servicePrincipalNames/any(n:n eq 'https://graph.microsoft.com')"
   ```

1. Read the delegated permission classifications for the API:

   ```powershell
   Get-EntraServicePrincipalDelegatedPermissionClassification `
       -ServicePrincipalId $serviceprincipal.ObjectId | Format-Table Id, PermissionName, Classification
   ```

### Classify a permission as "Low impact" using Microsoft Entra PowerShell

1. Retrieve the **ServicePrincipal** object for the API. Here we retrieve the ServicePrincipal object for the Microsoft Graph API:

   ```powershell
   $serviceprincipal = Get-EntraServicePrincipal `
       -Filter "servicePrincipalNames/any(n:n eq 'https://graph.microsoft.com')"
   ```

1. Find the delegated permission you would like to classify:

   ```powershell
   $delegatedPermission = $serviceprincipal.oauth2PermissionScopes | Where-Object { $_.Value -eq "User.ReadBasic.All" }
   ```

1. Set the permission classification using the permission name and ID:

   ```powershell
   Add-EntraServicePrincipalDelegatedPermissionClassification `
      -ServicePrincipalId $serviceprincipal.ObjectId `
      -PermissionId $delegatedPermission.Id `
      -PermissionName $delegatedPermission.Value `
      -Classification "low"
   ```

### Remove a delegated permission classification using Microsoft Entra PowerShell

1. Retrieve the **ServicePrincipal** object for the API. Here we retrieve the ServicePrincipal object for the Microsoft Graph API:

   ```powershell
   $serviceprincipal = Get-EntraServicePrincipal `
       -Filter "servicePrincipalNames/any(n:n eq 'https://graph.microsoft.com')"
   ```

1. Find the delegated permission classification you wish to remove:

   ```powershell
   $classifications = Get-EntraServicePrincipalDelegatedPermissionClassification `
       -ServicePrincipalId $serviceprincipal.ObjectId
   $classificationToRemove = $classifications | Where-Object {$_.PermissionName -eq "User.ReadBasic.All"}
   ```

1. Delete the permission classification:

   ```powershell
   Remove-EntraServicePrincipalDelegatedPermissionClassification `
       -ServicePrincipalId $serviceprincipal.ObjectId `
       -Id $classificationToRemove.Id
   ```

:::zone-end

:::zone pivot="ms-powershell"

You can use [Microsoft Graph PowerShell](/powershell/microsoftgraph/get-started?preserve-view=true&view=graph-powershell-1.0), to classify permissions. Permission classifications are configured on the **ServicePrincipal** object of the API that publishes the permissions.

Run the following command to connect to Microsoft Graph PowerShell. To consent to the required scopes, sign in as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).

```powershell
Connect-MgGraph -Scopes "Policy.ReadWrite.PermissionGrant", "Application.Read.All"
```

### List current permission classifications for an API using Microsoft Graph PowerShell

1. Retrieve the servicePrincipal object for the API:

   ```powershell
   $serviceprincipal = Get-MgServicePrincipal -Filter "displayName eq 'Microsoft Graph'" 
   ```

1. Read the delegated permission classifications for the API:

   ```powershell
   Get-MgServicePrincipalDelegatedPermissionClassification -ServicePrincipalId $serviceprincipal.Id 
   ```

### Classify a permission as "Low impact" using Microsoft Graph PowerShell

1. Retrieve the servicePrincipal object for the API:

   ```powershell
   $serviceprincipal = Get-MgServicePrincipal -Filter "displayName eq 'Microsoft Graph'" 
   ```

1. Find the delegated permission you would like to classify:

   ```powershell
   $delegatedPermission = $serviceprincipal.Oauth2PermissionScopes | Where-Object {$_.Value -eq "openid"} 
   ```

1. Set the permission classification:

   ```powershell
   $params = @{ 
      PermissionId = $delegatedPermission.Id 
      PermissionName = $delegatedPermission.Value 
      Classification = "Low"
   } 

   New-MgServicePrincipalDelegatedPermissionClassification -ServicePrincipalId $serviceprincipal.Id -BodyParameter $params 
   ```

### Remove a delegated permission classification using Microsoft Graph PowerShell

1. Retrieve the servicePrincipal object for the API:

   ```powershell
   $serviceprincipal = Get-MgServicePrincipal -Filter "displayName eq 'Microsoft Graph'" 
   ```

1. Find the delegated permission classification you wish to remove:

   ```powershell
   $classifications = Get-MgServicePrincipalDelegatedPermissionClassification -ServicePrincipalId $serviceprincipal.Id 

   $classificationToRemove = $classifications | Where-Object {$_.PermissionName -eq "openid"}
   ```

1. Delete the permission classification:

```powershell
Remove-MgServicePrincipalDelegatedPermissionClassification -DelegatedPermissionClassificationId $classificationToRemove.Id   -ServicePrincipalId $serviceprincipal.id 
```

:::zone-end

:::zone pivot="ms-graph"

To configure permissions classifications for an enterprise application, sign in to [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).

You need to consent to the `Policy.ReadWrite.PermissionGrant` and `Application.Read.All` permissions.

Run the following queries on Microsoft Graph explorer to add a delegated permissions classification for an application.

### List current permission classifications for an API using Microsoft Graph API

List current permission classifications for an API using the following Microsoft Graph API call.

   ```http
   GET https://graph.microsoft.com/v1.0/servicePrincipals(appId='00000003-0000-0000-c000-000000000000')/delegatedPermissionClassifications
   ```

### Classify a permission as "Low impact" using Microsoft Graph API

In the following example, we classify the permission as "low impact."

Add a delegated permission classification for an API using the following Microsoft Graph API call.

   ```http
   POST https://graph.microsoft.com/v1.0/servicePrincipals(appId='00000003-0000-0000-c000-000000000000')/delegatedPermissionClassifications
   Content-type: application/json

   {
      "permissionId": "b4e74841-8e56-480b-be8b-910348b18b4c",
      "classification": "low"
   }
   ```

### Remove a delegated permission classification using Microsoft Graph API

Run the following query on Microsoft Graph explorer to remove a delegated permissions classification for an API.

```http
DELETE https://graph.microsoft.com/v1.0/servicePrincipals(appId='00000003-0000-0000-c000-000000000000')/delegatedPermissionClassifications/QUjntFaOC0i-i5EDSLGLTAE
```

:::zone-end

## Related content

- [Manage app consent policies](manage-app-consent-policies.md)
- [Permissions and consent in the Microsoft identity platform](~/identity-platform/permissions-consent-overview.md)

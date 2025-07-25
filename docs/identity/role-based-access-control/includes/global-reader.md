---
title: Global Reader
description: Global Reader
ms.service: entra-id
ms.subservice: role-based-access-control
ms.topic: include
ms.date: 07/09/2025
ms.custom: include file
---

[![Privileged label icon.](../media/permissions-reference/privileged-label.png)](../privileged-roles-permissions.md)

This is a [privileged role](../privileged-roles-permissions.md). Users in this role can read settings and administrative information across Microsoft 365 services but can't take management actions. Global Reader is the read-only counterpart to Global Administrator. Assign Global Reader instead of Global Administrator for planning, audits, or investigations. Use Global Reader in combination with other limited admin roles like Exchange Administrator to make it easier to get work done without the assigning the Global Administrator role. Global Reader works with Microsoft 365 admin center, Exchange admin center, SharePoint admin center, Teams admin center, Microsoft 365 Defender portal, Microsoft Purview compliance portal, Azure portal, and Device Management admin center.

Users with this role **cannot** do the following:

- Cannot access the Purchase Services area in the Microsoft 365 admin center.

> [!NOTE]
> Global Reader role has the following limitations:
>
>- OneDrive admin center - OneDrive admin center does not support the Global Reader role
>- [Microsoft 365 Defender portal](/microsoft-365/security/defender/microsoft-365-defender-portal) - Global Reader can't do content search or see Secure Score.
>- [Teams admin center](/microsoftteams/manage-teams-in-modern-portal) - Global Reader cannot read **Teams lifecycle**, **Analytics & reports**, **IP phone device management**, and **App catalog**. For more information, see [Use Microsoft Teams administrator roles to manage Teams](/microsoftteams/using-admin-roles).
>- [Privileged Access Management](/microsoft-365/compliance/privileged-access-management) doesn't support the Global Reader role.
>- [Azure Information Protection](/azure/information-protection/what-is-information-protection) - Global Reader is supported [for central reporting](/azure/information-protection/reports-aip) only, and when your Microsoft Entra organization isn't on the [unified labeling platform](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform).
> - [SharePoint](/sharepoint/get-started-new-admin-center) - Global Reader has read access to SharePoint Online PowerShell cmdlets and Read APIs.
> - [Power Platform admin center](/power-platform/admin/admin-documentation) - Global Reader is not yet supported in the Power Platform admin center.
> - Microsoft Purview doesn't support the Global Reader role.

<!-- autogenerated content starts here -->

> [!div class="mx-tableFixed"]
> | Actions | Description |
> | --- | --- |
> | microsoft.azure.serviceHealth/allEntities/allTasks | Read and configure Azure Service Health |
> | microsoft.backup/allEntities/allProperties/read | Read all aspects of Microsoft 365 Backup |
> | microsoft.cloudPC/allEntities/allProperties/read | Read all aspects of Windows 365 |
> | microsoft.commerce.billing/allEntities/allProperties/read | Read all resources of Office 365 billing |
> | microsoft.commerce.billing/purchases/standard/read | Read purchase services in Microsoft 365 admin center. |
> | microsoft.directory/accessReviews/allProperties/read | Read all properties of access reviews |
> | microsoft.directory/accessReviews/definitions/allProperties/read | Read all properties of access reviews of all reviewable resources in Microsoft Entra ID |
> | microsoft.directory/adminConsentRequestPolicy/allProperties/read | Read all properties of admin consent request policies in Microsoft Entra ID |
> | microsoft.directory/administrativeUnits/allProperties/read | Read all properties of administrative units, including members |
> | microsoft.directory/appConsent/appConsentRequests/allProperties/read | Read all properties of consent requests for applications registered with Microsoft Entra ID |
> | microsoft.directory/applications/allProperties/read | Read all properties (including privileged properties) on all types of applications |
> | microsoft.directory/applications/synchronization/standard/read | Read provisioning settings associated with the application object |
> | microsoft.directory/auditLogs/allProperties/read | Read all properties on audit logs, excluding custom security attributes audit logs |
> | microsoft.directory/authorizationPolicy/standard/read | Read standard properties of authorization policy |
> | microsoft.directory/bitlockerKeys/key/read | Read bitlocker metadata and key on devices<br/>[![Privileged label icon.](../media/permissions-reference/privileged-label.png)](../privileged-roles-permissions.md) |
> | microsoft.directory/bulkJobs/standard/read | Read all bulk jobs in a directory |
> | microsoft.directory/cloudAppSecurity/allProperties/read | Read all properties for Cloud app security |
> | microsoft.directory/conditionalAccessPolicies/allProperties/read | Read all properties of Conditional Access policies |
> | microsoft.directory/connectorGroups/allProperties/read | Read all properties of application proxy connector groups |
> | microsoft.directory/connectors/allProperties/read | Read all properties of application proxy connectors |
> | microsoft.directory/contacts/allProperties/read | Read all properties for contacts |
> | microsoft.directory/crossTenantAccessPolicy/default/standard/read | Read basic properties of the default cross-tenant access policy |
> | microsoft.directory/crossTenantAccessPolicy/partners/identitySynchronization/standard/read | Read basic properties of cross-tenant sync policy |
> | microsoft.directory/crossTenantAccessPolicy/partners/standard/read | Read basic properties of cross-tenant access policy for partners |
> | microsoft.directory/crossTenantAccessPolicy/partners/templates/multiTenantOrganizationIdentitySynchronization/standard/read | Read basic properties of cross tenant sync policy templates for multi-tenant organization |
> | microsoft.directory/crossTenantAccessPolicy/partners/templates/multiTenantOrganizationPartnerConfiguration/standard/read | Read basic properties of cross tenant access policy templates for multi-tenant organization |
> | microsoft.directory/crossTenantAccessPolicy/standard/read | Read basic properties of cross-tenant access policy |
> | microsoft.directory/customAuthenticationExtensions/allProperties/read | Read custom authentication extensions |
> | microsoft.directory/deviceLocalCredentials/standard/read | Read all properties of the backed up local administrator account credentials for Microsoft Entra joined devices, except the password |
> | microsoft.directory/deviceManagementPolicies/standard/read | Read standard properties on mobile device management and mobile app management policies |
> | microsoft.directory/deviceRegistrationPolicy/standard/read | Read standard properties on device registration policies |
> | microsoft.directory/devices/allProperties/read | Read all properties of devices |
> | microsoft.directory/directoryRoles/allProperties/read | Read all properties of directory roles |
> | microsoft.directory/directoryRoleTemplates/allProperties/read | Read all properties of directory role templates |
> | microsoft.directory/domains/allProperties/read | Read all properties of domains |
> | microsoft.directory/domains/federationConfiguration/standard/read | Read standard properties of federation configuration for domains |
> | microsoft.directory/entitlementManagement/allProperties/read | Read all properties in Microsoft Entra entitlement management |
> | microsoft.directory/externalUserProfiles/standard/read | Read standard properties of external user profiles in the extended directory for Teams |
> | microsoft.directory/groups/allProperties/read | Read all properties (including privileged properties) on Security groups and Microsoft 365 groups, including role-assignable groups |
> | microsoft.directory/groupSettings/allProperties/read | Read all properties of group settings |
> | microsoft.directory/groupSettingTemplates/allProperties/read | Read all properties of group setting templates |
> | microsoft.directory/identityProtection/allProperties/read | Read all resources in Microsoft Entra ID Protection |
> | microsoft.directory/lifecycleWorkflows/workflows/allProperties/read | Read all properties of lifecycle workflows and tasks in Microsoft Entra ID |
> | microsoft.directory/loginOrganizationBranding/allProperties/read | Read all properties for your organization's branded sign-in page |
> | microsoft.directory/multiTenantOrganization/joinRequest/standard/read | Read properties of a multi-tenant organization join request |
> | microsoft.directory/multiTenantOrganization/standard/read | Read basic properties of a multi-tenant organization |
> | microsoft.directory/multiTenantOrganization/tenants/organizationDetails/read | Read organization details of a tenant participating in a multi-tenant organization |
> | microsoft.directory/multiTenantOrganization/tenants/standard/read | Read basic properties of a tenant participating in a multi-tenant organization |
> | microsoft.directory/namedLocations/standard/read | Read basic properties of custom rules that define network locations |
> | microsoft.directory/oAuth2PermissionGrants/allProperties/read | Read all properties of OAuth 2.0 permission grants |
> | microsoft.directory/onPremisesSynchronization/standard/read | Read standard on-premises directory synchronization information |
> | microsoft.directory/organization/allProperties/read | Read all properties for an organization |
> | microsoft.directory/pendingExternalUserProfiles/standard/read | Read standard properties of external user profiles in the extended directory for Teams |
> | microsoft.directory/permissionGrantPolicies/standard/read | Read standard properties of permission grant policies |
> | microsoft.directory/policies/allProperties/read | Read all properties of policies |
> | microsoft.directory/privilegedIdentityManagement/allProperties/read | Read all resources in Privileged Identity Management |
> | microsoft.directory/provisioningLogs/allProperties/read | Read all properties of provisioning logs |
> | microsoft.directory/roleAssignments/allProperties/read | Read all properties of role assignments |
> | microsoft.directory/roleDefinitions/allProperties/read | Read all properties of role definitions |
> | microsoft.directory/scopedRoleMemberships/allProperties/read | View members in administrative units |
> | microsoft.directory/serviceAction/getAvailableExtentionProperties | Can perform the getAvailableExtentionProperties service action |
> | microsoft.directory/servicePrincipalCreationPolicies/standard/read | Read standard properties of service principal creation policies |
> | microsoft.directory/servicePrincipals/allProperties/read | Read all properties (including privileged properties) on servicePrincipals |
> | microsoft.directory/servicePrincipals/synchronization/standard/read | Read provisioning settings associated with your service principal |
> | microsoft.directory/signInReports/allProperties/read | Read all properties on sign-in reports, including privileged properties |
> | microsoft.directory/subscribedSkus/allProperties/read | Read all properties of product subscriptions |
> | microsoft.directory/users/allProperties/read | Read all properties of users<br/>[![Privileged label icon.](../media/permissions-reference/privileged-label.png)](../privileged-roles-permissions.md) |
> | microsoft.directory/users/authenticationMethods/standard/restrictedRead | Read standard properties of authentication methods that do not include personally identifiable information for users |
> | microsoft.directory/verifiableCredentials/configuration/allProperties/read | Read configuration required to create and manage verifiable credentials |
> | microsoft.directory/verifiableCredentials/configuration/contracts/allProperties/read | Read a verifiable credential contract |
> | microsoft.directory/verifiableCredentials/configuration/contracts/cards/allProperties/read | Read a verifiable credential card |
> | microsoft.edge/allEntities/allProperties/read | Read all aspects of Microsoft Edge |
> | microsoft.graph.dataConnect/allEntities/allProperties/read | Read aspects of Microsoft Graph Data Connect |
> | microsoft.hardware.support/shippingAddress/allProperties/read | Read shipping addresses for Microsoft hardware warranty claims, including existing shipping addresses created by others |
> | microsoft.hardware.support/shippingStatus/allProperties/read | Read shipping status for open Microsoft hardware warranty claims |
> | microsoft.hardware.support/warrantyClaims/allProperties/read | Read Microsoft hardware warranty claims |
> | microsoft.insights/allEntities/allProperties/read | Read all aspects of Viva Insights |
> | microsoft.microsoft365.organizationalData/allEntities/allProperties/read | Read all aspects of organizational data in Microsoft 365 |
> | microsoft.networkAccess/allEntities/allProperties/read | Read all aspects of Microsoft Entra Network Access |
> | microsoft.office365.copilot/allEntities/allProperties/read | Read all settings for Microsoft 365 Copilot |
> | microsoft.office365.fileStorageContainers/allEntities/allProperties/read | Read entities and permissions of SharePoint Embedded containers |
> | microsoft.office365.messageCenter/messages/read | Read messages in Message Center in the Microsoft 365 admin center, excluding security messages |
> | microsoft.office365.messageCenter/securityMessages/read | Read security messages in Message Center in the Microsoft 365 admin center |
> | microsoft.office365.network/performance/allProperties/read | Read all network performance properties in the Microsoft 365 admin center |
> | microsoft.office365.organizationalMessages/allEntities/allProperties/read | Read all aspects of Microsoft 365 Organizational Messages |
> | microsoft.office365.protectionCenter/allEntities/allProperties/read | Read all properties in the Security and Compliance centers |
> | microsoft.office365.securityComplianceCenter/allEntities/read | Read standard properties in Microsoft 365 Security and Compliance Center |
> | microsoft.office365.serviceHealth/allEntities/allTasks | Read and configure Service Health in the Microsoft 365 admin center |
> | microsoft.office365.usageReports/allEntities/allProperties/read | Read Office 365 usage reports |
> | microsoft.office365.webPortal/allEntities/standard/read | Read basic properties on all resources in the Microsoft 365 admin center |
> | microsoft.office365.yammer/allEntities/allProperties/read | Read all aspects of Yammer |
> | microsoft.permissionsManagement/allEntities/allProperties/read | Read all aspects of Microsoft Entra Permissions Management |
> | microsoft.teams/allEntities/allProperties/read | Read all properties of Microsoft Teams |
> | microsoft.virtualVisits/allEntities/allProperties/read | Read all aspects of Virtual Visits |
> | microsoft.viva.glint/allEntities/allProperties/read | Read all Microsoft Viva Glint settings in the Microsoft 365 admin center |
> | microsoft.viva.goals/allEntities/allProperties/read | Read all aspects of Microsoft Viva Goals |
> | microsoft.viva.pulse/allEntities/allProperties/read | Read all aspects of Microsoft Viva Pulse |
> | microsoft.windows.updatesDeployments/allEntities/allProperties/read | Read all aspects of Windows Update Service |


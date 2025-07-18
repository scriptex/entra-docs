---
title: Configure Hootsuite for automatic user provisioning with Microsoft Entra ID
description: Learn how to automatically provision and de-provision user accounts from Microsoft Entra ID to Hootsuite.

author: thomasakelo
manager: mwongerapk
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: thomasakelo

# Customer intent: As an IT administrator, I want to learn how to automatically provision and deprovision user accounts from Microsoft Entra ID to Hootsuite so that I can streamline the user management process and ensure that users have the appropriate access to Hootsuite.
---

# Configure Hootsuite for automatic user provisioning with Microsoft Entra ID

This article describes the steps you need to do in both Hootsuite and Microsoft Entra ID to configure automatic user provisioning. When configured, Microsoft Entra ID automatically provisions and de-provisions users and groups to [Hootsuite](https://hootsuite.com/) using the Microsoft Entra provisioning service. For important details on what this service does, how it works, and frequently asked questions, see [Automate user provisioning and deprovisioning to SaaS applications with Microsoft Entra ID](~/identity/app-provisioning/user-provisioning.md).

## Capabilities supported
> [!div class="checklist"]
> * Create users in Hootsuite
> * Remove users in Hootsuite when they don't require access anymore
> * Keep user attributes synchronized between Microsoft Entra ID and Hootsuite
> * Provision groups and group memberships in Hootsuite
> * [Single sign-on](./hootsuite-tutorial.md) to Hootsuite (recommended)

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* A user account with [Hootsuite](http://www.hootsuite.com/) that has **Manage Member** permissions on the organization.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Step 1: Plan your provisioning deployment
1. Learn about [how the provisioning service works](~/identity/app-provisioning/user-provisioning.md).
2. Determine who's in [scope for provisioning](~/identity/app-provisioning/define-conditional-rules-for-provisioning-user-accounts.md).
3. Determine what data to [map between Microsoft Entra ID and Hootsuite](~/identity/app-provisioning/customize-application-attributes.md). 

<a name='step-2-configure-hootsuite-to-support-provisioning-with-azure-ad'></a>

## Step 2: Configure Hootsuite to support provisioning with Microsoft Entra ID

Reach out to your Hootsuite CSM for long lasting token required in later steps.

<a name='step-3-add-hootsuite-from-the-azure-ad-application-gallery'></a>

## Step 3: Add Hootsuite from the Microsoft Entra application gallery

Add Hootsuite from the Microsoft Entra application gallery to start managing provisioning to Hootsuite. If you have previously setup Hootsuite for SSO, you can use the same application. However it's recommended that you create a separate app when testing out the integration initially. Learn more about adding an application from the gallery [here](~/identity/enterprise-apps/add-application-portal.md). 

## Step 4: Define who is in scope for provisioning 

[!INCLUDE [create-assign-users-provisioning.md](~/identity/saas-apps/includes/create-assign-users-provisioning.md)]

## Step 5: Configure automatic user provisioning to Hootsuite 

This section guides you through the steps to configure the Microsoft Entra provisioning service to create, update, and disable users and groups in TestApp based on user and/or group assignments in Microsoft Entra ID.

<a name='to-configure-automatic-user-provisioning-for-hootsuite-in-azure-ad'></a>

### To configure automatic user provisioning for Hootsuite in Microsoft Entra ID:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps**

	![Enterprise applications blade](./media/hootsuite-provisioning-tutorial/enterprise-applications.png)

	![All applications blade](./media/hootsuite-provisioning-tutorial/all-applications.png)

1. In the applications list, select **Hootsuite**.

	![The Hootsuite link in the Applications list](common/all-applications.png)

3. Select the **Provisioning** tab. Select **Get started**.

	![Screenshot of the Manage options with the Provisioning option called out.](common/provisioning.png)

4. Set the **Provisioning Mode** to **Automatic**.

	![Screenshot of the Provisioning Mode dropdown list with the Automatic option called out.](common/provisioning-automatic.png)

5. Under the **Admin Credentials** section, input `https://platform.hootsuite.com/scim/v2` in Tenant URL. Input the long lasting secret token value retrieved earlier in **Step 2**. Select **Test Connection** to ensure Microsoft Entra ID can connect to Hootsuite. If the connection fails, ensure your Hootsuite account has admin permissions and try again.

 	![Screenshot shows the Admin Credentials dialog box, where you can enter your Tenant U R L and Secret Token.](./media/hootsuite-provisioning-tutorial/provisioning.png)

6. In the **Notification Email** field, enter the email address of a person or group who should receive the provisioning error notifications and select the **Send an email notification when a failure occurs** check box.

	![Notification Email](common/provisioning-notification-email.png)

7. Select **Save**.

8. Under the **Mappings** section, select **Provision Microsoft Entra users**.

9. Review the user attributes that are synchronized from Microsoft Entra ID to Hootsuite in the **Attribute-Mapping** section. The attributes selected as **Matching** properties are used to match the user accounts in Hootsuite for update operations. If you choose to change the [matching target attribute](~/identity/app-provisioning/customize-application-attributes.md), you need to ensure that the Hootsuite API supports filtering users based on that attribute. Select the **Save** button to commit any changes.

   |Attribute|Type|
   |---|---|
   |userName|String|
   |emails[type eq "work"].value|String|
   |active|Boolean|
   |displayName|String|
   |preferredLanguage|String|
   |timezone|String|
   |name.givenName|String|
   |name.familyName|String|

10. Under the **Mappings** section, select **Synchronize Microsoft Entra groups**.

11. Review the group attributes that are synchronized from Microsoft Entra ID to Hootsuite in the **Attribute-Mapping** section. The attributes selected as **Matching** properties are used to match the groups in Hootsuite for update operations. Select the **Save** button to commit any changes.

      |Attribute|Type|
      |---|---|
      |displayName|String|
      |externalId|String|
      |members|Reference|

12. To configure scoping filters, refer to the following instructions provided in the [Scoping filter  article](~/identity/app-provisioning/define-conditional-rules-for-provisioning-user-accounts.md).

13. To enable the Microsoft Entra provisioning service for Hootsuite, change the **Provisioning Status** to **On** in the **Settings** section.

	![Provisioning Status Toggled On](common/provisioning-toggle-on.png)

14. Define the users and groups that you would like to provision to Hootsuite by choosing the desired values in **Scope** in the **Settings** section.

	![Provisioning Scope](common/provisioning-scope.png)

15. When you're ready to provision, select **Save**.

	![Saving Provisioning Configuration](common/provisioning-configuration-save.png)

This operation starts the initial synchronization cycle of all users and groups defined in **Scope** in the **Settings** section. The initial cycle takes longer to complete than next cycles, which occur approximately every 40 minutes as long as the Microsoft Entra provisioning service is running. 

## Step 6: Monitor your deployment

[!INCLUDE [monitor-deployment.md](~/identity/saas-apps/includes/monitor-deployment.md)]

## Change log

* 10/22/2020 - Added support for User attributes "name.givenName" and "name.familyName". Custom extension attributes "organizationIds" and "teamIds" have been removed for Users.
Added support for Group attributes "displayName", "members" and "externalId".

## More resources

* [Managing user account provisioning for Enterprise Apps](~/identity/app-provisioning/configure-automatic-user-provisioning-portal.md)
* [What is application access and single sign-on with Microsoft Entra ID?](~/identity/enterprise-apps/what-is-single-sign-on.md)

## Related content

* [Learn how to review logs and get reports on provisioning activity](~/identity/app-provisioning/check-status-user-account-provisioning.md)

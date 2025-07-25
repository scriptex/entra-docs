---
title: Configure SolarWinds Service Desk (previously Samanage) for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and SolarWinds Service Desk (previously Samanage).
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and SolarWinds Service Desk so that I can control who has access to SolarWinds Service Desk, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure SolarWinds Service Desk (previously Samanage) for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate SolarWinds with Microsoft Entra ID. When you integrate SolarWinds with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to SolarWinds.
* Enable your users to be automatically signed-in to SolarWinds with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* SolarWinds single sign-on (SSO) enabled subscription.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* SolarWinds supports **SP** initiated SSO.
* SolarWinds supports [Automated user provisioning](samanage-provisioning-tutorial.md).

## Add SolarWinds from the gallery

To configure the integration of SolarWinds into Microsoft Entra ID, you need to add SolarWinds from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **SolarWinds** in the search box.
1. Select **SolarWinds** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-solarwinds'></a>

## Configure and test Microsoft Entra SSO for SolarWinds

Configure and test Microsoft Entra SSO with SolarWinds using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in SolarWinds.

To configure and test Microsoft Entra SSO with SolarWinds, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure SolarWinds SSO](#configure-solarwinds-sso)** - to configure the single sign-on settings on application side.
    1. **[Create SolarWinds test user](#create-solarwinds-test-user)** - to have a counterpart of B.Simon in SolarWinds that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **SolarWinds** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

	a. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<Company Name>.samanage.com/saml_login/<Company Name>`

    b. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://<Company Name>.samanage.com`

	> [!NOTE] 
	> These values aren't real. Update these values with the actual Sign-on URL and Identifier, which is explained later in the article. For more details contact [Samanage Client support team](https://www.samanage.com/support). You can also refer to the patterns shown in the **Basic SAML Configuration** section.

4. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Certificate (Base64)** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up SolarWinds** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure SolarWinds SSO

1. In a different web browser window, log into your SolarWinds company site as an administrator.

2. Select **Dashboard** and select **Setup** in left navigation pane.
   
    ![Dashboard](./media/samanage-tutorial/tutorial-samanage-1.png "Dashboard")

3. Select **Single Sign-On**.
   
    ![Single Sign-On](./media/samanage-tutorial/tutorial-samanage-2.png "Single Sign-On")

4. Navigate to **Login using SAML** section, perform the following steps:
   
    ![Login using SAML](./media/samanage-tutorial/tutorial-samanage-3.png "Login using SAML")
 
    a. Select **Enable Single Sign-On with SAML**.  
 
    b. In the **Identity Provider URL** textbox, enter the value like `https://YourAccountName.samanage.com`.
 
    c. Confirm the **Login URL** matches the **Sign On URL** of **Basic SAML Configuration** section in Azure portal.
 
    d. In the **Logout URL** textbox, enter the value of **Logout URL**..
 
    e. In the **SAML Issuer** textbox, type the app id URI set in your identity provider.
 
    f. Open your base-64 encoded certificate downloaded from Azure portal in notepad, copy the content of it into your clipboard, and then paste it to the **Paste your Identity Provider x.509 Certificate below** textbox.
 
    g. Select **Create users if they don't exist in SolarWinds**.
 
    h. Select **Update**.

### Create SolarWinds test user

To enable Microsoft Entra users to log in to SolarWinds, they must be provisioned into SolarWinds.  
In the case of SolarWinds, provisioning is a manual task.

**To provision a user account, perform the following steps:**

1. Log into your SolarWinds company site as an administrator.

2. Select **Dashboard** and select **Setup** in left navigation pan.
   
    ![Setup](./media/samanage-tutorial/tutorial-samanage-1.png "Setup")

3. Select the **Users** tab
   
    ![Users](./media/samanage-tutorial/tutorial-samanage-6.png "Users")

4. Select **New User**.
   
    ![New User](./media/samanage-tutorial/tutorial-samanage-7.png "New User")

5. Type the **Name** and the **Email Address** of a Microsoft Entra account you want to provision and select **Create user**.
   
    ![Create User](./media/samanage-tutorial/tutorial-samanage-8.png "Create User")
   
   >[!NOTE]
   >The Microsoft Entra account holder will receive an email and follow a link to confirm their account before it becomes active. You can use any other SolarWinds user account creation tools or APIs provided by SolarWinds to provision Microsoft Entra user accounts.

> [!NOTE]
> SolarWinds also supports automatic user provisioning, you can find more details [here](./samanage-provisioning-tutorial.md) on how to configure automatic user provisioning.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to SolarWinds Sign-on URL where you can initiate the login flow. 

* Go to SolarWinds Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the SolarWinds tile in the My Apps, this option redirects to SolarWinds Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure SolarWinds you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

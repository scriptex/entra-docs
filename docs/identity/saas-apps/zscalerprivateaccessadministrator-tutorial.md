---
title: Configure Zscaler Private Access Administrator for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Zscaler Private Access Administrator.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Zscaler Private Access Administrator so that I can control who has access to Zscaler Private Access Administrator, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Zscaler Private Access Administrator for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Zscaler Private Access Administrator with Microsoft Entra ID. When you integrate Zscaler Private Access Administrator with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Zscaler Private Access Administrator.
* Enable your users to be automatically signed-in to Zscaler Private Access Administrator with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Zscaler Private Access Administrator single sign-on enabled subscription.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Zscaler Private Access Administrator supports **SP** and **IDP** initiated SSO.

## Add Zscaler Private Access Administrator from the gallery

To configure the integration of Zscaler Private Access Administrator into Microsoft Entra ID, you need to add Zscaler Private Access Administrator from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Zscaler Private Access Administrator** in the search box.
1. Select **Zscaler Private Access Administrator** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-zscaler-private-access-administrator'></a>

## Configure and test Microsoft Entra SSO for Zscaler Private Access Administrator

Configure and test Microsoft Entra SSO with Zscaler Private Access Administrator using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Zscaler Private Access Administrator.

To configure and test Microsoft Entra SSO with Zscaler Private Access Administrator, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Zscaler Private Access Administrator SSO](#configure-zscaler-private-access-administrator-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Zscaler Private Access Administrator test user](#create-zscaler-private-access-administrator-test-user)** - to have a counterpart of B.Simon in Zscaler Private Access Administrator that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Zscaler Private Access Administrator** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, perform the following steps:

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.private.zscaler.com/auth/metadata`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.private.zscaler.com/auth/sso`

	c. Select **Set additional URLs**.

	d. In the **Relay State** text box, type a value:
    `idpadminsso`

1.  If you wish to configure the application in **SP** initiated mode, perform the following step:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.private.zscaler.com/auth/sso`   

    > [!NOTE]
    > These values aren't real. Update these values with the actual Identifier, Reply URL and Sign-on URL. Contact [Zscaler Private Access Administrator Client support team](https://help.zscaler.com/zpa-submit-ticket) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up Zscaler Private Access Administrator** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Zscaler Private Access Administrator SSO

1. In a different web browser window, sign to Zscaler Private Access Administrator as an Administrator.

2. On the top, select **Administration** and navigate to **AUTHENTICATION** section select **IdP Configuration**.

	![Zscaler Private Access Administrator admin](./media/zscalerprivateaccessadministrator-tutorial/admin.png)

3. In the top right corner, select **Add IdP Configuration**. 

	![Zscaler Private Access Administrator addidp](./media/zscalerprivateaccessadministrator-tutorial/add-configuration.png)

4. On the **Add IdP Configuration** page perform the following steps:
 
	![Zscaler Private Access Administrator idpselect](./media/zscalerprivateaccessadministrator-tutorial/select-file.png)

	a. Select **Select File** to upload the downloaded Metadata file from Microsoft Entra ID in the **IdP Metadata File Upload** field.

	b. It reads the **IdP metadata** from Microsoft Entra ID and populates all the fields information as shown below.

	![Zscaler Private Access Administrator idpconfig](./media/zscalerprivateaccessadministrator-tutorial/metadata.png)

	c. Select **Single Sign On** as **Administrator**.

	d. Select your domain from **Domains** field.
	
	e. Select **Save**.

### Create Zscaler Private Access Administrator test user

To enable Microsoft Entra users to sign in to Zscaler Private Access Administrator, they must be provisioned into Zscaler Private Access Administrator. In the case of Zscaler Private Access Administrator, provisioning is a manual task.

**To provision a user account, perform the following steps:**

1. Sign in to your Zscaler Private Access Administrator company site as an administrator.

2. On the top, select **Administration** and navigate to **AUTHENTICATION** section select **IdP Configuration**.

	![Zscaler Private Access Administrator admin](./media/zscalerprivateaccessadministrator-tutorial/admin.png)

3. Select **Administrators** from left side of the menu.

    ![Zscaler Private Access Administrator administrator](./media/zscalerprivateaccessadministrator-tutorial/administrator.png)

4. In the top right corner, select **Add Administrator**:

	![Zscaler Private Access Administrator add admin](./media/zscalerprivateaccessadministrator-tutorial/add-administrator.png)

5. In the **Add Administrator** page, perform the following steps:

	![Zscaler Private Access Administrator user admin](./media/zscalerprivateaccessadministrator-tutorial/user-admin.png)

	a. In the **Username** textbox, enter the email of user like BrittaSimon@contoso.com.

	b. In the **Password** textbox, type the Password.

	c. In the **Confirm Password** textbox, type the Password.

	d. Select **Role** as **Zscaler Private Access Administrator**.

	e. In the **Email** textbox, enter the email of user like BrittaSimon@contoso.com.

	f. In the **Phone** textbox, type the Phone number.

	g. In the **Timezone** textbox, select the Timezone.

    h. Select **Save**.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to Zscaler Private Access Administrator Sign on URL where you can initiate the login flow.  

* Go to Zscaler Private Access Administrator Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the Zscaler Private Access Administrator for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the Zscaler Private Access Administrator tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Zscaler Private Access Administrator for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Zscaler Private Access Administrator you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

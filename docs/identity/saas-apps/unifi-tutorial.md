---
title: Configure UNIFI for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and UNIFI.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and UNIFI so that I can control who has access to UNIFI, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure UNIFI for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate UNIFI with Microsoft Entra ID. When you integrate UNIFI with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to UNIFI.
* Enable your users to be automatically signed-in to UNIFI with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* UNIFI single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* UNIFI supports **SP and IDP** initiated SSO.
* UNIFI supports **Automated** user provisioning.

## Add UNIFI from the gallery

To configure the integration of UNIFI into Microsoft Entra ID, you need to add UNIFI from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **UNIFI** in the search box.
1. Select **UNIFI** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-unifi'></a>

## Configure and test Microsoft Entra SSO for UNIFI

Configure and test Microsoft Entra SSO with UNIFI using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in UNIFI.

To configure and test Microsoft Entra SSO with UNIFI, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure UNIFI SSO](#configure-unifi-sso)** - to configure the single sign-on settings on application side.
    1. **[Create UNIFI test user](#create-unifi-test-user)** - to have a counterpart of B.Simon in UNIFI that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **UNIFI** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, If you wish to configure the application in **IDP** initiated mode, perform the following steps:

    In the **Identifier** text box, type the URL: `INVIEWlabs`

5. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type the URL:
    `https://app.discoverunifi.com/login`

6. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Certificate (Base64)** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

7. On the **Set up UNIFI** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure UNIFI SSO

1. In a different web browser window, sign on to your **UNIFI** company site as administrator.

2. Select the **Users**.

	![Screenshot shows Users selected from the UNIFI site.](./media/unifi-tutorial/app-1.png)

3. Select the **Add New Identity Provider**.

	![Screenshot shows Ad New Identity Provider selected.](./media/unifi-tutorial/app-2.png)

4. In the **Add Identity Provider** section, perform the following steps:

	![Screenshot shows the Add Identity Provider where you can enter the values described.](./media/unifi-tutorial/app-3.png) 

	a. In the **Provider Name** textbox, type the name of the Identity Provider..

	b. In the **Provider URL** textbox paste the **Login URL** value.

	c. Open the Certificate that you have downloaded in notepad, remove the **---BEGIN CERTIFICATE---** and **---END CERTIFICATE---** tag and then paste the remaining content in the **Certificate** textbox.

	d. Select the **is Default Provider** checkbox.

### Create UNIFI test user

In this section, you create a user called Britta Simon. **UNIFI** supports automatic user provisioning so no manual steps are required. Users are created automatically after successful authentication from the Microsoft Entra ID.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to UNIFI Sign on URL where you can initiate the login flow.  

* Go to UNIFI Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the UNIFI for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the UNIFI tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the UNIFI for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure UNIFI you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

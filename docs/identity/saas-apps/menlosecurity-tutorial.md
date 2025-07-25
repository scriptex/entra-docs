---
title: Configure Menlo Security for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Menlo Security.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Menlo Security so that I can control who has access to Menlo Security, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Menlo Security for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Menlo Security with Microsoft Entra ID. When you integrate Menlo Security with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Menlo Security.
* Enable your users to be automatically signed-in to Menlo Security with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Menlo Security single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Menlo Security supports **SP** initiated SSO.

## Add Menlo Security from the gallery

To configure the integration of Menlo Security into Microsoft Entra ID, you need to add Menlo Security from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Menlo Security** in the search box.
1. Select **Menlo Security** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-menlo-security'></a>

## Configure and test Microsoft Entra SSO for Menlo Security

Configure and test Microsoft Entra SSO with Menlo Security using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Menlo Security.

To configure and test Microsoft Entra SSO with Menlo Security, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Menlo Security SSO](#configure-menlo-security-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Menlo Security test user](#create-menlo-security-test-user)** - to have a counterpart of B.Simon in Menlo Security that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Menlo Security** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    1. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.menlosecurity.com/account/login`

    1. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.menlosecurity.com/safeview-auth-server/saml/metadata`

    > [!NOTE]
    > These values aren't real. Update these values with the actual Sign on URL and Identifier. Contact [Menlo Security Client support team](https://www.menlosecurity.com/menlo-contact) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Certificate (Base64)** from the given options as per your requirement and save it on your computer.

    ![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Menlo Security** section, copy the appropriate URL(s) as per your requirement.

    ![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Menlo Security SSO

1. To configure single sign-on on **Menlo Security** side, login to the **Menlo Security** website as an administrator.

2. Under **Settings** go to **Authentication** and perform following actions:

    ![Configure Single Sign-On](./media/menlosecurity-tutorial/authentication.png)

    1. Tick the checkbox **Enable user authentication using SAML**.

    1. Select **Allow External Access** to **Yes**.

    1. Under **SAML Provider**, select **Microsoft Entra ID**.

    1. **SAML 2.0 Endpoint** : Paste the **Login URL**..

    1. **Service Identifier (Issuer)** : Paste the **Microsoft Entra Identifier**..

    1. **X.509 Certificate** : Open the **Certificate (Base64)** downloaded in notepad and paste it in this box.

    1. Select **Save** to save the settings.

### Create Menlo Security test user

In this section, you create a user called Britta Simon in Menlo Security. Work with [Menlo Security Client support team](https://www.menlosecurity.com/menlo-contact) to add the users in the Menlo Security platform. Users must be created and activated before you use single sign-on.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Menlo Security Sign-on URL where you can initiate the login flow. 

* Go to Menlo Security Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Menlo Security tile in the My Apps, this option redirects to Menlo Security Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Menlo Security you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

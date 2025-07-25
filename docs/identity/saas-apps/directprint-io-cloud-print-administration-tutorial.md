---
title: Configure directprint.io Cloud Print Administration for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and directprint.io Cloud Print Administration.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and directprint.io Cloud Print Administration so that I can control who has access to directprint.io Cloud Print Administration, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure directprint.io Cloud Print Administration for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate directprint.io Cloud Print Administration with Microsoft Entra ID. When you integrate directprint.io Cloud Print Administration with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to directprint.io Cloud Print Administration.
* Enable your users to be automatically signed-in to directprint.io Cloud Print Administration with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* directprint.io Cloud Print Administration single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* directprint.io Cloud Print Administration supports **IDP** initiated SSO.

* directprint.io Cloud Print Administration supports **Just In Time** user provisioning.

## Add directprint.io Cloud Print Administration from the gallery

To configure the integration of directprint.io Cloud Print Administration into Microsoft Entra ID, you need to add directprint.io Cloud Print Administration from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **directprint.io Cloud Print Administration** in the search box.
1. Select **directprint.io Cloud Print Administration** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-directprintio-cloud-print-administration'></a>

## Configure and test Microsoft Entra SSO for directprint.io Cloud Print Administration

Configure and test Microsoft Entra SSO with directprint.io Cloud Print Administration using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in directprint.io Cloud Print Administration.

To configure and test Microsoft Entra SSO with directprint.io Cloud Print Administration, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure directprint.io Cloud Print Administration SSO](#configure-directprintio-cloud-print-administration-sso)** - to configure the single sign-on settings on application side.
    1. **[Create directprint.io Cloud Print Administration test user](#create-directprintio-cloud-print-administration-test-user)** - to have a counterpart of B.Simon in directprint.io Cloud Print Administration that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **directprint.io Cloud Print Administration** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section the application is pre-configured in IDP initiated mode and the necessary URLs are already pre-populated with Azure. The user needs to save the configuration by selecting the **Save** button.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

1. On the **Set up directprint.io Cloud Print Administration** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure directprint.io Cloud Print Administration SSO

To configure single sign-on on **directprint.io Cloud Print Administration** side, you need to send the **App Federation Metadata Url** to [directprint.io Cloud Print Administration support team](mailto:support@directprint.io). They set this setting to have the SAML SSO connection set properly on both sides.

### Create directprint.io Cloud Print Administration test user

In this section, a user called B.Simon is created in directprint.io Cloud Print Administration. directprint.io Cloud Print Administration supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in directprint.io Cloud Print Administration, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options.

* Select **Test this application**, and you should be automatically signed in to the directprint.io Cloud Print Administration for which you set up the SSO.

* You can use Microsoft My Apps. When you select the directprint.io Cloud Print Administration tile in the My Apps, you should be automatically signed in to the directprint.io Cloud Print Administration for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure directprint.io Cloud Print Administration you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

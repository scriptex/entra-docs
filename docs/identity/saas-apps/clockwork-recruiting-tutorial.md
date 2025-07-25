---
title: Configure Clockwork Recruiting for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Clockwork Recruiting.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Clockwork Recruiting so that I can control who has access to Clockwork Recruiting, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Clockwork Recruiting for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Clockwork Recruiting with Microsoft Entra ID. When you integrate Clockwork Recruiting with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Clockwork Recruiting.
* Enable your users to be automatically signed-in to Clockwork Recruiting with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Clockwork Recruiting single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Clockwork Recruiting supports **SP** initiated SSO.

## Add Clockwork Recruiting from the gallery

To configure the integration of Clockwork Recruiting into Microsoft Entra ID, you need to add Clockwork Recruiting from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Clockwork Recruiting** in the search box.
1. Select **Clockwork Recruiting** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-clockwork-recruiting'></a>

## Configure and test Microsoft Entra SSO for Clockwork Recruiting

Configure and test Microsoft Entra SSO with Clockwork Recruiting using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Clockwork Recruiting.

To configure and test Microsoft Entra SSO with Clockwork Recruiting, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Clockwork Recruiting SSO](#configure-clockwork-recruiting-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Clockwork Recruiting test user](#create-clockwork-recruiting-test-user)** - to have a counterpart of B.Simon in Clockwork Recruiting that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Clockwork Recruiting** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

    ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    1. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.clockworkrecruiting.com/sp`

    1. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.clockworkrecruiting.com/session/new`

        > [!NOTE]
        > These values aren't real. Update these values with the actual Identifier and Sign on URL. Contact [Clockwork Recruiting Client support team](mailto:support@clockworkrecruiting.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

    ![The Certificate download link](common/copy-metadataurl.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Clockwork Recruiting SSO

To configure single sign-on on **Clockwork Recruiting** side, you need to send the **App Federation Metadata Url** to [Clockwork Recruiting support team](mailto:support@clockworkrecruiting.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Clockwork Recruiting test user

In this section, you create a user called Britta Simon in Clockwork Recruiting. Work with [Clockwork Recruiting support team](mailto:support@clockworkrecruiting.com) to add the users in the Clockwork Recruiting platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**. You're redirected to the Clockwork Recruiting Sign-on URL where you can initiate the login flow. 
* Go to the Clockwork Recruiting Sign-on URL directly and initiate the login flow from there.
* You can use Microsoft My Apps. When you select the Clockwork Recruiting tile in My Apps, you're redirected the to Clockwork Recruiting Sign-on URL. For more information about My Apps, see [Introduction to My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

After you configure Clockwork Recruiting you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

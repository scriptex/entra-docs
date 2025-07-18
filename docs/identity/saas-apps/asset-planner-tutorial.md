---
title: Configure Asset Planner for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Asset Planner.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Asset Planner so that I can control who has access to Asset Planner, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Asset Planner for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Asset Planner with Microsoft Entra ID. When you integrate Asset Planner with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Asset Planner.
* Enable your users to be automatically signed-in to Asset Planner with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Asset Planner single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Asset Planner supports **SP** initiated SSO.

* Asset Planner supports **Just In Time** user provisioning.

## Add Asset Planner from the gallery

To configure the integration of Asset Planner into Microsoft Entra ID, you need to add Asset Planner from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Asset Planner** in the search box.
1. Select **Asset Planner** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-asset-planner'></a>

## Configure and test Microsoft Entra SSO for Asset Planner

Configure and test Microsoft Entra SSO with Asset Planner using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Asset Planner.

To configure and test Microsoft Entra SSO with Asset Planner, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Asset Planner SSO](#configure-asset-planner-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Asset Planner test user](#create-asset-planner-test-user)** - to have a counterpart of B.Simon in Asset Planner that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Asset Planner** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier (Entity ID)** text box, type one of the following URLs:

    | **Identifier** |
    |---------|
    | `https://assetplanner.com` |
    | `https://us.assetplanner.com` |
    | `https://staging.assetplanner.com` |
    | `https://training.assetplanner.com` |

	b. In the **Reply URL** text box, type a URL using one of the following patterns:

    | **Reply URL** |
    |------|
    | `https://assetplanner.com/saml/ap_acs/<IDPName>` |
    | `https://us.assetplanner.com/saml/ap_acs/<IDPName>` |
    | `https://staging.assetplanner.com/saml/ap_acs/<IDPName>` |
    | `https://training.assetplanner.com/saml/ap_acs/<IDPName>` |
    
    c. In the **Sign on URL** text box, type one of the following URLs:
    
    | **Sign on URL** |
    |-----|
    | `https://assetplanner.com` |
    | `https://us.assetplanner.com` |
    | `https://staging.assetplanner.com` |
    | `https://training.assetplanner.com` |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Asset Planner** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Asset Planner SSO

To configure single sign-on on **Asset Planner** side, you need to send the downloaded **Certificate (Base64)** and appropriate copied URLs from the application configuration to [Asset Planner support team](mailto:support@assetplanner.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Asset Planner test user

In this section, a user called Britta Simon is created in Asset Planner. Asset Planner supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in Asset Planner, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Asset Planner Sign-on URL where you can initiate the login flow. 

* Go to Asset Planner Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Asset Planner tile in the My Apps, this option redirects to Asset Planner Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure Asset Planner you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).

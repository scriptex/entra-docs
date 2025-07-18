---
title: Configure 4me for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and 4me.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and 4me so that I can control who has access to 4me, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure 4me for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate 4me with Microsoft Entra ID. When you integrate 4me with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to 4me.
* Enable your users to be automatically signed-in to 4me with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* 4me single sign-on (SSO) enabled subscription.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* 4me supports **SP** initiated SSO.
* 4me supports **Just In Time** user provisioning.
* 4me supports [Automated user provisioning](4me-provisioning-tutorial.md).

## Add 4me from the gallery

To configure the integration of 4me into Microsoft Entra ID, you need to add 4me from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **4me** in the search box.
1. Select **4me** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-4me'></a>

## Configure and test Microsoft Entra SSO for 4me

Configure and test Microsoft Entra SSO with 4me using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in 4me.

To configure and test Microsoft Entra SSO with 4me, complete the following building blocks:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure 4me SSO](#configure-4me-sso)** - to configure the single sign-on settings on application side.
    1. **[Create 4me test user](#create-4me-test-user)** - to have a counterpart of B.Simon in 4me that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **4me** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, enter the values for the following fields:

	a. In the **Sign on URL** text box, type a URL using one of the following patterns:

	| Environment| URL|
	|---|---|
	| PRODUCTION | `https://<SUBDOMAIN>.4me.com`|
	| QA| `https://<SUBDOMAIN>.4me.qa`|
	| | |

    b. In the **Identifier (Entity ID)** text box, type a URL using one of the following patterns:

	| Environment| URL|
	|---|---|
	| PRODUCTION | `https://<SUBDOMAIN>.4me.com`|
	| QA| `https://<SUBDOMAIN>.4me.qa`|
	| | |

	> [!NOTE]
	> These values aren't real. Update these values with the actual Sign on URL and Identifier. Contact [4me Client support team](mailto:support@4me.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. 4me application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, 4me application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name | Source Attribute|
	| ---------------| --------------- |
	| first_name | user.givenname |
	| last_name | user.surname |

1. In the **SAML Signing Certificate** section, select **Edit** button to open **SAML Signing Certificate** dialog.

	![Edit SAML Signing Certificate](common/edit-certificate.png)

1. In the **SAML Signing Certificate** section, copy the **THUMBPRINT** and save it on your computer.

    ![Copy Thumbprint value](common/copy-thumbprint.png)

1. On the **Set up 4me** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure 4me SSO

1. In a different web browser window, sign in to 4me as an Administrator.

1. On the top left, select **Settings** logo and on the left side bar select **Single Sign-On**.

    ![4me settings](./media/4me-tutorial/settings.png)

1. On the **Single Sign-On** page, perform the following steps:

	![4me singleasignon](./media/4me-tutorial/single-sign-on.png)

	a. Select the **Enabled** option.

	b. In the **Remote logout URL** textbox, paste the value of **Logout URL**, which you copied previously.

	c. Under **SAML** section, in the **SAML SSO URL** textbox, paste the value of **Login URL**, which you copied previously.

	d. In the **Certificate fingerprint** textbox, paste the **THUMBPRINT** value separated by a colon in duplets order (AA:BB:CC:DD:EE:FF:GG:HH:II), which you copied previously.

	e. Select **Save**.

### Create 4me test user

In this section, a user called Britta Simon is created in 4me. 4me supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in 4me, a new one is created after authentication.

> [!Note]
> If you need to create a user manually, contact [4me support team](mailto:support@4me.com).

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to 4me Sign-on URL where you can initiate the login flow. 

* Go to 4me Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the 4me tile in the My Apps, this option redirects to 4me Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure 4me you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

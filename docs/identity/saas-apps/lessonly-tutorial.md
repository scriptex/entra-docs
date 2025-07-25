---
title: Configure Lessonly for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Lessonly.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Lessonly so that I can control who has access to Lessonly, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Lessonly for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Lessonly with Microsoft Entra ID. When you integrate Lessonly with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Lessonly.
* Enable your users to be automatically signed-in to Lessonly with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Lessonly single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Lessonly supports **SP** initiated SSO.
* Lessonly supports **Just In Time** user provisioning.

## Add Lessonly from the gallery

To configure the integration of Lessonly into Microsoft Entra ID, you need to add Lessonly from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Lessonly** in the search box.
1. Select **Lessonly** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-lessonly'></a>

## Configure and test Microsoft Entra SSO for Lessonly

Configure and test Microsoft Entra SSO with Lessonly using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Lessonly.

To configure and test Microsoft Entra SSO with Lessonly, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Lessonly SSO](#configure-lessonly-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Lessonly test user](#create-lessonly-test-user)** - to have a counterpart of B.Simon in Lessonly that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Lessonly** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, enter the values for the following fields:

    a. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<companyname>.lessonly.com/auth/saml`

	> [!NOTE]
	> When referencing a generic name that **companyname** needs to be replaced by an actual name.
	
    b. In the **Reply URL (Assertion Customer Service URL)** text box, type a URL using the following pattern:
    `https://<companyname>.lessonly.com/auth/saml/callback`

    c. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://<companyname>.lessonly.com/auth/saml/metadata`
    
	> [!NOTE]
	> These values aren't real. Update these values with the actual Sign on URL, Reply URL, and Identifier. Contact [Lessonly.com Client support team](mailto:support@lessonly.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. Lessonly application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, Lessonly application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.

    | Name | Source Attribute|
	| ---------------  | ----------------|
	| urn:oid:2.5.4.42 | user.givenname |
	| urn:oid:2.5.4.4  | user.surname |
	| urn:oid:0.9.2342.19200300.100.1.3 | user.mail |
	| urn:oid:1.3.6.1.4.1.5923.1.1.1.10 | user.objectid |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Lessonly** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Lessonly SSO

To configure single sign-on on **Lessonly** side, you need to send the downloaded **Certificate (Base64)** and appropriate copied URLs from the application configuration to [Lessonly support team](mailto:support@lessonly.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Lessonly test user

The objective of this section is to create a user called B.Simon in Lessonly.com. Lessonly.com supports just-in-time provisioning, which is by default enabled.

There's no action item for you in this section. A new user is created during an attempt to access Lessonly.com if it doesn't exist yet.

> [!NOTE]
> If you need to create a user manually, you need to contact the [Lessonly.com support team](mailto:support@lessonly.com).

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Lessonly Sign-on URL where you can initiate the login flow. 

* Go to Lessonly Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Lessonly tile in the My Apps, this option redirects to Lessonly Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Lessonly you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

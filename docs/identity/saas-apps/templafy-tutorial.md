---
title: Configure Templafy SAML2 for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Templafy SAML2.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Templafy SAML2 so that I can control who has access to Templafy SAML2, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Templafy SAML2 for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Templafy SAML2 with Microsoft Entra ID. When you integrate Templafy SAML2 with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Templafy SAML2.
* Enable your users to be automatically signed-in to Templafy SAML2 with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Templafy SAML2 single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Templafy SAML2 supports **SP** initiated SSO.
* Templafy SAML2 supports **Just In Time** user provisioning.
* Templafy SAML2 supports [Automated user provisioning](templafy-saml-2-provisioning-tutorial.md).

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add Templafy SAML2 from the gallery

To configure the integration of Templafy SAML2 into Microsoft Entra ID, you need to add Templafy SAML2 from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Templafy SAML2** in the search box.
1. Select **Templafy SAML2** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-templafy-saml2'></a>

## Configure and test Microsoft Entra SSO for Templafy SAML2

Configure and test Microsoft Entra SSO with Templafy SAML2 using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Templafy SAML2.

To configure and test Microsoft Entra SSO with Templafy SAML2, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Templafy SAML2 SSO](#configure-templafy-saml2-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Templafy SAML2 test user](#create-templafy-saml2-test-user)** - to have a counterpart of B.Simon in Templafy SAML2 that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Templafy SAML2** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following step:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<CLIENT_SUBDOMAIN>.templafy.com`

	> [!NOTE]
	> The value isn't real. Update the value with the actual Sign-On URL. Contact [Templafy SAML2 Client support team](mailto:support@templafy.com) to get the value. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. Templafy SAML2 application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, Templafy SAML2 application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name | Source Attribute| Namespace  |
	| ---------------| --------------- | --------- |
	| givenname | user.givenname | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims` |
	| surname | user.surname | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| emailaddress | user.mail | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`
	| streetaddress | user.streetaddress | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| city | user.city | `http://schemas.templafy.com/2016/06/identity/claims`|
	| postalcode | user.postalcode | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| stateorprovince | user.state | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| country | user.country | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| jobtitle | user.jobtitle | `http://schemas.templafy.com/2016/06/identity/claims`|
	| department | user.department | `http://schemas.templafy.com/2016/06/identity/claims`|
	| phonenumber | user.telephonenumber | `http://schemas.templafy.com/2016/06/identity/claims` |
	| facsimilenumber | user.facsimiletelephonenumber | `http://schemas.templafy.com/2016/06/identity/claims`|
	| upn | user.userprincipalname | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| nameidentifier | user.mail | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`|
	| | |

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Templafy SAML2 SSO

To configure single sign-on on **Templafy SAML2** side, you need to send the **App Federation Metadata Url** to [Templafy SAML2 support team](mailto:support@templafy.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Templafy SAML2 test user

In this section, a user called B.Simon is created in Templafy SAML2. Templafy SAML2 supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in Templafy SAML2, a new one is created after authentication.

Templafy SAML2 also supports automatic user provisioning, you can find more details [here](./templafy-saml-2-provisioning-tutorial.md) on how to configure automatic user provisioning.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Templafy SAML2 Sign-on URL where you can initiate the login flow. 

* Go to Templafy SAML2 Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Templafy SAML2 tile in the My Apps, this option redirects to Templafy SAML2 Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Templafy SAML2 you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

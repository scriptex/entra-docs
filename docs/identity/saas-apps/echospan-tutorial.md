---
title: Configure EchoSpan for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and EchoSpan.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and EchoSpan so that I can control who has access to EchoSpan, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure EchoSpan for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate EchoSpan with Microsoft Entra ID. When you integrate EchoSpan with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to EchoSpan.
* Enable your users to be automatically signed-in to EchoSpan with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* EchoSpan single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* EchoSpan supports **SP and IDP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add EchoSpan from the gallery

To configure the integration of EchoSpan into Microsoft Entra ID, you need to add EchoSpan from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **EchoSpan** in the search box.
1. Select **EchoSpan** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-echospan'></a>

## Configure and test Microsoft Entra SSO for EchoSpan

Configure and test Microsoft Entra SSO with EchoSpan using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in EchoSpan.

To configure and test Microsoft Entra SSO with EchoSpan, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure EchoSpan SSO](#configure-echospan-sso)** - to configure the single sign-on settings on application side.
    1. **[Create EchoSpan test user](#create-echospan-test-user)** - to have a counterpart of B.Simon in EchoSpan that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **EchoSpan** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, the user doesn't have to perform any step as the app is already pre-integrated with Azure.

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **SP** initiated mode then perform the following steps:

    a. In the **Identifier** textbox, type the value:
    `EchoSpanServiceProvider`

    b. In the **Reply URL** textbox, type the URL:
    `https://ssoeasy.echospan.com/easyconnect/ACS/Post.aspx`

    c. In the **Sign-on URL** text box, type the URL:
    `https://ssoeasy.echospan.com/easyconnect/ARS/SOAP.aspx`

1. Select **Save**.

1. EchoSpan application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, EchoSpan application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.
	
	| Name |  Source Attribute|
	| -----------| --------- |
	| email | user.mail |
    | clientid | static |

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up EchoSpan** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure EchoSpan SSO

To configure single sign-on on **EchoSpan** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [EchoSpan support team](mailto:support@echospan.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create EchoSpan test user

In this section, you create a user called Britta Simon in EchoSpan. Work with [EchoSpan support team](mailto:support@echospan.com) to add the users in the EchoSpan platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to EchoSpan Sign on URL where you can initiate the login flow.  

* Go to EchoSpan Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the EchoSpan for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the EchoSpan tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the EchoSpan for which you set up the SSO. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure EchoSpan you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).

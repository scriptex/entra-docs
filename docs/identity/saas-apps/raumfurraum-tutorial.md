---
title: Configure raum]für[raum for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and raum]für[raum.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and raum]fÃ¼r[raum so that I can control who has access to raum]fÃ¼r[raum, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure raum]für[raum for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate raum]für[raum with Microsoft Entra ID. When you integrate raum]für[raum with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to raum]für[raum.
* Enable your users to be automatically signed-in to raum]für[raum with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* raum]für[raum single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* raum]für[raum supports **SP and IDP** initiated SSO.
* raum]für[raum supports **Just In Time** user provisioning.

## Add raum]für[raum from the gallery

To configure the integration of raum]für[raum into Microsoft Entra ID, you need to add raum]für[raum from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **raum]für[raum** in the search box.
1. Select **raum]für[raum** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-raumfrraum'></a>

## Configure and test Microsoft Entra SSO for raum]für[raum

Configure and test Microsoft Entra SSO with raum]für[raum using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in raum]für[raum.

To configure and test Microsoft Entra SSO with raum]für[raum, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure raumfurraum SSO](#configure-raumfurraum-sso)** - to configure the single sign-on settings on application side.
    1. **[Create raumfurraum test user](#create-raumfurraum-test-user)** - to have a counterpart of B.Simon in raum]für[raum linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **raum]für[raum** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, perform the following steps:

    a. In the **Identifier** text box, type a URL using one of the following patterns:

    |Identifier|
    |----------|
    |`<CUSTOMER_NAME>.raumfuerraum.de`|
    |`<CUSTOMER_NAME>.rfr.md.intra`|

    b. In the **Reply URL** text box, type a URL using one of the following patterns:

    |Reply URL|
    |----------|
    |`https://<CUSTOMER_NAME>.raumfuerraum.de`|
    |`https://<CUSTOMER_NAME>.rfr.md.intra`|

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using one of the following patterns:

    |Sign-on URL|
    |----------|
    |`https://<CUSTOMER_NAME>.raumfuerraum.de/saml.php`|
    |`https://<CUSTOMER_NAME>.rfr.md.intra/saml.php`|

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier, Reply URL, and Sign-on URL. Contact [raumfurraum Client support team](mailto:it@mediadialog.de) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up raum]für[raum** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure raumfurraum SSO

To configure single sign-on on **raum]für[raum** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [raumfurraum support team](mailto:it@mediadialog.de). They set this setting to have the SAML SSO connection set properly on both sides.

### Create raumfurraum test user

In this section, a user called Britta Simon is created in raum]für[raum. raum]für[raum supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in raum]für[raum, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, in Azure portal, this option redirects to raum]für[raum Sign-on URL where you can initiate the sign-in flow.  

* Go to raum]für[raum Sign-on URL directly and initiate the sign-in flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the raum]für[raum for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the raum]für[raum tile in the My Apps, if configured in SP mode you would be redirected to the application sign-in page for initiating the sign-in flow and if configured in IDP mode, you should be automatically signed in to the raum]für[raum for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content
Once you configure raum]für[raum you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

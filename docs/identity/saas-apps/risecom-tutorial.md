---
title: Configure Rise.com for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Rise.com.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Rise.com so that I can control who has access to Rise.com, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Rise.com for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Rise.com with Microsoft Entra ID. When you integrate Rise.com with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Rise.com.
* Enable your users to be automatically signed-in to Rise.com with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

To get started, you need the following items:

* A Microsoft Entra subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Rise.com single sign-on (SSO) enabled subscription.
* Along with Cloud Application Administrator, Application Administrator can also add or manage applications in Microsoft Entra ID.
For more information, see [Azure built-in roles](~/identity/role-based-access-control/permissions-reference.md).

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Rise.com supports **SP** and **IDP** initiated SSO.
* Rise.com supports **Just In Time** user provisioning.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add Rise.com from the gallery

To configure the integration of Rise.com into Microsoft Entra ID, you need to add Rise.com from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Rise.com** in the search box.
1. Select **Rise.com** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-risecom'></a>

## Configure and test Microsoft Entra SSO for Rise.com

Configure and test Microsoft Entra SSO with Rise.com using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Rise.com.

To configure and test Microsoft Entra SSO with Rise.com, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Rise.com SSO](#configure-risecom-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Rise.com test user](#create-risecom-test-user)** - to have a counterpart of B.Simon in Rise.com that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Rise.com** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

    ![Screenshot shows to edit Basic S A M L Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, the user doesn't have to perform any step as the app is already pre-integrated with Azure.

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:    

    a. In the **Sign-on URL** text box, type the URL:
    `https://id.rise.com/sso/saml2`

    b. In the **Relay State** text box, type a URL using the following pattern:
    `https://<CustomerDomainName>.rise.com`

    > [!Note]
    > This value isn't real. Update this value with the actual Relay State URL. Contact [Rise.com support team](mailto:Enterprise@rise.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. Rise.com application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

    ![Screenshot shows the image of attributes.](common/default-attributes.png "Attributes")

1. The Rise.com application expects the default attributes to be replaced with the specific attributes as shown below. These attributes are also pre populated but you can review them as per your requirements.

    | Name | Source Attribute|
    | ------------ | --------- |    
    | firstName | user.givenname |
    | lastName | user.surname |
    | email | user.mail |
    
1. On the **Set-up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

    ![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

1. On the **Set up Rise.com** section, copy the appropriate URL(s) based on your requirement.

	![Screenshot shows to copy configuration appropriate U R L.](common/copy-configuration-urls.png "Metadata")  

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Rise.com SSO

To configure single sign-on on **Rise.com** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [Rise.com support team](mailto:Enterprise@rise.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Rise.com test user

In this section, a user called B.Simon is created in Rise.com. Rise.com supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in Rise.com, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to Rise.com Sign-On URL where you can initiate the login flow.  

* Go to Rise.com Sign-On URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the Rise.com for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the Rise.com tile in the My Apps, if configured in SP mode you would be redirected to the application sign-on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Rise.com for which you set up the SSO. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure Rise.com you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).

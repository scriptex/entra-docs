---
title: Configure Manabi Pocket for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Manabi Pocket.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Manabi Pocket so that I can control who has access to Manabi Pocket, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Manabi Pocket for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Manabi Pocket with Microsoft Entra ID. When you integrate Manabi Pocket with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Manabi Pocket.
* Enable your users to be automatically signed-in to Manabi Pocket with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

To configure Microsoft Entra integration with Manabi Pocket, you need the following items:

* A Microsoft Entra subscription. If you don't have a Microsoft Entra environment, you can get a [free account](https://azure.microsoft.com/free/).
* Manabi Pocket single sign-on enabled subscription.
* Along with Cloud Application Administrator, Application Administrator can also add or manage applications in Microsoft Entra ID.
For more information, see [Azure built-in roles](~/identity/role-based-access-control/permissions-reference.md).

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Manabi Pocket supports **SP** initiated SSO.

## Add Manabi Pocket from the gallery

To configure the integration of Manabi Pocket into Microsoft Entra ID, you need to add Manabi Pocket from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Manabi Pocket** in the search box.
1. Select **Manabi Pocket** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-manabi-pocket'></a>

## Configure and test Microsoft Entra SSO for Manabi Pocket

Configure and test Microsoft Entra SSO with Manabi Pocket using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Manabi Pocket.

To configure and test Microsoft Entra SSO with Manabi Pocket, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Manabi Pocket SSO](#configure-manabi-pocket-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Manabi Pocket test user](#create-manabi-pocket-test-user)** - to have a counterpart of B.Simon in Manabi Pocket that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Manabi Pocket** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://<SERVER-NAME>.ed-cl.com/<TENANT-ID>/idp/provider`
    
	b. In the **Sign on URL** text box, type the URL:
    `https://ed-cl.com/`

	> [!NOTE]
	> The Identifier value isn't real. Update this value with the actual Identifier. Contact [Manabi Pocket Client support team](mailto:info-ed-cl@ntt.com) to get the value. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

6. On the **Set up Manabi Pocket** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Manabi Pocket SSO

To configure single sign-on on **Manabi Pocket** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [Manabi Pocket support team](mailto:info-ed-cl@ntt.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Manabi Pocket test user

In this section, you create a user called Britta Simon in Manabi Pocket. Work with [Manabi Pocket support team](mailto:info-ed-cl@ntt.com) to add the users in the Manabi Pocket platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Manabi Pocket Sign-on URL where you can initiate the login flow. 

* Go to Manabi Pocket Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Manabi Pocket tile in the My Apps, this option redirects to Manabi Pocket Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure Manabi Pocket you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).

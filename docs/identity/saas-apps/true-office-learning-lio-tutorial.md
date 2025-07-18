---
title: Configure True Office Learning - LIO for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and True Office Learning - LIO.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and True Office Learning - LIO so that I can control who has access to True Office Learning - LIO, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure True Office Learning - LIO for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate True Office Learning - LIO with Microsoft Entra ID. When you integrate True Office Learning - LIO with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to True Office Learning - LIO.
* Enable your users to be automatically signed-in to True Office Learning - LIO with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* True Office Learning - LIO single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* True Office Learning - LIO supports **SP** initiated SSO.

## Add True Office Learning - LIO from the gallery

To configure the integration of True Office Learning - LIO into Microsoft Entra ID, you need to add True Office Learning - LIO from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **True Office Learning - LIO** in the search box.
1. Select **True Office Learning - LIO** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-true-office-learning---lio'></a>

## Configure and test Microsoft Entra SSO for True Office Learning - LIO

Configure and test Microsoft Entra SSO with True Office Learning - LIO using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in True Office Learning - LIO.

To configure and test Microsoft Entra SSO with True Office Learning - LIO, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure True Office Learning - LIO SSO](#configure-true-office-learning---lio-sso)** - to configure the single sign-on settings on application side.
    1. **[Create True Office Learning - LIO test user](#create-true-office-learning---lio-test-user)** - to have a counterpart of B.Simon in True Office Learning - LIO that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **True Office Learning - LIO** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    1. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://learn-sso.trueoffice.com/simplesaml/module.php/saml/sp/metadata.php/<CUSTOMER_NAME>-sp`

    1. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://learn-sso.trueoffice.com/<CUSTOMER_NAME>`
    
        > [!NOTE]
        > These values aren't real. Update these values with the actual Identifier and Sign on URL. Contact [True Office Learning - LIO Client support team](mailto:service@trueoffice.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

    ![The Certificate download link](common/metadataxml.png)

1. On the **Set up True Office Learning - LIO** section, copy the appropriate URL(s) based on your requirement.

    ![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure True Office Learning - LIO SSO

Please contact [True Office Learning - LIO support team](mailto:service@trueoffice.com) with configuration questions and/or to request a copy of the metadata. 
In your request please provide the following information:
* Company Name.
* CompanyID (if known).
* Existing or new configuration.

### Create True Office Learning - LIO test user

In this section, you create a user called Britta Simon in True Office Learning - LIO. Work with [True Office Learning - LIO support team](mailto:service@trueoffice.com) to add the users in the True Office Learning - LIO platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration by using the following options:

* Select **Test this application**. You're redirected to the True Office Learning - LIO Sign-on URL where you can initiate the login flow. 
* Go to the True Office Learning - LIO Sign-on URL directly, and initiate the login flow from that site.
* You can use Microsoft My Apps. When you select the True Office Learning - LIO tile in My Apps, you're redirected to the True Office Learning - LIO Sign-on URL. For more information about My Apps, see [Introduction to My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

After you configure True Office Learning - LIO you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

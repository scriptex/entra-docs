---
title: Configure GoProfiles for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and GoProfiles.
services: active-directory
author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps
ms.workload: identity
ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and GoProfiles so that I can control who has access to GoProfiles, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure GoProfiles for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate GoProfiles with Microsoft Entra ID. When you integrate GoProfiles with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to GoProfiles.
* Enable your users to be automatically signed-in to GoProfiles with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* GoProfiles single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* GoProfiles supports both **SP and IDP** initiated SSO.
* GoProfiles supports **Just In Time** user provisioning.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add GoProfiles from the gallery

To configure the integration of GoProfiles into Microsoft Entra ID, you need to add GoProfiles from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **GoProfiles** in the search box.
1. Select **GoProfiles** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

[!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

## Configure and test Microsoft Entra SSO for GoProfiles

Configure and test Microsoft Entra SSO with GoProfiles using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in GoProfiles.

To configure and test Microsoft Entra SSO with GoProfiles, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-microsoft-entra-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Create a Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure GoProfiles SSO](#configure-goprofiles-sso)** - to configure the single sign-on settings on application side.
    1. **[Create GoProfiles test user](#create-goprofiles-test-user)** - to have a counterpart of B.Simon in GoProfiles that's linked to the Microsoft Entra ID representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO in the Microsoft Entra admin center.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **GoProfiles** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows how to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, the application is preconfigured and the necessary URLs are already prepopulated with Microsoft Entra. The user needs to save the configuration by selecting the **Save** button.

1. Perform the following step, if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type the URL:
    `https://www.goprofiles.io/signin`

1. On the **Set-up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

    ![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

1. On the **Set up GoProfiles** section, copy the appropriate URL(s) based on your requirement.

    ![Screenshot shows to copy configuration appropriate URL.](common/copy-configuration-urls.png "Metadata")

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure GoProfiles SSO

1. Log in to GoProfiles company site as an administrator.

1. Go to **Settings** > **Workspace** > **Single sign-on** >  select **Azure** as an authentication method and select **Configure**.

    ![Screenshot shows Settings for the configuration.](./media/goprofiles-tutorial/settings.png "Settings")

1. In the **Azure** section, perform the following steps:

    ![Screenshot shows the Configuration.](./media/goprofiles-tutorial/configure.png "Configuration")

    1. Select **Enable Azure for your team** checkbox.

    1. Open the downloaded **Federation Metadata XML** into Notepad and paste the content into the **Identity Provider Metadata** textbox.

    1. Select **Save Changes**.

### Create GoProfiles test user

In this section, a user called Britta Simon is created in GoProfiles. GoProfiles supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in GoProfiles, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options.
 
#### SP initiated:
 
* Select **Test this application** in Microsoft Entra admin center. this option redirects to GoProfiles Sign on URL where you can initiate the login flow.  
 
* Go to GoProfiles Sign-on URL directly and initiate the login flow from there.
 
#### IDP initiated:
 
* Select **Test this application** in Microsoft Entra admin center and you should be automatically signed in to the GoProfiles for which you set up the SSO.
 
You can also use Microsoft My Apps to test the application in any mode. When you select the GoProfiles tile in the My Apps, if configured in SP mode you would be redirected to the application sign-on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the GoProfiles for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure GoProfiles you can enforce session control, which protects exfiltration and infiltration of your organization's sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).
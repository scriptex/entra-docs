---
title: Configure Acadia for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Acadia.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Acadia so that I can control who has access to Acadia, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Acadia for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Acadia with Microsoft Entra ID. When you integrate Acadia with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Acadia.
* Enable your users to be automatically signed-in to Acadia with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Acadia single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Acadia supports **SP and IDP** initiated SSO.
* Acadia supports **Just In Time** user provisioning.

## Add Acadia from the gallery

To configure the integration of Acadia into Microsoft Entra ID, you need to add Acadia from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Acadia** in the search box.
1. Select **Acadia** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-acadia'></a>

## Configure and test Microsoft Entra SSO for Acadia

Configure and test Microsoft Entra SSO with Acadia using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Acadia.

To configure and test Microsoft Entra SSO with Acadia, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Acadia SSO](#configure-acadia-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Acadia test user](#create-acadia-test-user)** - to have a counterpart of B.Simon in Acadia that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Acadia** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, If you wish to configure the application in **IDP** initiated mode, perform the following steps:

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://<CUSTOMER>.acadia.sysalli.com/shibboleth`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<CUSTOMER>.acadia.sysalli.com/Shibboleth.sso/SAML2/POST`

1. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<CUSTOMER>.acadia.sysalli.com/Shibboleth.sso/Login`

    > [!NOTE]
    > The values for steps 4 and 5 is provided in a metadata file by the Acadia team which can be imported by selecting **Upload metadata file** on the **Basic SAML Configuration** section. Update these values with the actual Identifier, Reply URL and Sign-on URL. You can also refer to the patterns shown in the **Basic SAML Configuration** section to confirm that the metadata values are correct. Contact [Acadia Client support team](mailto:support@systemsalliance.com) if the provided values are incorrect.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

    ![The Certificate download link](common/metadataxml.png)

1. On the **Set up Acadia** section, copy the appropriate URL(s) as per your requirement.

    ![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Acadia SSO

To configure single sign-on on the **Acadia** side, you need to send the downloaded **Metadata XML**, the **App Federation Metadata URL**, and appropriate copied URLs from the application configuration to [Acadia support team](mailto:support@systemsalliance.com). They configure this setting to have the SAML SSO connection set properly on both sides.

### Create Acadia test user

In this section, a user called Britta Simon is created in Acadia. Acadia supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in Acadia, a new one is created after authentication.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to Acadia Sign on URL where you can initiate the login flow.  

* Go to Acadia Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the Acadia for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the Acadia tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Acadia for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Acadia you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

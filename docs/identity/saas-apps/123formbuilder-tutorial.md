---
title: Configure 123FormBuilder SSO for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and 123FormBuilder SSO.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and 123FormBuilder so that I can control who has access to 123FormBuilder, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure 123FormBuilder SSO for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate 123FormBuilder SSO with Microsoft Entra ID. When you integrate 123FormBuilder SSO with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to 123FormBuilder SSO.
* Enable your users to be automatically signed in to 123FormBuilder SSO with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* 123FormBuilder SSO single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* 123FormBuilder SSO supports **SP and IDP** initiated SSO.
* 123FormBuilder SSO supports **Just In Time** user provisioning.

## Add 123FormBuilder SSO from the gallery

To configure the integration of 123FormBuilder SSO into Microsoft Entra ID, you need to add 123FormBuilder SSO from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **123FormBuilder SSO** in the search box.
1. Select **123FormBuilder SSO** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-123formbuilder-sso'></a>

## Configure and test Microsoft Entra SSO for 123FormBuilder SSO

Configure and test Microsoft Entra SSO with 123FormBuilder SSO using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in 123FormBuilder SSO.

To configure and test Microsoft Entra SSO with 123FormBuilder SSO, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure 123FormBuilder SSO](#configure-123formbuilder-sso)** - to configure the single sign-on settings on application side.
    1. **[Create 123FormBuilder SSO test user](#create-123formbuilder-sso-test-user)** - to have a counterpart of B.Simon in 123FormBuilder SSO that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **123FormBuilder SSO** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, If you wish to configure the application in **IDP** initiated mode, perform the following steps:

    a. In the **Identifier** text box, type a URL using the following pattern: `https://www.123formbuilder.com/saml/azure_ad/<TENANT_ID>/metadata`


    b. In the **Reply URL** text box, type a URL using the following pattern: `https://www.123formbuilder.com/saml/azure_ad/<TENANT_ID>/acs`

5. Select **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern: `https://www.123formbuilder.com/saml/azure_ad/<TENANT_ID>/sso`

	> [!NOTE]
	> These values aren't real. You'll need to update these value from actual URLs and Identifier which is explained later in the article.

1. On the **Setup single sign-on with SAML** page, in the **SAML Signing Certificate** section,  find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

1. On the **Set up 123FormBuilder SSO** section, copy the appropriate URL(s) based on your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure 123FormBuilder SSO

1. To configure single sign-on on **123FormBuilder SSO** side, go to [https://www.123formbuilder.com/form-2709121/](https://www.123formbuilder.com/form-2709121/) and perform the following steps:

	![Screenshot that shows the SSO SAML - Identity Provider configuration screen.](./media/123formbuilder-tutorial/submit.png) 

	a. In the **Email** textbox, type the email of the user like `B.Simon@Contoso.com`.

	b. Select **Upload** and browse the downloaded Metadata XML file, which you have downloaded previously.

	c. Select **SUBMIT FORM**.

2. The **Microsoft Entra ID - Single sign-on - Configure App Settings** page includes the following values:

   - IDENTIFIER
   - REPLY URL
   - SIGN ON URL

   Perform the following steps:

   1. If you wish to configure the application in **IDP initiated mode**, copy the **IDENTIFIER** value for your instance and paste it in **Identifier** textbox in **Basic SAML Configuration** section.

   1. If you wish to configure the application in **IDP initiated mode**, copy the **REPLY URL** value for your instance and paste it in **Reply URL** textbox in **Basic SAML Configuration** section.

   1. If you wish to configure the application in **SP initiated mode**, copy the **SIGN ON URL** value for your instance and paste it in **Sign On URL** textbox in **Basic SAML Configuration** section.

### Create 123FormBuilder SSO test user

In this section, a user called Britta Simon is created in 123FormBuilder SSO. 123FormBuilder SSO supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in 123FormBuilder SSO, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to 123FormBuilder SSO Sign-on URL where you can initiate the login flow.  

* Go to 123FormBuilder SSO Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the 123FormBuilder SSO for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the 123FormBuilder SSO tile in the My Apps, if configured in SP mode you would be redirected to the application sign-on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the 123FormBuilder SSO for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure 123FormBuilder SSO you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

---
title: Configure Nitro Productivity Suite for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Nitro Productivity Suite.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/03/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Nitro Productivity Suite so that I can control who has access to Nitro Productivity Suite, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Nitro Productivity Suite for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Nitro Productivity Suite with Microsoft Entra ID. When you integrate Nitro Productivity Suite with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Nitro Productivity Suite.
* Enable your users to be automatically signed in to Nitro Productivity Suite with their Microsoft Entra accounts.
* Manage your accounts in one central location: The Microsoft Entra admin center.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* A Nitro Productivity Suite [Enterprise subscription](https://www.gonitro.com/pricing).

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Nitro Productivity Suite supports **SP** and **IDP** initiated SSO.
* Nitro Productivity Suite supports **Just In Time** user provisioning.

## Add Nitro Productivity Suite from the gallery

To configure the integration of Nitro Productivity Suite into Microsoft Entra ID, you need to add Nitro Productivity Suite from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Nitro Productivity Suite** in the search box.
1. Select **Nitro Productivity Suite** from the results, and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]


<a name='configure-and-test-azure-ad-single-sign-on-for-nitro-productivity-suite'></a>

## Configure and test Microsoft Entra single sign-on for Nitro Productivity Suite

Configure and test Microsoft Entra SSO with Nitro Productivity Suite, by using a test user called **B.Simon**. For SSO to work, you need to establish a linked relationship between a Microsoft Entra user and the related user in Nitro Productivity Suite.

To configure and test Microsoft Entra SSO with Nitro Productivity Suite, complete the following building blocks:

1. [Configure Microsoft Entra SSO](#configure-azure-ad-sso) to enable your users to use this feature.

    a. Create a Microsoft Entra test user to test Microsoft Entra single sign-on with B.Simon.
    
    b. Assign the Microsoft Entra test user to enable B.Simon to use Microsoft Entra single sign-on.
    
2. [Create a Nitro Productivity Suite test user](#create-a-nitro-productivity-suite-test-user) to have a counterpart of B.Simon in Nitro Productivity Suite, linked to the Microsoft Entra representation of the user.
1. [Test SSO](#test-sso) to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Nitro Productivity Suite** application integration page, find the **Manage** section. Select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.

1. On the **Set up Single Sign-On with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot of Set up Single Sign-On with SAML page, with pencil icon highlighted](common/edit-urls.png)

1. In the **Basic SAML Configuration** section, if you want to configure the application in **IDP** initiated mode, enter the values for the following fields:

    a. In the **Identifier** text box, copy and paste the **SAML Entity ID** field from the [Nitro Admin portal](https://admin.gonitro.com/). It should have the following pattern:
    `urn:auth0:gonitro-prod:<ENVIRONMENT>`

    b. In the **Reply URL** text box, copy and paste the **ACS URL** field from the [Nitro Admin portal](https://admin.gonitro.com/). It should have the following pattern:
    `https://gonitro-prod.eu.auth0.com/login/callback?connection=<ENVIRONMENT>`

1. Select **Set additional URLs**, and perform the following step if you want to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type the URL:
    `https://sso.gonitro.com/login`

1. Select **Save**.

1. In the **SAML Signing Certificate** section, find **Certificate (Base64)**. Select **Download** to download the certificate and save it on your computer.

	![Screenshot of SAML Signing Certificate section, with Download link highlighted](common/certificatebase64.png)
    
1. In the **Set up Nitro Productivity Suite** section, select the copy icon beside **Login URL**.
    
    ![Screenshot of Set up Nitro Productivity Suite section, with URLs and copy icons highlighted](common/copy-configuration-urls.png)
    
1. In the [Nitro Admin portal](https://admin.gonitro.com/), on the **Enterprise Settings** page, find the **Single Sign-On** section. Select **Setup SAML SSO**.

	a. Paste the **Login URL** from step 9 into the **Sign In URL** field.
	
	b. Upload the **Certificate (Base64)** step 8 in the **X509 Signing Certificate** field.
	
	c. Select **Submit**.
	
	d. Select **Enable Single Sign-On**.

1. The Nitro Productivity Suite application expects the SAML assertions to be in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![Screenshot of default attributes](common/default-attributes.png)

1. In addition to the preceding attributes, the Nitro Productivity Suite application expects a few more attributes to be passed back in the SAML response. These attributes are pre-populated, but you can review them per your requirements.
	
	| Name  |  Source attribute|
	| ---------------| --------------- |
	| employeeNumber |  user.objectid |


<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

### Create a Nitro Productivity Suite test user

Nitro Productivity Suite supports just-in-time user provisioning, which is enabled by default. There's no additional action for you to take. If a user doesn't already exist in Nitro Productivity Suite, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

### SP initiated:

1. Select **Test this application**, this option redirects to Nitro Productivity Suite Sign on URL where you can initiate the login flow.  

2. Go to Nitro Productivity Suite Sign-on URL directly and initiate the login flow from there.

### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the Nitro Productivity Suite for which you set up the SSO 

You can also use Microsoft Access Panel to test the application in any mode. When you select the Nitro Productivity Suite tile in the Access Panel, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Nitro Productivity Suite for which you set up the SSO. For more information about the Access Panel, see [Introduction to the Access Panel](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).


## Related content

Once you configure the Nitro Productivity Suite you can enforce session controls, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session controls extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

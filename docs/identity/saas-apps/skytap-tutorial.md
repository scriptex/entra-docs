---
title: Configure Single Sign-on for Skytap for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Single Sign-on for Skytap.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Single Sign-on for Skytap so that I can control who has access to Single Sign-on for Skytap, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Single Sign-on for Skytap for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Single Sign-on for Skytap with Microsoft Entra ID. When you integrate Single Sign-on for Skytap with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Single Sign-on for Skytap.
* Enable your users to be automatically signed in to Single Sign-on for Skytap with their Microsoft Entra accounts.
* Manage your accounts in one central location, the Azure portal.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Single Sign-on for Skytap single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Single Sign-on for Skytap supports SP and IDP initiated SSO.

## Add Single Sign-on for Skytap from the gallery

To configure the integration of Single Sign-on for Skytap into Microsoft Entra ID, you need to add Single Sign-on for Skytap from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Single Sign-on for Skytap** in the search box.
1. Select **Single Sign-on for Skytap** from the results panel, and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-single-sign-on-for-skytap'></a>

## Configure and test Microsoft Entra SSO for Single Sign-on for Skytap

Configure and test Microsoft Entra SSO with Single Sign-on for Skytap by using a test user called **B.Simon**. For SSO to work, establish a linked relationship between a Microsoft Entra user and the related user in Single Sign-on for Skytap.

Here are the general steps to configure and test Microsoft Entra SSO with Single Sign-on for Skytap:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Single Sign-on for Skytap SSO](#configure-single-sign-on-for-skytap-sso)** to configure the single sign-on settings on the application side.
    1. **[Create a Single Sign-on for Skytap test user](#create-single-sign-on-for-skytap-test-user)** to have a counterpart of B.Simon in Single Sign-on for Skytap. This counterpart is linked to the Microsoft Entra representation of the user.
1. **[Test SSO](#test-sso)** to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Single Sign-on for Skytap** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)
   
1. In the **Basic SAML Configuration** section, if you want to configure the application in **IDP** initiated mode, enter the values for the following fields:

    a. In the **Identifier** text box, type a URL that uses the following pattern:
    `http://pingone.com/<custom EntityID>`

    b. In the **Reply URL** text box, type the URL:
    `https://sso.connect.pingidentity.com/sso/sp/ACS.saml2`

1. You can optionally select **Set additional URLs**, and perform the following steps to configure the application in **SP** initiated mode:

    a. In the **Sign-on URL** text box, type a URL that uses the following pattern:
    `https://sso.connect.pingidentity.com/sso/sp/initsso?saasid=<saasid>&idpid=<idpid>`

    
    b. In the **Relay State** text box, type a URL that uses the following pattern:
    `https://pingone.com/1.0/<custom ID>`

    > [!NOTE]
    > These values aren't real. Update these values with the actual Identifier, Reply URL, Sign-on URL and Relay State. Contact the [Single Sign-on for Skytap Client support team](mailto:support@skytap.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Federation Metadata XML**. Select **Download** to download the metadata file and save it on your computer.

	![Screenshot of the certificate download link](common/metadataxml.png)

1. On the **Set up Single Sign-on for Skytap** section, copy the appropriate URL or URLs, based on your requirement.

	![Screenshot of copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Single Sign-on for Skytap SSO

To configure single sign-on on the Single Sign-on for Skytap side, you need to send the downloaded **Federation Metadata XML**, and appropriate copied URLs, to the [Single Sign-on for Skytap Client support team](mailto:support@skytap.com). They configure this setting to have the SAML SSO connection set properly on both sides.

### Create Single Sign-on for Skytap test user

In this section, you create a user called B.Simon in Single Sign-on for Skytap. Work with the [Single Sign-on for Skytap Client support team](mailto:support@skytap.com) to add the users in the Single Sign-on for Skytap platform. You can't use single sign-on until you create and activate users.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to Single Sign-on for Skytap Sign on URL where you can initiate the login flow.  

* Go to Single Sign-on for Skytap Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the Single Sign-on for Skytap for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the Single Sign-on for Skytap tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Single Sign-on for Skytap for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Single Sign-on for Skytap you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

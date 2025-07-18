---
title: Configure BlogIn for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and BlogIn.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and BlogIn so that I can control who has access to BlogIn, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure BlogIn for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate BlogIn with Microsoft Entra ID. When you integrate BlogIn with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to BlogIn.
* Enable your users to be automatically signed-in to BlogIn with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* BlogIn single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* BlogIn supports **SP and IDP** initiated SSO.
* BlogIn supports **Just In Time** user provisioning.
* BlogIn supports [Automated user provisioning](blogin-provisioning-tutorial.md).

## Add BlogIn from the gallery

To configure the integration of BlogIn into Microsoft Entra ID, you need to add BlogIn from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **BlogIn** in the search box.
1. Select **BlogIn** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-blogin'></a>

## Configure and test Microsoft Entra SSO for BlogIn

Configure and test Microsoft Entra SSO with BlogIn using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in BlogIn.

To configure and test Microsoft Entra SSO with BlogIn, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure BlogIn SSO](#configure-blogin-sso)** - to configure the single sign-on settings on application side.
    1. **[Create BlogIn test user](#create-blogin-test-user)** - to have a counterpart of B.Simon in BlogIn that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **BlogIn** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you want to configure the application in **IDP** initiated mode, perform the following steps:

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.blogin.co/`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.blogin.co/sso/saml/callback`

1. Select **Set additional URLs** and perform the following step if you want to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<SUBDOMAIN>.blogin.co/`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier, Reply URL, and Sign-on URL. You can get the exact values for these fields on the **Settings** page on BlogIn (**User Authentication** tab > **Configure SSO and User Provisioning**). Alternatively, you can contact [BlogIn Client support team](mailto:support@blogin.co) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. BlogIn application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, BlogIn application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.
	
	| Name | Source Attribute |
	| ------ | --------- |
	| title |user.jobtitle |
	

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure BlogIn SSO

To configure single sign-on on **BlogIn** side login to your BlogIn account and follow these steps:

1. Go to **Settings** > **User Authentication** > **Configure SSO & User provisioning**.
2. On the next screen, change Single Sign-On status to **On** and choose a custom name for the SSO login button that's displayed on the login screen.

3. If you saved the **App Federation Metadata Url** in the last step of the previous section, choose the configuration method **Metadata URL** and paste **App Federation Metadata Url** into the Metadata URL field. Otherwise, change the Configuration method to **manual**, manually populate **Identity Provider SSO URL (Login URL)** and **Identity Provider Issuer (entity ID)**, and upload the **Certificate (base64)** you got from Microsoft Entra ID.

4. Choose the default user role for new users joining BlogIn using SSO.

5. Select **Save changes**.

For a more detailed explanation of setting up SSO on BlogIn, see [How to set up SSO for Microsoft Entra ID on BlogIn](https://blogin.co/blog/how-to-set-up-single-sign-on-sso-for-microsoft-azure-active-directory-azure-ad-267/). Feel free to contact the [BlogIn support team](mailto:support@blogin.co) at any time if you have any questions or need help.

### Create BlogIn test user

In this section, a user called B.Simon is created in BlogIn. BlogIn supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in BlogIn, a new one is created after authentication.

BlogIn also supports automatic user provisioning, you can find more details [here](./blogin-provisioning-tutorial.md) on how to configure automatic user provisioning.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to BlogIn Sign on URL where you can initiate the login flow.  

* Go to BlogIn Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the BlogIn for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the BlogIn tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the BlogIn for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure BlogIn you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

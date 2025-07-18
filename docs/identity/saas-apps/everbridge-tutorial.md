---
title: Configure EverBridge for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and EverBridge.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and EverBridge so that I can control who has access to EverBridge, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure EverBridge for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate EverBridge with Microsoft Entra ID.
When you integrate EverBridge with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to EverBridge.
* Allow your users to be automatically signed in to EverBridge with their Microsoft Entra accounts. This access control is called single sign-on (SSO).
* Manage your accounts in one central location by using the Azure portal.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* An EverBridge subscription that uses single sign-on.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* EverBridge supports IDP-initiated SSO.

## Add EverBridge from the Gallery

To configure the integration of EverBridge into Microsoft Entra ID, you need to add EverBridge from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **EverBridge** in the search box.
1. Select **EverBridge** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-everbridge'></a>

## Configure and test Microsoft Entra SSO for EverBridge

Configure and test Microsoft Entra SSO with EverBridge using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in EverBridge.

To configure and test Microsoft Entra SSO with EverBridge, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure EverBridge SSO](#configure-everbridge-sso)** - to configure the single sign-on settings on application side.
    1. **[Create EverBridge test user](#create-everbridge-test-user)** - to have a counterpart of B.Simon in EverBridge that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

### Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **EverBridge** application integration page, find the **Manage** section and select **Single sign-on**.
1. On the **Select a Single sign-on method** page, select **SAML**.
1. On the **Set up Single Sign-On with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

    >[!NOTE]
	>Configure the application either as the manager portal *or* as the member portal on both the Azure portal and the EverBridge portal.

4. To configure the **EverBridge** application as the **EverBridge manager portal**, in the **Basic SAML Configuration** section, follow these steps:

    a. In the **Identifier** box, enter a URL that follows the pattern.
    `https://sso.everbridge.net/<API_Name>`

    b. In the **Reply URL** box, enter a URL that follows the pattern.
    `https://manager.everbridge.net/saml/SSO/<API_Name>/alias/defaultAlias`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier and Reply URL values. To get these values, contact the [EverBridge support team](mailto:support@everbridge.com). You also can refer to the patterns shown in the **Basic SAML Configuration** section.

5. To configure the **EverBridge** application as the **EverBridge member portal**, in the **Basic SAML Configuration** section, follow these steps:

  * If you want to configure the application in IDP-initiated mode, follow these steps:

    a. In the **Identifier** box, enter a URL that follows the pattern `https://sso.everbridge.net/<API_Name>/<Organization_ID>`

    b. In the **Reply URL** box, enter a URL that follows the pattern `https://member.everbridge.net/saml/SSO/<API_Name>/<Organization_ID>/alias/defaultAlias`

   * If you want to configure the application in SP-initiated mode, select **Set additional URLs** and follow this step:

     a. In the **Sign on URL** box, enter a URL that follows the pattern `https://member.everbridge.net/saml/login/<API_Name>/<Organization_ID>/alias/defaultAlias?disco=true`

     > [!NOTE]
     > These values aren't real. Update these values with the actual Identifier, Reply URL, and Sign on URL values. To get these values, contact the [EverBridge support team](mailto:support@everbridge.com). You also can refer to the patterns shown in the **Basic SAML Configuration** section.

6. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML**. Save it on your computer.

	![Certificate download link](common/metadataxml.png)

7. In the **Set up EverBridge** section, copy the URLs you need for your requirements:

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure EverBridge SSO

To configure SSO on **EverBridge** as an **EverBridge manager portal** application, follow these steps.
 
1. In a different web browser window, sign in to EverBridge as an administrator.

1. In the menu on the top, select the **Settings** tab. Under **Security**, select **Single Sign-On for Manager Portal**.
   
     ![Configure single sign-on](./media/everbridge-tutorial/settings.png)
   
     a. In the **Name** box, enter the name of the identifier provider. An example is your company name.
   
     b. In the **API Name** box, enter the name of the API.
   
     c. Select **Choose File** to upload the metadata file that you downloaded.
   
     d. For **SAML Identity Location**, select **Identity is in the NameIdentifier element of the Subject statement**.
   
     e. In the **Identity Provider Login URL** box, paste the **Login URL** value that you copied.
   
     f. For **Service Provider initiated Request Binding**, select **HTTP Redirect**.

     g. Select **Save**.

## Configure EverBridge as EverBridge member portal SSO

To configure single sign-on on **EverBridge** as an **EverBridge member portal**, send the downloaded **Federation Metadata XML** to the [EverBridge support team](mailto:support@everbridge.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create EverBridge test user

In this section, you create the test user Britta Simon in EverBridge. To add users in the EverBridge platform, work with the [EverBridge support team](mailto:support@everbridge.com). Users must be created and activated in EverBridge before you use single sign-on. 

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options.

* Select **Test this application**, and you should be automatically signed in to the EverBridge for which you set up the SSO.

* You can use Microsoft My Apps. When you select the EverBridge tile in the My Apps, you should be automatically signed in to the EverBridge for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure EverBridge you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

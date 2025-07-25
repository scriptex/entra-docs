---
title: Configure Questetra BPM Suite for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Questetra BPM Suite.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Questetra BPM Suite so that I can control who has access to Questetra BPM Suite, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Questetra BPM Suite for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Questetra BPM Suite with Microsoft Entra ID. When you integrate Questetra BPM Suite with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Questetra BPM Suite.
* Enable your users to be automatically signed-in to Questetra BPM Suite with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Questetra BPM Suite single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Questetra BPM Suite supports **SP** initiated SSO.

## Add Questetra BPM Suite from the gallery

To configure the integration of Questetra BPM Suite into Microsoft Entra ID, you need to add Questetra BPM Suite from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Questetra BPM Suite** in the search box.
1. Select **Questetra BPM Suite** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-questetra-bpm-suite'></a>

## Configure and test Microsoft Entra SSO for Questetra BPM Suite

Configure and test Microsoft Entra SSO with Questetra BPM Suite using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Questetra BPM Suite.

To configure and test Microsoft Entra SSO with Questetra BPM Suite, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Questetra BPM Suite SSO](#configure-questetra-bpm-suite-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Questetra BPM Suite test user](#create-questetra-bpm-suite-test-user)** - to have a counterpart of B.Simon in Questetra BPM Suite that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Questetra BPM Suite** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `https://<subdomain>.questetra.net/`

	b. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<subdomain>.questetra.net/saml/SSO/alias/bpm`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier and Sign on URL. You can get these values from **SP Information** section on your **Questetra BPM Suite** company site, which is explained later in the article or contact [Questetra BPM Suite Client support team](https://support.questetra.com/support-service/). You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Certificate (Base64)** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Questetra BPM Suite** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Questetra BPM Suite SSO

1. In a different web browser window, Sign in to your **Questetra BPM Suite** company site as an administrator.

2. In the menu on the top, select **System Settings**. 
   
    ![Screenshot shows System Settings selected from your Questetra BPM Suite company site.](./media/questetra-bpm-suite-tutorial/settings.png)

3. To open the **SingleSignOnSAML** page, select **SSO (SAML)**. 

    ![Screenshot shows S S O (SAML) selected.](./media/questetra-bpm-suite-tutorial/apps.png)

4. On your **Questetra BPM Suite** company site, in the **SP Information** section, perform the following steps:

	a. Copy the **ACS URL**, and then paste it into the **Sign On URL** textbox in the **Basic SAML Configuration** section from Azure portal.
	
	b. Copy the **Entity ID**, and then paste it into the **Identifier** textbox in the **Basic SAML Configuration** section from Azure portal.

5. On your **Questetra BPM Suite** company site, perform the following steps: 
   
    ![Configure Single Sign-On](./media/questetra-bpm-suite-tutorial/certificate.png)
   
	a. Select **Enable Single Sign-On**.
   
	b. In **Entity ID** textbox, paste the value of **Microsoft Entra Identifier**..
	
	c. In **Sign-in page URL** textbox, paste the value of **Login URL**..
	
	d. In **Sign-out page URL** textbox, paste the value of **Logout URL**..
	
	e. In the **NameID format** textbox, type `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`.

    f. Open your **Base-64** encoded certificate in notepad downloaded from Azure portal, copy the content of it into your clipboard, and then paste it into the **Validation certificate** textbox. 

    g. Select **Save**.

### Create Questetra BPM Suite test user

The objective of this section is to create a user called Britta Simon in Questetra BPM Suite.

**To create a user called Britta Simon in Questetra BPM Suite, perform the following steps:**

1. Sign in to your Questetra BPM Suite company site as an administrator.

2. Go to **System Settings > User List > New User**.
 
3. On the New User dialog, perform the following steps: 
   
	![Create test user](./media/questetra-bpm-suite-tutorial/users.png)
   
    a. In the **Name** textbox, type **name** of the user britta.simon@contoso.com.
   
    b. In the **Email** textbox, type **email** of the user britta.simon@contoso.com.
   
    c. In the **Password** textbox, type a **password** of the user.
	
	d. Select **Add new user**.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to Questetra BPM Suite Sign-on URL where you can initiate the login flow. 

* Go to Questetra BPM Suite Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the Questetra BPM Suite tile in the My Apps, this option redirects to Questetra BPM Suite Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure Questetra BPM Suite you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

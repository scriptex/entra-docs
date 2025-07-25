---
title: Configure Procore SSO for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Procore SSO.
author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Procore SSO so that I can control who has access to Procore SSO, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Procore SSO for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Procore SSO with Microsoft Entra ID. When you integrate Procore SSO with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Procore SSO.
* Enable your users to be automatically signed-in to Procore SSO with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Procore SSO single sign-on enabled subscription.

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Procore SSO supports **IDP** initiated SSO.

## Add Procore SSO from the gallery

To configure the integration of Procore SSO into Microsoft Entra ID, you need to add Procore SSO from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Procore SSO** in the search box.
1. Select **Procore SSO** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-procore-sso'></a>

## Configure and test Microsoft Entra SSO for Procore SSO

Configure and test Microsoft Entra SSO with Procore SSO using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Procore SSO.

To configure and test Microsoft Entra SSO with Procore SSO, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Procore SSO](#configure-procore-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Procore SSO test user](#create-procore-sso-test-user)** - to have a counterpart of B.Simon in Procore SSO that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Procore SSO** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, the user doesn't have to perform any step as the app is already pre-integrated with Azure.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

6. On the **Set up Procore SSO** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Procore SSO 

1. To configure single sign-on on **Procore SSO** side, sign in to your procore company site as an administrator.

2. From the toolbox drop down, select **Admin** to open the SSO settings page.

	![Screenshot shows the Procore company site with Directory selected.](./media/procoresso-tutorial/admin.png)

3. Paste the values in the boxes as described below.

	![Screenshot shows the Add a Person dialog box.](./media/procoresso-tutorial/setting.png)	

	a. In the **Single Sign On Issuer URL** text box, paste the value of **Microsoft Entra Identifier** which you copied previously.

	b. In the **SAML Sign On Target URL** box, paste the value of **Login URL** which you copied previously.

	c. Now open the **Federation Metadata XML** downloaded above and copy the certificate in the tag named **X509Certificate**. Paste the copied value into the **Single Sign On x509 Certificate** box.

4. Select **Save Changes**.

5. After these settings, you needs to send the **domain name** (suh as `contoso.com`) through which you're logging into Procore to the [Procore Support team](https://support.procore.com/) and they will activate federated SSO for that domain.

### Create Procore SSO test user

Please follow the below steps to create a Procore test user on Procore SSO side.

1. Sign in to your procore company site as an administrator.	

2. From the toolbox drop down, select **Directory** to open the company directory page.

	![Screenshot shows the Procore company site with Directory selected from the toolbox.](./media/procoresso-tutorial/directory.png)

3. Select **Add a Person** option to open the form and enter perform following options.

	![Screenshot shows the Add a person to Boylan Construction where you can enter user information.](./media/procoresso-tutorial/user.png)

    a. In the **First Name** textbox, type user's first name like **Britta**.

    b. In the **Last name** textbox, type user's last name like **Simon**.

	c. In the **Email Address** textbox, type user's email address like BrittaSimon@contoso.com.

    d. Select **Permission Template** as **Apply Permission Template Later**.

    e. Select **Create**.

4. Check and update the details for the newly added contact.

	![Screenshot shows an edit page where you can verify the user settings.](./media/procoresso-tutorial/details.png)

5. Select **Save and Send Invitation** (if an invite through mail is required) or **Save** (Save directly) to complete the user registration.
	
	![Screenshot shows the Current Project Settings where you can Save and Send Invitation.](./media/procoresso-tutorial/save.png)

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options.

* Select **Test this application**, and you should be automatically signed in to the Procore SSO for which you set up the SSO.

* You can use Microsoft My Apps. When you select the Procore SSO tile in the My Apps, you should be automatically signed in to the Procore SSO for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Procore SSO you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

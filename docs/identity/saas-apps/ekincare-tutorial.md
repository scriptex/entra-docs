---
title: Configure eKincare for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and eKincare.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and eKincare so that I can control who has access to eKincare, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure eKincare for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate eKincare with Microsoft Entra ID. When you integrate eKincare with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to eKincare.
* Enable your users to be automatically signed-in to eKincare with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

To configure Microsoft Entra integration with eKincare, you need the following items:

* A Microsoft Entra subscription. If you don't have a Microsoft Entra environment, you can get a [free account](https://azure.microsoft.com/free/).
* eKincare single sign-on enabled subscription.
* Along with Cloud Application Administrator, Application Administrator can also add or manage applications in Microsoft Entra ID.
For more information, see [Azure built-in roles](~/identity/role-based-access-control/permissions-reference.md).

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* eKincare supports **IDP** initiated SSO.

* eKincare supports **Just In Time** user provisioning.

## Add eKincare from the gallery

To configure the integration of eKincare into Microsoft Entra ID, you need to add eKincare from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **eKincare** in the search box.
1. Select **eKincare** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-ekincare'></a>

## Configure and test Microsoft Entra SSO for eKincare

Configure and test Microsoft Entra SSO with eKincare using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in eKincare.

To configure and test Microsoft Entra SSO with eKincare, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure eKincare SSO](#configure-ekincare-sso)** - to configure the single sign-on settings on application side.
    1. **[Create eKincare test user](#create-ekincare-test-user)** - to have a counterpart of B.Simon in eKincare that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **eKincare** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows to edit Basic S A M L Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://<instancename>.ekincare.com/`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<instancename>.ekincare.com/hul/saml`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier and Reply URL. Contact [eKincare Client support team](mailto:tech@ekincare.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. eKincare application expects the SAML assertions in a specific format. Configure the following claims for this application. You can manage the values of these attributes from the **User Attributes** section on application integration page. On the **Set up Single Sign-On with SAML** page, select **Edit** button to open **User Attributes** dialog.

	![Screenshot that shows the User Attributes dialog with the edit button selected.](common/edit-attribute.png "Attributes")

1. In the **User Claims** section on the **User Attributes** dialog, edit the claims by using **Edit icon** or add the claims by using **Add new claim** to configure SAML token attribute as shown in the image above and perform the following steps: 

	| Name | Source Attribute |
	| ---------------| --------------- |    
	| employeeid | *user.extensionattribute1* |
	| organizationid | *"uniquevalue"* |
	| organizationname | *user.companyname* |
	
	a. Select **Add new claim** to open the **Manage user claims** dialog.

	![Screenshot that shows the "User claims" dialog with the "Add new claim" and "Save" buttons selected.](common/new-save-attribute.png "Claims")

	![Screenshot that shows the image of eKincare application.](common/new-attribute-details.png "Details")

	b. In the **Name** textbox, type the attribute name shown for that row.

	c. Leave the **Namespace** blank.

	d. Select Source as **Attribute**.

	e. From the **Source attribute** list, type the attribute value shown for that row.

	f. Select **Ok**

	g. Select **Save**.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![Screenshot that shows the Certificate download link.](common/metadataxml.png "Certificate")

1. On the **Set up eKincare** section, copy the appropriate URL(s) as per your requirement.

	![Screenshot shows to copy configuration appropriate U R L.](common/copy-configuration-urls.png "Metadata")

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure eKincare SSO

To configure single sign-on on **eKincare** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [eKincare support team](mailto:tech@ekincare.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create eKincare test user

In this section, a user called Britta Simon is created in eKincare. eKincare supports **just-in-time user provisioning**, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in eKincare, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options.

* Select **Test this application**, and you should be automatically signed in to the eKincare for which you set up the SSO.

* You can use Microsoft My Apps. When you select the eKincare tile in the My Apps, you should be automatically signed in to the eKincare for which you set up the SSO. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure eKincare you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).

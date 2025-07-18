---
title: Configure Directory Services Protector for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Directory Services Protector.
author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps
ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu
ms.custom: sfi-image-nochange
# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Directory Services Protector so that I can control who has access to Directory Services Protector, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Directory Services Protector for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Directory Services Protector with Microsoft Entra ID. When you integrate Directory Services Protector with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Directory Services Protector.
* Enable your users to be automatically signed-in to Directory Services Protector with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Directory Services Protector single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* Directory Services Protector supports both **SP and IDP** initiated SSO.
* Directory Services Protector supports **Just In Time** user provisioning.

## Adding Directory Services Protector from the gallery

To configure the integration of Directory Services Protector into Microsoft Entra ID, you need to add Directory Services Protector from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Directory Services Protector** in the search box.
1. Select **Directory Services Protector** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

[!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

## Configure and test Microsoft Entra SSO for Directory Services Protector

Configure and test Microsoft Entra SSO with Directory Services Protector using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Directory Services Protector.

To configure and test Microsoft Entra SSO with Directory Services Protector, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-microsoft-entra-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Directory Services Protector SSO](#configure-directory-services-protector-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Directory Services Protector test user](#create-directory-services-protector-test-user)** - to have a counterpart of B.Simon in Directory Services Protector that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO in the Microsoft Entra admin center.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Directory Services Protector** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows how to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, if you have **Service Provider metadata file**, perform the following steps:

	a. Select **Upload metadata file**.

    ![Screenshot shows how to upload metadata file.](common/upload-metadata.png "File")

	b. Select **folder logo** to select the metadata file and select **Upload**.

	![Screenshot shows how to choose metadata file.](common/browse-upload-metadata.png "Folder")

	c. After the metadata file is successfully uploaded, the **Identifier** and **Reply URL** values get auto populated in Basic SAML Configuration section.

	![Screenshot shows the image of metadata file.](common/idp-intiated.png "Section")

	> [!Note]
	> If the **Identifier** and **Reply URL** values don't get auto populated, then fill in the values manually according to your requirement.

1. Perform the following step, if you wish to configure the application in **SP** initiated mode:

	In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<HOSTNAME>.<DOMAIN>.<EXTENSION>/DSP/Login/SsoLogin`

	> [!NOTE]
    > The Sign on URL value isn't real. Update this value with the actual Sign on URL. Contact [Directory Services Protector support team](mailto:support@semperis.com) to get this value. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Microsoft Entra admin center.

1. Directory Services Protector support team application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![Screenshot shows the image of attributes configuration.](common/default-attributes.png "Image")

1. In addition to above, Directory Services Protector support team application expects few more attributes to be passed back in SAML response, which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name |  Source Attribute|
	| ---------------|  --------- |
	| role | user.assignedroles |

    > [!NOTE]
   > Please select [here](~/identity-platform/howto-add-app-roles-in-apps.md#app-roles-ui) to know how to configure Role in Microsoft Entra ID.

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

	![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

1. On the **Set up Directory Services Protector** section, copy the appropriate URL(s) based on your requirement.

	![Screenshot shows to copy configuration appropriate URL.](common/copy-configuration-urls.png "Metadata")

<a name='create-a-microsoft-entra-id-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Directory Services Protector SSO

1. Log in to Directory Services Protector company site as an administrator.

1. Go to **Settings (gear icon)** > **Data Connections** > 
**SAML Authentication** and toggle on the **Enabled** switch.

1. In Step **1 - Identity provider**, select **Microsoft Entra ID** from the drop-down menu and select **SAVE**.

1. In Step **2 – Data required by the SAML identity provider**, select **CONFIRM** button and **DOWNLOAD METADATA XML** to **Upload metadata file** in the **Basic SAML Configuration** section in Microsoft Entra admin center and select **SAVE**.

    ![Screenshot shows settings of the identity provider.](./media/directory-services-protector-tutorial/identity.png "Center")

1. In Step **3 - User Attributes & Claims**, we don't need this information now, so we can skip to Step 4.

1. In Step **4 – Data received from the SAML identity provider**, DSP supports both importing from a metadata URL and importing of a metadata XML provided by Microsoft Entra ID.

    1. Select **App federation metadata URL** radio button, and paste the **Metadata URL** in the field from Microsoft Entra ID, and then select **IMPORT**.

    1. Select the radio button to use **Import federation metadata XML** and select **IMPORT XML** to upload the **Federation Metadata XML** file from Microsoft Entra admin center.

    1. Select **SAVE**.

1. At the top of the **SAML Authentication** blade in DSP, it should show **Status** now as **Configured**.

### Create Directory Services Protector test user

In this section, a user called Britta Simon is created in Directory Services Protector. Directory Services Protector supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in Directory Services Protector, a new one is created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application** in Microsoft Entra admin center. this option redirects to Directory Services Protector Sign on URL where you can initiate the login flow.  

* Go to Directory Services Protector Sign on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application** in Microsoft Entra admin center and you should be automatically signed in to the Directory Services Protector for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you select the Directory Services Protector tile in the My Apps, if configured in SP mode you would be redirected to the application sign-on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Directory Services Protector for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Directory Services Protector you can enforce session control, which protects exfiltration and infiltration of your organization's sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

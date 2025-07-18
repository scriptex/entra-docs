---
title: Configure Appinux for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Appinux.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Appinux so that I can control who has access to Appinux, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure Appinux for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Appinux with Microsoft Entra ID. When you integrate Appinux with Microsoft Entra ID, you can:

- Control in Microsoft Entra ID who has access to Appinux.
- Enable your users to be automatically signed-in to Appinux with their Microsoft Entra accounts.
- Manage your accounts in one central location.

## Prerequisites

The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
- Appinux single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

- Appinux supports **SP** initiated SSO

- Appinux supports **Just In Time** user provisioning

## Adding Appinux from the gallery

To configure the integration of Appinux into Microsoft Entra ID, you need to add Appinux from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Appinux** in the search box.
1. Select **Appinux** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-appinux'></a>

## Configure and test Microsoft Entra SSO for Appinux

Configure and test Microsoft Entra SSO with Appinux using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Appinux.

To configure and test Microsoft Entra SSO with Appinux, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
   1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
   1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Appinux SSO](#configure-appinux-sso)** - to configure the single sign-on settings on application side.
   1. **[Create Appinux test user](#create-appinux-test-user)** - to have a counterpart of B.Simon in Appinux that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Appinux** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, enter the values for the following fields:

   a. In the **Sign on URL** text box, type a URL using the following pattern:
   `https://<Appinux_SUBDOMAIN>.appinux.com`

   b. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
   `https://<Appinux_SUBDOMAIN>.appinux.com/simplesaml/module.php/saml/sp/metadata.php/default-sp`

   > [!NOTE]
   > These values aren't real. Update these values with the actual Sign on URL and Identifier. Contact [Appinux Client support team](https://support.appinux.com/) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. Appinux application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes. Select **Edit** icon to open User Attributes dialog.

   ![image](common/edit-attribute.png)

1. In addition to above, Appinux application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirement.

   | **Name**         | **Namespace**                                                  | **Source Attribute**                         |
   | ---------------- | -------------------------------------------------------------- | -------------------------------------------- |
   | `givenname`      | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`        | `user.givenname`                             |
   | `surname`        | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`        | `user.surname`                               |
   | `emailaddress`   | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`        | `user.mail`                                  |
   | `name`           | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`        | `user.userprincipalname`                     |
   | `UserType`       | `http://bcv.appinux.com/claims`                                | `Provide the value as per your organization` |
   | `Tag`            | `http://appinux.com/Tag`                                       | `Provide the value as per your organization` |
   | `Role`           | `http://schemas.microsoft.com/ws/2008/06/identity/claims/role` | `user.assignedroles`                         |
   | `email`          | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/email`  | `user.mail`                                  |
   | `wanshort`       | `http://appinux.com/windowsaccountname2`                       | `extractmailprefix([userprincipalname])`     |
   | `nameidentifier` | `http://schemas.xmlsoap.org/ws/2005/05/identity/claims`        | `user.employeeid`                            |

   > [!NOTE]
   > Appinux expects roles for users assigned to the application. Please set up these roles in Microsoft Entra ID so that users can be assigned the appropriate roles. To understand how to configure roles in Microsoft Entra ID, see [here](~/identity-platform/howto-add-app-roles-in-apps.md#app-roles-ui).

1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Federation Metadata XML** and select **Download** to download the certificate and save it on your computer.

   ![The Certificate download link](common/metadataxml.png)

1. On the **Set up Appinux** section, copy the appropriate URL(s) based on your requirement.

   ![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Appinux SSO

To configure single sign-on on **Appinux** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to [Appinux support team](https://support.appinux.com/). They set this setting to have the SAML SSO connection set properly on both sides.

### Create Appinux test user

In this section, a user called Britta Simon is created in Appinux. Appinux supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in Appinux, a new one is created after authentication.

> [!Note]
> If you need to create a user manually, contact [Appinux support team](https://support.appinux.com).

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options.

- Select **Test this application**, this option redirects to Appinux Sign-on URL where you can initiate the login flow.

- Go to Appinux Sign-on URL directly and initiate the login flow from there.

- You can use Microsoft My Apps. When you select the Appinux tile in the My Apps, this option redirects to Appinux Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Appinux you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

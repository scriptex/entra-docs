---
title: Configure uniFLOW Online for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and uniFLOW Online.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and uniFLOW Online so that I can control who has access to uniFLOW Online, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure uniFLOW Online for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate uniFLOW Online with Microsoft Entra ID. When you integrate uniFLOW Online with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to uniFLOW Online.
* Enable your users to sign in to uniFLOW Online with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* uniFLOW Online tenant.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* uniFLOW Online supports **SP** initiated SSO.
* uniFLOW Online supports [Automated user provisioning](uniflow-online-provisioning-tutorial.md).

## Add uniFLOW Online from the gallery

To configure the integration of uniFLOW Online into Microsoft Entra ID, you need to add uniFLOW Online from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **uniFLOW Online** in the search box.
1. Select **uniFLOW Online** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-uniflow-online'></a>

## Configure and test Microsoft Entra SSO for uniFLOW Online

Configure and test Microsoft Entra SSO with uniFLOW Online using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in uniFLOW Online.

To configure and test Microsoft Entra SSO with uniFLOW Online, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
   1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
   1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure uniFLOW Online SSO](#configure-uniflow-online-sso)** - to configure the single sign-on settings on application side.
    1. **[Sign in to uniFLOW Online using the created test user](#sign-in-to-uniflow-online-using-the-created-test-user)** - to test user sign-in on the application side.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **uniFLOW Online** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier (Entity ID)** text box, type a URL using one of the following patterns:

	| **Identifier** |
	|---------|
	| `https://<tenant_domain_name>.eu.uniflowonline.com` |
	| `https://<tenant_domain_name>.uk.uniflowonline.com` |
	| `https://<tenant_domain_name>.us.uniflowonline.com` |
	| `https://<tenant_domain_name>.sg.uniflowonline.com` |
	| `https://<tenant_domain_name>.jp.uniflowonline.com` |
	| `https://<tenant_domain_name>.au.uniflowonline.com` |
	| `https://<tenant_domain_name>.ca.uniflowonline.com` |

	b. In the **Sign on URL** text box, type a URL using one of the following patterns:

	| **Sign on URL** |
	|---------|
	| `https://<tenant_domain_name>.eu.uniflowonline.com` |
	| `https://<tenant_domain_name>.uk.uniflowonline.com` |
	| `https://<tenant_domain_name>.us.uniflowonline.com` |
	| `https://<tenant_domain_name>.sg.uniflowonline.com` |
	| `https://<tenant_domain_name>.jp.uniflowonline.com` |
	| `https://<tenant_domain_name>.au.uniflowonline.com` |
    | `https://<tenant_domain_name>.ca.uniflowonline.com` |

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier and Sign on URL. Contact [uniFLOW Online Client support team](mailto:support@nt-ware.com) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal or refer to the reply URL displayed in your uniFLOW Online tenant.

1. uniFLOW Online application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes, whereas **nameidentifier** is mapped with **user.userprincipalname**. uniFLOW Online application expects **nameidentifier** to be mapped with **user.objectid**, so you need to edit the attribute mapping by selecting **Edit** icon and change the attribute mapping.

	![Screenshot shows the User Attributes pane with the edit icon highlighted.](common/edit-attribute.png)

1. In addition to above, uniFLOW Online application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name |  Source Attribute|
	| -----------| --------------- |
	| display name | user.displayname |
	| nickname | user.onpremisessamaccountname |

   > [!NOTE]
   > The `user.onpremisessamaccountname` attribute contains a value only if your Microsoft Entra users are synced from a local Windows Active Directory.

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure uniFLOW Online SSO

1. In a different web browser window, sign in to uniFLOW Online website as an administrator.

1. From the left navigation panel, select **Extensions** tab.

	![Screenshot shows Extension selected from the uniFLOW Online site.](./media/uniflow-online-tutorial/extensions.png)


1. Select **Identity Providers**.

	![Screenshot shows Identity Providers selected.](./media/uniflow-online-tutorial/identity-providers.png)
	
1. Select **Configure identity providers**

	![Screenshot shows box to configure identity providers](./media/uniflow-online-tutorial/configure-identity-providers.png)

1. Select **Add identity provider**.

	![Screenshot shows Add identity provider selected.](./media/uniflow-online-tutorial/add-identity-providers.png)


1. On the **ADD IDENTITY PROVIDER** section, perform the following steps:

	![Screenshot shows the ADD IDENTITY PROVIDER section where you can enter the values described.](./media/uniflow-online-tutorial/display-name.png)


	a. Enter the Display name Ex: **Microsoft Entra SSO**.

	b. For **Provider type**, select **WS-Federation** option from the dropdown.

	c. For **WS-Federation type**, select **Microsoft Entra ID** option from the dropdown.

	d. Select **Save**.

1. On the **General** tab, perform the following steps:

	![Screenshot shows the General tab where you can enter the values described.](./media/uniflow-online-tutorial/configuration.png)


	a. Enter the Display name Ex: **Microsoft Entra SSO**.
	
	b. Select **Identity provider** as **Enable Microsoft Entra SSO**.

	c. Select the **From URL** option for the **ADFS Federation Metadata**.

	d. In the **Federation Metadata URL** textbox, paste the **App Federation Metadata URL** value, which you copied previously.

	e. Select **Automatic user registration** as **Activated**.

	f. Select **Save**.
	
> [!NOTE]
> **Reply URL** is automatically prefilled and can't be changed.	

### Sign in to uniFLOW Online using the created test user

1. In a different web browser window, go to the uniFLOW Online URL for your tenant.

1. Select the previously created identity provider to sign-in via your Microsoft Entra instance.

1. Sign in using the test user.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to uniFLOW Online Sign-on URL where you can initiate the sign in flow. 

* Go to uniFLOW Online Sign-on URL directly and initiate the sign in flow from there.

* You can use Microsoft My Apps. When you select the uniFLOW Online tile in the My Apps, this option redirects to uniFLOW Online Sign-on URL. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure uniFLOW Online you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

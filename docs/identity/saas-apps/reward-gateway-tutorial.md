---
title: Configure Reward Gateway for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Reward Gateway.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Reward Gateway so that I can control who has access to Reward Gateway, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Reward Gateway for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Reward Gateway with Microsoft Entra ID. When you integrate Reward Gateway with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Reward Gateway.
* Enable your users to be automatically signed-in to Reward Gateway with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Reward Gateway single sign-on enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Reward Gateway supports **IDP** initiated SSO.

* Reward Gateway supports [Automated user provisioning](reward-gateway-provisioning-tutorial.md).

## Add Reward Gateway from the gallery

To configure the integration of Reward Gateway into Microsoft Entra ID, you need to add Reward Gateway from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Reward Gateway** in the search box.
1. Select **Reward Gateway** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-reward-gateway'></a>

## Configure and test Microsoft Entra SSO for Reward Gateway

Configure and test Microsoft Entra SSO with Reward Gateway using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in Reward Gateway.

To configure and test Microsoft Entra SSO with Reward Gateway, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure Reward Gateway SSO](#configure-reward-gateway-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Reward Gateway test user](#create-reward-gateway-test-user)** - to have a counterpart of B.Simon in Reward Gateway that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Reward Gateway** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

4. On the **Set up Single Sign-On with SAML** page, perform the following steps:

    a. In the **Identifier** text box, type a URL using one of the following patterns:

    | Identifier URL |
    |---|
    | `https://<COMPANY_NAME>.rewardgateway.com` |
    | `https://<COMPANY_NAME>.rewardgateway.co.uk/` |
    | `https://<COMPANY_NAME>.rewardgateway.co.nz/` |
    | `https://<COMPANY_NAME>.rewardgateway.com.au/`|
    |

    b. In the **Reply URL** text box, type a URL using one of the following patterns:

    | Reply URL |
    |---|
    | `https://<COMPANY_NAME>.rewardgateway.com/Authentication/EndLogin?idp=<Unique Id>` |
    | `https://<COMPANY_NAME>.rewardgateway.co.uk/Authentication/EndLogin?idp=<Unique Id>` |
    | `https://<COMPANY_NAME>.rewardgateway.co.nz/Authentication/EndLogin?idp=<Unique Id>` |
    | `https://<COMPANY_NAME>.rewardgateway.com.au/Authentication/EndLogin?idp=<Unique Id>` |
    |

	> [!NOTE]
	> These values aren't real. Update these values with the actual Identifier and Reply URL. To get these values start setting up an Integration on the Reward Manager Portal. Details can be found on https://success.rewardgateway.com/hc/en-us/articles/360038650573-Microsoft-Azure-for-Authentication

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

6. On the **Set up Reward Gateway** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Reward Gateway SSO

To configure single sign-on on **Reward Gateway** side, start setting up an Integration on the Reward Manager Portal. Use the downloaded metadata to obtain your Signing Certificate and upload that during the configuration. Details can be found on https://success.rewardgateway.com/hc/en-us/articles/360038650573-Microsoft-Azure-for-Authentication.

### Create Reward Gateway test user

In this section, you create a user called Britta Simon in Reward Gateway. Work with [Reward Gateway support team](mailto:clientsupport@rewardgateway.com) to add the users in the Reward Gateway platform. Users must be created and activated before you use single sign-on.

Reward Gateway also supports automatic user provisioning, you can find more details [here](./reward-gateway-provisioning-tutorial.md) on how to configure automatic user provisioning.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options.

* Select **Test this application**, and you should be automatically signed in to the Reward Gateway for which you set up the SSO.

* You can use Microsoft My Apps. When you select the Reward Gateway tile in the My Apps, you should be automatically signed in to the Reward Gateway for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Related content

Once you configure Reward Gateway you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

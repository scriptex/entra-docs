---
title: Configure OptiTurn for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and OptiTurn.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and OptiTurn so that I can control who has access to OptiTurn, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure OptiTurn for Single sign-on with Microsoft Entra ID

In this article, you learn how to integrate OptiTurn with Microsoft Entra ID. OptiTurn is a returns management platform that helps retailers route returned items, improve warehouse operations, and manage inventory backlogs. When you integrate OptiTurn with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to OptiTurn.
* Enable your users to be automatically signed-in to OptiTurn with their Microsoft Entra accounts.
* Manage your accounts in one central location.

You'll configure and test Microsoft Entra single sign-on for OptiTurn in a test environment. OptiTurn supports **SP** initiated single sign-on and **Just In Time** user provisioning.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Prerequisites

To integrate Microsoft Entra ID with OptiTurn, you need:

* A Microsoft Entra user account. If you don't already have one, you can [Create an account for free](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).
* One of the following roles: [Application Administrator](/entra/identity/role-based-access-control/permissions-reference#application-administrator), [Cloud Application Administrator](/entra/identity/role-based-access-control/permissions-reference#cloud-application-administrator), or [Application Owner](/entra/fundamentals/users-default-permissions#owned-enterprise-applications).
* A Microsoft Entra subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* OptiTurn single sign-on (SSO) enabled subscription.

## Add application and assign a test user

Before you begin the process of configuring single sign-on, you need to add the OptiTurn application from the Microsoft Entra gallery. You need a test user account to assign to the application and test the single sign-on configuration.

<a name='add-optiturn-from-the-azure-ad-gallery'></a>

### Add OptiTurn from the Microsoft Entra gallery

Add OptiTurn from the Microsoft Entra application gallery to configure single sign-on with OptiTurn. For more information on how to add application from the gallery, see the [Quickstart: Add application from the gallery](~/identity/enterprise-apps/add-application-portal.md).

<a name='create-and-assign-azure-ad-test-user'></a>

### Create and assign Microsoft Entra test user

Follow the guidelines in the [create and assign a user account](~/identity/enterprise-apps/add-application-portal-assign-users.md) article to create a test user account called B.Simon.

Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, and assign roles. The wizard also provides a link to the single sign-on configuration pane. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides). 

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Complete the following steps to enable Microsoft Entra single sign-on.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **OptiTurn** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows how to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

	a. In the **Identifier** textbox, type the URL using one of the following:

	| **Identifier** |
	|------------|
	| `https://optiturn.com/sp` - production |
	| `https://sandbox.optiturn.com/sp` - testing |

   b. In the **Reply URL** textbox, type a URL using one of the following patterns:
    
	| **Reply URL** |
	|------------|
	| `https://optiturn.com/auth/saml/<Customer_Name>_azure_saml/callback` - production |
	| `https://sandbox.optiturn.com/auth/saml/<Customer_Name>_azure_saml/callback` - testing |

	c. In the **Sign on URL** textbox, type one of the following:

	| **Sign on URL** |
	|----------|
   | `https://optiturn.com/session/new` - production |
	| `https://sandbox.optiturn.com/session/new` - testing |

	> [!NOTE]
   > `<Customer_Name>` should be replaced with a lowercased and underscored version of your company’s name. For example, Fake Corp. would become fake_corp. The [OptiTurn support team](mailto:support@optoro.com) can help choose this value.

1. OptiTurn application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![Screenshot shows the image of attributes configuration.](common/default-attributes.png "Image")

1. In addition to above, OptiTurn application expects few more attributes to be passed back in SAML response, which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name |  Source Attribute|
	| ---------------|  --------- |
	| email | user.mail |
	| first_name | user.givenname |
	| last_name | user.surname |

	> [!Note]
	> The warehouse_identifier assertion attribute is recommended for ease of use, but it isn't required. warehouse_identifier is an identifier for the warehouse where a given employee is physically located. We will match the identifier against a warehouse that's configured in OptiTurn. The user’s activity and data will then be “scoped” to that warehouse.

1. On the **Set-up single sign-on with SAML** page, in the **SAML Signing Certificate** section, find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

    ![Screenshot shows the Certificate download link.](common/certificatebase64.png "Certificate")

1. On the **Set up OptiTurn** section, copy the appropriate URL(s) based on your requirement.

	![Screenshot shows to copy configuration appropriate URL.](common/copy-configuration-urls.png "Metadata")

## Configure OptiTurn SSO

To configure single sign-on on **OptiTurn** side, you need to send the downloaded **Certificate (Base64)** and appropriate copied URLs from the application configuration to [OptiTurn support team](mailto:support@optoro.com). They set this setting to have the SAML SSO connection set properly on both sides

### Create OptiTurn test user

In this section, a user called B.Simon is created in OptiTurn. OptiTurn supports just-in-time user provisioning, which is enabled by default. There's no action item for you in this section. If a user doesn't already exist in OptiTurn, a new one is commonly created after authentication.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to OptiTurn Sign-on URL where you can initiate the login flow. 

* Go to OptiTurn Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the OptiTurn tile in the My Apps, this option redirects to OptiTurn Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Additional resources

* [What is single sign-on with Microsoft Entra ID?](~/identity/enterprise-apps/what-is-single-sign-on.md)
* [Plan a single sign-on deployment](~/identity/enterprise-apps/plan-sso-deployment.md).

## Related content

Once you configure OptiTurn you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).

---
title: Configure CrowdStrike Falcon Platform for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and CrowdStrike Falcon Platform.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and CrowdStrike Falcon Platform so that I can control who has access to CrowdStrike Falcon Platform, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure CrowdStrike Falcon Platform for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate CrowdStrike Falcon Platform with Microsoft Entra ID. When you integrate CrowdStrike Falcon Platform with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to CrowdStrike Falcon Platform.
* Enable your users to be automatically signed-in to CrowdStrike Falcon Platform with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

To get started, you need the following items:

* A Microsoft Entra subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* A valid CrowdStrike Falcon subscription.
* Along with Cloud Application Administrator, Application Administrator can also add or manage applications in Microsoft Entra ID.
For more information, see [Azure built-in roles](~/identity/role-based-access-control/permissions-reference.md).

> [!NOTE]
> This integration is also available to use from Microsoft Entra US Government Cloud environment. You can find this application in the Microsoft Entra US Government Cloud Application Gallery and configure it in the same way as you do from public cloud.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* CrowdStrike Falcon Platform supports **SP and IDP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Adding CrowdStrike Falcon Platform from the gallery

To configure the integration of CrowdStrike Falcon Platform into Microsoft Entra ID, you need to add CrowdStrike Falcon Platform from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **CrowdStrike Falcon Platform** in the search box.
1. Select **CrowdStrike Falcon Platform** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-crowdstrike-falcon-platform'></a>

## Configure and test Microsoft Entra SSO for CrowdStrike Falcon Platform

Configure and test Microsoft Entra SSO with CrowdStrike Falcon Platform using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in CrowdStrike Falcon Platform.

To configure and test Microsoft Entra SSO with CrowdStrike Falcon Platform, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure CrowdStrike Falcon Platform SSO](#configure-crowdstrike-falcon-platform-sso)** - to configure the single sign-on settings on application side.
    1. **[Create CrowdStrike Falcon Platform test user](#create-crowdstrike-falcon-platform-test-user)** - to have a counterpart of B.Simon in CrowdStrike Falcon Platform that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **CrowdStrike Falcon Platform** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows to edit Basic SAML Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier** text box, type one of the following URLs:

    | Identifier |
    | -------------- |
    | `https://falcon.crowdstrike.com/saml/metadata` |
    | `https://falcon.us-2.crowdstrike.com/saml/metadata` |
    | `https://falcon.eu-1.crowdstrike.com/saml/metadata` |
    | `https://falcon.laggar.gcw.crowdstrike.com/saml/metadata` |
    |

    b. In the **Reply URL** text box, type one of the following URLs:

    | Reply URL |
    | -------------- |
    | `https://falcon.crowdstrike.com/saml/acs` |
    | `https://falcon.us-2.crowdstrike.com/saml/acs` |
    | `https://falcon.eu-1.crowdstrike.com/saml/acs` |
    | `https://falcon.laggar.gcw.crowdstrike.com/saml/acs` |
    |

1. Select **Set additional URLs** and perform the following step, if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type one of the following URLs:

    | Sign-on URL |
    | -------------- |
    | `https://falcon.crowdstrike.com/login/sso` |
    | `https://falcon.us-2.crowdstrike.com/login/sso` |
    | `https://falcon.eu-1.crowdstrike.com/login/sso` |
    | `https://falcon.laggar.gcw.crowdstrike.com/login/sso` |
    |

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![Screenshot shows the Certificate download link.](common/copy-metadataurl.png "Certificate")

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure CrowdStrike Falcon Platform SSO

To configure single sign-on on **CrowdStrike Falcon Platform** side, you need to send the **App Federation Metadata Url** to [CrowdStrike Falcon Platform support team](mailto:support@crowdstrike.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create CrowdStrike Falcon Platform test user

In this section, you create a user called Britta Simon in CrowdStrike Falcon Platform. Work with [CrowdStrike Falcon Platform support team](mailto:support@crowdstrike.com) to add the users in the CrowdStrike Falcon Platform platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

#### SP initiated:

* Select **Test this application**, this option redirects to CrowdStrike Falcon Platform Sign-on URL where you can initiate the login flow.  

* Go to CrowdStrike Falcon Platform Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Select **Test this application**, and you should be automatically signed in to the CrowdStrike Falcon Platform for which you set up the SSO.

You can also use Microsoft My Apps to test the application in any mode. When you select the CrowdStrike Falcon Platform tile in the My Apps, if configured in SP mode you would be redirected to the application sign-on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the CrowdStrike Falcon Platform for which you set up the SSO. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure CrowdStrike Falcon Platform you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

---
title: Configure CompetencyIQ for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and CompetencyIQ.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 03/25/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and CompetencyIQ so that I can control who has access to CompetencyIQ, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure CompetencyIQ for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate CompetencyIQ with Microsoft Entra ID. When you integrate CompetencyIQ with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to CompetencyIQ.
* Enable your users to be automatically signed-in to CompetencyIQ with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites

To get started, you need the following items:

* A Microsoft Entra subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* CompetencyIQ single sign-on (SSO) enabled subscription.
* Along with Cloud Application Administrator, Application Administrator can also add or manage applications in Microsoft Entra ID.
For more information, see [Azure built-in roles](~/identity/role-based-access-control/permissions-reference.md).

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* CompetencyIQ supports **SP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add CompetencyIQ from the gallery

To configure the integration of CompetencyIQ into Microsoft Entra ID, you need to add CompetencyIQ from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **CompetencyIQ** in the search box.
1. Select **CompetencyIQ** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 [!INCLUDE [sso-wizard.md](~/identity/saas-apps/includes/sso-wizard.md)]

<a name='configure-and-test-azure-ad-sso-for-competencyiq'></a>

## Configure and test Microsoft Entra SSO for CompetencyIQ

Configure and test Microsoft Entra SSO with CompetencyIQ using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in CompetencyIQ.

To configure and test Microsoft Entra SSO with CompetencyIQ, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure CompetencyIQ SSO](#configure-competencyiq-sso)** - to configure the single sign-on settings on application side.
    1. **[Create CompetencyIQ test user](#create-competencyiq-test-user)** - to have a counterpart of B.Simon in CompetencyIQ that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **CompetencyIQ** application integration page, find the **Manage** section and select **single sign-on**.
2. On the **Select a single sign-on method** page, select **SAML**.
3. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

    ![Screenshot shows to edit Basic S A M L Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, perform the following steps:

    a. In the **Identifier (Entity ID)** text box, type the URL:
    `https://www.competencyiq.com/`

    b. In the **Sign on URL** text box, type a URL using the following pattern:
    `https://<customer>.competencyiq.com/`

    > [!NOTE]
    > The Sign on URL value isn't real. Update the value with the actual Sign on URL. Contact CompetencyIQ Client support team to get the value. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

    ![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

6. On the **Set up CompetencyIQ** section, copy the appropriate URL(s) as per your requirement.

   ![Screenshot shows to copy appropriate configuration U R L.](common/copy-configuration-urls.png "Configuration")

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure CompetencyIQ SSO

To configure single sign-on on **CompetencyIQ** side, you need to send the downloaded **Federation Metadata XML** and appropriate copied URLs from the application configuration to CompetencyIQ support team. They set this setting to have the SAML SSO connection set properly on both sides.

### Create CompetencyIQ test user

In this section, you create a user called Britta Simon in CompetencyIQ. Work with CompetencyIQ support team to add the users in the CompetencyIQ platform. Users must be created and activated before you use single sign-on.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to CompetencyIQ Sign-on URL where you can initiate the login flow. 

* Go to CompetencyIQ Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the CompetencyIQ tile in the My Apps, this option redirects to CompetencyIQ Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure CompetencyIQ you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Cloud App Security](/cloud-app-security/proxy-deployment-aad).

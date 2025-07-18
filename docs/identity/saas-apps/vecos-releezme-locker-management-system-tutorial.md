---
title: Configure VECOS Releezme Locker management system for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and VECOS Releezme Locker management system.

author: nguhiu
manager: mwongerapk
ms.reviewer: CelesteDG
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu


# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and VECOS Releezme Locker management system so that I can control who has access to VECOS Releezme Locker management system, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---

# Configure VECOS Releezme Locker management system for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate VECOS Releezme Locker management system with Microsoft Entra ID. When you integrate VECOS Releezme Locker management system with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to VECOS Releezme Locker management system. Access to the VECOS Releezme Locker Management System is only needed for users who need to manage the lockers, that is, facility managers, service desk employees, and so on.
* Enable your users to be automatically signed-in to VECOS Releezme Locker management system with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* VECOS Releezme Locker management system single sign-on (SSO) enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra SSO in a test environment.

* VECOS Releezme Locker management system supports **SP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add VECOS Releezme Locker management system from the gallery

To configure the integration of VECOS Releezme Locker management system into Microsoft Entra ID, you need to add VECOS Releezme Locker management system from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **VECOS Releezme Locker management system** in the search box.
1. Select **VECOS Releezme Locker management system** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-vecos-releezme-locker-management-system'></a>

## Configure and test Microsoft Entra SSO for VECOS Releezme Locker management system

Configure and test Microsoft Entra SSO with VECOS Releezme Locker management system using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between a Microsoft Entra user and the related user in VECOS Releezme Locker management system.

To configure and test Microsoft Entra SSO with VECOS Releezme Locker management system, perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with B.Simon.
    1. **Assign the Microsoft Entra test user** - to enable B.Simon to use Microsoft Entra single sign-on.
1. **[Configure VECOS Releezme Locker management system SSO](#configure-vecos-releezme-locker-management-system-sso)** - to configure the single sign-on settings on application side.
    1. **[Create VECOS Releezme Locker management system test user](#create-vecos-releezme-locker-management-system-test-user)** - to have a counterpart of B.Simon in VECOS Releezme Locker management system that's linked to the Microsoft Entra representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **VECOS Releezme Locker management system** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps: 

	a. In the **Identifier(Entity ID)** text box, type a URL using the following pattern: 
    `https://<baseURL>/`

    b. In the **Reply URL** textbox, type a URL using the following pattern: 
    `https://<baseURL>/Saml2/Acs`
    
    c. In the **Sign on URL** text box, type a URL using the following pattern:   
    `https://<baseURL>/sso` (optionally add the `?companycode=` query parameter with the company code value given by VECOS.)

    > [!NOTE]
    > These values aren't real. Update these values with the actual Identifier, Reply URL and Sign on URL. Contact [VECOS Releezme Locker management system support team](mailto:servicedesk@vecos.com) what region you're connecting to. Depending on your region, the URL's below is different:

    | **Region** | **baseURL** |
    |-------|-------|
	| Europe| `https://www.releezme.net` |
	| North America | `https://na.releezme.net` |
	| Asia Pacific | `https://au.releezme.net` |

1. On the **Set up single sign-on with SAML** page, In the **SAML Signing Certificate** section, select copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

## Configure VECOS Releezme Locker management system Roles

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **App registrations**, and then select **All applications**.
1. In the app registrations list, select **VECOS Releezme Locker management system**.
1. In the app registration open **App roles**.
1. In the app roles page, create a new app role by selecting **Create app role**
1. In the **display name** field enter a name for the role, e.g., `VECOS Company Facility Manager`.
1. Select **Users/Groups** as the **Allowed member types** value.
1. Enter the VECOS Releezme Locker management system role name in the **Value** field. See table below.
1. Select **Apply**.

| Role | Role Value | Description |
| -- | --------- | ---------- |
| Service Desk | CompanyServiceDesk | Limited access service desk. Mostly read-only access |
| Service Desk+ | CompanyServiceDeskPlus | Advanced version of the service desk with more read/write access |
| Facility Manager | CompanyFacilityManager | Facility Manager with access to setup of the company |
| Facility Manager+ | CompanyFacilityManagerPlus | Advanced Facility Manager with additional access within the company. |
| Administrator | CompanyAdmin | Administrator with full company access |

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure VECOS Releezme Locker management system SSO

To configure single sign-on on **VECOS Releezme Locker management system** side, you need to send the **App Federation Metadata Url** to [VECOS Releezme Locker management system support team](mailto:servicedesk@vecos.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Create VECOS Releezme Locker management system test user

In this section, you create a user called Britta Simon in VECOS Releezme Locker management system. Work with [VECOS Releezme Locker management system support team](mailto:servicedesk@vecos.com) to add the users in the VECOS Releezme Locker management system platform. Users must be created and activated before you use single sign-on.

## Test SSO 

In this section, you test your Microsoft Entra single sign-on configuration with following options. 

* Select **Test this application**, this option redirects to VECOS Releezme Locker management system Sign-on URL where you can initiate the login flow. 

* Go to VECOS Releezme Locker management system Sign-on URL directly and initiate the login flow from there.

* You can use Microsoft My Apps. When you select the VECOS Releezme Locker management system tile in the My Apps, this option redirects to VECOS Releezme Locker management system Sign-on URL. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

## Related content

Once you configure VECOS Releezme Locker management system you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

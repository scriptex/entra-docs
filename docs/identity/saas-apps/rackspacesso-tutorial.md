---
title: Configure Rackspace SSO for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and Rackspace SSO.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and Rackspace SSO so that I can control who has access to Rackspace SSO, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure Rackspace SSO for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate Rackspace SSO with Microsoft Entra ID. When you integrate Rackspace SSO with Microsoft Entra ID, you can:

* Control in Microsoft Entra ID who has access to Rackspace SSO.
* Enable your users to be automatically signed-in to Rackspace SSO with their Microsoft Entra accounts.
* Manage your accounts in one central location.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* Rackspace SSO single sign-on enabled subscription.

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* Rackspace SSO supports **IDP** initiated SSO.

> [!NOTE]
> Identifier of this application is a fixed string value so only one instance can be configured in one tenant.

## Add Rackspace SSO from the gallery

To configure the integration of Rackspace SSO into Microsoft Entra ID, you need to add Rackspace SSO from the gallery to your list of managed SaaS apps.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the **Add from the gallery** section, type **Rackspace SSO** in the search box.
1. Select **Rackspace SSO** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

 Alternatively, you can also use the [Enterprise App Configuration Wizard](https://portal.office.com/AdminPortal/home?Q=Docs#/azureadappintegration). In this wizard, you can add an application to your tenant, add users/groups to the app, assign roles, and walk through the SSO configuration as well. [Learn more about Microsoft 365 wizards.](/microsoft-365/admin/misc/azure-ad-setup-guides)

<a name='configure-and-test-azure-ad-sso-for-rackspace-sso'></a>

## Configure and test Microsoft Entra SSO for Rackspace SSO

In this section, you configure and test Microsoft Entra single sign-on with Rackspace SSO based on a test user called **Britta Simon**.
When using single sign-on with Rackspace, the Rackspace users are automatically created the first time they sign in to the Rackspace portal. 

To configure and test Microsoft Entra single sign-on with Rackspace SSO, you need to perform the following steps:

1. **[Configure Microsoft Entra SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with Britta Simon.
    1. **Assign the Microsoft Entra test user** - to enable Britta Simon to use Microsoft Entra single sign-on.
2. **[Configure Rackspace SSO](#configure-rackspace-sso)** - to configure the Single Sign-On settings on application side.
    1. **[Set up Attribute Mapping in the Rackspace Control Panel](#set-up-attribute-mapping-in-the-rackspace-control-panel)** - to assign Rackspace roles to Microsoft Entra users.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

<a name='configure-azure-ad-sso'></a>

## Configure Microsoft Entra SSO

Follow these steps to enable Microsoft Entra SSO.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **Rackspace SSO** > **Single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, select the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Screenshot shows to edit Basic S A M L Configuration.](common/edit-urls.png "Basic Configuration")

1. On the **Basic SAML Configuration** section, upload the **Service Provider metadata file** which you can download from the [URL](https://login.rackspace.com/federate/sp.xml) and perform the following steps:

	a. Select **Upload metadata file**.

    ![Screenshot shows Basic S A M L Configuration with the Upload metadata file link.](common/upload-metadata.png "Metadata")

	b. Select **folder logo** to select the metadata file and select **Upload**.

	![Screenshot shows a dialog box where you can select and upload a file.](common/browse-upload-metadata.png "Folder")

	c. Once the metadata file is successfully uploaded, the necessary URLs get auto populated automatically.

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![Screenshot shows the Certificate download link.](common/metadataxml.png "Certificate")

This file is uploaded to Rackspace to populate required Identity Federation configuration settings.

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

## Configure Rackspace SSO

To configure single sign-on on **Rackspace SSO** side:

1. See the documentation at [Add an Identity Provider to the Control Panel](https://developer.rackspace.com/docs/rackspace-federation/gettingstarted/add-idp-cp/)
1. It will lead you through the steps to:
    1. Create a new Identity Provider.
    1. Specify an email domain that users will use to identify your company when signing in.
    1. Upload the **Federation Metadata XML** previously downloaded from the Azure control panel.

This will correctly configure the basic SSO settings needed for Azure and Rackspace to connect.

### Set up Attribute Mapping in the Rackspace control panel

Rackspace uses an **Attribute Mapping Policy** to assign Rackspace roles and groups to your single sign-on users. The **Attribute Mapping Policy** translates Microsoft Entra SAML claims into the user configuration fields Rackspace requires. More documentation can be found in the Rackspace [Attribute Mapping Basics documentation](https://developer.rackspace.com/docs/rackspace-federation/appendix/map/). Some considerations:

* If you want to assign varying levels of Rackspace access using Microsoft Entra groups, you need to enable the Groups claim in the Azure **Rackspace SSO** Single Sign-on settings. The **Attribute Mapping Policy** will then be used to match those groups to desired Rackspace roles and groups:

    ![Screenshot shows the Groups claim settings.](common/sso-groups-claim.png "Groups")

* By default, Microsoft Entra ID sends the UID of Microsoft Entra groups in the SAML claim, versus the name of the Group. However, if you're synchronizing your on-premises Active Directory to Microsoft Entra ID, you have the option to send the actual names of the groups:

    ![Screenshot shows the Groups claim name settings.](common/sso-groups-claims-names.png "Claims")

The following example **Attribute Mapping Policy** demonstrates:
1. Setting the Rackspace user's name to the `user.name` SAML claim. Any claim can be used, but it's most common to set this to a field containing the user's email address.
1. Setting the Rackspace roles `admin` and `billing:admin` on a user by matching a Microsoft Entra group, by either Group Name or Group UID. A *substitution* of `"{0}"` in the `roles` field is used, and is replaced by the results of the `remote` rule expressions.
1. Using the `"{D}"` *default substitution* to let Rackspace retrieve additional SAML fields by looking for standard and well-known SAML claims in the SAML exchange.

```yaml
---
mapping:
    rules:
    - local:
        user:
          domain: "{D}"
          name: "{At(http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name)}"
          email: "{D}"
          roles:
              - "{0}"
          expire: "{D}"
      remote:
          - path: |
              (
                if (mapping:get-attributes('http://schemas.microsoft.com/ws/2008/06/identity/claims/groups')='7269f9a2-aabb-9393-8e6d-282e0f945985') then ('admin', 'billing:admin') else (),
                if (mapping:get-attributes('http://schemas.microsoft.com/ws/2008/06/identity/claims/groups')='MyAzureGroup') then ('admin', 'billing:admin') else ()
              )
            multiValue: true
  version: RAX-1
```
> [!TIP]
> Ensure that you use a text editor that validates YAML syntax when editing your policy file.

See the Rackspace [Attribute Mapping Basics documentation](https://developer.rackspace.com/docs/rackspace-federation/appendix/map/) for more examples.

## Test SSO

In this section, you test your Microsoft Entra single sign-on configuration with following options.

* Select **Test this application**, and you should be automatically signed in to the Rackspace SSO for which you set up the SSO.

* You can use Microsoft My Apps. When you select the Rackspace SSO tile in the My Apps, you should be automatically signed in to the Rackspace SSO for which you set up the SSO. For more information, see [Microsoft Entra My Apps](/azure/active-directory/manage-apps/end-user-experiences#azure-ad-my-apps).

You can also use the **Validate** button in the **Rackspace SSO** Single sign-on settings:

   ![Screenshot shows the SSO Validate Button.](common/sso-validate-sign-on.png "Validate")

## Related content

Once you configure Rackspace SSO you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-aad).

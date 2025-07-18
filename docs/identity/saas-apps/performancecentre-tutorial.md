---
title: Configure PerformanceCentre for Single sign-on with Microsoft Entra ID
description: Learn how to configure single sign-on between Microsoft Entra ID and PerformanceCentre.

author: nguhiu
manager: mwongerapk
ms.reviewer: celested
ms.service: entra-id
ms.subservice: saas-apps

ms.topic: how-to
ms.date: 05/20/2025
ms.author: gideonkiratu

# Customer intent: As an IT administrator, I want to learn how to configure single sign-on between Microsoft Entra ID and PerformanceCentre so that I can control who has access to PerformanceCentre, enable automatic sign-in with Microsoft Entra accounts, and manage my accounts in one central location.
---
# Configure PerformanceCentre for Single sign-on with Microsoft Entra ID

In this article,  you learn how to integrate PerformanceCentre with Microsoft Entra ID.
Integrating PerformanceCentre with Microsoft Entra ID provides you with the following benefits:

* You can control in Microsoft Entra ID who has access to PerformanceCentre.
* You can enable your users to be automatically signed-in to PerformanceCentre (Single Sign-On) with their Microsoft Entra accounts.
* You can manage your accounts in one central location.

If you want to know more details about SaaS app integration with Microsoft Entra ID, see [What is application access and single sign-on with Microsoft Entra ID](~/identity/enterprise-apps/what-is-single-sign-on.md).
If you don't have an Azure subscription, [create a free account](https://azure.microsoft.com/free/) before you begin.

## Prerequisites
The scenario outlined in this article assumes that you already have the following prerequisites:

[!INCLUDE [common-prerequisites.md](~/identity/saas-apps/includes/common-prerequisites.md)]
* PerformanceCentre single sign-on enabled subscription

## Scenario description

In this article,  you configure and test Microsoft Entra single sign-on in a test environment.

* PerformanceCentre supports **SP** initiated SSO

## Adding PerformanceCentre from the gallery

To configure the integration of PerformanceCentre into Microsoft Entra ID, you need to add PerformanceCentre from the gallery to your list of managed SaaS apps.

**To add PerformanceCentre from the gallery, perform the following steps:**

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **New application**.
1. In the search box, type **PerformanceCentre**, select **PerformanceCentre** from result panel then select **Add** button to add the application.

	 ![PerformanceCentre in the results list](common/search-new-app.png)

<a name='configure-and-test-azure-ad-single-sign-on'></a>

## Configure and test Microsoft Entra single sign-on

In this section, you configure and test Microsoft Entra single sign-on with PerformanceCentre based on a test user called **Britta Simon**.
For single sign-on to work, a link relationship between a Microsoft Entra user and the related user in PerformanceCentre needs to be established.

To configure and test Microsoft Entra single sign-on with PerformanceCentre, you need to complete the following building blocks:

1. **[Configure Microsoft Entra Single Sign-On](#configure-azure-ad-single-sign-on)** - to enable your users to use this feature.
2. **[Configure PerformanceCentre Single Sign-On](#configure-performancecentre-single-sign-on)** - to configure the Single Sign-On settings on application side.
3. **Create a Microsoft Entra test user** - to test Microsoft Entra single sign-on with Britta Simon.
4. **Assign the Microsoft Entra test user** - to enable Britta Simon to use Microsoft Entra single sign-on.
5. **[Create PerformanceCentre test user](#create-performancecentre-test-user)** - to have a counterpart of Britta Simon in PerformanceCentre that's linked to the Microsoft Entra representation of user.
6. **[Test single sign-on](#test-single-sign-on)** - to verify whether the configuration works.

<a name='configure-azure-ad-single-sign-on'></a>

### Configure Microsoft Entra single sign-on

In this section, you enable Microsoft Entra single sign-on.

To configure Microsoft Entra single sign-on with PerformanceCentre, perform the following steps:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Cloud Application Administrator](~/identity/role-based-access-control/permissions-reference.md#cloud-application-administrator).
1. Browse to **Entra ID** > **Enterprise apps** > **PerformanceCentre** application integration page, select **Single sign-on**.

    ![Configure single sign-on link](common/select-sso.png)

1. On the **Select a Single sign-on method** dialog, select **SAML/WS-Fed** mode to enable single sign-on.

    ![Single sign-on select mode](common/select-saml-option.png)

1. On the **Set up Single Sign-On with SAML** page, select **Edit** icon to open **Basic SAML Configuration** dialog.

	![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, perform the following steps:

    ![PerformanceCentre Domain and URLs single sign-on information](common/sp-identifier.png)

	a. In the **Sign on URL** text box, type a URL using the following pattern:
    `http://<companyname>.performancecentre.com/saml/SSO`

    b. In the **Identifier (Entity ID)** text box, type a URL using the following pattern:
    `http://<companyname>.performancecentre.com`

	> [!NOTE]
	> These values aren't real. Update these values with the actual Sign on URL and Identifier. Contact [PerformanceCentre Client support team](https://www.performio.co/contact-us) to get these values. You can also refer to the patterns shown in the **Basic SAML Configuration** section.

4. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, select **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

6. On the **Set up PerformanceCentre** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

	a. Login URL

	b. Microsoft Entra Identifier

	c. Logout URL

### Configure PerformanceCentre Single Sign-On

1. Sign-on to your **PerformanceCentre** company site as administrator.

2. In the tab on the left side, select **Configure**.
   
    ![Screenshot that shows the "PerformanceCenter" menu with "Configure" selected.][10]

3. In the tab on the left side, select **Miscellaneous**, and then select **Single Sign On**.
   
    ![Screenshot that shows the "Configure" tab with "Single Sign-On" selected from the "Miscellaneous" menu.][11]

4. As **Protocol**, select **SAML**.
   
    ![Screenshot that shows the "Single Sign-On Configuration" section with "S A M L" selected from the "Protocol" menu.][12]

5. Open your downloaded metadata file in notepad, copy the content, paste it into the **Identity Provider Metadata** textbox, and then select **Save**.
   
    ![Screenshot that shows the "Identity Provider Metadata" textbox.][13]

6. Verify that the values for the **Entity Base URL** and **Entity ID URL** are correct.
    
     ![Microsoft Entra Single Sign-On][14]

<a name='create-an-azure-ad-test-user'></a>

[!INCLUDE [create-assign-users-sso.md](~/identity/saas-apps/includes/create-assign-users-sso.md)]

### Create PerformanceCentre test user

The objective of this section is to create a user called Britta Simon in PerformanceCentre.

**To create a user called Britta Simon in PerformanceCentre, perform the following steps:**

1. Sign on to your PerformanceCentre company site as administrator.

2. In the menu on the left, select **Interrelate**, and then select **Create Participant**.
   
    ![Screenshot that shows the "PerformanceCenter" company site "Interrelate -Participants" page with the "Create Participant" button selected.][400]

3. On the **Interrelate - Create Participant** dialog, perform the following steps:
   
    ![Create User][401]
	
	a. Type the required attributes for Britta Simon into related textboxes.
	
	>[!IMPORTANT]
    >Britta's User Name attribute in PerformanceCentre must be the same as the User Name in Microsoft Entra ID.
	
	b. Select **Client Administrator** as **Choose Role**.
	
	c. Select **Save**. 

### Test single sign-on 

In this section, you test your Microsoft Entra single sign-on configuration using the Access Panel.

When you select the PerformanceCentre tile in the Access Panel, you should be automatically signed in to the PerformanceCentre for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Additional Resources

- [List of articles on How to Integrate SaaS Apps with Microsoft Entra ID](./tutorial-list.md)

- [What is application access and single sign-on with Microsoft Entra ID?](~/identity/enterprise-apps/what-is-single-sign-on.md)

- [What is Conditional Access in Microsoft Entra ID?](~/identity/conditional-access/overview.md)

<!--Image references-->

[10]: ./media/performancecentre-tutorial/tutorial_performancecentre_06.png
[11]: ./media/performancecentre-tutorial/tutorial_performancecentre_07.png
[12]: ./media/performancecentre-tutorial/tutorial_performancecentre_08.png
[13]: ./media/performancecentre-tutorial/tutorial_performancecentre_09.png
[14]: ./media/performancecentre-tutorial/tutorial_performancecentre_10.png
[400]: ./media/performancecentre-tutorial/tutorial_performancecentre_11.png
[401]: ./media/performancecentre-tutorial/tutorial_performancecentre_12.png

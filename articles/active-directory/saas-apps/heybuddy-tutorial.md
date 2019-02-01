---
title: 'Tutorial: Azure Active Directory integration with HeyBuddy | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and HeyBuddy.
services: active-directory
documentationCenter: na
author: jeevansd
manager: femila
ms.reviewer: joflore

ms.assetid: d51b5af6-018e-4678-9a3f-b70438394f67
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 11/06/2018
ms.author: jeedes

---
# Tutorial: Azure Active Directory integration with HeyBuddy

In this tutorial, you learn how to integrate HeyBuddy with Azure Active Directory (Azure AD).

Integrating HeyBuddy with Azure AD provides you with the following benefits:

- You can control in Azure AD who has access to HeyBuddy.
- You can enable your users to automatically get signed-on to HeyBuddy (Single Sign-On) with their Azure AD accounts.
- You can manage your accounts in one central location - the Azure portal.

If you want to know more details about SaaS app integration with Azure AD, see [what is application access and single sign-on with Azure Active Directory](../manage-apps/what-is-single-sign-on.md)

## Prerequisites

To configure Azure AD integration with HeyBuddy, you need the following items:

- An Azure AD subscription
- A HeyBuddy single sign-on enabled subscription

> [!NOTE]
> To test the steps in this tutorial, we do not recommend using a production environment.

To test the steps in this tutorial, you should follow these recommendations:

- Do not use your production environment, unless it is necessary.
- If you don't have an Azure AD trial environment, you can [get a one-month trial](https://azure.microsoft.com/pricing/free-trial/).

## Scenario description

In this tutorial, you test Azure AD single sign-on in a test environment. 
The scenario outlined in this tutorial consists of two main building blocks:

1. Adding HeyBuddy from the gallery
2. Configuring and testing Azure AD single sign-on

## Adding HeyBuddy from the gallery

To configure the integration of HeyBuddy into Azure AD, you need to add HeyBuddy from the gallery to your list of managed SaaS apps.

**To add HeyBuddy from the gallery, perform the following steps:**

1. In the **[Azure portal](https://portal.azure.com)**, on the left navigation panel, click **Azure Active Directory** icon. 

	![The Azure Active Directory button][1]

2. Navigate to **Enterprise applications**. Then go to **All applications**.

	![The Enterprise applications blade][2]

3. To add new application, click **New application** button on the top of dialog.

	![The New application button][3]

4. In the search box, type **HeyBuddy**, select **HeyBuddy** from result panel then click **Add** button to add the application.

	![HeyBuddy in the results list](./media/heybuddy-tutorial/tutorial_heybuddy_addfromgallery.png)

## Configure and test Azure AD single sign-on

In this section, you configure and test Azure AD single sign-on with HeyBuddy based on a test user called "Britta Simon".

For single sign-on to work, Azure AD needs to know what the counterpart user in HeyBuddy is to a user in Azure AD. In other words, a link relationship between an Azure AD user and the related user in HeyBuddy needs to be established.

To configure and test Azure AD single sign-on with HeyBuddy, you need to complete the following building blocks:

1. **[Configuring Azure AD Single Sign-On](#configuring-azure-ad-single-sign-on)** - to enable your users to use this feature.
2. **[Creating an Azure AD test user](#creating-an-azure-ad-test-user)** - to test Azure AD single sign-on with Britta Simon.
3. **[Creating a HeyBuddy test user](#creating-a-heybuddy-test-user)** - to have a counterpart of Britta Simon in HeyBuddy that is linked to the Azure AD representation of user.
4. **[Assigning the Azure AD test user](#assigning-the-azure-ad-test-user)** - to enable Britta Simon to use Azure AD single sign-on.
5. **[Testing single sign-on](#testing-single-sign-on)** - to verify whether the configuration works.

### Configuring Azure AD single sign-on

In this section, you enable Azure AD single sign-on in the Azure portal and configure single sign-on in your HeyBuddy application.

**To configure Azure AD single sign-on with HeyBuddy, perform the following steps:**

1. In the Azure portal, on the **HeyBuddy** application integration page, click **Single sign-on**.

	![Configure single sign-on link][4]

2. On the **Select a Single sign-on method** dialog, Click **Select** for **SAML** mode to enable single sign-on.

    ![Configure Single Sign-On](common/tutorial_general_301.png)

3. On the **Set up Single Sign-On with SAML** page, click **Edit** icon to open **Basic SAML Configuration** dialog.

	![Configure Single Sign-On](common/editconfigure.png)

4. On the **Basic SAML Configuration** section, perform the following steps:

	![HeyBuddy Domain and URLs single sign-on information](./media/heybuddy-tutorial/tutorial_heybuddy_url.png)

    a. In the **Sign on URL** textbox, type a URL using the following pattern: `https://api.heybuddy.com/auth/<ENTITY ID>`

	b. In the **Identifier (Entity ID)** textbox, type a URL using the following pattern: `YourCompanyInstanceofHeyBuddy`

	> [!NOTE]
	> These values are not real. Update these values with the actual Sign-On URL and Identifier (Entity ID). The `Entity ID` in the Sign on url is auto generated for each organization. Contact [HeyBuddy Client support team](mailto:support@heybuddy.com) to get these values.

5. HeyBuddy application expects the SAML assertions in a specific format. Configure the following claims for this application. You can manage the values of these attributes from the **User Attributes & Claims** section on application integration page. On the **Set up Single Sign-On with SAML** page, click **Edit** button to open **User Attributes & Claims** dialog.

	![image](./media/heybuddy-tutorial/tutorial_heybuddy_attribute.png)

	>[!NOTE]
	>Please refer to this [link](https://docs.microsoft.com/azure/active-directory/develop/active-directory-enterprise-app-role-management) on how to configure and setup the roles for the application.

6. In the **User Claims** section on the **User Attributes & Claims** dialog, configure SAML token attribute as shown in the image above and perform the following steps:
    
	| Name  | Source Attribute  |
	| --------------- | --------------- |
	| Roles 			  | user.assignedroles |

	a. Click **Add new claim** to open the **Manage user claims** dialog.

	![image](./common/new_save_attribute.png)

	![image](./common/new_attribute_details.png)

	b. In the **Name** textbox, type the attribute name shown for that row.

	c. Leave the **Namespace** value blank.

	d. Select Source as **Attribute**.

	e. From the **Source attribute** list, type the attribute value shown for that row.

	f. Click **Save**.

7. On the **SAML Signing Certificate** page, in the **SAML Signing Certificate** section, click the copy **icon** to copy **App Federation Metadata Url** and paste it into notepad.

	![The Certificate download link](./media/heybuddy-tutorial/tutorial_heybuddy_certificate.png) 

8. To configure single sign-on on **HeyBuddy** side, you need to send the copied **App Federation Metadata Url** to [HeyBuddy support team](mailto:support@heybuddy.com). They set this setting to have the SAML SSO connection set properly on both sides.

### Creating an Azure AD test user

The objective of this section is to create a test user in the Azure portal called Britta Simon.

1. In the Azure portal, in the left pane, select **Azure Active Directory**, select **Users**, and then select **All users**.

	![Create Azure AD User][100]

2. Select **New user** at the top of the screen.

	![Creating an Azure AD test user](common/create_aaduser_01.png) 

3. In the User properties, perform the following steps.

	![Creating an Azure AD test user](common/create_aaduser_02.png)

    a. In the **Name** field, enter **BrittaSimon**.
  
    b. In the **User name** field, type **brittasimon@yourcompanydomain.extension**  
    For example, BrittaSimon@contoso.com

    c. Select **Properties**, select the **Show password** check box, and then write down the value that's displayed in the Password box.

    d. Select **Create**.

### Creating a HeyBuddy test user

The objective of this section is to create a user called Britta Simon in HeyBuddy. HeyBuddy supports just-in-time provisioning, which is by default enabled. There is no action item for you in this section. A new user is created during an attempt to access HeyBuddy if it doesn't exist yet.
>[!Note]
>If you need to create a user manually, contact [HeyBuddy support team](mailto:support@heybuddy.com).

### Assigning the Azure AD test user

In this section, you enable Britta Simon to use Azure single sign-on by granting access to HeyBuddy.

1. In the Azure portal, select **Enterprise Applications**, select **All applications**.

	![Assign User][201]

2. In the applications list, select **HeyBuddy**.

	![Configure Single Sign-On](./media/heybuddy-tutorial/tutorial_heybuddy_app.png)

3. In the menu on the left, click **Users and groups**.

	![Assign User][202]

4. Click **Add** button. Then select **Users and groups** on **Add Assignment** dialog.

	![Assign User][203]

5. In the **Users and groups** dialog select **Britta Simon** in the Users list, then click the **Select** button at the bottom of the screen.

6. In the **Add Assignment** dialog select the **Assign** button.

### Testing single sign-on

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the HeyBuddy tile in the Access Panel, you should get automatically signed-on to your HeyBuddy application.
For more information about the Access Panel, see [Introduction to the Access Panel](../user-help/active-directory-saas-access-panel-introduction.md).

## Additional resources

* [List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory](tutorial-list.md)
* [What is application access and single sign-on with Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: common/tutorial_general_01.png
[2]: common/tutorial_general_02.png
[3]: common/tutorial_general_03.png
[4]: common/tutorial_general_04.png

[100]: common/tutorial_general_100.png

[201]: common/tutorial_general_201.png
[202]: common/tutorial_general_202.png
[203]: common/tutorial_general_203.png

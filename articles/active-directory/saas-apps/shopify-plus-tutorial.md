---
title: 'Tutorial: Azure Active Directory single sign-on (SSO) integration with Shopify Plus | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Shopify Plus.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 09/01/2021
ms.author: jeedes
---

# Tutorial: Azure Active Directory single sign-on (SSO) integration with Shopify Plus

In this tutorial, you'll learn how to integrate Shopify Plus with Azure Active Directory (Azure AD). When you integrate Shopify Plus with Azure AD, you can:

* Control in Azure AD who has access to Shopify Plus.
* Enable your users to be automatically signed-in to Shopify Plus with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Shopify Plus single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment.

* Shopify Plus supports **SP and IDP** initiated SSO.
* Shopify Plus supports [Automated user provisioning](shopify-plus-provisioning-tutorial.md).

## Add Shopify Plus from the gallery

To configure the integration of Shopify Plus into Azure AD, you need to add Shopify Plus from the gallery to your list of managed SaaS apps.

1. Sign in to the Azure portal using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **Shopify Plus** in the search box.
1. Select **Shopify Plus** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

## Configure and test Azure AD SSO for Shopify Plus

Configure and test Azure AD SSO with Shopify Plus using a test user called **B.Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in Shopify Plus.

To configure and test Azure AD SSO with Shopify Plus, perform the following steps:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** - to enable your users to use this feature.
    1. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with B.Simon.
    1. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable B.Simon to use Azure AD single sign-on.
1. **[Configure Shopify Plus SSO](#configure-shopify-plus-sso)** - to configure the single sign-on settings on application side.
    1. **[Create Shopify Plus test user](#create-shopify-plus-test-user)** - to have a counterpart of B.Simon in Shopify Plus that is linked to the Azure AD representation of user.
1. **[Test SSO](#test-sso)** - to verify whether the configuration works.

## Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the Azure portal, on the **Shopify Plus** application integration page, find the **Manage** section and select **single sign-on**.
1. On the **Select a single sign-on method** page, select **SAML**.
1. On the **Set up single sign-on with SAML** page, click the pencil icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

1. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, enter the values for the following fields:

    In the **Reply URL** text box, type a URL using the following pattern:
    `https://accounts.shopify.com/saml/consume/organization/<ORGANIZATION_ID>`

1. Click **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    In the **Sign-on URL** text box, type the URL:
    `https://shopify.plus/login`

	> [!NOTE]
	> The Reply URL value is not real. Update the value with the actual Reply URL. Contact [Shopify Plus Client support team](mailto:plus-user-management@shopify.com) to get the value. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal.

1. Shopify Plus application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes.

	![image](common/default-attributes.png)

1. In addition to above, Shopify Plus application expects few more attributes to be passed back in SAML response which are shown below. These attributes are also pre populated but you can review them as per your requirements.

	| Name | Source Attribute|
	| ---- | --------------- |
	| email | user.mail |

1. Change the **Name ID** format to **Persistent**. Select the **Unique User Identifier (Name ID)** option, and then select the **Name identifier** format. Select **Persistent** for this option. Save your changes.
1. On the **Set up single sign-on with SAML** page, in the **SAML Signing Certificate** section, select the copy button to copy **App Federation Metadata Url** and save it on your computer.

	![The Certificate download link](common/copy-metadataurl.png)

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B.Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B.Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B.Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B.Simon to use Azure single sign-on by granting access to Shopify Plus.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **Shopify Plus**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.
1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.
1. In the **Users and groups** dialog, select **B.Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you are expecting a role to be assigned to the users, you can select it from the **Select a role** dropdown. If no role has been set up for this app, you see "Default Access" role selected.
1. In the **Add Assignment** dialog, click the **Assign** button.

## Configure Shopify Plus SSO

To view the full steps, see [Shopify's documentation on setting up SAML integrations](https://help.shopify.com/en/manual/shopify-plus/saml).

To configure single sign-on on the **Shopify Plus** side, copy the **App Federation Metadata URL** from Azure Active Directory. Then, log into the [organization admin](https://shopify.plus) and go to **Users** > **Security**. Select **Set up configuration**, and then paste your App Federation Metadata URL in the **Identity provider metadata URL** section. Select **Add** to complete this step.

### Create Shopify Plus test user

In this section, you create a user called B.Simon in Shopify Plus. Return to the **Users** section and add a user by entering their email and permissions. Users must be created and activated before you use single sign-on.

> [!NOTE]
> Shopify Plus also supports automatic user provisioning, you can find more details [here](./shopify-plus-provisioning-tutorial.md) on how to configure automatic user provisioning.

### Enforce SAML authentication

> [!NOTE]
> We recommend testing the integration by using individual users before applying broadly.

Individual users:
1. Go to an individual user’s page in Shopify Plus with an email domain that’s managed by Azure AD and verified in Shopify Plus.
1. In the SAML authentication section, select **Edit**, select **Required**, and then select **Save**.
1. Test that this user can successfully sign in via the idP-initiated and SP-initiated flows.

For all users under an email domain:
1. Return to the **Security** page.
1. Select **Required** for your SAML authentication setting. This enforces SAML for all users with that email domain across Shopify Plus.
1. Select **Save**.

> [!IMPORTANT]
> Enabling SAML for all users under an email domain affects all users who use this application. Users won't be able to sign in by using their regular sign-in page. They will only be able to access the app through Azure Active Directory. Shopify does not provide a backup sign-in URL at which users can sign in by using their normal username and password. You can contact Shopify Support to turn off SAML, if necessary.

## Test SSO 

In this section, you test your Azure AD single sign-on configuration with following options. 

#### SP initiated:

* Click on **Test this application** in Azure portal. This will redirect to Shopify Plus Sign on URL where you can initiate the login flow.  

* Go to Shopify Plus Sign-on URL directly and initiate the login flow from there.

#### IDP initiated:

* Click on **Test this application** in Azure portal and you should be automatically signed in to the Shopify Plus for which you set up the SSO. 

You can also use Microsoft My Apps to test the application in any mode. When you click the Shopify Plus tile in the My Apps, if configured in SP mode you would be redirected to the application sign on page for initiating the login flow and if configured in IDP mode, you should be automatically signed in to the Shopify Plus for which you set up the SSO. For more information about the My Apps, see [Introduction to the My Apps](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Next steps

Once you configure Shopify Plus you can enforce session control, which protects exfiltration and infiltration of your organization’s sensitive data in real time. Session control extends from Conditional Access. [Learn how to enforce session control with Microsoft Defender for Cloud Apps](/cloud-app-security/proxy-deployment-any-app).

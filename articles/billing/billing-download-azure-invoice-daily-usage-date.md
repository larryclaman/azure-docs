---
title: Download Azure billing invoice and daily usage data | Microsoft Docs
description: Describes how to download or view your Azure billing invoice and daily usage data.
keywords: billing invoice,invoice download,azure invoice,azure usage
services: 'billing'
documentationcenter: ''
author: genlin
manager: adpick
editor: ''
tags: billing

ms.service: billing
ms.workload: na
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: banders

---
# Download or view your Azure billing invoice and daily usage data

For most subscriptions, you can download your invoice from the [Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade) or have it sent in email. If you're an Azure customer with an Enterprise Agreement (EA customer), you can't download your organization's invoices. Invoices are sent to whoever is set up to receive invoices for the enrollment.

If you want to download usage as an EA customer, it's available in the [Azure portal](https://portal.azure.com/) > **Cost Management + Billing** > **Usage + charges**. For other subscriptions, go to the [Azure Account Center](https://account.azure.com/Subscriptions).

Only certain roles have permission to get billing invoice and usage information, like the Account Administrator, or Enterprise Administrator. To learn more about getting access to billing information, see [Manage access to Azure billing using roles](billing-manage-access.md).

[!INCLUDE [GDPR-related guidance](../../includes/gdpr-intro-sentence.md)]

## Download or view your invoice

 If you're an EA customer, you can't download your organization's invoices. Invoices are sent to whoever is set up to receive invoices for the  enrollment. For other subscriptions, you can get your invoice in email or download it from the Azure portal.

### Get your invoice in email (.pdf)
You can opt in and configure additional recipients to receive your Azure invoice in an email. This feature may not be available for certain subscriptions such as support offers, Enterprise Agreements, or Azure in Open.

1. Select your subscription from the [Subscriptions page](https://portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade). Opt in for each subscription you own. Click **Invoices** then **Email my invoice**. 

    ![Screenshot that shows the opt-in flow](./media/billing-download-azure-invoice-daily-usage-date/InvoicesDeepLink.PNG)
    
2. Click **Opt in** and accept the terms.

    ![Screenshot that shows the opt-in flow step 2](./media/billing-download-azure-invoice-daily-usage-date/InvoiceArticleStep2.PNG)
 
3. Once you've accepted the agreement, you can configure additional recipients. When a recipient is removed, the email address is no longer stored. If you change your mind, you need to re-add them.

    ![Screenshot that shows the opt-in flow step 3](./media/billing-download-azure-invoice-daily-usage-date/InvoiceArticleStep3.PNG)
    
If you don't get an email after following the steps, make sure your email address is correct in the [communication preferences on your profile](https://account.windowsazure.com/profile).

### Opt out from getting your invoice in email
If you don't want to get your invoice in email, click **Opt out of emailed invoices**. This option removes any email addresses set to receive invoices in email. If you opt back in, you will have to reconfigure recipients.

 ![Screenshot that shows the opt-out flow](./media/billing-download-azure-invoice-daily-usage-date/InvoiceArticleStep4.PNG)

### Download invoice from Azure portal (.pdf)

1. Select your subscription from the [Subscriptions page](https://portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade) in Azure portal as [a user with access to invoices](billing-manage-access.md).

2. Select **Invoices**. 

    ![Screenshot that shows the Billing & usage option](./media/billing-download-azure-invoice-daily-usage-date/billingandusage.png) 

3. Click **Download Invoice** to view a copy of your PDF invoice. If it says **Not available**, see [Why don't I see an invoice for the last billing period?](#noinvoice)

    ![Screenshot that shows billing periods, the download option, and total charges for each billing period](./media/billing-download-azure-invoice-daily-usage-date/billing4.png)

4. You can also view your daily usage by clicking the billing period. 

For more information about your invoice, see [Understand your bill for Microsoft Azure](billing-understand-your-bill.md). For help managing your costs, see [Prevent unexpected costs with Azure billing and cost management](billing-getting-started.md).

### <a name="noinvoice"></a> Why don't I see an invoice for the last billing period?

There could be several reasons that you don't see an invoice:

- You have a monthly credit amount with your subscription that you didn't exceed or you have a Free Trial. An invoice is only generated when you owe money.

- It's less than 30 days from the day you subscribed to Azure.

- The invoice isn't generated yet. Wait until the end of the billing period.

- If you're not the Account Administrator, older invoices may not be available to you.

## Download usage

 For most subscriptions, find your  daily usage file in the [Azure Account Center](https://account.azure.com/Subscriptions). If you want to download usage as an EA customer, it's available in the [Azure portal](https://portal.azure.com/) > **Cost Management + Billing** > **Usage + charges**. 

### Download usage from the Account Center (.csv)

1. Sign into the [Azure Account Center](https://account.windowsazure.com/subscriptions) as the Account Administrator.

2. Select the subscription for which you want the invoice and usage information.

3. Select **BILLING HISTORY**. 

    ![Screenshot that shows billing history option](./media/billing-download-azure-invoice-daily-usage-date/Billinghisotry.png)

4. You can see your statements for the last six billing periods and the current unbilled period. 

    ![Screenshot that shows billing periods, options to download invoice and daily usage, and total charges for each billing period](./media/billing-download-azure-invoice-daily-usage-date/billingSum.png)

5. Select **View Current Statement** to see an estimate of your charges at the time the estimate was generated. This information is only updated daily and may not include all your usage. Your monthly invoice may differ from this estimate.

    ![Screenshot that shows the View Current Statement option](./media/billing-download-azure-invoice-daily-usage-date/billingSum2.png)

    ![Screenshot that shows the estimate of current charges](./media/billing-download-azure-invoice-daily-usage-date/billingSum3.png)

6. Select **Download Usage** to download the daily usage data as a CSV file. If you see two versions available, download version 2.

    ![Screenshot that shows the Download Usage option](./media/billing-download-azure-invoice-daily-usage-date/DLusage.png)

Only the Account Administrator can access the Azure Account Center. Other billing admins, such as an Owner, can get usage information using the [Billing APIs](billing-usage-rate-card-overview.md).

For more information about your daily usage, see [Understand your bill for Microsoft Azure](billing-understand-your-bill.md). For help managing your costs, see [Prevent unexpected costs with Azure billing and cost management](billing-getting-started.md).

### Download usage for EA customers

To view and download usage data as a EA customer, you must be an Enterprise Administrator, or Account Owner or Department Admin with the view charges policy enabled.

1. Sign in to the [Azure portal](https://portal.azure.com).
1. Search on **Cost Management + Billing**.

    ![Screenshot that shows Azure portal search](./media/billing-download-azure-invoice-daily-usage-date/portal-cm-billing-search.png)

1. Select **Usage + charges**.
1. For the month you want to download, select **Download**.

## Need help? Contact us.

If you have questions or need help, [create a support request](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest).

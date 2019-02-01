---
title: What's new? Release notes - Azure Active Directory | Microsoft Docs
description: Learn what is new with Azure Active Directory, such as the latest release notes, known issues, bug fixes, deprecated functionality, and upcoming changes.
services: active-directory
author: eross-msft
manager: daveba
featureFlags:
 - clicktale
 
ms.assetid: 06a149f7-4aa1-4fb9-a8ec-ac2633b031fb
ms.service: active-directory
ms.subservice: fundamentals
ms.workload: identity
ms.topic: conceptual
ms.date: 01/29/2019
ms.author: lizross
ms.reviewer: dhanyahk
ms.custom: it-pro
---

# What's new in Azure Active Directory?

>Get notified about when to revisit this page for updates by copying and pasting this URL: `https://docs.microsoft.com/api/search/rss?search=%22release+notes+for+azure+AD%22&locale=en-us` into your ![RSS icon](./media/whats-new/feed-icon-16x16.png) feed reader.

Azure AD receives improvements on an ongoing basis. To stay up-to-date with the most recent developments, this article provides you with information about:

- The latest releases
- Known issues
- Bug fixes
- Deprecated functionality
- Plans for changes

This page is updated monthly, so revisit it regularly. If you're looking for items that are older than six months, you can find them in the [Archive for What's new in Azure Active Directory](whats-new-archive.md).

---
## January 2019

### New Azure AD Application Proxy cookie settings

**Type:** New feature  
**Service category:** App Proxy  
**Product capability:** Access Control

We've introduced three new cookie settings, available for your apps that are published through Application Proxy:

- **Use HTTP-Only cookie.** Sets the **HTTPOnly** flag on your Application Proxy access and session cookies. Turning on this setting provides additional security benefits, such as helping to prevent copying or modifying of cookies through client-side scripting. We recommend you turn on this flag (choose **Yes**) for the added benefits.

- **Use secure cookie.** Sets the **Secure** flag on your Application Proxy access and session cookies. Turning on this setting provides additional security benefits, by making sure cookies are only transmitted over TLS secure channels, such as HTTPS. We recommend you turn on this flag (choose **Yes**) for the added benefits.

- **Use persistent cookie.** Prevents access cookies from expiring when the web browser is closed. These cookies last for the lifetime of the access token. However, the cookies are reset if the expiration time is reached or if the user manually deletes the cookie. We recommend you keep the default setting **No**, only turning on the setting for older apps that don't share cookies between processes.

For more information about the new cookies, see [Cookie settings for accessing on-premises applications in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-cookie-settings).

---

### New Federated Apps available in Azure AD app gallery - January 2019

**Type:** New feature  
**Service category:** Enterprise Apps  
**Product capability:** 3rd Party Integration
 
In January 2019, we've added these 35 new apps with Federation support to the app gallery:

[Firstbird](https://docs.microsoft.com/azure/active-directory/saas-apps/firstbird-tutorial), [Folloze](https://docs.microsoft.com/azure/active-directory/saas-apps/folloze-tutorial), [Talent Palette](https://docs.microsoft.com/azure/active-directory/saas-apps/talent-palette-tutorial), [Infor CloudSuite](https://docs.microsoft.com/azure/active-directory/saas-apps/infor-cloud-suite-tutorial), [Cisco Umbrella](https://docs.microsoft.com/azure/active-directory/saas-apps/cisco-umbrella-tutorial), [Zscaler Internet Access Administrator](https://docs.microsoft.com/azure/active-directory/saas-apps/zscaler-internet-access-administrator-tutorial), [Expiration Reminder](https://docs.microsoft.com/azure/active-directory/saas-apps/expiration-reminder-tutorial), [InstaVR Viewer](https://docs.microsoft.com/azure/active-directory/saas-apps/instavr-viewer-tutorial), [CorpTax](https://docs.microsoft.com/azure/active-directory/saas-apps/corptax-tutorial), [Verb](https://app.verb.net/login), [MazeMap Link](https://docs.microsoft.com/azure/active-directory/saas-apps/mazemaplink-tutorial), [OpenLattice](https://openlattice.com/agora), [TheOrgWiki](https://www.theorgwiki.com/signup), [Pavaso Digital Close](https://docs.microsoft.com/azure/active-directory/saas-apps/pavaso-digital-close-tutorial), [GoodPractice Toolkit](https://docs.microsoft.com/azure/active-directory/saas-apps/goodpractice-toolkit-tutorial), [Cloud Service PICCO](https://docs.microsoft.com/azure/active-directory/saas-apps/cloud-service-picco-tutorial), [AuditBoard](https://docs.microsoft.com/azure/active-directory/saas-apps/auditboard-tutorial), [iProva](https://docs.microsoft.com/azure/active-directory/saas-apps/iprova-tutorial), [Workable](https://docs.microsoft.com/azure/active-directory/saas-apps/workable-tutorial), [CallPlease](https://webapp.callplease.com/create-account/create-account.html), [GTNexus SSO System](https://docs.microsoft.com/azure/active-directory/saas-apps/gtnexus-sso-module-tutorial), [CBRE ServiceInsight](https://docs.microsoft.com/azure/active-directory/saas-apps/cbre-serviceinsight-tutorial), [Deskradar](https://docs.microsoft.com/azure/active-directory/saas-apps/deskradar-tutorial), [Coralogixv](https://docs.microsoft.com/azure/active-directory/saas-apps/coralogix-tutorial), [Signagelive](https://docs.microsoft.com/azure/active-directory/saas-apps/signagelive-tutorial), [ARES for Enterprise](https://docs.microsoft.com/azure/active-directory/saas-apps/ares-for-enterprise-tutorial), [K2 for Office 365](https://www.k2.com/O365), [Xledger](https://www.xledger.net/), [iDiD Manager](https://docs.microsoft.com/azure/active-directory/saas-apps/idid-manager-tutorial), [HighGear](https://docs.microsoft.com/azure/active-directory/saas-apps/highgear-tutorial), [Visitly](https://docs.microsoft.com/azure/active-directory/saas-apps/visitly-tutorial), [Korn Ferry ALP](https://docs.microsoft.com/azure/active-directory/saas-apps/korn-ferry-alp-tutorial), [CaféX Portal (Meetings)](https://docs.microsoft.com/azure/active-directory/saas-apps/caf%c3%a9xportal%28meetings%29-tutorial), [Acadia](https://docs.microsoft.com/azure/active-directory/saas-apps/acadia-tutorial), [Adoddle cSaas Platform](https://docs.microsoft.com/azure/active-directory/saas-apps/adoddle-csaas-platform-tutorial)        

For more information about the apps, see [SaaS application integration with Azure Active Directory](https://aka.ms/appstutorial). For more information about listing your application in the Azure AD app gallery, see [List your application in the Azure Active Directory application gallery](https://aka.ms/azureadapprequest).

---

### New Azure AD Identity Protection enhancements (Public preview)

**Type:** Changed feature  
**Service category:** Identity Protection  
**Product capability:** Identity Security & Protection

We're excited to announce that we've added the following enhancements to the Azure AD Identity Protection public preview offering, including:

- An updated and more integrated user interface

- Additional APIs

- Improved risk assessment through machine learning

- Product-wide alignment across risky users and risky sign-ins

For more information about the enhancements, see [What is Azure Active Directory Identity Protection (refreshed)?](https://aka.ms/IdentityProtectionDocs) to learn more and to share your thoughts through the in-product prompts.

---

### New App Lock feature for the Microsoft Authenticator app on iOS and Android devices

**Type:** New feature  
**Service category:** Microsoft Authenticator App  
**Product capability:** Identity Security & Protection

To keep your one-time passcodes, app information, and app settings more secure, you can turn on the App Lock feature in the Microsoft Authenticator app. Turning on App Lock means you’ll be asked to authenticate using your PIN or biometric every time you open the Microsoft Authenticator app.

For more information, see the [Microsoft Authenticator app FAQ](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-faq).

---

### Enhanced Azure AD Privileged Identity Management (PIM) export capabilities

**Type:** New feature  
**Service category:** Privileged Identity Management  
**Product capability:** Privileged Identity Management

Privileged Identity Management (PIM) administrators can now export all active and eligible role assignments for a specific resource, which includes role assignments for all child resources. Previously, it was difficult for administrators to get a complete list of role assignments for a subscription and they had to export role assignments for each specific resource.

For more information, see [View activity and audit history for Azure resource roles in PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/azure-pim-resource-rbac).

---

## November/December 2018

### Users removed from synchronization scope no longer switch to cloud-only accounts

**Type:** Fixed  
**Service category:** User Management  
**Product capability:** Directory

>[!Important]
>We've heard and understand your frustration because of this fix. Therefore, we've reverted this change until such time that we can make the fix easier for you to implement in your organization.

We’ve fixed a bug in which the DirSyncEnabled flag of a user would be erroneously switched to **False** when the Active Directory Domain Services (AD DS) object was excluded from synchronization scope and then moved to the Recycle Bin in Azure AD on the following sync cycle. As a result of this fix, if the user is excluded from sync scope and afterwards restored from Azure AD Recycle Bin, the user account remains as synchronized from on-premises AD, as expected, and cannot be managed in the cloud since its source of authority (SoA) remains as on-premises AD.

Prior to this fix, there was an issue when the DirSyncEnabled flag was switched to False. It gave the wrong impression that these accounts were converted to cloud-only objects and that the accounts could be managed in the cloud. However, the accounts still retained their SoA as on-premises and all synchronized properties (shadow attributes) coming from on-premises AD. This condition caused multiple issues in Azure AD and other cloud workloads (like Exchange Online) that expected to treat these accounts as synchronized from AD but were now behaving like cloud-only accounts.

At this time, the only way to truly convert a synchronized-from-AD account to cloud-only account is by disabling DirSync at the tenant level, which triggers a backend operation to transfer the SoA. This type of SoA change requires (but is not limited to) cleaning all the on-premises related attributes (such as LastDirSyncTime and shadow attributes) and sending a signal to other cloud workloads to have its respective object converted to a cloud-only account too.

This fix consequently prevents direct updates on the ImmutableID attribute of a user synchronized from AD, which in some scenarios in the past were required. By design, the ImmutableID of an object in Azure AD, as the name implies, is meant to be immutable. New features implemented in Azure AD Connect Health and Azure AD Connect Synchronization client are available to address such scenarios:

- **Large-scale ImmutableID update for many users in a staged approach**
  
  For example, you need to do a lengthy AD DS inter-forest migration. Solution: Use Azure AD Connect to **Configure Source Anchor** and, as the user migrates, copy the existing ImmutableID values from Azure AD into the local AD DS user’s ms-DS-Consistency-Guid attribute of the new forest. For more information, see [Using ms-DS-ConsistencyGuid as sourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#using-ms-ds-consistencyguid-as-sourceanchor).

- **Large-scale ImmutableID updates for many users in one shot**

  For example, while implementing Azure AD Connect you make a mistake, and now you need to change the SourceAnchor attribute. Solution: Disable DirSync at the tenant level and clear all the invalid ImmutableID values. For more information, see [Turn off directory synchronization for Office 365](/office365/enterprise/turn-off-directory-synchronization).

- **Rematch on-premises user with an existing user in Azure AD**
  For example, a user that has been re-created in AD DS generates a duplicate in Azure AD account instead of rematching it with an existing Azure AD account (orphaned object). Solution: Use Azure AD Connect Health in the Azure portal to remap the Source Anchor/ImmutableID. For more information, see [Orphaned object scenario](/azure/active-directory/hybrid/how-to-connect-health-diagnose-sync-errors#orphaned-object-scenario).

### Breaking Change: Updates to the audit and sign-in logs schema through Azure Monitor

**Type:** Changed feature  
**Service category:** Reporting  
**Product capability:** Monitoring & Reporting

We're currently publishing both the Audit and Sign-in log streams through Azure Monitor, so you can seamlessly integrate the log files with your SIEM tools or with Log Analytics. Based on your feedback, and in preparation for this feature's general availability announcement, we're making the following changes to our schema. These schema changes and its related documentation updates will happen by the first week of January.

#### New fields in the Audit schema
We're adding a new **Operation Type** field, to provide the type of operation performed on the resource. For example, **Add**, **Update**, or **Delete**.

#### Changed fields in the Audit schema
The following fields are changing in the Audit schema:

|Field name|What changed|Old values|New Values|
|----------|------------|----------|----------|
|Category|This was the **Service Name** field. It's now the **Audit Categories** field. **Service Name** has been renamed to the **loggedByService** field.|<ul><li>Account Provisioning</li><li>Core Directory</li><li>Self-service Password Reset</li></ul>|<ul><li>User Management</li><li>Group Management</li><li>App Management</li></ul>|
|targetResources|Includes **TargetResourceType** at the top level.|&nbsp;|<ul><li>Policy</li><li>App</li><li>User</li><li>Group</li></ul>|
|loggedByService|Provides the name of the service that generated the audit log.|Null|<ul><li>Account Provisioning</li><li>Core Directory</li><li>Self-service password reset</li></ul>|
|Result|Provides the result of the audit logs. Previously, this was enumerated, but we now show the actual value.|<ul><li>0</li><li>1</li></ul>|<ul><li>Success</li><li>Failure</li></ul>|

#### Changed fields in the Sign-in schema
The following fields are changing in the Sign-in schema:

|Field name|What changed|Old values|New Values|
|----------|------------|----------|----------|
|appliedConditionalAccessPolicies|This was the **conditionalaccessPolicies** field. It's now the **appliedConditionalAccessPolicies** field.|No change|No change|
|conditionalAccessStatus|Provides the result of the Conditional Access Policy Status at sign-in. Previously, this was enumerated, but we now show the actual value.|<ul><li>0</li><li>1</li><li>2</li><li>3</li></ul>|<ul><li>Success</li><li>Failure</li><li>Not Applied</li><li>Disabled</li></ul>|
|appliedConditionalAccessPolicies: result|Provides the result of the individual Conditional Access Policy Status at sign-in. Previously, this was enumerated, but we now show the actual value.|<ul><li>0</li><li>1</li><li>2</li><li>3</li></ul>|<ul><li>Success</li><li>Failure</li><li>Not Applied</li><li>Disabled</li></ul>|

For more information about the schema, see [Interpret the Azure AD audit logs schema in Azure Monitor (preview)](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-azure-monitor-audit-log-schema)

---

### Identity Protection improvements to the supervised machine learning model and the risk score engine

**Type:** Changed feature  
**Service category:** Identity Protection  
**Product capability:** Risk Scores

Improvements to the Identity Protection-related user and sign-in risk assessment engine can help to improve user risk accuracy and coverage. Administrators may notice that user risk level is no longer directly linked to the risk level of specific detections, and that there's an increase in the number and level of risky sign-in events.

Risk detections are now evaluated by the supervised machine learning model, which calculates user risk by using additional features of the user’s sign-ins and a pattern of detections. Based on this model, the administrator might find users with high risk scores, even if detections associated with that user are of low or medium risk. 

---

### Administrators can reset their own password using the Microsoft Authenticator app (Public preview)

**Type:** Changed feature  
**Service category:** Self Service Password Reset  
**Product capability:** User Authentication

Azure AD administrators can now reset their own password using the Microsoft Authenticator app notifications or a code from any mobile authenticator app or hardware token. To reset their own password, administrators will now be able to use two of the following methods:

- Microsoft Authenticator app notification

- Other mobile authenticator app / Hardware token code

- Email

- Phone call

- Text message

For more information about using the Microsoft Authenticator app to reset passwords, see [Azure AD self-service password reset - Mobile app and SSPR (Preview)](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-howitworks#mobile-app-and-sspr-preview)

---

### New Azure AD Cloud Device Administrator role (Public preview)

**Type:** New feature  
**Service category:** Device Registration and Management  
**Product capability:** Access control

Administrators can assign users to the new Cloud Device Administrator role to perform cloud device administrator tasks. Users assigned the Cloud Device Administrators role can enable, disable, and delete devices in Azure AD, along with being able to read Windows 10 BitLocker keys (if present) in the Azure portal.

For more information about roles and permissions, see [Assigning administrator roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

---

### Manage your devices using the new activity timestamp in Azure AD (Public preview)

**Type:** New feature  
**Service category:** Device Registration and Management  
**Product capability:** Device Lifecycle Management

We realize that over time you must refresh and retire your organizations' devices in Azure AD, to avoid having stale devices hanging around in your environment. To help with this process, Azure AD now updates your devices with a new activity timestamp, helping you to manage your device lifecycle.

For more information about how to get and use this timestamp, see [How To: Manage the stale devices in Azure AD](https://docs.microsoft.com/azure/active-directory/devices/manage-stale-devices)

---

### Administrators can require users to accept a Terms of use on each device

**Type:** New feature  
**Service category:** Terms of Use  
**Product capability:** Governance
 
Administrators can now turn on the **Require users to consent on every device** option to require your users to accept your Terms of use on every device they're using on your tenant.

For more information, see the [Per-device Terms of use section of the Azure Active Directory Terms of use feature](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou#per-device-terms-of-use).

---

### Administrators can configure a Terms of use to expire based on a recurring schedule

**Type:** New feature  
**Service category:** Terms of Use  
**Product capability:** Governance
 

Administrators can now turn on the **Expire consents** option to make a Terms of use expire for all of your users based on your specified recurring schedule. The schedule can be annually, bi-annually, quarterly, or monthly. After the Terms of use expires, users must reaccept.

For more information, see the [Add Terms of use section of the Azure Active Directory Terms of use feature](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou#add-terms-of-use).

---

### Administrators can configure a Terms of use to expire based on each user’s schedule

**Type:** New feature  
**Service category:** Terms of Use  
**Product capability:** Governance

Administrators can now specify a duration that user must reaccept a Terms of use. For example, administrators can specify that users must reaccept a Terms of use every 90 days.

For more information, see the [Add Terms of use section of the Azure Active Directory Terms of use feature](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou#add-terms-of-use).
 
---

### New Azure AD Privileged Identity Management (PIM) emails for Azure Active Directory roles

**Type:** New feature  
**Service category:** Privileged Identity Management  
**Product capability:** Privileged Identity Management
 
Customers using Azure AD Privileged Identity Management (PIM) can now receive a weekly digest email, including the following information for the last seven days:

- Overview of the top eligible and permanent role assignments

- Number of users activating roles

- Number of users assigned to roles in PIM

- Number of users assigned to roles outside of PIM

- Number of users "made permanent" in PIM

For more information about PIM and the available email notifications, see [Email notifications in PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-email-notifications).

---

### Group-based licensing is now generally available

**Type:** Changed feature  
**Service category:** Other  
**Product capability:** Directory

Group-based licensing is out of public preview and is now generally available. As part of this general release, we've made this feature more scalable and have added the ability to reprocess group-based licensing assignments for a single user and the ability to use group-based licensing with Office 365 E3/A3 licenses.

For more information about group-based licensing, see [What is group-based licensing in Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)

---

### New Federated Apps available in Azure AD app gallery - November 2018

**Type:** New feature  
**Service category:** Enterprise Apps  
**Product capability:** 3rd Party Integration
 
In November 2018, we've added these 26 new apps with Federation support to the app gallery:

[CoreStack](https://cloud.corestack.io/site/login), [HubSpot](https://docs.microsoft.com/azure/active-directory/saas-apps/HubSpot-tutorial), [GetThere](https://docs.microsoft.com/azure/active-directory/saas-apps/getthere-tutorial), [Gra-Pe](https://docs.microsoft.com/azure/active-directory/saas-apps/grape-tutorial), [eHour](https://getehour.com/try-now), [Consent2Go](https://docs.microsoft.com/azure/active-directory/saas-apps/Consent2Go-tutorial), [Appinux](https://docs.microsoft.com/azure/active-directory/saas-apps/appinux-tutorial), [DriveDollar](https://www.drivedollar.com/Account/Login), [Useall](https://docs.microsoft.com/azure/active-directory/saas-apps/useall-tutorial), [Infinite Campus](https://docs.microsoft.com/azure/active-directory/saas-apps/infinitecampus-tutorial), [Alaya](https://alayagood.com/en/demo/), [HeyBuddy](https://docs.microsoft.com/azure/active-directory/saas-apps/heybuddy-tutorial), [Wrike SAML](https://docs.microsoft.com/azure/active-directory/saas-apps/wrike-tutorial), [Drift](https://docs.microsoft.com/azure/active-directory/saas-apps/drift-tutorial), [Zenegy for Business Central 365](https://accounting.zenegy.com/), [Everbridge Member Portal](https://docs.microsoft.com/azure/active-directory/saas-apps/everbridge-tutorial), [IDEO](https://profile.ideo.com/users/sign_up), [Ivanti Service Manager (ISM)](https://docs.microsoft.com/azure/active-directory/saas-apps/ivanti-service-manager-tutorial), [Peakon](https://docs.microsoft.com/azure/active-directory/saas-apps/peakon-tutorial), [Allbound SSO](https://docs.microsoft.com/azure/active-directory/saas-apps/allbound-sso-tutorial), [Plex Apps - Classic Test](https://test.plexonline.com/signon), [Plex Apps – Classic](https://www.plexonline.com/signon), [Plex Apps - UX Test](https://test.cloud.plex.com/sso), [Plex Apps – UX](https://cloud.plex.com/sso), [Plex Apps – IAM](https://accounts.plex.com/), [CRAFTS - Childcare Records, Attendance, & Financial Tracking System](https://getcrafts.ca/craftsregistration) 

For more information about the apps, see [SaaS application integration with Azure Active Directory](https://aka.ms/appstutorial). For more information about listing your application in the Azure AD app gallery, see [List your application in the Azure Active Directory application gallery](https://aka.ms/azureadapprequest).

---

## October 2018

### Azure AD Logs now work with Azure Log Analytics (Public preview)

**Type:** New feature  
**Service category:** Reporting  
**Product capability:** Monitoring & Reporting

We're excited to announce that you can now forward your Azure AD logs to Azure Log Analytics! This top-requested feature helps give you even better access to analytics for your business, operations, and security, as well as a way to help monitor your infrastructure. For more information, see the [Azure Active Directory Activity logs in Azure Log Analytics now available](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Azure-Active-Directory-Activity-logs-in-Azure-Log-Analytics-now/ba-p/274843) blog.

---

### New Federated Apps available in Azure AD app gallery - October 2018

**Type:** New feature  
**Service category:** Enterprise Apps  
**Product capability:** 3rd Party Integration
 
In October 2018, we've added these 14 new apps with Federation support to the app gallery:

[My Award Points](https://docs.microsoft.com/azure/active-directory/saas-apps/myawardpoints-tutorial), [Vibe HCM](https://docs.microsoft.com/azure/active-directory/saas-apps/vibehcm-tutorial), ambyint, [MyWorkDrive](https://docs.microsoft.com/azure/active-directory/saas-apps/myworkdrive-tutorial), [BorrowBox](https://docs.microsoft.com/azure/active-directory/saas-apps/borrowbox-tutorial), Dialpad, [ON24 Virtual Environment](https://docs.microsoft.com/azure/active-directory/saas-apps/on24-tutorial), [RingCentral](https://docs.microsoft.com/azure/active-directory/saas-apps/ringcentral-tutorial), [Zscaler Three](https://docs.microsoft.com/azure/active-directory/saas-apps/zscaler-three-tutorial), [Phraseanet](https://docs.microsoft.com/azure/active-directory/saas-apps/phraseanet-tutorial), [Appraisd](https://docs.microsoft.com/azure/active-directory/saas-apps/appraisd-tutorial), [Workspot Control](https://docs.microsoft.com/azure/active-directory/saas-apps/workspotcontrol-tutorial), [Shuccho Navi](https://docs.microsoft.com/azure/active-directory/saas-apps/shucchonavi-tutorial), [Glassfrog](https://docs.microsoft.com/azure/active-directory/saas-apps/glassfrog-tutorial)

For more information about the apps, see [SaaS application integration with Azure Active Directory](https://aka.ms/appstutorial). For more information about listing your application in the Azure AD app gallery, see [List your application in the Azure Active Directory application gallery](https://aka.ms/azureadapprequest).

---

### Azure AD Domain Services Email Notifications

**Type:** New feature  
**Service category:** Azure AD Domain Services  
**Product capability:** Azure AD Domain Services

Azure AD Domain Services provides alerts on the Azure portal about misconfigurations or problems with your managed domain. These alerts include step-by-step guides so you can try to fix the problems without having to contact support.

Starting in October, you'll be able to customize the notification settings for your managed domain so when new alerts occur, an email is sent to a designated group of people, eliminating the need to constantly check the portal for updates.

For more information, see [Notification settings in Azure AD Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/active-directory-ds-notifications).

---

### Azure AD portal supports using the ForceDelete domain API to delete custom domains 

**Type:** Changed feature  
**Service category:** Directory Management  
**Product capability:** Directory

We're pleased to announce that you can now use the ForceDelete domain API to delete your custom domain names by asynchronously renaming references, like users, groups, and apps from your custom domain name (contoso.com) back to the initial default domain name (contoso.onmicrosoft.com).

This change helps you to more quickly delete your custom domain names if your organization no longer uses the name, or if you need to use the domain name with another Azure AD.

For more information, see [Delete a custom domain name](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-manage#delete-a-custom-domain-name).

---

## September 2018
 
### Updated administrator role permissions for dynamic groups

**Type:** Fixed  
**Service category:** Group Management  
**Product capability:** Collaboration

We've fixed an issue so specific administrator roles can now create and update dynamic membership rules, without needing to be the owner of the group.

The roles are:

- Global administrator or Company Writer

- Intune Service Administrator

- User Account Administrator

For more information, see [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

---

### Simplified Single Sign-On (SSO) configuration settings for some third-party apps

**Type:** New feature  
**Service category:** Enterprise Apps  
**Product capability:** SSO

We realize that setting up Single Sign-On (SSO) for Software as a Service (SaaS) apps can be challenging due to the unique nature of each apps configuration. We've built a simplified configuration experience to auto-populate the SSO configuration settings for the following third-party SaaS apps:

- Zendesk

- ArcGis Online

- Jamf Pro

To start using this one-click experience, go to the **Azure portal** > **SSO configuration** page for the app. For more information, see [SaaS application integration with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list)

---

### Azure Active Directory - Where is your data located? page

**Type:** New feature  
**Service category:** Other  
**Product capability:** GoLocal

Select your company's region from the **Azure Active Directory - Where is your data located** page to view which Azure datacenter houses your Azure AD data at rest for all Azure AD services. You can filter the information by specific Azure AD services for your company's region.

To access this feature and for more information, see [Azure Active Directory - Where is your data located](https://aka.ms/AADDataMap).

---

### New deployment plan available for the My Apps Access panel

**Type:** New feature  
**Service category:** My Apps  
**Product capability:** SSO

Check out the new deployment plan that's available for the My Apps Access panel (https://aka.ms/deploymentplans).
The My Apps Access panel provides users with a single place to find and access their apps. This portal also provides users with self-service opportunities, such as requesting access to apps and groups, or managing access to these resources on behalf of others.

For more information, see [What is the My Apps portal?](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction)

---

### New Troubleshooting and Support tab on the Sign-ins Logs page of the Azure portal

**Type:** New feature  
**Service category:** Reporting  
**Product capability:** Monitoring & Reporting

The new **Troubleshooting and Support** tab on the **Sign-ins** page of the Azure portal, is intended to help admins and support engineers troubleshoot issues related to Azure AD sign-ins. This new tab provides the error code, error message, and remediation recommendations (if any) to help solve the problem. If you're unable to resolve the problem, we also give you a new way to create a support ticket using the **Copy to clipboard** experience, which populates the **Request ID** and **Date (UTC)** fields for the log file in your support ticket.  

![Sign-in logs with the new tab](media/whats-new/troubleshooting-and-support.png)

---

### Enhanced support for custom extension properties used to create dynamic membership rules

**Type:** Changed feature  
**Service category:** Group Management  
**Product capability:** Collaboration

With this update, you can now click the **Get custom extension properties** link from the dynamic user group rule builder, enter your unique app ID, and receive the full list of custom extension properties to use when creating a dynamic membership rule for users. This list can also be refreshed to get any new custom extension properties for that app.

For more information about using custom extension properties for dynamic membership rules, see [Extension properties and custom extension properties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#extension-properties-and-custom-extension-properties)

---

### New approved client apps for Azure AD app-based conditional access

**Type:** Plan for change  
**Service category:** Conditional access  
**Product capability:** Identity security and protection

The following apps are on the list of [approved client apps](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#approved-client-app-requirement):

- Microsoft To-Do

- Microsoft Stream

For more information, see:

- [Azure AD app-based conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access)

---

### New support for Self-Service Password Reset from the Windows 7/8/8.1 Lock screen

**Type:** New feature  
**Service category:** SSPR  
**Product capability:** User Authentication

After you set up this new feature, your users will see a link to reset their password from the **Lock** screen of a device running Windows 7, Windows 8, or Windows 8.1. By clicking that link, the user is guided through the same password reset flow as through the web browser.

For more information, see [How to enable password reset from Windows 7, 8, and 8.1](https://aka.ms/ssprforwindows78)

---

### Change notice: Authorization codes will no longer be available for reuse 

**Type:** Plan for change  
**Service category:** Authentications (Logins)  
**Product capability:** User Authentication

Starting on November 15, 2018, Azure AD will stop accepting previously used authentication codes for apps. This security change helps to bring Azure AD in line with the OAuth specification and will be enforced on both the v1 and v2 endpoints.

If your app reuses authorization codes to get tokens for multiple resources, we recommend that you use the code to get a refresh token, and then use that refresh token to acquire additional tokens for other resources. Authorization codes can only be used once, but refresh tokens can be used multiple times across multiple resources. An app that attempts to reuse an authentication code during the OAuth code flow will get an invalid_grant error.

For this and other protocols-related changes, see [the full list of what's new for authentication](https://docs.microsoft.com/azure/active-directory/develop/reference-breaking-changes).

---

### New Federated Apps available in Azure AD app gallery - September 2018

**Type:** New feature  
**Service category:** Enterprise Apps  
**Product capability:** 3rd Party Integration
 
In September 2018, we've added these 16 new apps with Federation support to the app gallery:

[Uberflip](https://docs.microsoft.com/azure/active-directory/saas-apps/uberflip-tutorial), [Comeet Recruiting Software](https://docs.microsoft.com/azure/active-directory/saas-apps/comeetrecruitingsoftware-tutorial), [Workteam](https://docs.microsoft.com/azure/active-directory/saas-apps/workteam-tutorial), [ArcGIS Enterprise](https://docs.microsoft.com/azure/active-directory/saas-apps/arcgisenterprise-tutorial), [Nuclino](https://docs.microsoft.com/azure/active-directory/saas-apps/nuclino-tutorial), [JDA Cloud](https://docs.microsoft.com/azure/active-directory/saas-apps/jdacloud-tutorial), [Snowflake](https://docs.microsoft.com/azure/active-directory/saas-apps/snowflake-tutorial), NavigoCloud, [Figma](https://docs.microsoft.com/azure/active-directory/saas-apps/figma-tutorial), join.me, [ZephyrSSO](https://docs.microsoft.com/azure/active-directory/saas-apps/zephyrsso-tutorial), [Silverback](https://docs.microsoft.com/azure/active-directory/saas-apps/silverback-tutorial), Riverbed Xirrus EasyPass, [Rackspace SSO](https://docs.microsoft.com/azure/active-directory/saas-apps/rackspacesso-tutorial), Enlyft SSO for Azure, SurveyMonkey, [Convene](https://docs.microsoft.com/azure/active-directory/saas-apps/convene-tutorial), [dmarcian](https://docs.microsoft.com/azure/active-directory/saas-apps/dmarcian-tutorial)

For more information about the apps, see [SaaS application integration with Azure Active Directory](https://aka.ms/appstutorial). For more information about listing your application in the Azure AD app gallery, see [List your application in the Azure Active Directory application gallery](https://aka.ms/azureadapprequest).

---

### Support for additional claims transformations methods

**Type:** New feature  
**Service category:** Enterprise Apps  
**Product capability:** SSO

We've introduced new claim transformation methods, ToLower() and ToUpper(), which can be applied to SAML tokens from the SAML-based **Single Sign-On Configuration** page.

For more information, see [How to customize claims issued in the SAML token for enterprise applications in Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-saml-claims-customization)

---

### Updated SAML-based app configuration UI (preview)

**Type:** Changed feature  
**Service category:** Enterprise Apps  
**Product capability:** SSO

As part of our updated SAML-based app configuration UI, you'll get:

- An updated walkthrough experience for configuring your SAML-based apps.

- More visibility about what's missing or incorrect in your configuration.

- The ability to add multiple email addresses for expiration certificate notification.

- New claim transformation methods, ToLower() and ToUpper(), and more.

- A way to upload your own token signing certificate for your enterprise apps.

- A way to set the NameID Format for SAML apps, and a way to set the NameID value as Directory Extensions.

To turn on this updated view, click the **Try out our new experience** link from the top of the **Single Sign-On** page. For more information, see [Tutorial: Configure SAML-based single sign-on for an application with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-single-sign-on-portal).

---

## August 2018

### Changes to Azure Active Directory IP address ranges

**Type:** Plan for change  
**Service category:** Other  
**Product capability:** Platform

We're introducing larger IP ranges to Azure AD, which means if you've configured Azure AD IP address ranges for your firewalls, routers, or Network Security Groups, you'll need to update them. We're making this update so you won't have to change your firewall, router, or Network Security Groups IP range configurations again when Azure AD adds new endpoints. 

Network traffic is moving to these new ranges over the next two months. To continue with uninterrupted service, you must add these updated values to your IP Addresses before September 10, 2018:

- 20.190.128.0/18 

- 40.126.0.0/18 

We strongly recommend not removing the old IP Address ranges until all of your network traffic has moved to the new ranges. For updates about the move and to learn when you can remove the old ranges, see [Office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

---

### Change notice: Authorization codes will no longer be available for reuse 

**Type:** Plan for change  
**Service category:** Authentications (Logins)  
**Product capability:** User Authentication

Starting on November 15, 2018, Azure AD will stop accepting previously used authentication codes for apps. This security change helps to bring Azure AD in line with the OAuth specification and will be enforced on both the v1 and v2 endpoints.

If your app reuses authorization codes to get tokens for multiple resources, we recommend that you use the code to get a refresh token, and then use that refresh token to acquire additional tokens for other resources. Authorization codes can only be used once, but refresh tokens can be used multiple times across multiple resources. An app that attempts to reuse an authentication code during the OAuth code flow will get an invalid_grant error.

For this and other protocols-related changes, see [the full list of what's new for authentication](https://docs.microsoft.com/azure/active-directory/develop/reference-breaking-changes).
 
---

### Converged security info management for self-service password (SSPR) and Multi-Factor Authentication (MFA)

**Type:** New feature  
**Service category:** SSPR  
**Product capability:** User Authentication
 
This new feature helps people manage their security info (such as, phone number, mobile app, and so on) for SSPR and MFA in a single location and experience; as compared to previously, where it was done in two different locations.

This converged experience also works for people using either SSPR or MFA. Additionally, if your organization doesn't enforce MFA or SSPR registration, people can still register any MFA or SSPR security info methods allowed by your organization from the My Apps portal.

This is an opt-in public preview. Administrators can turn on the new experience (if desired) for a selected group or for all users in a tenant. For more information about the converged experience, see the [Converged experience blog](https://cloudblogs.microsoft.com/enterprisemobility/2018/08/06/mfa-and-sspr-updates-now-in-public-preview/)

---

### New HTTP-Only cookies setting in Azure AD Application proxy apps

**Type:** New feature  
**Service category:** App Proxy  
**Product capability:** Access Control

There's a new setting called, **HTTP-Only Cookies** in your Application Proxy apps. This setting helps provide extra security by including the HTTPOnly flag in the HTTP response header for both Application Proxy access and session cookies, stopping access to the cookie from a client-side script and further preventing actions like copying or modifying the cookie. Although this flag hasn't been used previously, your cookies have always been encrypted and transmitted using an SSL connection to help protect against improper modifications.

This setting isn't compatible with apps using ActiveX controls, such as Remote Desktop. If you're in this situation, we recommend that you turn off this setting.

For more information about the HTTP-Only Cookies setting, see [Publish applications using Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-publish-azure-portal).

---

### Privileged Identity Management (PIM) for Azure resources supports Management Group resource types

**Type:** New feature  
**Service category:** Privileged Identity Management  
**Product capability:** Privileged Identity Management
 
Just-In-Time activation and assignment settings can now be applied to Management Group resource types, just like you already do for Subscriptions, Resource Groups, and Resources (such as VMs, App Services, and more). In addition, anyone with a role that provides administrator access for a Management Group can discover and manage that resource in PIM.

For more information about PIM and Azure resources, see [Discover and manage Azure resources by using Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-discover-resources)
 
---

### Application access (preview) provides faster access to the Azure AD portal

**Type:** New feature  
**Service category:** Privileged Identity Management  
**Product capability:** Privileged Identity Management
 
Today, when activating a role using PIM, it can take over 10 minutes for the permissions to take effect. If you choose to use Application access, which is currently in public preview, administrators can access the Azure AD portal as soon as the activation request completes.

Currently, Application access only supports the Azure AD portal experience and Azure resources. For more information about PIM and Application access, see [What is Azure AD Privileged Identity Management?](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)
 
---

### New Federated Apps available in Azure AD app gallery - August 2018

**Type:** New feature  
**Service category:** Enterprise Apps  
**Product capability:** 3rd Party Integration
 
In August 2018, we've added these 16 new apps with Federation support to the app gallery:

[Hornbill](https://docs.microsoft.com/azure/active-directory/saas-apps/hornbill-tutorial), [Bridgeline Unbound](https://docs.microsoft.com/azure/active-directory/saas-apps/bridgelineunbound-tutorial), [Sauce Labs - Mobile and Web Testing](https://docs.microsoft.com/azure/active-directory/saas-apps/saucelabs-mobileandwebtesting-tutorial), [Meta Networks Connector](https://docs.microsoft.com/azure/active-directory/saas-apps/metanetworksconnector-tutorial), [Way We Do](https://docs.microsoft.com/azure/active-directory/saas-apps/waywedo-tutorial), [Spotinst](https://docs.microsoft.com/azure/active-directory/saas-apps/spotinst-tutorial), [ProMaster (by Inlogik)](https://docs.microsoft.com/azure/active-directory/saas-apps/promaster-tutorial), SchoolBooking, [4me](https://docs.microsoft.com/azure/active-directory/saas-apps/4me-tutorial), [Dossier](https://docs.microsoft.com/azure/active-directory/saas-apps/DOSSIER-tutorial), [N2F - Expense reports](https://docs.microsoft.com/azure/active-directory/saas-apps/n2f-expensereports-tutorial), [Comm100 Live Chat](https://docs.microsoft.com/azure/active-directory/saas-apps/comm100livechat-tutorial), [SafeConnect](https://docs.microsoft.com/azure/active-directory/saas-apps/safeconnect-tutorial), [ZenQMS](https://docs.microsoft.com/azure/active-directory/saas-apps/zenqms-tutorial), [eLuminate](https://docs.microsoft.com/azure/active-directory/saas-apps/eluminate-tutorial), [Dovetale](https://docs.microsoft.com/azure/active-directory/saas-apps/dovetale-tutorial).

For more information about the apps, see [SaaS application integration with Azure Active Directory](https://aka.ms/appstutorial). For more information about listing your application in the Azure AD app gallery, see [List your application in the Azure Active Directory application gallery](https://aka.ms/azureadapprequest).

---

### Native Tableau support is now available in Azure AD Application Proxy

**Type:** Changed feature  
**Service category:** App Proxy  
**Product capability:** Access Control

With our update from the OpenID Connect to the OAuth 2.0 Code Grant protocol for our pre-authentication protocol, you no longer have to do any additional configuration to use Tableau with Application Proxy. This protocol change also helps Application Proxy better support more modern apps by using only HTTP redirects, which are commonly supported in JavaScript and HTML tags.

For more information about our native support for Tableau, see [Azure AD Application Proxy now with native Tableau support](https://blogs.technet.microsoft.com/applicationproxyblog/2018/08/14/azure-ad-application-proxy-now-with-native-tableau-support).

---

### New support to add Google as an identity provider for B2B guest users in Azure Active Directory (preview)

**Type:** New feature  
**Service category:** B2B  
**Product capability:** B2B/B2C

By setting up federation with Google in your organization, you can let invited Gmail users sign in to your shared apps and resources using their existing Google account, without having to create a personal Microsoft Account (MSAs) or an Azure AD account.

This is an opt-in public preview. For more information about Google federation, see [Add Google as an identity provider for B2B guest users](https://docs.microsoft.com/azure/active-directory/b2b/google-federation).

---

## July 2018

### Improvements to Azure Active Directory email notifications

**Type:** Changed feature  
**Service category:** Other  
**Product capability:** Identity lifecycle management
 
Azure Active Directory (Azure AD) emails now feature an updated design, as well as changes to the sender email address and sender display name, when sent from the following services:
 
- Azure AD Access Reviews
- Azure AD Connect Health 
- Azure AD Identity Protection 
- Azure AD Privileged Identity Management
- Enterprise App Expiring Certificate Notifications
- Enterprise App Provisioning Service Notifications
 
The email notifications will be sent from the following email address and display name:

- Email address: azure-noreply@microsoft.com
- Display name: Microsoft Azure
 
For an example of some of the new e-mail designs and more information, see [Email notifications in Azure AD PIM](https://go.microsoft.com/fwlink/?linkid=2005832).

---

### Azure AD Activity Logs are now available through Azure Monitor

**Type:** New feature  
**Service category:** Reporting  
**Product capability:** Monitoring & Reporting

The Azure AD Activity Logs are now available in public preview for the Azure Monitor (Azure's platform-wide monitoring service). Azure Monitor offers you long-term retention and seamless integration, in addition to these improvements:

- Long-term retention by routing your log files to your own Azure storage account.

- Seamless SIEM integration, without requiring you to write or maintain custom scripts.

- Seamless integration with your own custom solutions, analytics tools, or incident management solutions.

For more information about these new capabilities, see our blog [Azure AD activity logs in Azure Monitor diagnostics is now in public preview](https://cloudblogs.microsoft.com/enterprisemobility/2018/07/26/azure-ad-activity-logs-in-azure-monitor-diagnostics-now-in-public-preview/) and our documentation, [Azure Active Directory activity logs in Azure Monitor (preview)](https://docs.microsoft.com/azure/active-directory/reporting-azure-monitor-diagnostics-overview).

---

### Conditional access information added to the Azure AD sign-ins report

**Type:** New feature  
**Service category:** Reporting  
**Product capability:** Identity Security & Protection
 
This update lets you see which policies are evaluated when a user signs in along with the policy outcome. In addition, the report now includes the type of client app used by the user, so you can identify legacy protocol traffic. Report entries can also now be searched for a correlation ID, which can be found in the user-facing error message and can be used to identify and troubleshoot the matching sign-in request.

---

### View legacy authentications through Sign-ins activity logs

**Type:** New feature  
**Service category:** Reporting  
**Product capability:** Monitoring & Reporting
 
With the introduction of the **Client App** field in the Sign-in activity logs, customers can now see users that are using legacy authentications. Customers will be able to access this information using the Sign-ins MS Graph API or through the Sign-in activity logs in Azure AD portal where you can use the **Client App** control to filter on legacy authentications. Check out the documentation for more details.

---

### New Federated Apps available in Azure AD app gallery - July 2018

**Type:** New feature  
**Service category:** Enterprise Apps  
**Product capability:** 3rd Party Integration
 
In July 2018, we've added these 16 new apps with Federation support to the app gallery:

[Innovation Hub](https://docs.microsoft.com/azure/active-directory/saas-apps/innovationhub-tutorial), [Leapsome](https://docs.microsoft.com/azure/active-directory/saas-apps/leapsome-tutorial), [Certain Admin SSO](https://docs.microsoft.com/azure/active-directory/saas-apps/certainadminsso-tutorial), PSUC Staging, [iPass SmartConnect](https://docs.microsoft.com/azure/active-directory/saas-apps/ipasssmartconnect-tutorial), [Screencast-O-Matic](https://docs.microsoft.com/azure/active-directory/saas-apps/screencast-tutorial), PowerSchool Unified Classroom, [Eli Onboarding](https://docs.microsoft.com/azure/active-directory/saas-apps/elionboarding-tutorial), [Bomgar Remote Support](https://docs.microsoft.com/azure/active-directory/saas-apps/bomgarremotesupport-tutorial), [Nimblex](https://docs.microsoft.com/azure/active-directory/saas-apps/nimblex-tutorial), [Imagineer WebVision](https://docs.microsoft.com/azure/active-directory/saas-apps/imagineerwebvision-tutorial), [Insight4GRC](https://docs.microsoft.com/azure/active-directory/saas-apps/insight4grc-tutorial), [SecureW2 JoinNow Connector](https://docs.microsoft.com/azure/active-directory/saas-apps/securejoinnow-tutorial), [Kanbanize](https://review.docs.microsoft.com/azure/active-directory/saas-apps/kanbanize-tutorial), [SmartLPA](https://review.docs.microsoft.com/azure/active-directory/saas-apps/smartlpa-tutorial), [Skills Base](https://docs.microsoft.com/azure/active-directory/saas-apps/skillsbase-tutorial)

For more information about the apps, see [SaaS application integration with Azure Active Directory](https://aka.ms/appstutorial). For more information about listing your application in the Azure AD app gallery, see [List your application in the Azure Active Directory application gallery](https://aka.ms/azureadapprequest).

---
 
### New user provisioning SaaS app integrations - July 2018

**Type:** New feature  
**Service category:** App Provisioning  
**Product capability:** 3rd Party Integration
 
Azure AD allows you to automate the creation, maintenance, and removal of user identities in SaaS applications such as Dropbox, Salesforce, ServiceNow, and more. For July 2018, we have added user provisioning support for the following applications in the Azure AD app gallery:

- [Cisco Spark](https://docs.microsoft.com/azure/active-directory/saas-apps/cisco-spark-provisioning-tutorial)

- [Cisco WebEx](https://docs.microsoft.com/azure/active-directory/saas-apps/cisco-webex-provisioning-tutorial)

- [Bonusly](https://docs.microsoft.com/azure/active-directory/saas-apps/bonusly-provisioning-tutorial)

For a list of all applications that support user provisioning in the Azure AD gallery, see [SaaS application integration with Azure Active Directory](https://aka.ms/appstutorial).

---

### Connect Health for Sync - An easier way to fix orphaned and duplicate attribute sync errors

**Type:** New feature  
**Service category:** AD Connect  
**Product capability:** Monitoring & Reporting
 
Azure AD Connect Health introduces self-service remediation to help you highlight and fix sync errors. This feature troubleshoots duplicated attribute sync errors and fixes objects that are orphaned from Azure AD. This diagnosis has the following benefits:

- Narrows down duplicated attribute sync errors, providing specific fixes

- Applies a fix for dedicated Azure AD scenarios, resolving errors in a single step

- No upgrade or configuration is required to turn on and use this feature

For more information, see [Diagnose and remediate duplicated attribute sync errors](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-diagnose-sync-errors)

---

### Visual updates to the Azure AD and MSA sign-in experiences

**Type:** Changed feature  
**Service category:** Azure AD  
**Product capability:** User Authentication

We've updated the UI for Microsoft's online services sign-in experience, such as for Office 365 and Azure. This change makes the screens less cluttered and more straightforward. For more information about this change, see the [Upcoming improvements to the Azure AD sign-in experience](https://cloudblogs.microsoft.com/enterprisemobility/2018/04/04/upcoming-improvements-to-the-azure-ad-sign-in-experience/) blog.

---

### New release of Azure AD Connect - July 2018

**Type:** Changed feature  
**Service category:** App Provisioning  
**Product capability:** Identity Lifecycle Management

The latest release of Azure AD Connect includes: 

- Bug fixes and supportability updates 

- General Availability of the Ping-Federate integration

- Updates to the latest SQL 2012 client 

For more information about this update, see [Azure AD Connect: Version release history](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-version-history)

---

### Updates to the Terms of Use (ToU) end-user UI

**Type:** Changed feature  
**Service category:** Terms of Use  
**Product capability:** Governance

We're updating the acceptance string in the TOU end-user UI.

**Current text.** In order to access [tenantName] resources, you must accept the terms of use.<br>**New text.** In order to access [tenantName] resource, you must read the terms of use.

**Current text:** Choosing to accept means that you agree to all of the above terms of use.<br>**New text:** Please click Accept to confirm that you have read and understood the terms of use.

---
 
### Pass-through Authentication supports legacy protocols and applications

**Type:** Changed feature  
**Service category:** Authentications (Logins)  
**Product capability:** User Authentication
 
Pass-through Authentication now supports legacy protocols and apps. The following limitations are now fully supported:

- User sign-ins to legacy Office client applications, Office 2010 and Office 2013, without requiring modern authentication.

- Access to calendar sharing and free/busy information in Exchange hybrid environments on Office 2010 only.

- User sign-ins to Skype for Business client applications without requiring modern authentication.

- User sign-ins to PowerShell version 1.0.

- The Apple Device Enrollment Program (Apple DEP), using the iOS Setup Assistant. 

---
 
### Converged security info management for self-service password reset and Multi-Factor Authentication

**Type:** New feature  
**Service category:** SSPR  
**Product capability:** User Authentication

This new feature lets users manage their security info (for example, phone number, email address, mobile app, and so on) for self-service password reset (SSPR) and Multi-Factor Authentication (MFA) in a single experience. Users will no longer have to register the same security info for SSPR and MFA in two different experiences. This new experience also applies to users who have either SSPR or MFA.

If an organization isn't enforcing MFA or SSPR registration, users can register their security info through the **My Apps** portal. From there, users can register any methods enabled for MFA or SSPR. 

This is an opt-in public preview. Admins can turn on the new experience (if desired) for a selected group of users or all users in a tenant.

---
 
### Use the Microsoft Authenticator app to verify your identity when you reset your password

**Type:** Changed feature  
**Service category:** SSPR  
**Product capability:** User Authentication

This feature lets non-admins verify their identity while resetting a password using a notification or code from Microsoft Authenticator (or any other authenticator app). After admins turn on this self-service password reset method, users who have registered a mobile app through aka.ms/mfasetup or aka.ms/setupsecurityinfo can use their mobile app as a verification method while resetting their password.

Mobile app notification can only be turned on as part of a policy that requires two methods to reset your password.

---

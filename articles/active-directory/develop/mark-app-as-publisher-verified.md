---
title: Mark an app as publisher verified
description: Describes how to mark an app as publisher verified. When an application is marked as publisher verified, it means that the publisher has verified their identity using a Microsoft Partner Network account that has completed the verification process and has associated this MPN account with their application registration.
services: active-directory
author: rwike77
manager: CelesteDG
ms.service: active-directory
ms.subservice: develop
ms.topic: how-to
ms.workload: identity
ms.date: 11/12/2022
ms.author: ryanwi
ms.custom: aaddev
ms.reviewer: xurobert, brianokoyo, ardhanap
---

# Mark your app as publisher verified

When an app registration has a verified publisher, it means that the publisher of the app has [verified](/partner-center/verification-responses) their identity using their Microsoft Partner Network (MPN) account and has associated this MPN account with their app registration. This article describes how to complete the [publisher verification](publisher-verification-overview.md) process.

## Quickstart
If you are already enrolled in the Microsoft Partner Network (MPN) and have met the [pre-requisites](publisher-verification-overview.md#requirements), you can get started right away: 

1. Sign into the [App Registration portal](https://aka.ms/PublisherVerificationPreview) using [multi-factor authentication](../fundamentals/concept-fundamentals-mfa-get-started.md)

1. Choose an app and click **Branding**. 

1. Click **Add MPN ID to verify publisher** and review the listed requirements.

1. Enter your MPN ID and click **Verify and save**.

For more details on specific benefits, requirements, and frequently asked questions see the [overview](publisher-verification-overview.md).

## Mark your app as publisher verified
Make sure you have met the [pre-requisites](publisher-verification-overview.md#requirements), then follow these steps to mark your app(s) as Publisher Verified.  

1. Ensure you are signed in using [multi-factor authentication](../fundamentals/concept-fundamentals-mfa-get-started.md) to an organizational (Azure AD) account that is authorized to make changes to the app(s) you want to mark as Publisher Verified and on the MPN Account in Partner Center.

    - In Azure AD this user must be a member of one of the following [roles](../roles/permissions-reference.md): Application Admin, Cloud Application Admin, or Global Admin. 

    - In Partner Center this user must have of the following [roles](/partner-center/permissions-overview): MPN Admin, Accounts Admin, or a Global Admin (this is a shared role mastered in Azure AD). 

1. Navigate to the **App registrations** blade:  

1. Click on an app you would like to mark as Publisher Verified and open the **Branding** blade. 

1. Ensure the app’s [publisher domain](howto-configure-publisher-domain.md) is set. 

1. Ensure that either the publisher domain or a DNS-verified [custom domain](../fundamentals/add-custom-domain.md) on the tenant matches the domain of the email address used during the verification process for your MPN account.

1. Click **Add MPN ID to verify publisher** near the bottom of the page. 

1. Enter your **MPN ID**. This MPN ID must be for: 

    - A valid Microsoft Partner Network account that has completed the verification process.  

    - The Partner global account (PGA) for your organization. 

1. Click **Verify and save**. 

1. Wait for the request to process, this may take a few minutes. 

1. If the verification was successful, the publisher verification window will close, returning you to the Branding blade. You will see a blue verified badge next to your verified **Publisher display name**. 

1. Users who get prompted to consent to your app will start seeing the badge soon after you have gone through the process successfully, although it may take some time for this to replicate throughout the system. 

1. Test this functionality by signing into your application and ensuring the verified badge shows up on the consent screen. If you are signed in as a user who has already granted consent to the app, you can use the *prompt=consent* query parameter to force a consent prompt. This parameter should be used for testing only, and never hard-coded into your app's requests.

1. Repeat this process as needed for any additional apps you would like the badge to be displayed for. You can use Microsoft Graph to do this more quickly in bulk, and PowerShell cmdlets will be available soon. See [Making Microsoft API Graph calls](troubleshoot-publisher-verification.md#making-microsoft-graph-api-calls) for more info. 

That’s it! Let us know if you have any feedback about the process, the results, or the feature in general. 

## Next steps
If you run into problems, read the [troubleshooting information](troubleshoot-publisher-verification.md).

---
layout: post
title: 'Important update for all SeamlessAccess integrators regarding the impact of browser changes.'
date: 2024-04-02
categories: [General]
hero: true
heroHeading: 'Important update for all SeamlessAccess integrators regarding the impact of browser changes.'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# Important update for all SeamlessAccess integrators regarding the impact of browser changes.

Today’s post updates the evolving story about changes to browser engines and how those changes affect SeamlessAccess. Perhaps the most visible change in this context is the deprecation of third-party cookies by Google Chrome, which has already been rolled out to 1% of users and that will be ramped up _“to reach 100% of Chrome clients by the end of Q4, subject to addressing any remaining concerns of the CMA.”_, as stated on the [Google Developers Blog](https://developers.googleblog.com/2024/02/federated-credential-management-migration-for-google-identity-services.html)

Before we dive into updates and our recommendations, a reminder from [last month’s](https://seamlessaccess.org/posts/2024-02-29-third-party-storage-deprecation-trial/) post:
**If you are a service provider that integrates with SeamlessAccess, we highly recommend that you participate in Google’s [deprecation trial for unpartitioned third-party storage](https://developers.google.com/privacy-sandbox/3pcd/temporary-exceptions/storage-partitioning-deprecation-trial) to keep the SeamlessAccess ‘smart button’ working for your users.**


## Testing new technologies

In last month’s post, we explained that SeamlessAccess is actively prototyping and testing alternative technologies, such as [FedCM](https://developers.google.com/privacy-sandbox/3pcd/fedcm), [CHIPS](https://developers.google.com/privacy-sandbox/3pcd/chips), and the [Storage Access API](https://developers.google.com/privacy-sandbox/3pcd/storage-access-api), which are designed to fill some of the functional gaps that will be left after the deprecation of third-party access to cookies and local browser storage. As a reminder, this is important for SeamlessAccess because we use local browser storage to remember the user’s choice of institution across participating websites and service providers. (See [here](https://seamlessaccess.org/posts/2024-02-29-third-party-storage-deprecation-trial/) for more details, an introduction, and links to further information).

From the technologies mentioned above, our tests suggest that the [Storage Access API](https://developers.google.com/privacy-sandbox/3pcd/storage-access-api) is the most promising option. It appears to be designed for exactly the kind of use case that SeamlessAccess is all about: Storing certain information about the user in a way that respects user privacy and that delivers direct value to the user by supporting a more consistent and intuitive user experience. Unlike FedCM, it is also implemented across all major browsers. 


While it is important to realize that these technologies are under active development, with several improvements and extensions underway, our current testing suggests that:

* SeamlessAccess can use the Storage Access API for the **Limited** and **Standard** mode integration patterns, including the SeamlessAccess ‘smart button’ (which shows the user’s last choice of institute directly in the button) – however with some additional steps that the user will need to take, in particular providing consent when the website first wants to retrieve information through the API.
* The current implementation of the Storage Access API does <u>not</u> provide a ready-to-go alternative for the **Advanced** integration mode. (This is because the Storage Access API is designed for scenarios where functional components are embedded in iframes, which are used for the Standard integration mode but not for Advanced).

As mentioned before, this is a rapidly evolving space and there are suggested extensions to the Storage Access API that may be used to power the Advanced integration mode – however, as of today, these are not widely supported and untested. We also note that Advanced integrators may still be able to locally remember the user’s choice of institute, though that possibility will likely be dependent on the user’s choice of browser and their configuration settings, and needs further testing. 


## What does this mean for parties that integrate with SeamlessAccess?

**If you use the SeamlessAccess Standard or Limited mode integration, we recommend no changes to your current implementation at this point** – though be advised that users may experience seeing a SeamlessAccess button without their choice of remembered institute more often than they are used to (depending on their choice of browser and other specific context), so we recommend to prepare for user support queries.

**If you use the SeamlessAccess Advanced mode integration, we recommend that you start preparing for alternatives and mitigating actions such as switching to the Standard mode integration.** To be clear, we will continue to drive for and test new technologies that can continue to power the SeamlessAccess Advanced mode – but at this point in time, it is uncertain if and when these will become available.


**It should be emphasized that the area of risk is focused on ‘global persistence’ i.e. the ability to store and share the user’s last choice of institute between different websites that integrate with SeamlessAccess. While this information is very valuable to deliver a seamless user experience, it is <u>not</u> part of the critical path for a user to log in via federated authentication.** In other words: Even in a scenario in which global persistence would break completely, users will still be able to gain access via federated authentication. Also, the central SeamlessAccess IdP discovery service will continue to work and will be able to remember the user’s choice of IdP (because this is first-party access). And, as noted above, Advanced integrators may still be able to remember the user’s choice of institute on their own site, though the specifics of this will likely be browser-dependent and require further testing. 

SeamlessAccess will continue to test new technologies as they become available, and we'll keep the community updated via posts like these. Additionally, we are setting up a Slack channel to facilitate dialogue and knowledge exchange at a technical level between SeamlessAccess and parties that integrate with SeamlessAccess about these topics. If you represent a service that is integrated with SeamlessAccess, and are interested in joining this channel, please email Hylke Koers at hylke@stm-solutions.org. 







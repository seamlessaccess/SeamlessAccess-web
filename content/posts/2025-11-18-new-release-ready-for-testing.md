---
layout: post
title: 'New features available for testing: Pinning and Co-branding'
date: 2025-11-18
categories: [General]
hero: true
heroHeading: 'New features available for testing: Pinning and Co-branding'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---

# New features available for testing: Pinning and Co-branding

SeamlessAccess is announcing three new features that are available for testing in our beta environment at [https://use.thiss.io/](https://use.thiss.io/). Both features increase the ability for service providers to customize SeamlessAccess Identity Provider (IdPs) discovery service - also called “Where Are You From” or “WAYF” service - to meet the specific needs of their communities.

These features are made available on an “opt in” basis and are backward compatible, so no changes are needed unless you want to use (one of) these features. 

**We invite all parties integrating with SeamlessAccess to test these new features and provide feedback before 20 Dec**


### Co-branding

Co-branding, introduces a capability for service providers to display their own brand identity alongside SeamlessAccess. Specifically, the co-branding enhancement makes it possible for a service provider to show their logo on the SeamlessAccess IdP discovery service. To provide a consistent, familiar user experience that builds on and reinforces SeamlessAccess’ usability benefits.

By showing the logo of the service provider alongside that of SeamlessAccess, co-branding signals that the user remains in a trusted environment as they start their access journey - strengthening user confidence and trust.

To implement co-branding in a clear and user-friendly way, we have made some changes to the overall design of the IdP discovery page. This includes a top and bottom container that provides more space for supplementary information (logo’s, terms and conditions, error messages) and creates a clear space for the discovery experience.


**Release notes:** [https://thiss-js.readthedocs.io/en/2.1.155/components.html#showing-the-sp-logo](https://thiss-js.readthedocs.io/en/2.1.155/components.html#showing-the-sp-logo)



### Pinning


Pinning, the second capability included in this release, is a new capability designed to optimize the IdP discovery experience in situations where there’s a small number of commonly used IdPs, such as within individual research organisations, institutional repositories, or internal wikis. In such contexts, the pinning feature allows service providers to designate (“pin”) up to five IdPs that are most likely to be relevant for their user community. When pinned, these IdPs are prioritized in the interface, making it easier for users to find the identity provider relevant for them.

While the “pinned” IdPs take prominence in the interface, the full search functionality of SeamlessAccess is retained so that users are still able to find and select other (non-pinned) IdPs.

Note that the service provider integrating with SeamlessAccess determines if, and which, IdPs are pinned. In keeping with our strong privacy-by-design principles, SeamlessAccess has no visibility into which IdPs individual users select or interact with, and therefore cannot generate such recommendations automatically. Instead we generally suggest service providers to analyse their own authentication logs to determine which IdPs are most frequently used and define up to five preferred IdPs to display prominently.

**Release notes:** [https://thiss-js.readthedocs.io/en/2.1.155/components.html#adding-suggested-institutions](https://thiss-js.readthedocs.io/en/2.1.155/components.html#adding-suggested-institutions)



### Improved error messaging

Thirdly, we are introducing styling elements for error messages to signal clearly to the end-user when issues occur or further information is required. SeamlessAccess did not yet have a consistent approach to present such messages; with this release we are putting in place the necessary styling elements to do so.



### Please test and share your feedback

We encourage the SeamlessAccess community to test these features and share any feedback through email (hylke@stm-solutions.org) or Slack.

**Deadline for feedback: 20 December**




---
layout: post
title: 'Clarifications About the SeamlessAccess.org Service'
date: 2020-01-13
categories: [General]
hero: true
heroHeading: 'Clarifications About the SeamlessAccess.org Service'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---

Following feedback before and during the Internet2 Technology Exchange, the Seamless Access program is reviewing the permissible use of the stored Identity Provider (IdP) preference information when using some of the SeamlessAccess.org integration models (see our “Getting Started” page for more information about the different integration models).

What we realized is that in its current form, authorized Service Providers (SPs) using the advanced integration model may be able to access stored IdP choices before a user logs into that SP’s service. When a website authorized to use SeamlessAccess connects their Federated Identity Management (FIM) service, the website can see the user’s previous choice of IdP before any user authentication occurs. This design choice was originally made to enable full flexibility of the user interface for advanced integrators, for example, to display the preferred IdP in the interface. Further, integrators using the limited and standard integration models are unable to access stored IdP choices.

We now understand that the current situation has some privacy implications that take the service beyond what SeamlessAccess has been promising. For example, a SeamlessAccess-authorized SP could potentially collect information about exactly which IdPs are preferred by the user (which is often correlated to a person’s affiliation) without the user being aware. While the persisted choice of IdP is not considered personally identifiable information (see the WAYF Cloud and P3W Security & Privacy Recommendations from RA21 for more detail) the exposure of any information outside of what matches a more traditional authentication flow runs counter to the principles of SeamlessAccess. 

The SeamlessAccess Governance Committee is currently evaluating several options to remediate this unintended possibility, including, but not limited to:

* Changes to the advanced integration API which make it impossible to access the stored IdP choices while still allowing the UI customization and integration with local discovery services for which this model was originally intended.
* A UI mechanism to allow users to grant permission to SPs to access their stored IdP preference information.
* Clear prohibition in the Terms of Use of SeamlessAccess of utilization of stored preference information in any way that is not intended.

In order to become an authorized SP for the advanced integration model using our production service, the SP has to follow a process that includes a review of their proposed integration with SeamlessAccess. The SeamlessAccess governance committee is currently working with appropriate legal counsel to develop a strong Terms of Service and Privacy Statements that will be part of authorizing any new SP. A link to the onboarding process and appropriate policies will be made available on the SeamlessAccess website as soon as they are complete. 

As we have more information and documentation on how to integrate with SeamlessAccess, we will let you know. 

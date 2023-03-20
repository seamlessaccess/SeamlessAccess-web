---
layout: post
title: 'FedCM: Update'
date: 2023-03-20
categories: [General]
hero: true
heroHeading: 'FedCM: An update on the efforts between the R&E community and browser vendors'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# FedCM: An update on the efforts between the R&E community and browser vendors 



_This is an update following a recent meet-up between representatives of the Research & Education (R&E) community and Mozilla and Google – discussing what capabilities in and around FedCM are required for our community to continue to serve academic users and their use cases.
**Note: SeamlessAccess is organizing a more in-depth webinar on this topic on April 6 - register [here](https://www.stm-assoc.org/events/seamlessaccess-stm-webinar/)!**_


<h3>Background</h3>

In a recent blog post called [“An emerging new technology for federated access: Federated Credential Management (FedCM)”](https://seamlessaccess.org/posts/2023-02-20-fedcm/) and several earlier
[blog posts](https://seamlessaccess.org/posts/2021-07-06-browserchanges/), videos ([one](https://www.stm-assoc.org/events/web-browsers-privacy-and-your-publishing-platform-webinar/), [two](https://www.youtube.com/watch?v=NQNQ_sRPzHc)) and FAQs (for [librarians](https://seamlessaccess.org/learning-center/browser-faq-librarians/) and [publishers](https://seamlessaccess.org/learning-center/browser-faq-publishers/)), we talked about ongoing developments at the major browser vendors that are bound to have a significant impact on how users will experience the web in general, and on federated access in particular. To recap, these changes are driven by concerns around user privacy - including regulations such as GDPR - and meant to stop the unsanctioned tracking of users across the web.

“Why is that relevant to federated access?”, you might ask. Well, the complicating factor is that some browser functionalities that are used to track users, for example third-party cookies, are also used to support federated access - and the browser has no way to tell the difference! This means that, in an effort to improve user privacy, current access solutions for scholarly resources on the web may no longer work in the way they used to.

This is, in fact, already happening today with IP-based access: Apple has started to hide IP addresses by default for certain users, which means that these users may suddenly find themselves unable to access research publications or other scholarly resources if their library relies on IP authentication to provide access (see ["Apple’s iCloud Private Relay impacting IP recognition"](https://seamlessaccess.org/posts/2021-09-03-aug2021newsletter/) in our August 2021 newsletter). It also is affecting the implementations of SeamlessAccess as they exist today, with the experience of persistence (a remembered choice of institution) becoming dependent  on which browser is being used – but it is yet to have an effect on the core functionality of discovery and authentication.


<h3>Update</h3>

In early March, representatives of SeamlessAccess and other organisations representing the R&E community met up with developers from Google and Mozilla in Mountain View.

The meeting started with the research community describing our use cases, the technology that makes access on the scholarly web work today, and detailing examples of how federations are run and maintained. After this introduction to the R&E space, we dug in on what changes the browser vendors are looking to achieve and how those changes would rhyme with academic requirements and use cases, in particular with the established multilateral trust between parties in R&E federations. SeamlessAccess was received very positively and used as a reference for a good IdP discovery implementation throughout the conversation.

The outcome of the two days are two proposals that are publicly available (links below). Both of these proposals provide a context in which SeamlessAccess can continue to function and play an important role in providing researchers with powerful and easy-to-use access flows.

The two proposals are different in the levels of engagement and complexity for both identity federations and browsers. One proposal ([link to GitHub](https://github.com/fedidcg/proposals/issues/4)) is centered around explicit user consent to establish a local connection (cookie) between the user's chosen institution (IdP) and the relying party (SP). The other proposal ([link to GitHub](https://github.com/fedidcg/proposals/issues/5)) consists of browsers using the trust established inside the federation context to allow for the user to flow more freely between vetted IdPs and SPs using the federation's metadata as a guiding tool.

Work on elaborating these proposals will likely continue over the course of the year, and SeamlessAccess will continue to be heavily engaged in this. Both in the [W3C group](https://www.w3.org/groups/cg/fed-id/), and the [REFEDS group](https://wiki.refeds.org/display/GROUPS/Browser+Changes+and+Federation) that has been formed to keep the community informed and educated about what the new landscape looks like.
If you would like to join in on the conversation then you can find more information on the [W3C website](https://www.w3.org/groups/cg/fed-id/). The resources for the proposals can be found in the project’s [GitHub](https://github.com/fedidcg), and the discussions around it can be accessed through the mailing list of W3C, mailing list of [REFEDS group](https://wiki.refeds.org/display/GROUPS/Browser+Changes+and+Federation) for browser changes.



**We will continue to post updates, so please check our website regularly or subscribe to our [mailing list](https://seamlessaccess.org/contact/).**

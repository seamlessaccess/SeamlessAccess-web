---
layout: post
title: 'FedCM: July Update'
date: 2023-07-07
categories: [General]
hero: true
heroHeading: 'FedCM: July update on the efforts between the R&E community and browser vendors'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# FedCM: July update on the efforts between the R&E community, the web community, and browser vendors 



_This is an update following continuous meet-ups and other gatherings between representatives of the Research & Education (R&E) community and the browser vendors – discussing what capabilities in and around FedCM are required for our community to continue to serve academic users and their use cases._


<h3>Background</h3>

In a blog post titled [“An emerging new technology for federated access: Federated Credential Management (FedCM)”](https://seamlessaccess.org/posts/2023-02-20-fedcm/) and several later blog posts ([most recent](https://seamlessaccess.org/posts/2023-03-20-fedcm-postevent/), [previous](https://seamlessaccess.org/posts/2021-07-06-browserchanges/)), videos ([one](https://www.stm-assoc.org/events/web-browsers-privacy-and-your-publishing-platform-webinar/), [two](https://www.youtube.com/watch?v=NQNQ_sRPzHc)) and FAQs (for [librarians](https://seamlessaccess.org/learning-center/browser-faq-librarians/) and [publishers](https://seamlessaccess.org/learning-center/browser-faq-publishers/)), we discussed ongoing developments at the major browser vendors that are bound to have a significant impact on how users will experience the web in general, and on federated access in particular. To recap, these changes are driven by concerns around user privacy - including regulations such as GDPR - and meant to stop the unsanctioned tracking of users across the web.

“Why is that relevant to federated access?”, you might ask. Well, the complicating factor is that some browser functionalities that are used to track users, for example third-party cookies, are also used to support federated access - and the browser has no way to tell the difference! This means that, in an effort to improve user privacy, current access solutions for scholarly resources on the web may no longer work in the way they used to.

This is, in fact, already happening today with IP-based access: Apple has started to hide IP addresses by default for certain users, which means that these users may suddenly find themselves unable to access research publications or other scholarly resources if their library relies on IP authentication to provide access (see [“Apple’s iCloud Private Relay impacting IP recognition”](https://seamlessaccess.org/posts/2021-09-03-aug2021newsletter/) in our August 2021 newsletter). It also is affecting the implementations of SeamlessAccess as they exist today, with the experience of persistence (a remembered choice of institution) becoming dependent on which browser is being used – but it is yet to have an effect on the core functionality of discovery and authentication.



<h3>Recent developments at browser vendors
</h3>

Google ([Privacy Sandbox](https://privacysandbox.com/news/the-next-stages-of-privacy-sandbox-general-availability)), Apple ([one](https://www.apple.com/newsroom/2021/06/apple-advances-its-privacy-leadership-with-ios-15-ipados-15-macos-monterey-and-watchos-8/), [“blocking known tracking query”](https://developer.apple.com/documentation/safari-release-notes/safari-17-release-notes#Private-Browsing)) and Mozilla ([one](https://blog.mozilla.org/en/mozilla/firefox-rolls-out-total-cookie-protection-by-default-to-all-users-worldwide/), [two](https://groups.google.com/a/mozilla.org/g/dev-platform/c/ncmUwK1uO98/m/COhPA4ZrAAAJ), [three](https://support.mozilla.org/en-US/kb/enhanced-tracking-protection-firefox-desktop)) have introduced either timelines for implementing, or already implemented, changes that affect third party cookies, IP-authentication and potentially the SAML-protocol.

**In particular, Google has [announced](https://techcrunch.com/2023/05/18/google-will-disable-third-party-cookies-for-1-of-chrome-users-in-q1-2024/) that they will disable third-party cookies for 1% of Chrome users in Q1 2024.**

Mozilla has now included FedCM as part of their developer versions of the Firefox browser. And, in part through our efforts, Google is looking to put together an easy way for service providers to test how their service would work with the current FedCM profiles.


<h3>Help us test FedCM</h3>

In a [lightning talk](https://tnc23.geant.org/recordings/?session=s274) (starting at minute 27:30) at the TNC23 conference organized by GÉANT, Zacharias Törnblom (Product Manager for SeamlessAccess) issued a call to the community to help test the features in FedCM with their use case and report back to the GitHub repo for FedCM. This remains the best way for our community to help shape the browser changes to something that works for us. 


<h3>New resources available</h3>
Several new resources have been created to you may find helpful to better understand the issues and their likely implications:

* [“REFEDS Community Chat: Federated Identity and the Browser Update”](https://youtu.be/7L4Atm9FEBw) - a new video by REFEDS that can be used as an introduction to the subject of how this affects the R&E community. 
* Representatives from two National Research & Education Networks (NRENs), Canary (Canada) and JISC (UK), put together a test service with FedCM and explain it in [this video](https://1drv.ms/v/s!As-EAz5cVj8XgZNNewYG55DrDMm3Iw?e=UxZdMT).

We would suggest visiting and following the REFEDS group “Browser Changes and Federation”, specifically the page [“State of browser privacy evolution”](https://wiki.refeds.org/display/GROUPS/State+of+browser+privacy+evolution) where the current known actions taken by browser vendors alongside their adverse affect on R&E technology is listed.

And, as always, you can read up more in the [W3C group](https://www.w3.org/groups/cg/fed-id/), and the [REFEDS group](https://wiki.refeds.org/display/GROUPS/Browser+Changes+and+Federation) (also mentioned above) that has been formed to keep the community informed and educated about what the new landscape looks like. If you would like to join in on the conversation then you can find more information on the [W3C website](https://www.w3.org/groups/cg/fed-id/). The resources for the proposals can be found in the project’s [GitHub](https://github.com/fedidcg), and the discussions around it can be accessed through the mailing list of the [W3C community group](https://www.w3.org/community/fed-id/) and the mailing list of the [REFEDS group](https://wiki.refeds.org/display/GROUPS/Browser+Changes+and+Federation) for browser changes.



**We will continue to post updates, so please check our website regularly or subscribe to our [mailing list](https://seamlessaccess.org/contact/).**

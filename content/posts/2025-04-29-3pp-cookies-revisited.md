---
layout: post
title: '3rd-Party Cookies and Storage Access API, Revisited, Once again'
date: 2025-04-29
categories: [General]
hero: true
heroHeading: '3rd-Party Cookies and Storage Access API, Revisited, Once again'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---

# 3rd-Party Cookies and Storage Access API, Revisited, Once again

### News from Google

Last week, in an unexpected turn of events, Google announced that they have _“made the decision to maintain our current approach to offering users third-party cookie choice in Chrome, and will not be rolling out a new standalone prompt for third-party cookies.”_ - in other words: **Google will continue to support third-party cookies 'as is' for the foreseeable future, after all.**

The recent announcement, entitled “[Next steps for Privacy Sandbox and tracking protections in Chrome](https://privacysandbox.com/news/privacy-sandbox-next-steps/)”, goes on to explain that work on the Privacy Sandbox initiative - which was conceived as a program to develop alternative solutions to 3rd-party cookies and other privacy-invasive browser functionalities - will not be halted, but that it _“may have a different role to play in supporting the ecosystem”_ and that _“[Google will] continue to work with the ecosystem on determining how these technologies can best serve the industry and consumers”_.

This pivot comes at a time when many organizations, including SeamlessAccess, have prepared for the deprecation of third-party cookies in Chrome and other browsers. In particular, SeamlessAccess has [implemented support for the Storage Access API](https://seamlessaccess.org/posts/2024-10-16-storage-access-api/) - one of the technologies developed under the Privacy Sandbox - and is in the process of [testing this implementation](https://seamlessaccess.org/posts/2025-01-14-storage-access-api-please-test/) with a number of service providers that integrate with SeamlessAccess. One very attractive feature of the Storage Access API is its cross-browser support, which offers technical benefits as well as a consistent user experience across different browsers. 


### So, what does this announcement mean for SeamlessAccess? 

The announcement is very high-level, and Google has so far not shared further details either publicly or privately. This means that questions remain about the exact feature set that Google will continue to support, and to what extent users would be able to (or expected to) protect their privacy through configuration settings. In addition, the future role of the Storage Access API and how other browser engines will respond to this pivot remains unclear. The Storage Access API was supported by all major browser vendors, and some browsers may decide to pursue this technology further. 

From a SeamlessAccess standpoint, the most optimistic outcome would be that the SeamlessAccess service can continue to remember the user’s choice of institute across participating websites (“[global persistence](https://seamlessaccess.org/posts/2024-10-16-storage-access-api/)”) with additional privacy safeguards that are not as disruptive as those foreseen for Google Chrome’s implementation of the Storage Access API - but it is too early to say if that is indeed how things will play out.


For the moment, until we have a better grasp of the implications of Google's announcement, **we recommend pausing efforts to test SeamlessAccess’ Storage Access API implementation.** We appreciate the support that you have shown in recent months, and we understand that teams have put significant effort into exploring this solution. From our side, the experimentation with the Storage Access API has helped us develop a much stronger understanding of user consent flows in a distributed environment. These findings will help us move forward with the service more effectively.

**We will follow up with a more detailed analysis as soon as possible.**




---
layout: post
title: 'Important update on 3rd-party cookies and SeamlessAccess'
date: 2025-06-18
categories: [General]
hero: true
heroHeading: 'Important update on 3rd-party cookies and SeamlessAccess'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---

# Important update on 3rd-party cookies and SeamlessAccess



### The summary: good news!

As mentioned in our [last blog post](https://seamlessaccess.org/posts/2025-04-29-3pp-cookies-revisited/), Google’s [recent announcement](https://privacysandbox.com/news/privacy-sandbox-next-steps/) about their continued support for third-party cookies left us with some unanswered questions about what that exactly means for SeamlessAccess. In particular, what was not clear from the brief announcement text is what impact this change of direction will have on SeamlessAccess' ability to remember the user’s choice of institute across participating websites, an important part of the usability improvements that SeamlessAccess offers.

Following more detailed conversations with the team at Google and detailed tests by the SeamlessAccess team and others, we are now able to confirm positive news: **SeamlessAccess will continue to be able to offer global persistence (i.e., the ability to remember the user’s choice of institute across participating websites) for Chrome and Chromium-based browsers like Microsoft Edge. This applies to all SeamlessAccess integration patterns - Limited, Standard, and Advanced - with no or limited effort for integrators.**

_Caveat: Although this appears to be the long-term direction that Google is now settling in, we cannot exclude the possibility that this might again change in the future. Also, behavior in other browsers will be different - more on that in the below._



### The back story

Over the last several years, the team at SeamlessAccess has closely followed developments at   browser vendors related to third-party cookies and other mechanisms that can be used to track users on the web (see e.g. [this blog post](https://seamlessaccess.org/posts/2021-07-06-browserchanges/)). This journey started several years ago, when new legislation was introduced that led browser vendors to [review their safeguards](https://blog.google/products/chrome/building-a-more-private-web/) for user privacy. 

User privacy is a key value for SeamlessAccess, and the SeamlessAccess service has been designed with privacy at its core. Despite that alignment on underlying values, the specific changes that browser vendors have been making (or planning to make) would come with unintended side effects for the SeamlessAccess service.

More specifically, the most significant change that browsers have been working on deals with  how user information that is stored by one website can be read by another website, a mechanism that is called “third-party access”. This mechanism was under scrutiny because it can be exploited to track users across the web without their consent. However, it can also be used in ways that are entirely respectful of users’ privacy - and that is exactly how SeamlessAccess has been using third-party access to remember the user’s choice of institution between participating websites (see [this blog post](https://seamlessaccess.org/posts/2023-11-16-3pp-cookies-and-the-sa-button/) from the end of 2023 that explains in detail how SeamlessAccess uses third-party access). Without the ability for third-party access, SeamlessAccess can only remember the user’s choice of institute on individual websites. While that is still helpful to ease user’s access journeys, it is more limited in scope compared to being able to remember this choice across participating websites (a functionality that we refer to as ‘[global persistence](https://seamlessaccess.org/posts/2024-10-16-storage-access-api/)’). 


### Introduction of the Storage Access API

In an effort to develop more privacy-focused alternatives to third-party cookies, Google launched an initiative called the [Privacy Sandbox](https://privacysandbox.com/intl/en_us/). One of the new approaches developed within this program is the so-called [Storage Access API](https://privacysandbox.google.com/cookies/storage-access-api) which offers a mechanism for third-party access with much greater control in the hands of the user. A benefit of this technology is its cross-browser support; the downside is that the additional privacy safeguards would come with significant negative impacts in terms of user experience - including browser-mediated consent pop-ups that the user would need to frequently go through.

Despite those drawbacks, the Storage Access API offered SeamlessAccess a path forward to retain the ability to remember the user’s choice of institution across participating websites. Because of this, SeamlessAccess developed support for the Storage Access API and [made this available for testing](https://seamlessaccess.org/posts/2024-11-29-storage-access-api-prepare-for-testing/) at the end of 2024. Following a round of testing, with great support from the community, support for the Storage Access API was [rolled out in March](https://seamlessaccess.org/posts/2025-02-19-release-next-week/) of this year in preparation for the moment that third-party cookies would be retired for all users in Google Chrome and Chromium-based browsers.

_And that is when Google [announced](https://privacysandbox.com/news/privacy-sandbox-next-steps/) that they would, after all, continue to support 3rd-party cookies without overhauling the associated user experience…_


### Implications of the April Google announcement

In an interesting turn of events, the team behind the Chrome browser [announced in April](https://privacysandbox.com/news/privacy-sandbox-next-steps/) that they were not going to follow the plan as originally set out: _“... we’ve made the decision to maintain our current approach to offering users third-party cookie choice in Chrome, and will not be rolling out a new standalone prompt for third-party cookies.”_

This announcement [made us optimistic](https://seamlessaccess.org/posts/2025-04-29-3pp-cookies-revisited/) that it would allow SeamlessAccess to continue to offer global persistence without the strong UX downsides that we had been told would come with the Storage Access API. However, the announcement itself lacked technical detail to be sure about this interpretation. Since then, we have discussed this in detail with technical contacts at Google and have implemented additional tests which confirm that:

* The Chrome browser will still use the Storage Access API, as planned, but as a back-end technology that’s decoupled from the UX changes that were originally part of the scope;
* The Storage Access API will, by default, not require user consent and will not require the user to have visited the top-level domain (i.e., seamlessaccess.org). Users will have the option to switch on additional privacy controls that bring these requirements back;
* Through the Storage Access API, websites can access third-party information in a way that's effectively unpartitioned, which is exactly what SeamlessAccess needs to deliver global persistence.

Note that the above holds for Google Chrome and other Chromium-based browsers like Microsoft Edge. Firefox has indicated that they will introduce the Storage Access API with privacy controls enabled by default, meaning that users will be prompted to provide consent and will need to have visited the seamlessaccess.org domain. (If the user does not do this, the fall-back behaviour is local persistence i.e. SeamlessAccess can still be used to remember the user’s choice of institute for the individual website). 

For **Safari** users, we don't expect global persistence to work because Safari still hasn't said they will support the implementation pattern that SeamlessAccess is using - though that might change in the future.


### What does that mean for researchers and scholars using SeamlessAccess? 

For a researcher using **Chrome with default settings**: Use of the Storage Access API is enabled without the user having to adjust any settings. If the user visits a website and saves their choice of institute through SeamlessAccess, then this choice will be saved and visible when the user goes to another site that integrates with SeamlessAccess. No difference compared to the original SeamlessAccess experience.


For a researcher using **Chrome with additional privacy controls** enabled (opt-in setting): Assuming that the user has visited seamlessaccess.org, they will see a prompt asking them to allow sharing their information before the website is able to use the remembered choice of institute (see [this blog](https://seamlessaccess.org/posts/2025-02-19-release-next-week/) post for an image of how that prompt would look like). This means that for this user, the SeamlessAccess button will be empty until they have clicked  “allow”; thereafter the button will again show the user’s remembered institute.

For a researcher using **Firefox** (with the default “block 3rd-party cookies” setting enabled) or Safari: Storage Access API is not enabled, and SeamlessAccess will fall back to local persistence. That means that the user will still see their remembered choice of institute in the button for individual websites, but not between participating websites.

For a researcher using **Edge**: the user experience will be very similar to that in Chrome after support has been implemented (which is currently on our roadmap).

For a researcher using **Safari**: SeamlessAccess will fall back to local persistence, i.e. the user will still see their remembered choice of institute in the button for individual websites, but not between participating websites.


### What does that mean for service providers integrating with SeamlessAccess?

SeamlessAccess has implemented the Storage Access API at the end of last year, which means that this new behaviour is already supported by the latest version of SeamlessAccess. That means that, for **Limited** or **Standard Mode** integrators, the only requirement is to use the most recent version of SeamlessAccess.

For **Advanced Mode** integrators:

* Please update to the most recent version of SeamlessAccess for your integration.
* If you would like to offer a path for Chrome or Edge users who choose to block 3rd-party cookies to go through a consent flow and remember their choice of institute, you need to update your code to expose a checkbox that’s served as an iframe from SeamlessAccess. (To be sure, this is not needed for users who are using Chrome or Edge with the default setting to not block 3rd-party cookies).


### To wrap up…

We appreciate this has been a long read with a lot of information, but the overall take-away is this: SeamlessAccess will continue to be able to remember the user’s choice of institute across participating websites for Chrome and Edge users, with limited effort required for parties that integrate with SeamlessAccess.

Feel free to contact us with any questions through the usual channels (email or Slack).



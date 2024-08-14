---
layout: post
title: 'Google’s updated approach to third-party cookies: What does it mean for SeamlessAccess?'
date: 2024-08-14
categories: [General]
hero: true
heroHeading: 'Google’s updated approach to third-party cookies: What does it mean for SeamlessAccess?'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# Google’s updated approach to third-party cookies: What does it mean for SeamlessAccess?


In a [blog post](https://seamlessaccess.org/posts/2024-04-02-important-update/) that came out in April, we spoke about changes to browser technology and what impact those are likely to have on access experiences and SeamlessAccess. At the time, following Google’s communication on the subject, we worked under the understanding that Google would roll out deprecation of third-party cookies in Chrome to 100% by the end of this year.

Last month, Google announced a change of course. In an [announcement](https://privacysandbox.com/intl/en_us/news/privacy-sandbox-update/) on the Privacy Sandbox website they stated that _“Instead of deprecating third-party cookies, we would introduce a new experience in Chrome that lets people make an informed choice that applies across their web browsing, and they’d be able to adjust that choice at any time. We're discussing this new path with regulators, and will engage with the industry as we roll this out.”_ This update came as a surprise to many in our community, as well as to other sectors that are impacted by these changes such as online advertising.

The announcement is very high-level, and Google has not shared further details either publicly or privately - which makes it impossible to fully assess what this new approach will mean for SeamlessAccess. However, we do know that other browser engines such as Safari are no longer (by default) supporting third-party cookies. We also know that, if Google will leave third-party cookies as a choice to the user, a (presumably significant) portion of users will opt out. All of that is to say that third-party cookies (or, to be precise, third-party access to local browser storage) will in the future only work for some users and for some browsers. This is in stark contrast to the essentially universal mechanism that third-party cookies once offered for SeamlessAccess to store the user’s remembered choice of institute.

SeamlessAccess is all about delivering a consistent and reliable user experience to ease access pathways to scholarly resources. The kind of fragmentation and inconsistency described above is clearly at tension with that ambition, and so we will continue to explore alternative technologies – such as the Storage Access API – that have the potential to let SeamlessAccess persist the user’s choice of remembered institute in a consistent, easy-to-use, and privacy-respecting way across different browsers. Google’s recent announcement means that there is more time to develop and test such new technologies before the current SeamlessAccess implementation will break, but it is also likely to introduce additional complexity to a future solution.

As we continue to move in this direction, our previous recommendations for Service Providers that integrate with SeamlessAccess still hold:

* We highly recommend that you participate in Google’s [deprecation trial for unpartitioned third-party storage](https://developers.google.com/privacy-sandbox/3pcd/temporary-exceptions/storage-partitioning-deprecation-trial) to keep the SeamlessAccess ‘smart button’ working for your users.
* If you use the SeamlessAccess Advanced Mode integration, we recommend that you consider switching to the Standard Mode integration because that integration pattern will be significantly more robust under changes in browser technology.

 
Finally, we recognize the communications challenge that our community faces to navigate this ongoing period of uncertainty that is driven by agendas essentially external to us. From the SeamlessAccess side, we will continue to engage with browser vendors and publish posts like these where we share our findings and perspectives. Additionally, we have set up a Slack channel to facilitate dialogue and knowledge exchange at a technical level between SeamlessAccess and parties that integrate with SeamlessAccess about these topics. If you represent a service that is integrated with SeamlessAccess, and are interested in joining this channel, please email Hylke Koers at hylke@stm-solutions.org.





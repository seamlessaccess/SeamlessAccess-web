---
layout: post
title: 'Signed up for Storage Partitioning trial? Time to renew!'
date: 2024-10-16
categories: [General]
hero: true
heroHeading: 'A new chapter in the ‘browser changes’ journey: Preparing for the switch to Storage Access API'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# A new chapter in the ‘browser changes’ journey: Preparing for the switch to Storage Access API


Over the last couple of years, we have posted regularly about changes that are being made to the way that browsers work and how those changes will affect SeamlessAccess (see e.g. [this post from Feb 2024](https://seamlessaccess.org/posts/2024-04-02-important-update/) or [this post from Nov 2023](https://seamlessaccess.org/posts/2023-11-16-3pp-cookies-and-the-sa-button/) and references therein). These changes primarily impact SeamlessAccess’ ability to remember the user’s choice of home institute across participating websites, a functionality that we refer to as “global persistence”. That global persistence is one of the ways in which SeamlessAccess helps service providers to offer intuitive and, well, seamless access experiences to the research community.
Since its development, SeamlessAccess has relied on third-party access to local browser storage as the technical capability to deliver that global persistence. (This mechanism is similar to third-party cookies and we’ll just use ‘third-party cookies’ as a short-hand in the rest of this post). 

For a long time (see e.g. [this post from 2021](https://seamlessaccess.org/posts/2021-07-06-browserchanges/)) browser engines have been planning to move away from third-party cookies because of user privacy concerns. And despite a [recent announcement](https://seamlessaccess.org/posts/2024-08-14-google-3ppcookies-announcement/) from Google suggesting a change of course, we continue to see steps being taken to limit the browser's ability to store and make available data across different websites.

The path towards phase-out of third-party cookies has been hard to navigate at times, as browser vendors typically provide only limited information about specific steps and timelines. The same can be said about the development of new technologies that are meant to provide an alternative to third-party cookies. In the past, we’ve reported on [FedCM](https://seamlessaccess.org/posts/2023-02-20-fedcm/), the Privacy Sandbox and, more recently, the [Storage Access API](https://seamlessaccess.org/posts/2024-04-02-important-update/).

**We are now entering a new phase in this journey, one that thankfully comes with greater clarity. After intensive testing and discussions, the SeamlessAccess team has settled on adopting the Storage Access API as its new technology to store and retrieve the user’s choice of institute in the browser.** One very important advantage of this solution is that it is supported by all major browser engines. While we are happy that this provides a clear path forward to retain global persistence, it should be noted that it will come with some changes to the user experience such as a consent step.

**With that decision made, we are now planning for the transition process.** For service providers that use the Limited or Standard Mode integration, we expect to be able to make the required changes entirely on the side of SeamlessAccess – meaning no development work for the service provider that integrates with SeamlessAccess. For Advanced Integrations the situation is different: Changes will be needed on both the SeamlessAccess side *and* on the the service provider side. SeamlessAccess will be developing documentation and guidance to assist with this process, and we will continue to engage with service providers to help them prepare.

**For now it is important to be aware of timelines: SeamlessAccess will implement the Storage Access API before the end of this year (to work in parallel with the current implementation), and we strongly urge Advanced Integrators to reserve some development capacity to implement their part of the switch-over in the first quarter of 2025.** Alternatively, Advanced Integrators could consider moving to the Standard Mode integration pattern.

**We’re organizing an integrator workshop on 23 October** to discuss the transition to the Storage Access API in more detail. If you represent a service provider that has integrated with SeamlessAccess, and you have not yet been invited to this workshop, feel free to send an email to hylke@stm-solutions.org and we’ll be happy to add you to the list (or get in touch with you separately).



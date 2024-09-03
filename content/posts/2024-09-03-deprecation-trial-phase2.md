---
layout: post
title: 'Signed up for Storage Partitioning trial? Time to renew!'
date: 2024-09-03
categories: [General]
hero: true
heroHeading: 'Signed up for Storage Partitioning trial? Time to renew!'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# Signed up for Google's storage partitioning trial? Time to renew!


As we talked about in a post back in February "[Calling all SeamlessAccess integrators to participate in deprecation trial for unpartitioned third-party storage](https://seamlessaccess.org/posts/2024-02-29-third-party-storage-deprecation-trial/)" - and before that as part of a [longer explanation](https://seamlessaccess.org/posts/2023-11-16-3pp-cookies-and-the-sa-button/) back in 2023 - the team that works on Google Chrome has made available a limited-time trial that allows participating sites to continue to use unpartitioned storage in the browser. This is a feature that is critical for SeamlessAccess’ ability remember the user’s choice of IdP across integrating websites. The deprecation trial provides more time to implement new solutions as browsers are changing their default behaviour for users and become more restrictive about sharing information between different websites.

As the current trial is coming to an end, Google has [announced](https://developers.google.com/privacy-sandbox/blog/storage-partitioning-deprecation-trial-renewal?hl=en) that a new trial period will begin. **However, in order to be part of the new trial you will need to renew your application! You can do that [here](https://developer.chrome.com/origintrials/#/view_trial/568016503002103809).**

We have worked  with the Chrome team to collect answers to some of the questions that you may have at this point:

### *What happens if a site doesn't renew?*
The origin trial will officially stop working on September 3rd for any users on Chrome 111 to Chrome 126. Users who are already on 127 or 128 (current stable release) will see the default behavior already (that is to say, they will have partitioned 3rd party storage).

### *Is there a latest date a site needs to apply for renewal?*
The Chrome team will review applications for the lifetime of the current origin trial, scheduled to be until March 2025 or thereabouts. 


### *What will the experience be for different users (on different browser versions)?*
If your site is part of the deprecation trial, and the user is using a Chrome browser of version 127 or later, then they will have the experience of the unpartioned storage that the trial promises.

If the user is using Chrome 111 to 126 then they will have partitioned 3rd party storage, i.e. the storage partitioning trial will not apply to those users.

When a user updates to Chrome version 133, or March 18th at the very latest, they will have partitioned storage.

### *What happens after this next trial ends?*

The advice that the Chrome team gives is to plan for the future where no origin trials exist to support the legacy behavior. The outlook is clear: Partitioned storage is here to stay and will become part of the standard behaviour of all browsers in the future.

As we discussed in other blog posts ([here](https://seamlessaccess.org/posts/2024-04-02-important-update/) and [here](https://seamlessaccess.org/posts/2024-08-14-google-3ppcookies-announcement/)), the SeamlessAccess team is working hard to test how emerging alternative technologies, in particular the Storage Access API, can be applied to power SeamlessAccess' ability to remember the user’s choice of institute across different websites - which we know is a great piece of functionality to streamline to user’s access experience. We'll keep you, and the rest of the community, updated through posts like these. 







---
layout: post
title: 'Please test: SeamlessAccess with Storage Access API (and an update from Google)'
date: 2025-01-14
categories: [General]
hero: true
heroHeading: 'Please test: SeamlessAccess with Storage Access API (and an update from Google)'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# Please test: SeamlessAccess with Storage Access API (and an update from Google)

## Migration to Storage Access API

As discussed in a [string](https://seamlessaccess.org/posts/2023-11-16-3pp-cookies-and-the-sa-button/) of [blog](https://seamlessaccess.org/posts/2024-04-02-important-update/) [posts](https://seamlessaccess.org/posts/2024-10-16-storage-access-api/) last year, SeamlessAccess will be migrating to a new technology. This migration is needed in order to adapt to changes in how browser engines operate, in particular the deprecation of third-party cookies. If you are not familiar with this topic, we encourage you to read through the posts linked just above.

The new implementation makes use of a technology called Storage Access API that has been developed under the [Privacy Sandbox](https://privacysandbox.com/intl/en_us/) initiative spearheaded by Google. Importantly, the Storage Access API is supported across browsers and will enable SeamlessAccess to continue to remember the user’s choice of institute across participating websites in a privacy-preserving manner - though the user experience will be somewhat different compared to the current implementation (which relies on third-party access to local browser storage). We will be following up with a separate post to talk more about the expected changes in user experience.

**With this post, we are announcing that a (test) version of the SeamlessAccess service using the Storage Access API is now available for testing. We strongly recommend service providers that are currently integrating with SeamlessAccess to test and share feedback with us.** We specifically urge those using the Advanced Mode integration pattern to test because the changes are expected to be the greatest for that pattern and development effort will be required to migrate to the new implementation. As a [reminder](https://seamlessaccess.org/posts/2024-10-16-storage-access-api/), we strongly advise integrators to plan to migrate before the end of Q1.

### How to test? ###

A test version of SeamlessAccess that uses the Storage Access API can be found here (see also [this blog post](https://seamlessaccess.org/posts/2024-11-29-storage-access-api-prepare-for-testing/) for more detail about the various environments available for testing and integrations):

* Discovery service: https://use.thiss.io/ds/
* Persistence service: https://use.thiss.io/ps/
* Front-end code: https://use.thiss.io/thiss.js


Using SeamlessAccess with the Storage Access API feature will require some configuration. To accommodate the different integration patterns that service providers use, we have created a migration guideline which outlines how the new integration is done. The guideline can be found under our documentation here: [https://thiss-ds-js.readthedocs.io/en/stable/using-saa.html](https://thiss-ds-js.readthedocs.io/en/stable/using-saa.html).

We welcome any feedback and questions that you may have, preferably over [Slack](https://seamlessaccess.slack.com/archives/C06RU8DS8BE). If you don’t have access to this channel, or would rather contact us over email, feel free to reach out to Hylke Koers (SeamlessAccess Program Director) at [hylke@stm-solutions.org](mailto:hylke@stm-solutions.org).


### Integrator Workshop ###

We will be hosting another Integrator Workshop on Feb 4 to assist service providers that have integrated with SeamlessAccess with the migration process. If you’d like to join, and have not yet been invited, please contact [hylke@stm-solutions.org](mailto:hylke@stm-solutions.org).



## News from Google: Storage Partitioning deprecation trial renewal ##

Under ‘related news’, Google has recently [announced](https://developers.google.com/privacy-sandbox/blog/storage-partitioning-deprecation-trial-second-renewal) that they will renew their deprecation trial to *“temporarily unpartition and restore prior behavior of storage, service workers, and communication APIs”*. As a reminder, this trial allows participating services to continue to use unpartitioned storage in the browser, a feature that is critical for SeamlessAccess’ ability to remember the user’s choice of IdP across integrating websites in its current implementation (that is to say, without the Storage Access API technology discussed above). As with the previous extension, discussed in this [post](https://seamlessaccess.org/posts/2024-09-03-deprecation-trial-phase2/), only parties that are already enrolled will be eligible to take part in this extension. **If you represent an organization that is currently taking part in ‘phase two’ of the deprecation trial, we encourage you to apply for this extension.**

While this announcement, thankfully, provides a bit more time for parties to continue to use the current SeamlessAccess implementation to its full potential, it does not change the fundamental dynamics at play: 3rd-party access to cookies and local browser storage is being phased out and SeamlessAccess will be migrating to the Storage Access API in response to this change. In that light, as discussed above, we urge integrators to engage in testing, provide feedback, and plan development work as needed (for Advanced Integrators).


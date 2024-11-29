---
layout: post
title: 'Coming up: Storage Access API and IdP filtering, ready for testing'
date: 2024-11-29
categories: [General]
hero: true
heroHeading: 'Coming up: Storage Access API and IdP filtering, ready for testing'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# Coming up: Storage Access API and IdP filtering, ready for testing

As discussed in previous blog posts, see for example [this post](https://seamlessaccess.org/posts/2024-10-16-storage-access-api/) from 16 October, we are developing a version of SeamlessAccess that uses a new technology called Storage Access API. With this new technology, which is supported by different browsers, SeamlessAccess will continue to be able to remember and present the user's choice of institute in the SeamlessAccess button. For the user this means that once they have located their home institute provider  on one website, they can re-use that choice on the next website they visit and enjoy a much easier access experience.

We expect that this new version of SeamlessAccess will be ready for *testing* next week. We highly recommend all SeamlessAccess integrators to explore and test how this updated code integrates with your own environment. Testing can be done for both the Standard Mode and Advanced Mode integration patterns.

In addition to the migration to Storage Access API, this release will also include new functionality called "IdP filtering", which enables service providers that use SeamlessAccess' Standard Mode to customize the list of IdPs that is presented to their end-users in the IdP discovery (also known as "Where-Are-You-From" or WAYF).

For reference, the latest version of the SeamlessAccess code **intended for testing and explorative work** can be found here:

* Discovery service: https://use.thiss.io/ds/
* Persistence service: https://use.thiss.io/ps/
* Front-end code: https://use.thiss.io/thiss.js


Whereas the stable version of SeamlessAccess, which we **recommend to use for production and production-like testing**, is here:

* Discovery service: https://service.seamlessaccess.org/ds/
* Persistence service: https://service.seamlessaccess.org/ps/
* Front-end code: https://service.seamlessaccess.org/thiss.js

If you'd like to discuss the details of the release, you are welcome to join in on the discussion in our Slack channel. If you encounter any bugs or issues, the best place to post these is through [Github](https://github.com/seamlessaccess/SeamlessAccess-web).
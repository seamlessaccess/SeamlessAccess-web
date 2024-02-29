---
layout: post
title: 'Calling all SeamlessAccess integrators to participate in deprecation trial for unpartitioned third-party storage'
date: 2024-02-29
categories: [General]
hero: true
heroHeading: 'Calling all SeamlessAccess integrators to participate in deprecation trial for unpartitioned third-party storage'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# Calling all SeamlessAccess integrators to participate in deprecation trial for unpartitioned third-party storage 


In a [blog post](https://seamlessaccess.org/posts/2023-11-16-3pp-cookies-and-the-sa-button/) published towards the end of last year, we spoke about an update to Google’s Chrome browser that by default enabled a new feature called Storage Partitioning. This feature effectively blocks third-party websites from accessing information held in the local browser storage, which is used by SeamlessAccess to show the user’s remembered choice of institute in its button. This specific change is an example of a broader-scale and ongoing journey by the main browser vendors to deprecate functionalities that can be used to track users on the web. In that process, however, also non-privacy-invading use cases are impacted including access to scholarly resources through SeamlessAccess.



We also described in that blog post [how individual users are able to restore the SeamlessAccess button by opting out of this feature](https://seamlessaccess.org/posts/2023-11-16-3pp-cookies-and-the-sa-button/), and we continue to recommend this practice.


In addition to this option, which requires individual users to take action, **Service Providers that integrate with SeamlessAccess are also able to opt out of the Storage Partitioning setting in Google Chrome** without placing the burden on their end-users. This can be done at the level of the website, following these instructions from the Privacy Sandbox: [Participate in deprecation trial for unpartitioned third-party storage, Service Workers, and Communication APIs](Participate in deprecation trial for unpartitioned third-party storage, Service Workers, and Communication APIs).

This approach has been tested and validated by Atypon, who have implemented it to ensure SeamlessAccess continues to work as intended across several of the publishing domains which they host. Olly Rickard, Product Manager, confirmed: _“By taking part in this deprecation trial, we are able to continue to provide our customers with the SeamlessAccess user experience which they trust and value until at least the end of this trial. The process to make use of this option was very straightforward and I highly recommend other parties that have integrated with SeamlessAccess to do the same.The more people that sign up, the more sites can share the remembered institute, the more valuable the feature is for our community”._



While this is good news for the moment, the deprecation trial is time-bound and currently set to expire on September 3rd with the release of Chrome 127. The SeamlessAccess team, together with several of partner organizations, is working hard to explore a number of alternative technologies such as [FedCM](https://developers.google.com/privacy-sandbox/3pcd/fedcm), [CHIPS](https://developers.google.com/privacy-sandbox/3pcd/chips), and the [Storage Access API](https://developers.google.com/privacy-sandbox/3pcd/storage-access-api). These technologies have been made available by Google and other parties - in some cases very recently - to offset some of the impact of upcoming browser changes for use cases such as access and authentication. Some of these should work across browsers, offering a more standardized solution, while others are more specific to Google Chrome and browsers that use the same code-base (such as Microsoft Edge). We’re eagerly testing all options to learn if they are able to provide an alternative solution for SeamlessAccess’ function of remembering the user’s last choice of institute across participating websites and scholarly resources.



This is a very dynamic space, with lots of change happening in sometimes parallel tracks. To navigate those changes, we are stronger together. **If your organization is already experimenting with the above technologies, has learnings to share, or would like to contribute - we’d love to hear from you!**

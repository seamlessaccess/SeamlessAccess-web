---
layout: post
title: 'Upcoming SeamlessAccess release on 12 March (was: 27 Feb)'
date: 2025-02-19
categories: [General]
hero: true
heroHeading: Upcoming SeamlessAccess release on 12 March (was: 27 Feb)'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---

# Update: SeamlessAccess release on 12 March

**Update:** As communicated over Slack, the below release was rolled back because of unexpected compatibility issues for a small number of integrators. These issues have now been addressed and tested. **We are releasing the new version of SeamlessAccess on Wed, 12 March.**

Please note that this is a **backward compatible change**, also supporting the current SeamlessAccess implementation. As always, we will be closely monitoring the service before, during and after the release. If you experience any unforeseen behaviour, please alert us via Slack or email.




# Upcoming SeamlessAccess release on 27 Feb

**We will be releasing a new version of SeamlessAccess to production on Thursday, Feb 27.**



This new version (link to [GitHub](https://github.com/TheIdentitySelector/thiss-js/releases/tag/2.1.38)) includes [IdP filtering capabilities and support for the Storage Access API technology](https://seamlessaccess.org/posts/2024-11-29-storage-access-api-prepare-for-testing/). Both of these changes have been [tested](https://seamlessaccess.org/posts/2025-01-14-storage-access-api-please-test/) over the last couple of months with several SeamlessAccess integrators, and we are excited to now bring these into the production environment.

**Please note that this is a backward compatible change, also supporting the current SeamlessAccess implementation.** 

Advanced Mode integrators will be able to make the switch to Storage Access API at their convenience.

For Standard Mode integrators, we don’t expect the release will have an impact on user experience, _except_ for users on Google Chrome who have either manually enabled “third party cookies phase-out” and/or have been enrolled into that program by Google. Such users may be presented with an additional consent screen by the browser. If so, they will need to grant such permission before they can benefit from SeamlessAccess’ capability to remember the user’s choice of institution across integrating websites.

<img src="/posts/consentscreen.png" width="720" />

Above is a screenshot of how the browser consent screen is expected to look like (note: “thiss.io” will change to “seamlessaccess.org” after the release). We continue to be involved in further development of these features by the browser vendors.

For integrators that connect a Standard-Mode button to a third-party IdP discovery tool (sometimes referred to as ‘hybrid’ integration mode), we expect that the changes on the publisher side will be the same as for Standard Mode integrators, as described above. The third-party IdP discovery tool would need to make changes on their end to switch over to the Storage Access API implementation, just as is the case for Advanced Integrators. While we are working with relevant parties to design an optimal user flow for this integration pattern, we invite other service provides who uses this hybrid integration pattern to reach out and join the discussion.

**As always, we will be closely monitoring the service before, during and after the release. If you experience any unforeseen behaviour, please alert us via Slack or email.**



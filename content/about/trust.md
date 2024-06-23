---
title: 'Privacy and Trust'
date: 2020-02-15T09:29:16+10:00
icon: 'features/icn_privacy.svg'
featured: true
draft: false
type: about
weight: 3
heroHeading: 'Privacy and Trust'
heroSubHeading: ''
heroBackground: 'images/hero_privacy.jpg'
---

SeamlessAccess is a service designed to help foster a more streamlined online access experience when using scholarly collaboration tools, information resources, and shared research infrastructure. It promotes digital authentication leveraging an existing single-sign-on infrastructure through your home institution, while maintaining an environment that protects your personal data and privacy.

One of the important goals of SeamlessAccess is to reduce the need for you to have to find your institution on a list before being able to sign in to access a resource. To make this happen, SeamlessAccess stores information in your own browser about the institution(s) that you use to sign in. At no point is any personal information such as your name, email, or other personal information stored in your browser.

# What information is collected by SeamlessAccess?

When you select the institutions that you prefer to sign in with, SeamlessAccess will store information about the last three selections in your browser. The concept is similar to storing information as a cookie, although in this case it is stored in a different location - in your Browser Local Storage.

The information stored is only about your selection, not about you personally. For example, it includes the name of the institution you previously chose to sign in with, and the URL to its sign-in service.

SeamlessAccess runs its software locally in your browser and stores this information in browser local storage. In some cases, the authorized, participating services may be the ones to provide information about the sign-in service that you selected so that it can be stored. This exchange is done through a secure Application Programming Interface (API.) If you are curious about how this works, we invite you to take a look at our technical documentation in the [Getting Started](../../work) section of our site.  
   
# Who can access this information and how is it used?

Once this information is stored in your browser, a research service or resource that you use (such as a publisher, research collaboration tool, or library resource)  that also participates in SeamlessAccess may make an electronic request to SeamlessAccess to find out which sign-in service you prefer. The service will then use this information to present that sign-in option to you first instead of presenting a list of sign-in services for you to choose from. This hopefully makes your sign-in a bit easier.

# How can I see and affect what is being stored?

Since SeamlessAccess uses standard web browser local storage, the best resource to learn how to check and affect the stored information is found in the help pages for the browser that you are using. For convenience, we have included links to a few of these pages here as were available at the time that this was written.

In all cases, you will need to first navigate to service.seamlessaccess.org before following the instructions specific to your browser.

* **Mozilla Firefox**: [Manage local site storage settings](https://support.mozilla.org/en-US/kb/storage)
* **Google Chrome**: [View and Edit Local Storage With Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)
* **Microsoft Edge**: [View and Edit Local Storage with Microsoft Edge DevTools](https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/storage/localstorage)

For most browsers, if you completely block third party access (sometimes called third party cookies even though cookies are not involved) and/or browse in “private” or “incognito” mode, SeamlessAccess will not be able to facilitate your login experience.

# What other information about me might be shared?

The sign-in service you have chosen (aka your home institution) is the only party that can determine what information about you is shared with the service. SeamlessAccess plays no part whatsoever in any exchange of data between the home institution and the service. Exactly what information is shared about you between the home institution and the service is determined by a combination of bi- and multilateral agreements and asking for user consent.

# A note about how we value your privacy

User privacy is one of the [guiding principles](../) of the SeamlessAccess service. The General Data Protection Regulation (GDPR) and the e-privacy regulation proposal arising from the EU provide a set of legal requirements that inform the configuration and use of the service.

# How is SeamlessAccess governed?

See the [About Us](../) page for more information about SeamlessAccess.

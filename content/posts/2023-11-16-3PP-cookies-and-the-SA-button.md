---
layout: post
title: 'Third-party cookie deprecation and its effect on SeamlessAccess'
date: 2023-11-15
categories: [General]
hero: true
heroHeading: 'Third-party cookie deprecation and its effect on SeamlessAccess'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---


# Third-party cookie deprecation and its effect on SeamlessAccess 


**Is your SeamlessAccess button acting weird? Not showing your remembered institute as you expect?
This might be due to a new browser configuration setting that blocks third-party cookies. Without those cookies, the SeamlessAccess button (i.e. “Access through..”) will work differently than you might expect  - but the other SeamlessAccess services (login, discovery, remembered choice on the discovery page) continue to work as before. 
And you can fix the button, too! (at least for now)**



<h2>What’s the situation?</h2>

Late October,  Google  released version 118 of its Chrome browser. This version enables a feature called _Storage Partitioning_ by default. This feature prevents third-party cookies from being used in the traditional sense, which impacts - among many other services on the web - the SeamlessAccess button. You can read more about this specific feature in [this post by Google](https://developer.chrome.com/en/docs/privacy-sandbox/storage-partitioning/). 

This is a recent, and very visible, example of a broader trend with browser vendors making changes to how browser engines work in order to prevent unsanctioned tracking of users across the web - which will also impact access experiences on the scholarly web. This has been covered in several earlier SeamlessAccess presentations and blog posts (see e.g. [this blog post from July](https://seamlessaccess.org/posts/2023-07-07-fedcm-update/) and references therein).


<h2>What to do about it?</h2>

**There is a temporary solution to continue third-party cookie support for Chrome users.** This is said to be supported until September 2024.

The solution is presented by Google as a set of instructions for the user and for the service provider. As a user, you can toggle off Storage Partitioning in Chrome (version 118 or higher):

* Type 'chrome://flags/#third-party-storage-partitioning' into your browser's address bar (note: start with 'chrome:', not 'http:' or 'www ' as you would normally do)
* **Disable** the "Third-party Storage Partitioning" flag.

(More information can be found [here](https://developer.chrome.com/en/docs/privacy-sandbox/storage-partitioning/))

As a service provider, you can follow [this guide](https://developer.chrome.com/en/blog/storage-partitioning-deprecation-trial/) to enable a (temporary) solution.  




<h2>Background</h2>

For a number of years, the tech industry has been targeting third-party cookies. This is part of a broader push towards a more user privacy-friendly web, with browser vendors using the tools at their disposal to progressively make their browsers more respectful of the user’s privacy.

For many years the browser highlighted how cookies are stored and used and made it possible for the user to **opt out** of third party cookie use. In the last couple years, several browsers have set third-party cookie support to **opt in**. The most recent to follow this path is Google Chrome which, in its latest build, requires the user to effectively opt in for third-party cookies to be stored and used.

To be clear, the opt-in pattern means that the browser will not support third-party cookies unless the user explicitly  configures the browser to do so. And, even for users who want their browser to support third-party cookies, this is not always an easy thing to do. 
To understand why all this matters to SeamlessAccess, Let's talk about how SeamlessAccess uses these cookies to create a ‘smart’ access button. 




<h2>The smart button - presenting an actionable option</h2>

SeamlessAccess is a discovery service* with extra everything: Easy to set up and start using on the service side, a standard version that's great out of the box and support for customisation where needed, an accessible interface (WCAG 2.x) with an emphasis on user-friendly flows proven through extensive user testing.

_*) beyond the actual service, we are also very much involved with the community and industry as a whole to make sure our user base login is covered also in the future_.

Part of what makes the federated user access journey so appealing through the SeamlessAccess service is that we're able to populate the SeamlessAccess button with the user's last used identity provider. This looks something like "Access through SUNET" (SUNET being an example of an Identity Provider that will be recognized by its users) - which immediately makes the button recognizable and trusted. If, on the other hand, no previous choice was made the button instead displays "Access through your institution".

<img src="/posts/buttons.png" width="720" />

Because of how we are displaying the user's identity provider in the button, and thus on the frontpage of many scholarly online resources,  the button is immediately recognizable, clear and actionable for the end-user.

Up until now we've even been able to populate the Access button with e.g. "Access through SUNET" even the first time a user visits a new website. How? Through the use of a specific third-party cookie that was set by another website using SeamlessAccess - the same type of cookie that is now being targeted for deprecation.

Note that this does _not_ mean that SeamlessAccess is not respectful of the user's privacy - quite the opposite! SeamlessAccess uses this type of cookie in a very user-privacy friendly manner: the fact that the user has a cookie from "SeamlessAccess" only means that they have at some point used a service that integrates with SeamlessAccess as a federated discovery service, but it does not point back to any service in particular; it could be any number of the hundreds of services (or even thousands; we specifically don't track exactly where SeamlessAccess is used). And SeamlessAccess does not track anything about how the cookie or the service is used. In fact, it could well be argued that, if instead of a single third-party cookie we would use first-party cookies to save the user’s previously visited sites and services in the users browser, then the use of our service would leave a trail in the browser which someone could read and figure out which services the user has accessed - which would clearly be a much greater breach of privacy.

In summary, SeamlessAccess has taken the appropriate route to preserve user privacy while enabling a user friendly access journey. However, because the same technology is used to track users in other use cases we are seeing the kind of impact that is described here on the SeamlessAccess button.


<h2>In conclusion...</h2>

This means (at least for now) that, going forward, the SeamlessAccess button will behave in one of three ways:

1. It displays the users previous identity provider inside the button, e.g. "Access through SUNET" even if it's the first time a user is visiting that service.
2. It only displays the identity provider inside the button if the user has previously visited that site and chose an identity provider, i.e. "Access through your institution" the first time and thereafter e.g. "Access through SUNET".
3. The button does not display the previous identity provider choice, i.e. it will always show "Access through your institution".

These behaviours are dependent on browser, browser version, browser engine and specific user and service settings - which means that it won't always be obvious to the user (or to someone running a service) why a specific type of behaviour is observed. **However, if your browser since recently is presenting the SeamlessAccess button differently then what you are used to, it might be because a recent upgrade is now blocking SeamlessAccess from accessing its cookie!**

As communicated in presentations and blog posts before, we are working with browser vendors and the industry at large to future-proof SeamlessAccess.

<h2>Links about the future of third party cookies, and option to opt-in for Chrome</h2>

As previously mentioned, many browsers already use opt-in for third party cookies, and we've talked about them in previous blog posts and videos (see e.g. [this blog post from July](https://seamlessaccess.org/posts/2023-07-07-fedcm-update/) and references therein). So here is the latest change, which is for Chrome.


<h3>Google Chrome </h3>

* _"To prevent certain types of side-channel cross-site tracking, Chrome is partitioning storage and communications APIs in third-party contexts."_ - describes how the user can enable and disable Storage partitioning (i.e. third party cookie support):
https://developer.chrome.com/en/docs/privacy-sandbox/storage-partitioning/ 

* _"Preparing for the end of third-party cookies"_: https://developer.chrome.com/blog/cookie-countdown-2023oct/

* _"Storage partitioning"_ enabled by default since Chrome 117/118: https://developer.chrome.com/en/docs/privacy-sandbox/storage-partitioning/ 

* _"Participate in deprecation trial for unpartitioned third-party storage, Service Workers, and Communication APIs"_: https://developer.chrome.com/en/blog/storage-partitioning-deprecation-trial/ 





**We will continue to post updates, so please check our website regularly or subscribe to our [mailing list](https://seamlessaccess.org/contact/).**

_(shout-out to the colleagues at Atypon for providing the links to the recent Google changes)_
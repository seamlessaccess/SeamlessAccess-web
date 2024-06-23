---
layout: post
title: 'Web browsers, privacy, and federated identity'
date: 2021-07-06
categories: [General]
hero: true
heroHeading: 'Web browsers, privacy, and federated identity'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---

# Web browsers, privacy, and federated identity

> _Dr. Jane Smith is a postdoc at a major research institution. Overnight, 
> she upgraded her Apple Macbook to the latest version 
> of Apple’s MacOS.  While in her lab she powers up her Macbook
>  and connects to the campus WiFi network.  She reads an email 
> from a colleague containing a link to a recently published 
> journal article.  She clicks the link, which launches the 
> Safari browser on her Macbook, but receives a message from the 
> publisher’s website saying she doesn’t have access to the 
> article.  Strange.  She browses to a journal on another 
> publisher’s website that she reads on a regular basis, and also 
> finds she doesn’t have access.  Really strange.  She asks a 
> colleague in the lab if he is having trouble accessing journal 
> articles.  Access from his Windows laptop is working just fine._
 
This scenario could begin to happen at campuses across the globe in the not-so-distant future.  Browser vendors are beginning to signal changes they plan to make that will bolster privacy but could also cause unintended disruption.  On June 7, 2021 during Apple’s WWDC conference, Apple [announced](https://www.apple.com/newsroom/2021/06/apple-advances-its-privacy-leadership-with-ios-15-ipados-15-macos-monterey-and-watchos-8/) that subscribers to their iCloud+ service will have their IP address obfuscated from website operators.  This is a strong signal regarding Apple’s thoughts on how to protect privacy, and this kind of feature will almost certainly make its way to the rest of Apple’s products (like Safari). While Apple is making this move (and others) to protect user privacy, for an industry that has leveraged IP address recognition as the predominant means of authorizing access to scholarly resources, the potential for unintended disruption is massive.

Even more recently, [Google](https://www.cnet.com/news/google-delays-chromes-cookie-blocking-privacy-plan-by-nearly-2-years/) has recommitted to removing support for third-party cookies in 2023. While that is a delay from their original timeline, again we’re seeing browser vendors move in the direction of supporting consumer privacy, potentially at the expense of other legitimate use cases.

Services like SeamlessAccess and even the underlying [federated authentication](https://seamlessaccess.org/learning-center/) infrastructure utilize various means of exchanging information across website operators.  The significant challenge the browser vendors face is trying to distinguish between legitimate use cases and those that are more suspect.  The browser vendors would all likely agree that exchanging information among trusted third parties for the purpose of facilitating access to scientific and scholarly resources is quite different from tracking users' website visits for the purpose of facilitating targeted advertising.  However, both of these situations use the same underlying features.

It’s important to note that some of the potential changes under discussion could disrupt usage patterns in common use today.  Over twenty years ago, IT architects and visionaries put together ideas for single sign-on (SSO) services that now span the Internet. They developed the Security Assertion Markup Language (SAML) and began organizing the other various systems components to make SSO function. As mobile devices became more prevalent, the limits of SAML led people to develop OAuth, and from there, OpenID Connect. (If you’ve logged into a website using your Google account, you’ve used OpenID Connect.) And, through all of this innovation and development, the most common medium for users to log in and access services and content was via the World Wide Web.

SSO services that use a third-party's account information are known as "federated." An individual's federated identity is their identity information, hosted at one organization like their school, employer, or favorite social media service. Federated identity is used by various service providers to let a user login without creating a new account. The benefits to this arrangement include fewer passwords for a user to keep track of, improved privacy when the user does not need to offer personal information to create an account, and fewer ways for a hacker to compromise service providers.  If the service provider doesn't store the password, the password can't be hacked through their systems. Federated authentication also supports an additional benefit of allowing for granular release of information about the user (i.e., this site gets this information about the user, while that site gets different information), which, if used properly, can add to privacy and anonymity of the user.

Several pieces of functionality in web browsers enable the features that support federated single sign-on. One of those features are browser cookies. Cookies come in various types, but what they all have in common is that they put a small bit of data in a user's web browser. That data can serve many different purposes: it can let a site know whether or not a user is logged in, it can be used to store information that will allow a service to personalize services in some manner, and, most infamously, it can be used to track what sites a user visits as they surf the web. That last part is how digital advertising networks collect (sometimes personal) information about users to deliver targeted ads. From the browser's perspective, though, one cookie looks just like the next. The browser cannot tell the difference between a cookie that lets a service know the user is authenticated from a cookie that allows an advertiser network to track a user around the web. That's a problem when cookies come under fire because of their role in user tracking.

As the world becomes more aware of and concerned with the privacy implications of engaging on the web, and as legislation like GDPR come into effect, browser vendors like Google (Chrome), Apple (Safari), and Mozilla (Firefox) are trying to figure out how to protect user privacy (e.g. by preventing hidden tracking, obfuscating IP addresses, etc.) while also supporting legitimate use cases like federated single sign on.. Since the tools used by both are technically the same, this is a tricky problem to solve! SeamlessAccess, which does not use third-party cookies and does not track a user in any way, relies on information written into the browser’s storage to streamline the Identity Provider Discovery step in federated authentication. Services like this will also break as browsers restrict sites to reading only the information they themselves have written into the browser’s local storage.

Some browser vendors have already taken steps to block third-party access to information in the browser’s local storage. Apple's Safari is at the forefront of blocking hidden tracking. But as a result, Safari and other browsers running on iOS and iPadOS are also platforms where services like Microsoft Teams just won't work anymore. Mozilla's Firefox has partly implemented the limits on third-party cookies but is actively looking for ways to do this more efficiently. And Google is actively developing their Privacy Sandbox but has realized that deprecating third-party access without a plan for federated single sign-on is a problem and may even open them up to [anti-trust lawsuits](https://arstechnica.com/tech-policy/2021/06/eu-antitrust-regulators-launch-probe-into-googles-floc-plan/). As the different vendors diverge on how they support what has been basic functionality on the web, there is a potential for users to be restricted to services only working with a specific browser vendor and their ecosystem. 

Several proposals are being explored as potential ways to preserve federated single sign-on while preventing hidden tracking. Still, for right now, they are all just proposals. No one has a solution at hand, not even (or perhaps especially) not the browser vendors themselves. Since there is no solution ready outside of prototypes, the question of when third-party cookies will go the way of the Flash protocol is still open. A new community group in the W3C is forming to consider this challenge in depth - stay tuned to learn more about what happens from here. 

SeamlessAccess is monitoring these developments closely and is seeking to provide a vehicle for our community to engage in these issues, since they will have a big impact on libraries, publishers, and anyone else who uses federated identity on the web. 

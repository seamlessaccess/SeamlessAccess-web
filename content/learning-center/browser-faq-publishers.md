---
title: 'FAQ on Browser Privacy Changes for Publishers'
date: 2023-02-09T11:58:54+10:00
featured: true
draft: false
weight: 1
heroHeading: 'FAQ on Browser Privacy Changes for Publishers'
heroSubHeading: ''
heroBackground: 'learning-center/hero_theservices.jpg'
---

This FAQ is intended for product managers, developers, technology staff and others with an interest in access methods within academic publishing organisations. 


# Questions:

- [Question 1: What is this “changes to browser technology” issue?](#question-1-what-is-this-changes-to-browser-technology-issue)
- [Question 2: Who is doing this?](#question-2-who-is-doing-this)
- [Question 3: Why are the vendors doing this? Why is this happening?](#question-3-why-are-the-vendors-doing-this-why-is-this-happening)
- [Question 4: When is this happening?](#question-4-when-is-this-happening)
- [Question 5: Will these changes impact IP-based authentication?](#question-5-will-these-changes-impact-ip-based-authentication)
- [Question 6: Will these changes impact federated authentication?](#question-6-will-these-changes-impact-federated-authentication)
- [Question 7: ... and SeamlessAccess?](#question-7--and-seamlessaccess)
- [Question 8: How will I know if my users are encountering this browser issue?](#question-8-how-will-i-know-if-my-users-are-encountering-this-browser-issue)
- [Question 9: Which software and browsers are affected?](#question-9-which-software-and-browsers-are-affected)
- [Question 10: Why now, why this change? And why make access more difficult?](#question-10-why-now-why-this-change-and-why-make-access-more-difficult)
- [Question 11: How are users tracked in a browser?](#question-11-how-are-users-tracked-in-a-browser)
- [Question 12: Is this impacting only scholarly resources?](#question-12-is-this-impacting-only-scholarly-resources)
- [Question 13: What is SAML-based federated authentication?](#question-13-what-is-saml-based-federated-authentication)
- [Question 14: What can publishers do about this?](#question-14-what-can-publishers-do-about-this)
- [Question 15: Where can I learn more?](#question-15-where-can-i-learn-more)
- [Question 16: This FAQ is interesting. I have questions or would like to share my thoughts. How can I do that?](#question-16-this-faq-is-interesting-i-have-questions-or-would-like-to-share-my-thoughts-how-can-i-do-that)



## Question 1: What is this “changes to browser technology” issue?

**Answer 1:** Browser vendors are making progress on plans that will bolster user privacy but are very likely to have a significant impact on technology that is currently widely used by researchers to access online content such as journal articles and monographs. Access technologies that are likely to be impacted include IP-based authentication, which is widely being used today, and cross-origin cookies (also known as third-party cookies).

## Question 2: Who is doing this?

**Answer 2:** AAll major browser vendors (Apple, Google, and Mozilla being the top three) are working towards their interpretation of a more privacy-preserving web experience. That said, Apple, via their Safari browser as well as any other browser on their mobile device operating systems, is currently at the forefront of these changes. The changes that Apple and the other browser vendors are making are global in reach and impact and are much broader than the scholarly web; there is no one government, company, or sector that controls these changes.


## Question 3: Why are the vendors doing this? Why is this happening?

**Answer 3:** Companies like Apple (Safari browser), Google (Chrome browser) and Mozilla (Firefox browser) are responding to various policies and regulations like the General Data Protection Regulation (GDPR) and others around the world regarding the protection of user privacy. These policies and regulations impact all possible ways an individual may be tracked across the web, including via their IP address and through information written into the browser’s local storage. For an industry like scholarly publishers and vendors, the IP address is recognized and leveraged as the common means of authorizing access to scholarly resources. Thus, there is the potential for unintended but massive disruption as the technology underlying web browsers will be subject to substantial changes.

## Question 4: When is this happening?

**Answer 4:** It is, unfortunately, very hard to get details on exact changes and timelines (or possible alternative implementations) from the companies that develop these browser engines. What we know is that these developments started in 2017 with Apple and Safari blocking cross-origin cookies by default. By July 2021, in certain circumstances, Apple began to obfuscate IP addresses. Google on the other hand, made their initial plan to block cross-origin cookies in 2019 but have delayed the universal implementation of the most significant of these changes until 2024.



## Question 5: Will these changes impact IP-based authentication?

**Answer 5:** One of the changes that we expect to see is that browsers may start to hide or obfuscate the user’s IP address. This will make it impossible for websites, such as a publishing platform, to detect the user’s IP address and authorize their access on this basis.
Apple, via their Safari browser as well as any other browser on their mobile device operating systems, is currently at the forefront of these changes. For example, iCloud+ implements [iCloud Private Relay](https://www.apple.com/newsroom/2021/06/apple-advances-its-privacy-leadership-with-ios-15-ipados-15-macos-monterey-and-watchos-8/), which hides the user’s IP address, by default.



## Question 6: Will these changes impact federated authentication? 

**Answer 6:** It is impossible to answer this question with certainty given that we don’t know exactly which changes browser vendors will implement. However, it is expected that the core functionalities of (SAML-based) federated authentication will continue to be supported, making the implementation and support for this mechanism the best long-term strategy that we know of. Certain functionality from OpenID Connect services (e.g., login with Google) will be impacted sooner as actions like front-channel logout uses cross-origin cookies.


## Question 7: … and SeamlessAccess?

**Answer 7:** SeamlessAccess does not replace federated authentication, but it adds a layer of functionality and guidelines that make federated authentication much easier to use for researchers and other end-users. The good news is that SeamlessAccess’ UX guidelines and central IdP discovery service (which researchers can use to easily find their home institute) are not expected to be affected, preserving the core access journey from a functional point of way.

This is less certain for features, in use today, that enable publishers and other Service Providers to tightly integrate SeamlessAccess into their platforms to streamline the user’s access journey. The reason for this is that such integrations require access to cross-origin information, which will likely become impossible by changes to browser technology. To be clear: If that happens, users can still use SeamlessAccess but their user experience will be degraded compared to today. For example, the SeamlessAccess call-to-action button reads the user’s browser local storage for information on what identity provider (IdP) the user has chosen in the past. If the information exists and is readable, then the button populates itself with the name of the last institution the user chose (no other information is stored about the user). As support for cross-origin data is removed by browser vendors, SeamlessAccess will no longer be able to populate the button on the website of the integrating party. Today, this limited behavior, where the button does not populate with the user’s choice of IdP, is visible in Safari. As other browser vendors increase the restrictions on cross-origin data, they will also find themselves limited in terms of what the call-to-action button will do. The experience will vary depending on how exactly the publisher has implemented their integration with SeamlessAccess.



## Question 8: How will I know if my users are encountering this browser issue?

**Answer 8:** Users may try to access content online and find their access restricted even though they are entitled to the content; the actual error message will vary depending on the publisher and/or campus network configuration. This is a key indicator that the issue may be an “access remote content issue” originating from a browser change for protecting user privacy.



## Question 9: Which software and browsers are affected?

**Answer 9:** The software that is affected by blocking or reducing access to third-party cookies currently includes: Web browsers on iOS or iPadOS (including Safari, Chrome, and others), Safari 15 on MacOS Apple for iCloud+ Plus subscribers, and Mozilla Firefox.  \[*Note that this is subject to
change as new versions of the popular web browsers are released*.\].

If users are using Safari or are iCloud+ subscriber, their browser may be blocking access to content already: On June 7, 2021 during Apple’s Worldwide Developers Conference (WWDC) conference, Apple announced that subscribers to their iCloud+ service will have their IP address obfuscated from website operators. This is a strong signal regarding Apple’s thoughts on how to protect privacy, and this kind of feature will almost certainly make its way to the rest of Apple’s products (like Safari).




## Question 10: Why now, why this change? And why make access more difficult?

**Answer 10:** All the browser vendors feel they must prevent unsanctioned tracking of users across the Internet. Countries and regions are holding browser vendors accountable and browser vendors are trying to respond to the criticisms. This is part of a larger Internet trend towards protecting user privacy and identifying and removing all the ways the user can be tracked, including IP addresses, cross-origin cookies, and more.

While these changes were never meant to impact how users access scholarly content or other resources on the web, they will have a big impact on researcher access. This is because very similar technologies are used for tracking users and for providing access to scholarly resources – and the browser is not able to tell the difference between a website asking for a user’s IP address as part of unsanctioned user tracking or because of them seeking access to a scholarly publication. It is worth noting that IP authentication was never intentionally meant to be used for scholarly access the way that it currently is used; IP authentication was just so easy and effective for scholarly access that it became a de-facto standard and libraries, publishers and vendors have not moved on to other more privacy-preserving access methods. In contrast, many other industries have come to rely on single sign-on or other SAML methods and do not depend on IP-based authorization.

Similarly for federated authentication, there are several pieces of functionality in web browsers that enable this. These include browser cookies and other information written into browser local storage. Cookies come in various types, but what they all have in common is that they put a small bit of data in a user’s web browser. That data can serve many different purposes: it can let a site know whether or not a user is logged in, it can be used to store information that will allow a service to personalize services in some manner, and, most infamously, it can be used to track what sites a user visits as they surf the web.

From the browser’s perspective, though, one cookie looks just like the next. The browser cannot tell the difference between a cookie that lets a service know the user is authenticated from a cookie that allows an advertiser network to track a user around the web. The sticking point is not that the information is written into the browser, but whether or not there are restrictions on what sites can then read that information. If any site can read the information in the browser, that’s known as cross-origin information. This is functionality that enables that advertising services that track a user across the web but that also supports logins to companies that have more than one domain name (e.g., microsoft.com and sharepoint.com are both Microsoft domains), and services like SeamlessAccess that improve the access experience for users using federated access.


## Question 11: How are users tracked in a browser?

**Answer 11:** A user can be tracked via a variety of mechanisms. Individually, cross-origin cookies and IP addresses are one simple way to track a user, and so are on the short list for browser vendors to remediate. More complicated, but not uncommon, is something called “browser fingerprinting” - the fonts, plug-ins, add-ons, browser version, IP address, and so on form a remarkably unique method of identifying a specific user.

There are other ways involving even more complicated technologies such as [bounce tracking](https://www.fastcompany.com/90663878/bounce-tracking-privacy-browsers-brave-firefox-safari-edge) and [link decoration](https://digiday.com/marketing/wtf-link-decoration/); these mechanisms are also heavily used by authentication and authorization protocols as well as by trackers, and so will take longer for the browser vendors to figure out how to remediate.


## Question 12: Is this impacting only scholarly resources?

**Answer 12:** The changes underway definitely impact scholarly resources, but they also impact all other resources on the web. However, there may be a disproportionate impact on scholarly resources, as most other consumer or industry vendor access methods stopped using IP authentication a long time ago. For example, many other industries including the payments industry, large-scale CRM businesses, and various software-as-a-service applications, have come to rely on single sign-on or other SAML methods and do not depend on IP-based authorization.


## Question 13: What is SAML-based federated authentication?

**Answer 13:** Many organisations in higher education and research use SAML and do not depend on IP address or cross-origin cookies to provide users with access. SAML stands for “Security Assertion Markup Language,” an open standard that allows identity providers (IdP) to pass authorization credentials to service providers (SP). What that jargon means is that users can use one set of credentials to log into many different websites. It’s much simpler to manage one login per user than it is to manage separate logins to email, customer relationship management (CRM) software, Active Directory, etc. SAML transactions use Extensible Markup Language (XML) for standardized communications between the identity provider and service providers. SAML is the link between the authentication of a user’s identity and the authorization to use a service.

SAML-based federated authentication is a well-established remote authentication mechanism, and there are many vendors and consultants available to assist with implementing it for your environment.


## Question 14: What can publishers do about this?

**Answer 14:** Right now, there are few good answers. To provide users that cannot access content that they are entitled to with immediate support, publishers can suggest that the user switches to a different browser or disable Private Relay on Apple devices.

For a more durable solution, publishers should intensify conversations with libraries and other stakeholders and review access methods, where SAML-based federated authentication would be the best long-term strategy that we know of. Other mitigations may be developed over time as more organizations engage in developing the standards for browser behavior, though it is highly unlikely that IP address authorization will be re-enabled by browser vendors.


## Question 15: Where can I learn more?

 **Answer 15:** Here are some other resources that may be helpful:

* Access Apocalypse: Be Prepared for Anything (NISO+ conference, [YouTube video](https://www.youtube.com/watch?v=NQNQ_sRPzHc))
* Web browsers, privacy, and your publishing platform webinar (STM, [webinar](https://www.stm-assoc.org/events/web-browsers-privacy-and-your-publishing-platform-webinar/))
* Web browsers, privacy, and federated identity (SeamlessAccess, [blog post](https://seamlessaccess.org/posts/2021-07-06-browserchanges/))
* Federated Identity Community Group (W3C, [community group](https://www.w3.org/community/fed-id/))



## Question 16: This FAQ is interesting. I have questions or would like to share my thoughts. How can I do that?

**Answer 16:** To get started, please review the information, blog and Learning Center on the SeamlessAccess website [https://seamlessaccess.org/](https://seamlessaccess.org/). Sign-up to the SeamlessAccess mailing list on the home page to stay informed of developments. Unfortunately, SeamlessAccess does not have resources to provide 1:1 support but we highly recommend talking with colleagues, your IT department, libraries, and vendors. 

It may also be useful to know that SeamlessAccess as an organization is currently working in an advocacy-role with the major browser vendors. It is “advocating” for the needs of the publishers, libraries, and other service providers in the scholarly communications ecosystem to help browser vendors understand the unique needs regarding access to scholarly resources.


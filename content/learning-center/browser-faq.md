---
title: 'FAQ on Browser Privacy Changes and Library Resource Access'
date: 2021-04-21T11:58:54+10:00
featured: true
draft: false
weight: 1
heroHeading: 'FAQ on Browser Privacy Changes and Library Resource Access'
heroSubHeading: '(Or Why Your IP Authentication is About to Break)'
heroBackground: 'learning-center/hero_theservices.jpg'
---

This FAQ is intended for librarians and IT departments. It will also be
useful for librarians communicating with their end-users, whether that
is a student, faculty, or practitioner of any kind. It is intended for
the scholarly library ecosystem to advise, explain, and provide some
suggestions on how to recognize if an access issue stems from this
specific browser problem. This FAQ can also be helpful when working with
technical staff to problem-solve a solution for your library and
institutional needs. When you hear a patron say, “*I can’t access this
content*,” we hope this FAQ may provide clues for you to use, to either
rule this issue “in” as the cause; or, to rule it “out.” It is a sneaky
thing, this browser problem.
[<u>https://seamlessaccess.org/posts/2021-07-06-browserchanges/</u>](https://seamlessaccess.org/posts/2021-07-06-browserchanges/)

# Questions:

- [Question 1: What is this “accessing remote content” issue?](#question-1-what-is-this-accessing-remote-content-issue)
- [Question 2: Who is doing this?](#question-2-who-is-doing-this)
- [Question 3: Why are the vendors doing this? Why is this happening?](#question-3-why-are-the-vendors-doing-this-why-is-this-happening)
- [Question 4: Will these changes impact federated authentication?](#question-4-will-these-changes-impact-federated-authentication)
- [Question 5: How will I know if my library and my users have encountered this browser issue?](#question-5-how-will-i-know-if-my-library-and-my-users-have-encountered-this-browser-issue)
- [Question 6: What browsers are affected now?](#question-6-what-browsers-are-affected-now)
- [Question 7: My user is using Safari and I am using Chrome, and they can’t access the article and I can. Why?](#question-7-my-user-is-using-safari-and-i-am-using-chrome-and-they-can-t-access-the-article-and-i-can-why)
- [Question 8: What devices and operating systems are affected?](#question-8-what-devices-and-operating-systems-are-affected)
- [Question 9: Why now, why this change?](#question-9-why-now-why-this-change)
- [Question 10: When did this trend and impact start?](#question-10-when-did-this-trend-and-impact-start)
- [Question 11: How are users tracked in a browser?](#question-11-how-are-users-tracked-in-a-browser)
- [Question 12: When might a user find browser access issues? E.g. the “remote access issues”](#question-12-when-might-a-user-find-browser-access-issues-eg-the-remote-access-issues)
- [Question 13: Will this impact SeamlessAccess?](#question-13-will-this-impact-seamlessaccess)
- [Question 14: Is this impacting only scholarly resources?](#question-14-is-this-impacting-only-scholarly-resources)
- [Question 15: What is the solution for my library? Will federated authentication be needed for my library and resource access?](#question-15-what-is-the-solution-for-my-library-will-federated-authentication-be-needed-for-my-library-and-resource-access)
- [Question 16: What other solutions are there I could consider for my library and discuss with my IT department?](#question-16-what-other-solutions-are-there-i-could-consider-for-my-library-and-discuss-with-my-it-department)
- [Question 17: What do librarians need to do about this?](#question-17-what-do-librarians-need-to-do-about-this)
- [Question 18: Will this last, what is the future of this trend?](#question-18-will-this-last-what-is-the-future-of-this-trend)
- [Question 19: Should I be worried about this for my library and my end-users?](#question-19-should-i-be-worried-about-this-for-my-library-and-my-end-users)
- [Question 20: I do not think I can move to Federated Authentication, what can I do?](#question-20-i-do-not-think-i-can-move-to-federated-authentication-what-can-i-do)
- [Question 21: Are there any immediate solutions my library or campus can take that will allow IP address authorization to continue to work?](#question-21-are-there-any-immediate-solutions-my-library-or-campus-can-take-that-will-allow-ip-address-authorization-to-continue-to-work)
- [Question 22: This FAQ is interesting, and I have questions and would like to share my thoughts. How can I do that?](#question-22-this-faq-is-interesting-and-i-have-questions-and-would-like-to-share-my-thoughts-how-can-i-do-that)


# Answers

## Question 1: What is this “accessing remote content” issue?

* **Answer 1:** Browser vendors are beginning to signal changes they
plan to make that will bolster user privacy but could also cause
unintended disruption when your library end-users access content on the
internet. In short, they will get error messages that prevent them from
accessing content both on and off campus.

## Question 2: Who is doing this?

* **Answer 2:** All major browser vendors (Apple, Google, and Mozilla
being the top three) are working towards their interpretation of a more
privacy-preserving web experience. That said, Apple, via their Safari
browser as well as any other browser on their mobile device operating
systems, is currently at the forefront of these changes. The changes
that Apple and the other browser vendors are making are global in reach
and impact; there is no one government, company, or sector that controls
these changes.

## Question 3: Why are the vendors doing this? Why is this happening?

* **Answer 3:** Companies like Apple (Safari browser), Google (Chrome
browser) and Mozilla (Firefox browser) are responding to various
policies and regulations like the General Data Protection Regulation
(GDPR) and others around the world regarding the protection of user
privacy. These policies and regulations impact all possible ways an
individual may be tracked across the web, including via their IP address
and through information written into the browser’s local storage. For an
industry like scholarly publishers and vendors, the IP address is
recognized and leveraged as the common means of authorizing access to
scholarly resources. Thus, there is the potential for unintended massive
disruption as the browser technology and processes that underpin IP
authentication and SeamlessAccess are changing dramatically.

## Question 4: Will these changes impact federated authentication?

* **Answer 4:** Several pieces of functionality in web browsers enable
the features that support federated authentication. This includes
browser cookies and other information written into browser local
storage. Cookies come in various types, but what they all have in common
is that they put a small bit of data in a user’s web browser. That data
can serve many different purposes: it can let a site know whether or not
a user is logged in, it can be used to store information that will allow
a service to personalize services in some manner, and, most infamously,
it can be used to track what sites a user visits as they surf the web.
From the browser’s perspective, though, one cookie looks just like the
next.  
  
*The browser cannot tell the difference between a cookie that lets a
service know the user is authenticated from a cookie that allows an
advertiser network to track a user around the web.* The sticking point
is not that the information is written into the browser, but whether or
not there are restrictions on what sites can then read that information.
If any site can read the information in the browser, that’s known as
cross-origin information. This is functionality that enables services
like SeamlessAccess, logins to companies that have more than one domain
name (e.g., microsoft.com and sharepoint.com are both Microsoft
domains), and, unfortunately, advertising services that track a user
across the web.

## Question 5: How will I know if my library and my users have encountered this browser issue?

* **Answer 5:** Your user may try to access an article online and find
their access restricted; the actual error message will vary depending on
the publisher and/or campus network configuration. This is a key
indicator that the issue may be an “access remote content issue”
originating from a browser change for protecting user-privacy.

## Question 6: What browsers are affected now?

* **Answer 6:** If your user is using Safari and an iCloud+ subscriber,
the browser may be blocking access to content. On June 7, 2021 during
Apple’s Worldwide Developers Conference (WWDC) conference, Apple
announced that subscribers to their iCloud+ service will have their IP
address obfuscated from website operators. This is a strong signal
regarding Apple’s thoughts on how to protect privacy, and this kind of
feature will almost certainly make its way to the rest of Apple’s
products (like Safari).

## Question 7: My user is using Safari and I am using Chrome, and they can’t access the article and I can. Why?

* **Answer 7:** The user may be running into new privacy protections
that Apple added. Google, with its Chrome browser, has not yet
implemented these protections. Thus you can get to the article and the
user cannot do so.

## Question 8: What devices and operating systems are affected?

* **Answer 8:** The software that is affected includes: Web browsers on
iOS or iPadOS (including Safari, Chrome, and others), Safari 15 on MacOS
Apple for iCloud+ Plus subscribers \[*Note that this is subject to
change as new versions of the popular web browsers are released*.\]

## Question 9: Why now, why this change?

* **Answer 9:** All the browser vendors feel they must prevent
unsanctioned tracking of users across the Internet. Countries and
regions are holding browser vendors accountable and browser vendors are
trying to respond to the criticisms. This is part of a larger Internet
trend towards protecting user privacy and identifying and removing all
the ways the user can be tracked, including IP addresses, cross-origin
cookies, and more. Unfortunately, this directly impacts scholarly work
and access to library resources.

## Question 10: When did this trend and impact start?

* **Answer 10:** This started in March of 2020 with Apple and Safari. By
July 2021, in certain circumstances, Apple began to obfuscate IP
addresses. Google on the other hand, made their initial plan to block
cross-origin cookies in 2019 but have delayed the universal
implementation of the most significant of these changes until 2023.

## Question 11: How are users tracked in a browser? 

* **Answer 11:** A user can be tracked via a variety of mechanisms.
Individually, cross-origin cookies and IP addresses are one simple way
to track a user, and so are on the short list for browser vendors to
remediate. More complicated, but not uncommon, is something called
“browser fingerprinting” - the fonts, plug-ins, add-ons, browser
version, IP address, and so on form a remarkably unique method of
identifying a specific user.  
  
There are other ways involving even more complicated technologies such
as [<u>bounce
tracking</u>](https://www.fastcompany.com/90663878/bounce-tracking-privacy-browsers-brave-firefox-safari-edge)
and [<u>link
decoration</u>](https://digiday.com/marketing/wtf-link-decoration/);
these mechanisms are also heavily used by authentication and
authorization protocols as well as by trackers, and so will take longer
for the browser vendors to figure out how to remediate.

## Question 12: When might a user find browser access issues? E.g. the “remote access issues”

* **Answer 12:** In 2021, users will find these issues when using these
devices with IP authentication to access library resources, such as
online articles, ebooks, databases, and research and learning platforms
from publishers and vendors. Depending on a user’s location on or off
campus, they may encounter different browser behavior.

## Question 13: Will this impact SeamlessAccess?

* **Answer 13:** The SeamlessAccess call-to-action button reads the
user’s browser local storage for information on what identity provider
(IdP) the user has chosen in the past. If the information exists and is
readable, then the button populates itself with the name of the last
institution the user chose (no other information is stored about the
user). As support for cross-origin data is removed by browser vendors,
SeamlessAccess will no longer be able to populate the button. Instead,
the user will have to search for their IdP every time they go to a new
service provider. Today, this limited behavior, where the button does
not populate with the user’s choice of IdP, is visible in Safari. As
other browser vendors increase the restrictions on cross-origin data,
they will also find themselves limited in terms of what the
call-to-action button will do. The experience will vary depending on how
exactly the publisher has implemented their integration with
SeamlessAccess.

## Question 14: Is this impacting only scholarly resources?

* **Answer 14:** The changes underway definitely impact scholarly
resources, but they also impact all other resources on the web. However,
there may be a disproportionate impact on scholarly resources, as most
other consumer or industry vendor access methods stopped using IP
authentication a long time ago. IP authentication was NEVER
intentionally meant to be used for scholarly access the way it currently
is utilized in the scholarly marketplace. Nonetheless, IP authentication
became so easy and effective for scholarly access that libraries,
publishers and vendors have not moved on to other more
privacy-preserving access methods. For example, others use single
sign-on or other SAML methods and do not depend on IP-based
authorization.

## Question 15: What is the solution for my library? Will federated authentication be needed for my library and resource access?

* **Answer 15:** Right now, there are few good answers. Many sites and
services direct users away from the more restrictive browsers such as
Safari, a temporary solution at best. If there is any possibility to
direct your campus and your vendors towards SAML-based federated
authentication, that is the best long-term strategy we know of. Other
mitigations may be developed over time as more organizations engage in
developing the standards for browser behavior, though it is highly
unlikely that IP address authorization will be re-enabled by browser
vendors.

## Question 16: What other solutions are there I could consider for my library and discuss with my IT department?

* **Answer 15:** Many in higher education use SAML and do not depend on
IP address and cross-origin cookies. SAML is “Security Assertion Markup
Language,” an open standard that allows identity providers (IdP) to pass
authorization credentials to service providers (SP). What that jargon
means is that users can use one set of credentials to log into many
different websites. It’s much simpler to manage one login per user than
it is to manage separate logins to email, customer relationship
management (CRM) software, Active Directory, etc. SAML transactions use
Extensible Markup Language (XML) for standardized communications between
the identity provider and service providers. SAML is the link between
the authentication of a user’s identity and the authorization to use a
service.

SAML-based federated authentication is a well-established remote
authentication mechanism, and there are many vendors and consultants
available to assist a campus in implementing it for your environment.

## Question 17: What do librarians need to do about this?

* **Answer 17:** To provide the user with immediate support, Librarians
can suggest that the user switch to a different browser or disable
Private Relay on the Apple device. In the long-term librarians should
start a conversation with organizational stakeholders and start planning
to move away from IP authentication access methods.

To get started librarians should consider sharing this FAQ and the
following two resources with their IT department: 1) Apple announcement
[<u>https://www.apple.com/newsroom/2021/06/apple-advances-its-privacy-leadership-with-ios-15-ipados-15-macos-monterey-and-watchos-8/</u>](https://www.apple.com/newsroom/2021/06/apple-advances-its-privacy-leadership-with-ios-15-ipados-15-macos-monterey-and-watchos-8/)
and 2) SeamlessAccess blog post, “Web browsers, privacy, and federated
identity”
[<u>https://seamlessaccess.org/posts/2021-07-06-browserchanges/</u>](https://seamlessaccess.org/posts/2021-07-06-browserchanges/).
Start a discussion with your IT, your administration, library committee
or others to create awareness and a sense of urgency. Then discuss what
it would take for your library to move to using a ‘federated
authentication’ access method for patrons’ to access your library
resources.

## Question 18: Will this last, what is the future of this trend?

* **Answer 18:** The expectation is that this is just the start of the
IP authorization access issues. This issue is not going away. Librarians
need to be knowledgeable about it to better participate in discussions
and implement possible technological solutions for access to library
resources.

## Question 19: Should I be worried about this for my library and my end-users?

* **Answer 19:** Yes, but talking and learning about it helps! With
enough attention and persistence and administrative support, librarians
can find solutions with their institution, partners, and IT departments.
If you are proactive and knowledgeable about it, you can lessen the
potential negative impact for your library.

## Question 20: I do not think I can move to Federated Authentication, what can I do?

* **Answer 20:** If you do not have the budget or technical ability to
move to federated authentication as a solo library, consider working
with your local consortia or professional group. National and
international organizations also exist that may be able to provide
advice and mind-share on the problems. Examples of such organizations
include: [<u>Educause</u>](https://educause.edu), [<u>ALA
Core</u>](https://www.ala.org/core/), and
[<u>FIM4L</u>](https://www.fim4l.org/). There may be ways that consortia
and these groups can help, advise, and perhaps share costs for federated
authentication and other SAML solutions.

## Question 21: Are there any immediate solutions my library or campus can take that will allow IP address authorization to continue to work?

* **Answer 21:** Apple, currently the leading browser vendor in
enforcing user privacy options such as IP address obfuscation, has
provided instructions for how to prepare, and potentially block, these
changes for any specific network. Please share these instructions with
your campus network administrators:
[<u>https://developer.apple.com/support/prepare-your-network-for-icloud-private-relay/</u>](https://developer.apple.com/support/prepare-your-network-for-icloud-private-relay/)

## Question 22: This FAQ is interesting, and I have questions and would like to share my thoughts. How can I do that?

* **Answer 22:** To get started, please review the information, blog and
Learning Center on the SeamlessAccess website
[<u>https://seamlessaccess.org/</u>](https://seamlessaccess.org/).
Sign-up to the SeamlessAccess mailing list on the home page to stay
informed of developments.  
  
SeamlessAccess does not have resources to provide 1:1 support for
libraries and librarians. We suggest talking with colleagues, your IT
department and vendors. Your various library groups may also be able to
organize further discussions or support.

It may also be useful for your library to know that SeamlessAccess as an
organization is currently working in an advocacy-role with the major
browser vendors. It is “advocating” for the needs of the scholarly
industry, libraries, and service providers to help browser vendors
understand your unique needs regarding access to scholarly resources.

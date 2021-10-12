---
title: 'Acronyms and Terminology'
date: 2021-04-21T11:58:54+10:00
featured: true
draft: false
weight: 1
heroHeading: 'Acronyms and Terminology'
heroBackground: 'learning-center/hero_theservices.jpg'
---

(last updated 12 October 2021)

| Acronym | Term | Definition |
| ---- | ----| ---- |
|  | Attribute | Attributes are used in Federated Authentication to pass extra data about an authenticated user. They are shared by the Identity Provider (IdP) with a Service Provider (SP). The exact format of the attribute depends on the underlying technology, e.g. SAML, OpenID Connect. |
| | Discovery | In the context of federated identity, discovery is the process of discovering a user's IdP.
|   | eduGAIN | An interconnection of identity federations around the world, simplifying access to content, services and resources for the global research and education community. eduGAIN enables the trustworthy exchange of information related to identity, authentication and authorization. |
|   | Entity Category | Entity Categories group federation entities that share common criteria.  The intent is that all entities in a given entity category are obliged to conform to the characteristics set out in the definition of that category. See <https://wiki.refeds.org/display/ENT/Entity-Categories+Home> |
| | Federated Authentication | An authentication process that allows a user to log in with a single ID and password to any of several independent, unrelated, software systems. This is an expansion of the term Single Sign-on (SSO). |
| | Identity Federation, aka “Federation” | An organisation that operates a trust framework for exchange of authentication assertions between its members and/or customers, that are Identity Providers and Service Providers. (Examples: InCommon, OpenAthens, Australian Access Federation) |
| IdP | Identity Provider | A member or a customer of an identity federation that assigns access credentials to qualifying individual natural persons. Typically, Identity Providers are universities, schools and research institutes. |
| IdP Proxy | Identity Provider Proxy | An IdP Proxy is a bridge or gateway between a federation of SAML IdPs and a federation of SAML SPs. To an SP, an IdP Proxy looks like an ordinary IdP. Likewise, to an IdP, an IdP Proxy looks like an SP. Thus an IdP Proxy has the combined capability of both an IdP and SP. A proxy is often used by research collaboration infrastructures. See <https://spaces.at.internet2.edu/display/GS/SAMLIdPProxy> |
| IP Address | Internet Protocol Address | An Internet Protocol address (IP address) is a numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. See <https://en.wikipedia.org/wiki/IP_address> |
| | OAuth | OAuth is an open standard for access delegation. See <https://en.wikipedia.org/wiki/OAuth? |
| |  Online Platform | An Online Platform is a platform through which a Service Provider provides access to resources, such as information resources, scholarly collaboration tools and shared research infrastructure, that requires end users accessing those resources to be reliably authenticated. |
| OIDC | OpenID Connect | OIDC is an identity layer that allows for the verification of an end-user’s identity. It sits on top of the OAuth protocol. See <https://openid.net/connect> |
| | Pseudonymous Identifier | An opaque, unguessable user identifier for use with a specific individual SP. This identifier is unique to the individual at that SP but is not correlatable across multiple SPs. |
| SAML | Security Assertion Markup Language | SAML is an open standard for authentication and authorization. See <https://en.wikipedia.org/wiki/Security_Assertion_Markup_Language> | 
| SP | Service Provider | A provider of resources such as information resources, scholarly collaboration tools and shared research infrastructure, by means of an online platform that requires end users accessing those resources to be reliably authenticated, and that is a member or a customer in good standing of an identity federation and is as such part of the trust framework provided by the identity federation. |
| SSO | Single Sign-On | An authentication process that allows a user to log in with a single ID and password to any of several related, yet independent, software systems. When using the term “SSO” the topic usually describes logging into related yet independent systems within a single organization. When SSO is supported outside a single organization, it becomes federated authentication.| 
| | User |An individual natural person to whom access credentials have been assigned by Identity Providers thereby enabling them to access resources supplied on the online platform of a given Service Provider by means of a log-in or sign-on. Typically, in the case of identity providers that are universities, schools and research institutes, Users are affiliated to those Identity Providers as faculty staff, students, employees or otherwise, and have access to resources of Service Providers for so long as they are so affiliated. |
| UX | User Experience | The User Experience encompasses the entirety of a user's direct interaction with a product or service. See <https://en.wikipedia.org/wiki/User_experience> |
| WAYF | “Where Are You From?” | A WAYF service allows users to identify the Identity Provider (IdP) they will use to authenticate. To minimize the number of times a user must use a WAYF service, a federated authentication system may store the selected IdP in the user’s browser and use it as a default for subsequent WAYF prompts or encode it into a WAYFless URL.|
| | WAYFless URL | A WAYFless URL enables a user from an institution to gain federated access to the service or resource in a way that bypasses the 'Where Are You From' (WAYF) or IdP Discovery Service step.|


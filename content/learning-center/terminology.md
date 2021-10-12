---
title: 'Acronyms and Terminology'
date: 2021-04-21T11:58:54+10:00
featured: true
draft: false
weight: 1
heroHeading: 'Acronyms and Terminology'
heroBackground: 'learning-center/hero_theservices.jpg'
---

<p>(last updated 12 October 2021)</p>
<table style="width:100%">
<colgroup>
<col style="width: 20%" />
<col style="width: 30%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr>
<th>Acronym</th>
<th>Term</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td>Attribute</td>
<td>Attributes are used in Federated Authentication to pass extra data about an authenticated user. They are shared by the Identity Provider (IdP) with a Service Provider (SP). The exact format of the attribute depends on the underlying technology, e.g. SAML, OpenID Connect.</td>
</tr>
<tr class="even">
<td></td>
<td>Discovery</td>
<td>In the context of federated identity, discovery is the process of discovering a user’s IdP.</td>
</tr>
<tr class="odd">
<td></td>
<td>eduGAIN</td>
<td>An interconnection of identity federations around the world, simplifying access to content, services and resources for the global research and education community. eduGAIN enables the trustworthy exchange of information related to identity, authentication and authorization.</td>
</tr>
<tr class="even">
<td></td>
<td>Entity Category</td>
<td>Entity Categories group federation entities that share common criteria. The intent is that all entities in a given entity category are obliged to conform to the characteristics set out in the definition of that category. See <a href="https://wiki.refeds.org/display/ENT/Entity-Categories+Home" class="uri">https://wiki.refeds.org/display/ENT/Entity-Categories+Home</a></td>
</tr>
<tr class="odd">
<td></td>
<td>Federated Authentication</td>
<td>An authentication process that allows a user to log in with a single ID and password to any of several independent, unrelated, software systems. This is an expansion of the term Single Sign-on (SSO).</td>
</tr>
<tr class="even">
<td></td>
<td>Identity Federation, aka “Federation”</td>
<td>An organisation that operates a trust framework for exchange of authentication assertions between its members and/or customers, that are Identity Providers and Service Providers. (Examples: InCommon, OpenAthens, Australian Access Federation)</td>
</tr>
<tr class="odd">
<td>IdP</td>
<td>Identity Provider</td>
<td>A member or a customer of an identity federation that assigns access credentials to qualifying individual natural persons. Typically, Identity Providers are universities, schools and research institutes.</td>
</tr>
<tr class="even">
<td>IdP Proxy</td>
<td>Identity Provider Proxy</td>
<td>An IdP Proxy is a bridge or gateway between a federation of SAML IdPs and a federation of SAML SPs. To an SP, an IdP Proxy looks like an ordinary IdP. Likewise, to an IdP, an IdP Proxy looks like an SP. Thus an IdP Proxy has the combined capability of both an IdP and SP. A proxy is often used by research collaboration infrastructures. See <a href="https://spaces.at.internet2.edu/display/GS/SAMLIdPProxy" class="uri">https://spaces.at.internet2.edu/display/GS/SAMLIdPProxy</a></td>
</tr>
<tr class="odd">
<td>IP Address</td>
<td>Internet Protocol Address</td>
<td>An Internet Protocol address (IP address) is a numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. See <a href="https://en.wikipedia.org/wiki/IP_address" class="uri">https://en.wikipedia.org/wiki/IP_address</a></td>
</tr>
<tr class="even">
<td></td>
<td>OAuth</td>
<td>OAuth is an open standard for access delegation. See &lt;https://en.wikipedia.org/wiki/OAuth?</td>
</tr>
<tr class="odd">
<td></td>
<td>Online Platform</td>
<td>An Online Platform is a platform through which a Service Provider provides access to resources, such as information resources, scholarly collaboration tools and shared research infrastructure, that requires end users accessing those resources to be reliably authenticated.</td>
</tr>
<tr class="even">
<td>OIDC</td>
<td>OpenID Connect</td>
<td>OIDC is an identity layer that allows for the verification of an end-user’s identity. It sits on top of the OAuth protocol. See <a href="https://openid.net/connect" class="uri">https://openid.net/connect</a></td>
</tr>
<tr class="odd">
<td></td>
<td>Pseudonymous Identifier</td>
<td>An opaque, unguessable user identifier for use with a specific individual SP. This identifier is unique to the individual at that SP but is not correlatable across multiple SPs.</td>
</tr>
<tr class="even">
<td>SAML</td>
<td>Security Assertion Markup Language</td>
<td>SAML is an open standard for authentication and authorization. See <a href="https://en.wikipedia.org/wiki/Security_Assertion_Markup_Language" class="uri">https://en.wikipedia.org/wiki/Security_Assertion_Markup_Language</a></td>
</tr>
<tr class="odd">
<td>SP</td>
<td>Service Provider</td>
<td>A provider of resources such as information resources, scholarly collaboration tools and shared research infrastructure, by means of an online platform that requires end users accessing those resources to be reliably authenticated, and that is a member or a customer in good standing of an identity federation and is as such part of the trust framework provided by the identity federation.</td>
</tr>
<tr class="even">
<td>SSO</td>
<td>Single Sign-On</td>
<td>An authentication process that allows a user to log in with a single ID and password to any of several related, yet independent, software systems. When using the term “SSO” the topic usually describes logging into related yet independent systems within a single organization. When SSO is supported outside a single organization, it becomes federated authentication.</td>
</tr>
<tr class="odd">
<td></td>
<td>User</td>
<td>An individual natural person to whom access credentials have been assigned by Identity Providers thereby enabling them to access resources supplied on the online platform of a given Service Provider by means of a log-in or sign-on. Typically, in the case of identity providers that are universities, schools and research institutes, Users are affiliated to those Identity Providers as faculty staff, students, employees or otherwise, and have access to resources of Service Providers for so long as they are so affiliated.</td>
</tr>
<tr class="even">
<td>UX</td>
<td>User Experience</td>
<td>The User Experience encompasses the entirety of a user’s direct interaction with a product or service. See <a href="https://en.wikipedia.org/wiki/User_experience" class="uri">https://en.wikipedia.org/wiki/User_experience</a></td>
</tr>
<tr class="odd">
<td>WAYF</td>
<td>“Where Are You From?”</td>
<td>A WAYF service allows users to identify the Identity Provider (IdP) they will use to authenticate. To minimize the number of times a user must use a WAYF service, a federated authentication system may store the selected IdP in the user’s browser and use it as a default for subsequent WAYF prompts or encode it into a WAYFless URL.</td>
</tr>
<tr class="even">
<td></td>
<td>WAYFless URL</td>
<td>A WAYFless URL enables a user from an institution to gain federated access to the service or resource in a way that bypasses the ‘Where Are You From’ (WAYF) or IdP Discovery Service step.</td>
</tr>
</tbody>
</table>
</body>

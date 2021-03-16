---
layout: post
title: 'Identity Provider Filtering in SeamlessAccess'
date: 2021-03-16
categories: [General]
hero: true
heroHeading: 'Identity Provider Filtering in SeamlessAccess'
heroSubHeading: ''
heroBackground: "images/hero_news.jpg"
---
# Identity Provider Filtering in SeamlessAccess
##Thoughts on architecture

Today SeamlessAccess presents a single view of all the identity providers it knows about - a single set of IdPs is available for searches to whatever SP is calling the discovery service. 

This presents a problem because of the reciprocity problem inherent in how identity federations based on SAML federations work. In this blog post, we will describe the problem and how we propose to solve it.

**The reciprocity problem** means that Identity federations where technical trust is based on public-key signatures of shared configuration information (aka metadata), while highly scalable, suffer from a basic asymmetry of technical trust: **An IdP can choose to trust an SP without any guarantee or even knowledge that the SP will reciprocate and trust the IdP.** This causes a fundamental usability problem; A user may be offered an IdP as a possible login choice that will recognize the SP.

In enterprise deployments, this doesn’t happen because establishing trust between SPs and IdPs is always a manual process that is guaranteed to be reciprocated. This approach does not scale however which is why larger federations for decades have been willing to accept a certain amount of pain resulting from the lack of reciprocity of trust inherent in relying on signed metadata to scale federations.

The obvious solution is to always present the user only with such IdPs, that SP made its service available to. In the classical single-federation case (ie when there are no interfederations in place) this is still pretty easy because the federation operator will typically deploy a discovery service configured using the shared SAML metadata of both IdPs and SPs. 

With interfederations in play, things become a lot more complicated; an SP may or may not be present in a particular interfederation. This information needs to affect the subset of IdPs available to the discovery service. 

A case that is recently affecting many users of SeamlessAccess is that OpenAthens is part of the set of metadata trusted by SeamlessAccess. Some SPs using SeamlessAccess trust OpenAthens (e.g., publishers) and some do not. Because SeamlessAccess can’t tell the difference between these two types of SPs, it will present OpenAthens IdPs even to the users of SPs that do not trust OpenAthens. The result is a very confusing user experience.

Since SeamlessAccess will continue to serve multiple federations we need to be able to present a set of Identity Providers tailored to each SP. A commonly used term of art for the ability to present a tailored set of IdPs to users of a particular SP is to filter the set of IdPs. Filtering implies SP presenting a set of parameters to the SeamlessAccess discovery service that is used to tailor the user experience when presenting IdPs.

There are three basic problems we have to solve when designing filtering for SeamlessAccess:

What parameters/capabilities are needed to express the common use-cases?
How are filtering parameters communicated to the discovery service?
How is filtering signaled to the user?

The user interface is (unsurprisingly) the hardest problem. Usability is a core value for SeamlessAccess and our UX team is working on methods for signaling filtering with the user through UX elements. The major issue is that the trust profile of an SP is often at odds with the expectations of the user. Let’s look at an example to illustrate this:

Kenny from Podunk University typically uses the Podunk University IdP for accessing all his services. As a result, all of Kenny’s browsers have the PU IdP in browser local storage for SeamlessAccess and when visiting SPs, Kenny’s browser always presents his default choice of IdP. 

All is well. 

Unfortunately, PU has not yet implemented MFA (multifactor authentication) and one day Kenny is invited to authenticate to a service that requires MFA. The service is using the new filtering capabilities to signal that only IdPs that are capable of MFA, and are tagged as such in metadata, should be presented to the user. 

The UX challenge, in this case, is this: what should be presented to Kenny? Should the button be empty (appear as non-configured) because the IdP does not belong to the set of permitted IdPs for the SP? Or should it present the next working IdP choice from users' browser local storage? How should the discovery service behave when Kenny nevertheless tries to search for “Podunk University”. Remember that Kenny may not even be aware that the SP in question requires MFA and may be quite surprised (irked even) when Podunk University fails to appear as expected in search results.

The objective of this exercise is to get Kenny to a fallback IdP that supports MFA, or in the worst case to inform Kenny that he won’t be able to authenticate to the SP at all. The thing we want to avoid at all costs is sending Kenny on a frustrating wild goose chase through various helpdesks only to find out that he won’t be able to login that day. We want Kenny to succeed or to fail quickly - and hopefully to understand why.

**The choice of filtering parameters** is the subject of an ongoing dialog within the SeamlessAccess community. We are relying heavily on feedback from federation operators, publishers, and research infrastructure providers (e.g., in the [AEGIS](https://aegisresearch.eu/) community). The basic set of parameters seems to include selecting based on (combinations of):

- federation membership
- explicit listing of IdPs
- capability of the IdP (e.g., by entity attributes)
- source of the federation

Finally **providing filtering parameters to the discovery service** can be done in basically two ways:

1. via the front-channel, by providing filtering parameters in the discovery service protocol request. This is best represented by a proposal from the AEGIS group.
2. via the backchannel, by providing filtering parameters as configuration to the discovery service on a per-SP basis.

Modern web architecture would suggest (1) as an obvious choice - developers typically have no problem calling web-based APIs, especially those that are based on HTTP redirects. 

However most SAML (and OpenID Connect (OIDC)) stacks are hidden from developers and the discovery process is typically not initiated by the application but by the SAML/OIDC stack which is separated from the application and sometimes even running as a separate infrastructure component on a different VM/kernel than the application itself - e.g., part of a TLS concentrator or frontend cluster. 

In the case of commonly used software like Shibboleth, AzureAD, ADFS, SimpleSAMLPHP, or pySAML2 the discovery service is called from deep into the library code; adding parameters for doing filtering is difficult at best and impossible in many situations.

Option (1) is really only fully available to federation proxies where the discovery process is fully under the developer’s control. This represents a relatively small number of deployments and would leave the majority of SPs without a mechanism for filtering IdPs.

On closer scrutiny, other problems with option (1) are revealed: Sending parameters in the front-channel will affect the cache-friendly property of the current application which could have a pretty severe impact on SeamlessAccess scalability and the SeamlessAccess application could probably no longer be delivered entirely as an SPA.

There are related proposals (e.g., from AEGIS) covering issues related to proxies that rely on sending additional parameters via the front-channel that are relatively easy for SeamlessAccess to implement and are strongly being considered for inclusion in the SeamlessAccess filtering roadmap. These proposals are not affected by this argument. We will come back to those and other future directions for SeamlessAccess in other posts.

**Filtering via the backchannel** - option (2) above - means finding some way of conveying filtering parameters for an SP to SeamlessAccess independent of the discovery service request.

Fortunately, there is already a mechanism for providing such configuration information about SPs: SAML metadata. The solution SeamlessAccess is working on currently is to extend SAML metadata with information about which sets of IdPs are trusted by an SP. We are currently working on a specification we hope to present to the SeamlessAccess community and  relevant standards bodies for consideration and in parallel, we are working on an implementation.

A downside of using SAML metadata is that it often takes a long time for SAML metadata extensions to be available in the tooling used by federation operators and that it increases the size of metadata. Our plan is to reduce this pain by providing a mechanism whereby SPs can annotate metadata at SeamlessAccess site (aka, “pixie dusting”).

Our roadmap for filtering looks something like this:

1. Communicate and get feedback from the SeamlessAccess stakeholders on filtering parameters and UX/UI
2. Specify a metadata extension for representing reciprocal trust information that can be used by early adopters
3. Identify and implement a possible extension to MDQ that are needed to effectively communicate filtering to the SeamlessAccess frontend
4. Implement the chosen UX/UI solution for filtering
5. Begin roll-out
6. Provide a pixie-dusting service

---
title: 'Challenges and Recommendations in Federated Where-Are-You-From (WAYF) Services'
date: 2021-04-21T11:58:54+10:00
featured: true
draft: false
weight: 1
heroHeading: 'Challenges in Federated Where-Are-You-From (WAYF) Services'
heroBackground: 'learning-center/hero_theservices.jpg'
---
# Challenges in Federated Where-Are-You-From (WAYF) Services
_Work Product of the SeamlessAccess WAYF Entry Disambiguation Working Group_


## Purpose of this white paper:

-   Describe the problem; set the stage for framing the [recommendations](/learning-center/WAYF-Recommendations.pdf)
-   Clarify terminology

## Target audiences

-   IdP Operators / Campus IT
    -   they need to be aware of the implications of the choices they
        make in their metadata
    -   they need to know that they might not be alone wanting to use
        their institution’s name in WAYF services
-   Librarian IT
    -   they need to be aware of the implications of the choices they
        make in their metadata (using the Metadata Explorer Tool
        (met.refeds.org) may help the librarian see what their
        institution’s metadata looks like to others)
    -   they need to be in close conversation with Campus IT
    -   they need to know how to handle user feedback when there is
        confusion
-   Federation Operators
    -   need to consider how they’re handling metadata from the same
        institution
-   SP Operators
    -   they are the ones sending their users to WAYF
    -   and when they are building their own WAYF, they need to be aware
    -   they need to know how to handle user feedback when there is
        confusion
-   Vendors of IdP Software
    -   encourage vendors to be consistent with what they include in
        metadata such as including DisplayName
    -   support communication with academic identity federations


## Abstract

There are many ways to manage access to remote resources. From the use
of IP addresses via VPN or proxy services to federated identity, the
goal of enabling access to remote content is both easier and more
complicated than ever before. This article focuses on the user
experience with federated identity at the point where users have to
select the institution they want to use to authorize their access. In
particular, we look into the challenges that exist in the
Where-Are-You-From (WAYF) identity provider discovery process when a
user is presented with nearly identical choices for the same
institution.

## Introduction

What is WAYF and why is it important? A user wants to access a resource
and needs to tell it which institution they are from. The user finds
themselves on a WAYF discovery page where they must find their
institution. When the institutional name is clear, they have no problem
selecting the right one from a multitude of other names. When they find
a number of similar names, they are not sure which one to select, they
are likely to select the one that is not their institution and they will
not get access to the resource. The resources get the names they display
from federation metadata.

Federated identity management permits extending Single Sign-On (SSO)
above the enterprise level, creating a trusted authority for digital
identities across multiple organizations. In a federated system,
participating institutions share identity attributes based on
agreed-upon standards, facilitating authentication from other members of
the federation and granting appropriate access to online resources. This
approach streamlines access to digital assets while protecting
restricted resources.

### Terminology

One of the more immediate challenges of federated identity is
understanding the terminology commonly used to describe the different
components that make up the federated identity ecosystem. In this paper,
we use the following terms:

***Identity Provider*** - A member or a customer of an identity
federation that assigns access credentials to qualifying individual
natural persons. Typically, Identity Providers are universities,
schools, and research institutes. This is commonly abbreviated as “IdP.”

-   **Display Name** (identifying the IdP for the user) - The
    user-friendly name registered in federation metadata with an Entity
    ID.

-   **Entity ID** (identifying the IdP for the system) - The name the
    IdP includes in their metadata to identify itself to a federated SSO
    service.

***Service Provider*** - A provider of resources such as information
resources, scholarly collaboration tools, or shared research
infrastructure, by means of an online platform that requires end users
accessing those resources to be reliably authenticated, and that is a
member or a customer in good standing of an identity federation and is
as such part of the trust framework provided by the identity federation.

-   ***Where Are You From (WAYF) service*** (aka, IdP Discovery Service)
    (helps the user to select IdP to login to this Service Provider) - A
    WAYF service allows users to identify the Identity Provider (IdP)
    they will use to authenticate. To minimize the number of times a
    user must use a WAYF service, a federated authentication system may
    store the selected IdP in the user’s browser and use it as a default
    for subsequent WAYF prompts, including another provider’s site, or
    encode it into a WAYFless URL.

***Federation*** (aka, Identity Federation) - An organization that
operates a trust framework for the exchange of authentication assertions
between its members and/or customers, that are Identity Providers and
Service Providers. (Examples: InCommon, OpenAthens, Australian Access
Federation)

***eduGAIN*** - An interconnection of identity federations around the
world, simplifying access to content, services, and resources for the
global research and education community. eduGAIN enables the trustworthy
exchange of information related to identity, authentication, and
authorization.

***IdP Proxy*** - An IdP Proxy is a bridge or gateway between a
federation of SAML IdPs and a federation of SAML SPs. To an SP, an IdP
Proxy looks like an ordinary IdP. Likewise, to an IdP, an IdP Proxy
looks like an SP. Thus an IdP Proxy has the combined capability of both
an IdP and SP. A proxy is often used by research collaboration
infrastructures.

## Problem Space / Use Cases

During the IdP Discovery journey, an end user may encounter what appear
to be identical IdPs in a WAYF service, but in actuality are not. There
are a variety of reasons this might occur, reasons that are technically
correct with understandable business decisions behind them.

<img src="/learning-center/wayf-image1.png" style="width:6.26772in;height:4.68056in" />

*Figure 1: WAYF Entry Conflicts*

This may occur for a variety of reasons

### Reason 1 - Similar Display Names, Multiple Federations

Example: The library has an IdP service registered in OpenAthens with a
similar display name as an IdP service from the campus that is
registered in InCommon; metadata from both federations is included in
the SeamlessAccess metadata aggregate. It is impossible for the user to
distinguish between the Library/OpenAthens and the Campus/InCommon IdP
in the discovery service.

<img src="/learning-center/wayf-image2.png" style="width:2.64271in;height:3.77198in" />

*Figure 2: WAYF results example, similar Display Names across multiple
federations*

One of the more common use cases involves a scenario where a department
within an organization signs up to one federation, while the
organization itself signs up for another federation. This results in a
situation where an institution has two separate IdPs registered with
similar Display Names but different Entity IDs in two separate
federations. When an SP or WAYF service aggregates the metadata from
multiple federations, then both IdPs will be shown in that aggregated
WAYF service.

In some cases, the similarity between the display names is only obvious
to a human. This is particularly the case when the pattern being matched
is a name in English and its direct translation in another language.

While one obvious response is to disallow the aggregation of metadata,
this is not always possible. SPs are often members of more than one
federation, and so will want to display all the IdPs possible from any
federation the SPs have joined. For services like SeamlessAccess, the
more IdPs are represented in the metadata, the more choices are
available to the user. Users are confused when they cannot find their
organization in a WAYF list.

### Reason 2 - Similar Display Names, Same Federation

Example: A campus has a test IdP and a production IdP with the same
entityID (in the same federation). Alternatively, two departments on a
single campus have registered separate IdPs with a federation with
similar Display Names.

<img src="/learning-center/wayf-image3.png" style="width:2.6599in;height:2.49746in" />

*Figure 3: WAYF results example, similar Display Names across a single
federation*

The apparent name conflict does not necessarily have to cross federation
boundaries. Even within a federation, duplications may appear if the
display names are similar but the entity ID is different. This might
happen if two departments register their own IdPs with names like
“University of the Very Long Name - Physics” and “University of the Very
Long Name - Library.” While the example above is clear, the length of
the name may result in the last part being cut off, leaving the user
without enough information to distinguish between the two options.

A similar case can happen when an organization registers a test IdP as
well as a production IdP. If the display names are not obviously
dissimilar, then the user may not be able to recognize which system they
should be using when authenticating.

### Reason 3 - Same EntityID, Multiple Federations

Example: a university has a Shibboleth IdP in InCommon and an OpenAthens
IdP with the same entityID (in different federations). This is often a
part of a planned migration from one IdP to another, but sometimes the
institution does not update the metadata to remove the old IdP. Which
IdP (old or new) is presented to the user will depend on what the SP has
in their metadata; the user will be unable to determine or control if
that is the current IdP for their institution. There are no visible
distinctions when presenting the IdP to the user, and the SP may not be
able to control which IdP is presented to the user. In the example
below, the user will see only one IdP, but it is the older one and will
not work as intended.

<img src="/learning-center/wayf-image4.png" style="width:2.69853in;height:2.01882in" />

*Figure 4: WAYF entry example, same EntityID across multiple
federations*

In previous scenarios, the entity ID was the technically distinguishable
characteristic in all examples. There are situations, however, where the
entity ID remains the same even though the backend system is different.
This may happen when an entity ID registered in one federation points to
a campus IdP, but in another federation, that same entity ID points to
something entirely different. Unfortunately, which IdP is listed in a
WAYF will depend on the SP, which IdP they have in their metadata, and
what order it happens to be displayed to the user. This is often outside
of the SP’s control. The user will also have an inconsistent login
experience because they may see the “wrong” IdP for that particular SP
and not gain access to the content they are entitled to.

### Reason 4 - Similar Display Names, Unrelated Institutions

Example: Boston College in the US, Boston College in the UK.

<img src="/learning-center/wayf-image5.png" style="width:2.46198in;height:3.50941in" />

*Figure 5: WAYF entry example, similar display names for unrelated
institutions*

The challenge of visually similar names in a WAYF is not restricted to
something that happens within one organization. Two unrelated
institutions with similar Display Names may be registered in one or more
federations. While not as common as the scenarios involving confusion
within a single organization, this is definitely something that occurs
today.

### Reason 5 - Shared IdP 

Example: Feide, the Norwegian identity federation, uses interstitial
landing pages to direct the user from the single IdP in eduGAIN to the
IdPs at the federation’s member institutions. Searching for the user’s
IdP may not result in their institution appearing in the list of
options; the only option that will appear is Feide.

<img src="/learning-center/wayf-image6a.png" style="width:3.04in;height:2.67932in" /><img src="/learning-center//wayf-image6b.png" style="width:3.01207in;height:2.6547in" />

*Figure 6: WAYF entry example, shared IdP for multiple institutions*

In some scenarios, organizations will share a common IdP. This may
happen as a result of the complexity of the organization (e.g., a large
hospital system such as the National Health Service \[NHS\] in the
United Kingdom). Alternatively, if a national federation is organized to
offer a single IdP to all its members, as is the case in Norway, this
may display the same characteristic of a common name shared by all
participating institutions.

In the screenshots above, “Oslo” and “Bergen” are both part of the name
of universities in Norway. The Norwegian federation is called “Feide.”
“Bergen Community College” is a community college in the state of New
Jersey, US.

## Wrap Up

There is no clear best practice for preventing visual name collisions
within a WAYF service. These collisions cannot be easily identified by
existing technology; human perception plays an enormous part in how
users understand these Display Names in a WAYF service. The first step,
then, is for the different entities, from IdPs to SPs to federation
operators, to be aware that this problem exists. From there, they can
make a decision that best meets the needs of their particular use case.

The SeamlessAccess WAYF Entry Disambiguation Working Group is focused on
raising awareness of the issues and coming up with short, medium, and
long-term solutions that will offer the needed best practice guidance
for these issues.

**_A PDF copy of the Challenges paper is available for download [here](/learning-center/challenges-federated-WAYF.pdf)._**

# Recommendations to Improve Federated Where-Are-You-From Services

_Developed by the SeamlessAccess WAYF Entry Disambiguation Working Group; if you have questions or comments, please reach out to contact@seamlessaccess.org._

If there are terms in this document that are new to you, we encourage you to look at the [Acronyms and Terminology](https://seamlessaccess.org/learning-center/terminology/) page on the SeamlessAccess website. 



## Introduction
The Where-Are-You-From (WAYF) entry disambiguation problem, where identity provider (IdP) discovery services offer what look like duplicate names to users, is a solvable one. IdPs have several options that will mitigate or even eliminate the problem for users, including adapting their logos, improving the searchable keyword terms, and modifying their display name. Federation operators can also help mitigate this issue by offering standardized guidance for logos and support for keywords in their metadata, as well as supporting a registry for common keywords that should be used as part of the disambiguation process.
This document provides specific, detailed recommendations for every technical option currently available. Additional options, in particular user education, are entirely within the mandate of the organization managing the IdP.

### Understanding the Actions
Each section offers specific guidance for the different stakeholders that are involved in enabling federated access to online content. 

The “Action for the Institution” recommendations offers guidance to whatever person, team, or department manages the IdP, either from a contractual perspective or a technical one. For example, this may be applicable to the library or to campus IT, or possibly both if the campus is running multiple IdPs.

The “Action for the Federation” recommendations offers guidance to federation operators to help them assist their members in avoiding the WAYF entry disambiguation problem. 

In some cases, the WAYF service is itself offered by a third party, at which point the “Action for the IdP Discovery Service” comes into play.

“Action for REFEDS” is a very specific recommendation to the organization, REFEDS, that facilitates the development of best practices in the academic and research federation community. 


## Community Survey
To better understand community awareness of these issues, we identified 64 organizations that might encounter WAYF disambiguation problems as a result of having multiple IdPs registered in federation metadata.  A brief survey was sent in March 2022 to each organization's registered public contacts (a mixture of librarians and IT staff) asking whether they or their users viewed  multiple WAYF entries as a problem and, if so, how they had resolved any user confusion.
The 16 responses that we received to our survey reinforced our understanding that:

1. Libraries are experiencing problems with multiple IdPs.  Twelve respondents recognized multiple WAYF entries as a problem for their users, and ten respondents had received reports from users about multiple entries.
2. Institutional IT departments do not appear to be aware of or engaging with this issue.  We received no responses from IT staff outside the library.
3. There is no shared understanding across the community on how to address these issues.  Seven of the twelve respondents who recognized the problem did not know how to resolve it, and the remainder adopted various approaches including user education and approaching their service provider.
In summary, the results of the survey validated the need for user education around these issues and guidance on best practices for addressing them.


## DisplayName
DisplayName is the user-friendly name registered in federation metadata with an Entity ID. It may be used in an IdP discovery service, in a service catalog, or any other display where a more human-readable name is appropriate. A typical entry looks like this:

<mdui:DisplayName xml:lang="en">Example University</mdui:DisplayName>

Before joining a federation, it is important to search for your domain name (e.g., example.edu) in a tool like the REFEDS Metadata Explorer Tool (MET). If your institution has joined one of the identity federations that provides data to MET, you will see what name(s) is being displayed to users for that IdP. 

When considering what name to include in your DisplayName, note that many users will be going through an IdP discovery service from a mobile device. The number of characters that will display are going to be limited (though the exact limit will depend on the device, the IdP discovery service service, and possibly other factors). So, a DisplayName of “The University of Extended Learning, Experience, and Opportunity - Library” will be less helpful by itself than “UELEO - Library”. What acronym or short name is most commonly used within your institution? That will likely provide the best option for your DisplayName if you need to add department-specific information to the text. 


### Action for the Institution: 
* Check to see if your organization has an IdP registered in a federation. 
* If you are registering a second IdP, make sure the DisplayName is unique and makes sense to your users.
* Make sure your DisplayName fits on a mobile device. 

### Action for the Federation:
* Make sure your members can update their DisplayName



## Metadata User Interface (MDUI) Extensions
SAML metadata is rich with options for improving IdP discovery services. The SAML V2.0 Metadata Extensions for Login and Discovery User Interface, commonly known as the MDUI extensions, includes provisions for informing user interface (UI) elements. From the standard:

“This document defines a set of extensions to metadata that provide information necessary for user agents to present effective user interfaces and, in the case of identity provider discovery, provide for recommendation of appropriate choices to the user.”

DisplayName is one of those elements, as is Logo. Other elements exist, however, that can further assist the user in reaching the appropriate choice of IdP with minimal confusion.

### Description
The MDUI Description includes support for human-readable text, and can include different descriptions in different languages. According to the standard, “this SHOULD include a description of the user community serviced.” For example:

<mdui:Description xml:lang="en">Identity Provider for Example University (https://example.edu/) and Example University Library (https://library.example.edu)</mdui:Description>

IdP descriptions are, currently, very rarely used. Most IdP discovery services do not even attempt to display this field.

#### Action for the Institution:
Include simple, descriptive text regarding what users and/or services your IdP is primarily intended to support (e.g., Identity Provider for %mdui:DisplayName%)

#### Action for the Federation:
If not already in place, add support for Description in your federation’s metadata.

#### Action for the IdP Discovery Service:
When Description is available, display that to the user.

### Keyword
Keywords are another field that is available to help include information that should help the user get to the appropriate IdP. In the MDUI specification, keyword “specifies a list of localized search keywords, tags, categories, or labels that apply to the containing role.” 

Suitable keywords are often challenging to identify, so a registry where the more common keywords appropriate to IdP discovery services would help organizations get started with keywords that shared a common, documented definition.

#### Action for the Institution:
* Prepare a list of keywords (e.g., “library”, “physics”, “law school”) and request they be added to your IdPs metadata entry.
* (When available) Check the MDUI keyword registry to see if suitable, clearly defined keywords exist for your use case.

#### Action for the Federation:
* If not already in place, add support for Keywords in your federation’s metadata.

#### Action for the IdP Discovery Service:
* Make sure your service includes keywords as part of their search function.

#### Action for REFEDS:
* Develop a registry of common keywords with their specific descriptions that institutions may refer to as they develop their keyword lists.


## Logos
Logos can make it easy for users to visually differentiate between organizations that look similar, or potentially between departments within an organization that have separate entity IDs (e.g. library vs general campus).  Although various organizations across our industry have published standards for images, including federations, Research and Education Networks (RENs), and other IdP discovery service providers, the availability of standards (or perhaps the overabundance of standards) has not led to wide scale use of logos.

That said, we strongly recommend the use of logos as a tool for disambiguation. Federations should adopt common standards for their members, specifically:

1. Moving away from raster (pixel-based) image formats to vector image formats that can be resized as needed for the IdP discovery experience without loss of image quality, such as SVG (Scalable Vector Graphics).

2. Transparent backgrounds to allow more flexibility about the use of logo images.

Regarding accessibility concerns, in the absence of image alt text which can be used for disambiguation - which, if it existed, would by definition be used as the main display name of the IdP discovery service result - the use of a logo would be explicitly intended as a visual enhancement rather than a core page element. As such, the alt text for logos of this kind would be intentionally blank or set to be ignored by assistive technologies, as any attempt to provide an alt text value would make the user experience worse, for example by leading to repetition. Where more specific text is available, it should be provided as the main display name for the IdP, so that it’s available universally.

### Action for the Institution:
* Create a logo suitable for use on an IdP discovery service with a height and width, as required by the Metadata User Interface (MDUI) specifications, that will inform the aspect ratio for the vector image.

### Action for the Federation:
* At minimum, request your members use an SVG image on a transparent background. This may require coordination with members’ branding policies.

### Action for the IdP Discovery Service:
* Be prepared to support additional image formats, specifically SVG. 


## WAYFless URLs
When looking specifically at library use cases, WAYFless URLs are an additional option.  WAYFless URLs are links that libraries can request from SPs to allow their users to directly access a content item using federated authentication credentials without having to go through the WAYF process. Not all SPs support these types of URLs, and even for those that do, the librarian must request the URLs.

While WAYFless URLs seem like a very straightforward option, it’s worth noting that these are not useful when individuals are accessing content from the open web and not the library portal or discovery service. 

## Conclusion
The confusing user experience that exists when organizations have seemingly identical names in a WAYF service is more than a technical challenge. It is a communication challenge that reinforces the need for better communication between campus services, such as libraries, and campus IT departments, as well as better communication with users. There are ways that technology can mitigate this confusion, as noted in the above recommendations, but ultimately this is a communications exercise for all parties involved in offering federated services to their users. 


# WAYF Entry Disambiguation Working Group Membership
Tim Lloyd, LibLynx
Albert Wu, InCommon
Ralph Youngen, ACS
Richard Northover, Elsevier
Jason Griffey, NISO
Fredrik Domeij, SWAMID
Meshna Koren, Elsevier
Hong Ma, Loyola University Chicago
Phil Leahy, OpenAthens
Heather Flanagan, SeamlessAccess
Adam Snook, OpenAthens
Amanda Ferrante, EBSCO Information Services
Logan Thomison, Wiley





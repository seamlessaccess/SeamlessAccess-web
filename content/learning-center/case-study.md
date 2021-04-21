---
title: 'Case Study'
date: 2021-04-21T11:58:54+10:00
featured: true
draft: false
weight: 1
heroHeading: 'Case Study'
heroSubHeading: ''
heroBackground: 'learning-center/hero_theservices.jpg'
---

#Case Study

##One library’s journey from IP access to Seamless Access

##Summary
Georgetown University Medical Center Library uses Seamless Access services to deeply integrate library resources into the busy user’s workflow.

##Challenge
[Dahlgren Memorial Library](https://dml.georgetown.edu/) (DML) is the Graduate Health and Life Sciences Research Library for the Georgetown University Medical Center (GUMC). Our collections are 99% electronic.

Our library serves graduate students, staff and faculty in medicine, nursing and biomedicine as well as the physicians, staff and researchers in one hospital of a large health system and a cancer center. In total this works out to about 40% of the total University FTE.
In 2016, library administration identified long term goals for resource management and access:

* stronger security  
* access entitlement determined by the user identity than location
* usage statistics that included demographic data
* select subscriptions for targeted users only
* better integration of resources within the clinical/research workflow

By moving from IP access to Federated Authentication for medical library resources we felt these goals could be achieved.

##Solutions
###Working with other stakeholders
After obtaining approval from the Medical Center leadership team to move to a federated authentication system for library resource access,  we were able to get started with the implementation.  The resources staff at DML worked with the Georgetown University Information Systems (UIS) department to identify the solution. We chose OpenAthens federated authentication system, provided by TDNet.

OpenAthens allows resource access based on the user’s university department affiliation and not on their location within the campus or proxy IP address.  Federated access provides a higher level of security as access is tied into a specific users account. So any inappropriate use can quickly be traced back to a specific user.  

Federated access also enables the library to purchase and limit access to clinical resources to only Medical Center users. This reduces the cost of resources based on FTEs.	And, as the source of the library budget was under review, there was an increased demand for demographic based library resource usage numbers.  

Finally, it was anticipated that federated authentication would provide more stable access for users.  For example, due to tighter security restrictions, Hospital IP ranges changed more frequently and without warning than University IP numbers. This left hospital users without access until the library could update the IP information at the vendor sites.  A federated solution eliminates the issue for these busy users who have little time to deal with resource access problems.  

And, in future years, the federated authentication system would allow for an even better patron resource access experience. Additional tools such as the Lean Library browser plug in and the Seamless Access service enable patrons to login to subscribed resources directly at the publisher site more simply and easily than they could before.

##Process/Technical
After the library selected OpenAthens as the solution, it was vetted by UIS security and identity management teams to ensure that the solution satisfied University requirements.

Implementation consisted of:

* connecting OpenAthens and the University network authentication system,
* identifying Medical Center users,
* creating a programming logic to add an attribute to user network accounts for DML resource access,
* configuring OpenAthens for each resource,
* contacting publishers with the new authentication information,
* testing access pathway and,
* changing  resource URLs across the library’s finding tools.

As most of the work was behind the scenes, there was minimal user education; however, regular communications to library staff were important.  

Results [for example, impact on user experience, changes to processes or how you work with other departments]
Implementation was gradual but after eighteen months, most resources were authenticated via OpenAthens.  There was some concern that users would be upset at the new login request when on campus; yet there were very few comments. As expected, resource availability for hospital users improved when their access was no longer tied to an IP address.

The recent implementation of Seamless Access by some of our major resource providers such as Elsevier, SpringerNature and Wiley brought a new improvement for users that would not have been possible if resource access was still tied to IP addresses.  We’re delighted by the increasing acceptance of Seamless Access.  It makes for a better, more streamlined user experience that is so important for busy users in search of high quality, evidence based information.

Even before any advertisement by the library, users found the “Login via your Institution” Seamless Access button on the publisher sites. Users easily accessed subscribed content without having to leave the publisher site, go to the library’s web site, and re-find the content.  Streamlined access is welcomed by busy users needing fast access to content, especially for those that provide patient care.

##Lessons learned
Having our UIS team on board and part of the process was very beneficial for both departments and the users.   

Transitioning all resources to federated authentication took more staff time than anticipated, particularly four years ago when less publishers were familiar with the solution.  We recommend you specifically assign dedicated staff time to the project. Or, if possible, hire additional staff to complete the work.

Be prepared for unexpected issues and be ready for creative problem solving!  For example,  we recently discovered our users may be presented with two similar WAYF prompts as the University belongs to one federation and the library participates in another.  We have shared with our users that they should follow the more specific Georgetown University Medical Center link.  We’ve also used our library branding, whenever possible, to further help the users make the correct choice.

##Resources
* [Open Athens](https://openathens.org)
* [Authentication and Single Sign On](https://tdnet.io/services/authentication)


***With many thanks to [ORCID](https://orcid.org) for their [participation](https://seamlessaccess.org/posts/2020-07-14-july2020newsletter/) in the kick-off of the beta phase of SeamlessAccess***.

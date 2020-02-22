---
title: 'Service Providers'
date: 2018-11-28T15:15:34+10:00
icon: 'services/icn_serviceproviders.svg'
featured: true
draft: false
weight: 2
heroHeading: 'Service Providers'
heroBackground: 'services/hero_serviceprov.jpg'
description: ""
---

# SeamlessAccess for Service Providers

As federated identity management (FIM) becomes more and more common among services that cater to multiple organizations, each service provider faces the challenge of how to turn this experience into something easy and familiar to its users. Using SeamlessAccess allows service providers to participate in a global FIM experience that reduces the friction for users to authenticate to the service. 

Service providers have choices around how they integrate with SeamlessAccess:

* Limited - lets you use the SeamlessAccess discovery service for users to find and sign into their preferred Identity Provider, but doesn’t integrate this service into your site.
* Standard - lets you use the SeamlessAccess service to display the button on your site, and use the SeamlessAccess discovery and persistence services as integrated components on your site.
* Advanced - provides you with the SeamlessAccess persistence service while giving you greater control over the appearance of the service on your site, and what Identity Providers (IdPs) you include in your discovery service.

Please recognize that we are in a beta phase and therefore the integration methods are subject to change. In particular, the method for controlling access to the Advanced Integration API is currently accomplished by domain whitelisting. This form of access control is not a scalable solution, and we plan to implement some form of API security key mechanism during the beta phase.  Other changes are possible as well. Service providers will be given a minimum of 60 days’ notice for any breaking changes.

More information on how to integrate with SeamlessAccess, as well as our source code, is available at [thiss.io](https://thiss.io/).
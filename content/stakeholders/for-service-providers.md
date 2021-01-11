---
title: 'Service Providers'
date: 2018-11-28T15:15:34+10:00
icon: 'stakeholders/icn_serviceproviders.svg'
featured: true
draft: false
weight: 2
heroHeading: 'Service Providers'
heroBackground: 'stakeholders/hero_serviceprov.jpg'
description: ""
---

# SeamlessAccess for Service Providers

As federated identity management (FIM) becomes more and more common among services that cater to multiple organizations, each service provider faces the challenge of how to turn this experience into something easy and familiar to its users. Using SeamlessAccess allows service providers to participate in a global FIM experience that reduces the friction for users to authenticate to the service. 

Service providers have choices around how they integrate with SeamlessAccess:

* Limited - lets you use the SeamlessAccess discovery service for users to find and sign into their preferred Identity Provider, but doesn’t integrate this service into your site.
* Standard - lets you use the SeamlessAccess service to display the button on your site, and use the SeamlessAccess discovery and persistence services as integrated components on your site.
* Advanced - provides you with the SeamlessAccess persistence service while giving you greater control over the appearance of the service on your site, and what Identity Providers (IdPs) you include in your discovery service.

Please recognize that we are in a beta phase and therefore the integration methods are subject to change. In particular, the method for controlling access to the Advanced Integration API is currently accomplished by domain whitelisting. This form of access control is not a scalable solution, and we plan to implement some form of API security key mechanism during the beta phase.  Other changes are possible as well. Service providers will be given a minimum of 60 days’ notice for any breaking changes.

More information on how to integrate with SeamlessAccess, as well as our source code, is available at [Getting Started](/work).

# Live Implementations of SeamlessAccess

<table style="width:100%">
  <tr>
    <th>Service Provider</th>
    <th>Level of Integration</th>
    <th>URL</th>
  </tr>
  <tr>
    <td>American Chemical Society (ACS)</td>
    <td>Advanced</td>
    <td><a href="https://pubs.acs.org/action/ssostart?redirectUri=/page/remoteaccess/confirm">pubs.acs.org</a></td>
  </tr>
      <tr>
    <td>Elsevier's ScienceDirect</td>
    <td>Advanced</td>
    <td><a href="https://www.sciencedirect.com/science/article/pii/S1878535217300990">www.sciencedirect.com</a> - example</td>
  </tr>
  <tr>
    <td>GÉANT Trusted Certificate Service (TCS)</td>
    <td>Limited</td>
    <td><a href="https://wiki.geant.org/display/TCSNT/TCS+Participants+Sectigo">wiki.geant.org</a> - click on platform links</td>
  </tr>
  <tr>
    <td>Nature.com</td>
    <td>Advanced</td>
    <td><a href="https://www.nature.com/articles/s41586-019-1750-x">nature.com</a> - example</td>
  </tr>
  <tr>
    <td>SAFIRE Test Service Provider</td>
    <td>Standard</td>
    <td><a href="https://testsp.safire.ac.za/">testsp.safire.ac.za</a></td>
  </tr>
    </tr>   
    <tr>
    <td>SUNET</td>
    <td>Standard</td>
    <td><a href="https://edusign.sunet.se/">edusign.sunet.se</a></td>
  </tr>   
  <tr>
    <td>SWAMID</td>
    <td>Limited</td>
    <td><a href="https://wiki.swamid.se/">wiki.swamid.se</a> - click on Login button</td>
  </tr>
    <tr>
    <td>Taylor & Francis</td>
    <td>Advanced</td>
    <td><a href="https://www.tandfonline.com/doi/full/10.1080/00049158.2020.1819009">https://www.tandfonline.com/doi/full/10.1080/00049158.2020.1819009</a> - example</td>
  </tr>
    <tr>
    <td>Wiley Online Library</td>
    <td>Advanced</td>
    <td><a href="https://onlinelibrary.wiley.com/doi/full/10.1002/jgc4.1316/">onlinelibrary.wiley.com</a></td>
  </tr>
    

</table>


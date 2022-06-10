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
    <th>Example URL</th>
  </tr>
   <tr>
    <td>AIP Publishing - Scitation</td>
    <td>Advanced</td>
    <td><a href="https://aapt.scitation.org/doi/full/10.1119/10.0003395">scitation.org</a></td>
  </tr>

  <tr>
    <td>American Chemical Society (ACS)</td>
    <td>Advanced</td>
    <td><a href="https://pubs.acs.org/action/ssostart?redirectUri=/page/remoteaccess/confirm">pubs.acs.org</a> </td>
  </tr>
      <tr>
    <td>Cambridge University Press Higher Education</td>
    <td>Advanced</td>
    <td><a href="https://www.cambridge.org/highereducation/books/geometry/337E4BCCB67C04A25028255A6FB553FC#overview">CUP Higher Education</a></td>
  </tr>
        <tr>
    <td>De Gruyter</td>
    <td>Advanced</td>
    <td><a href="https://www.degruyter.com/">www.degruyter.com</a></td>
  </tr>
      <tr>
    <td>Elsevier ScienceDirect</td>
    <td>Advanced</td>
    <td><a href="https://www.sciencedirect.com/science/article/abs/pii/S0753396918300120">www.sciencedirect.com</a></td>
  </tr>
      <tr>
    <td>Emerald Publishing</td>
    <td>Advanced</td>
    <td><a href="https://www.emerald.com/insight/content/doi/10.1108/IJPCC-10-2020-0169/full/html">emerald.com</a></td>
  </tr>

  <tr>
    <td>GÉANT Trusted Certificate Service (TCS)</td>
    <td>Limited</td>
    <td><a href="https://wiki.geant.org/display/TCSNT/TCS+Participants+Sectigo">wiki.geant.org</a> - click on platform links</td>
  </tr>
  <tr>
    <td>IOP Publishing</td>
    <td>Standard</td>
    <td><a href="https://iopscience.iop.org/article/10.35848/1882-0786/abdcd7">iopscience.iop.org</a></td>
  </tr>
  <tr>
    <td>Mark Allen Group</td>
    <td>Advanced</td>
    <td><a href="https://www.magonlinelibrary.com">magonlinelibrary.com</a></td>
  </tr>
  <tr>  <tr>
    <td>Nature</td>
    <td>Advanced</td>
    <td><a href="https://www.nature.com/articles/s41586-019-1750-x">nature.com</a></td>
  </tr>
    <tr>
    <td>REFEDS Metadata Explorer Tool</td>
    <td>Standard</td>
    <td><a href="https://met.refeds.org">met.refeds.org</a></td>
  </tr>
  <tr>
    <td>SAFIRE Test Service Provider</td>
    <td>Standard</td>
    <td><a href="https://testsp.safire.ac.za/">testsp.safire.ac.za</a></td>
  </tr>
  <tr>
    <td>Sage Publishing</td>
    <td>Advanced</td>
    <td><a href="https://journals.sagepub.com/doi/full/10.1177/00013455211049160">Abstracts in Anthropology article</a></td>
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
    <td><a href="https://www.tandfonline.com/doi/full/10.1080/00049158.2020.1819009">tandfonline.com</a></td>
  </tr>
  <tr>
    <td>The HistoryMakers</td>
    <td>Standard</td>
    <td><a href="https://www.thehistorymakers.org/digital-archives">thehistorymakers.org</a></td>
  </tr>
    <tr>
    <td>Wiley Online Library</td>
    <td>Advanced</td>
    <td><a href="https://onlinelibrary.wiley.com/doi/full/10.1002/jgc4.1316/">onlinelibrary.wiley.com</a></td>
  </tr>
<tr>
    <td>Wolters Kluwer</td>
    <td>Standard</td>
    <td><a href="https://oce.ovid.com/journals/aaprac/202203000/02054229-202203000-00001">ovid.com</a></td>
  </tr>    

</table>


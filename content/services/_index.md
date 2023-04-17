---
title: 'The Service'
date: 2020-08-31T11:52:18+07:00
heroHeading: 'The Service'
heroBackground: 'images/hero_about.jpg'

---

# SeamlessAccess is free
but there are some [Terms of Service](https://seamlessaccess.org/services/tos/) a Service Provider will need to agree to in order to use SeamlessAccess. Please [contact us](https://seamlessaccess.org/contact/) if you are interested to integrate with SeamlessAccess as a Service Provider. This will also allow us to contact you when there are service changes.

**_The functionality of SeamlessAccess in a beta service; services are expected to change as we gain experience and feedback from the community. The availability of the service is a full production, highly available environment._**

# Product Roadmap
The SeamlessAccess roadmap is based on the backlog of issues reported in GitHub as well as insights that we receive from the service adopters and stakeholders. 

Most of our early adopters are coming from the publishing industry and are using the Advanced Integration. Our current strategy is to introduce some of the features that are the reason for choosing the Advanced Integration into the Standard and Limited Integrations. This will provide more flexibility for Standard and Limited Integration models, and we hope the changes will attract new adopters. 

The new features include the ability to filter the IdPs that are available in the discovery services for a given SP, localize the SeamlessAccess central discovery service, and others as indicated below. 

_Please note that the time frames presented in this roadmap are aspirational goals for when our teams will be working on particular features, and not the committed release dates._


![2022 Roadmap](/posts/SA-roadmap-2022-mid.png)



# Architecture and Availability
SeamlessAccess is hosted by SUNET with funding by GÉANT. Monitored 24x7, SeamlessAccess is considered a production service. A detailed diagram of the technical architecture is available [here](https://wiki.geant.org/display/gn43wp5/Seamless+Access+Deployment+Architecture).

## Service Announcements
To check on the status of the SeamlessAccess central services, or to sign up for scheduled service announcements, please see our [status pages](https://status.seamlessaccess.org/).

## A Quick Comparison of the Different Integration Models

<table style="width:100%"
 <tr>
  <th>Integration Model</th>
  <th>Uses the SeamlessAccess WAYF Discovery Service</th>
  <th>Persists IdP Choice</th>
  <th>Uses SeamlessAccess-managed Metadata and Button</th>
  <th>Uses Locally-managed Metadata and Button</th>
 </tr> 
 <tr>
  <td>Limited</td>
  <td>Yes</td>
  <td>Yes</td>
  <td>No</td>
  <td>No</td>
 </tr> 
 <tr>
   <td>Standard</td>
   <td>Yes</td>
   <td>Yes</td>
   <td>Yes</td>
   <td>No</td>
  </tr>
  <tr>
   <td>Advanced</td>
   <td>No</td>
   <td>Yes</td>
   <td>No</td>
   <td>Yes</td>
  </tr>
  </table>
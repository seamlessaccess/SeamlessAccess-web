---
title: 'Step 2'
date: 2020-02-15T12:33:46+10:00
draft: false
weight: 2
stepname: 'Select your implementation flavor'
heroHeading: ''
heroSubHeading: ''
heroBackground: ''
thumbnail: ''
images: []
---

How does your system support federated authentication? In all cases, your service needs to be enabled with federated authentication. If a user can already sign into your site using their institution's sign in credentials you may be able to simply configure your service to use SeamlessAccess.


# 2. Select your implementation flavor

---

> **Who does this work?** The decision about which flavor you will implement depends on what you are trying to do and the technical capabilities that your team can devote at the moment. You likely will want to involve members of your technical and site design teams, and potentially individuals that would be interested about how the SeamlessAccess service fits into the strategic goals of your organization.

--- 

SeamlessAccess.org provides services and software, enabling three different “flavors” of implementation, each with their own benefits and challenges. Each integration will do something slightly different in terms of the data flow for user information - learn more [here](/work/SA_User-DataFlow.pdf). 



## Limited

![Limited Icon](/work/icn_flavors_limited.svg)

_lets you use the Seamless Access discovery service for users to find and sign into their preferred Identity Provider, but doesn’t integrate this service into your site._

### How it works

You will display a link to sign into your site. When the end user clicks on the button, they are redirected to the SeamlessAccess service to sign in and then will be returned back to your site after they sign in.

### Benefits

* The process for finding the user’s institution in a list will be consistent across all SeamlessAccess-enabled sites.
* Once a user has signed in once, SeamlessAccess will register this provider as the user’s preferred sign in host, enabling easier subsequent sign in.

### Challenges

* In some cases, the user will still have to sign in each time they try to access a resource, even if (s)he has already signed in.

---

## Standard

![Standard Icon](/work/icn_flavors_standard.svg)

_lets you use the SeamlessAccess service to display the button on your site, and use the SeamlessAccess discovery and persistence services as integrated components on your site._

### How it works

You will embed the SeamlessAccess widget on your site. The widget will know if the user is already signed in or not and will display appropriate feedback to the user as a result. The user will click the button to sign in, and your site will receive this confirmation. 

### Benefits

All of the benefits of the **Limited** implementation PLUS

* The user will interact with the SeamlessAccess button - an increasingly recognizable symbol for access using their institution
* If the user has a preferred sign in host (identity provider), the name of this institution will be displayed on the SeamlessAccess button.
* If the user is currently signed into ANY SeamlessAccess-enabled site, the user will not have to enter their sign in credentials again.

### Challenges

* If you are not using one of the "easy-connect" providers ([step 3](/step3)), the full implementation could be significantly more involved, and may require additional technical resources.

---

## Advanced

![Advanced Icon](/work/icn_flavors_advanced.svg)

_provides you with the Seamless Access persistence service while giving you greater control over the appearance of the service on your site, and what Identity Providers (IdPs) you include in your discovery service._

### How it works

You will implement nearly all components of the SeamlessAccess service, so you'll have control over which organizations individuals may sign in from as well as the ability to decouple several steps that happen while your users are interacting with the button, selecting the organization they will use to sign in, and how these items appear on your site.

### Benefits

All of the benefits of the **Standard** implementation PLUS

* Greater control over the user experience.
* More control over the look and feel.

### Challenges

* Requires significant technical resources, including knowledge of APIs, and a greater understanding federated sign in workflows.
* Greater technical risk as the SeamlessAccess service evolves during the Beta Period (scheduled to conclude on or before December 2020.)


NEXT: [Step 3. Implementation the service](../step3)
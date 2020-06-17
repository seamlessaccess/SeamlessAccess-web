---
title: 'Step 3'
date: 2020-02-15T12:33:46+10:00
draft: false
weight: 3
stepname: 'Implement the service'
heroHeading: ''
heroSubHeading: ''
heroBackground: ''
thumbnail: ''
images: []
---

How does your system support federated authentication? In all cases, your service needs to be enabled with federated authentication. If a user can already sign into your site using their institution's sign in credentials you may be able to simply configure your service to use SeamlessAccess.


# 3. Implement the service

---

> **Who does this work?** This work is done by someone who configures your access systems for your site and the person/team that modifies the pages where sign in happens will make this change. This may be a system administrator, a software interface designer, or it could be a software developer. In some cases this work may be done by a vendor or consultant. The SeamlessAccess team will help you to identify the right person.

--- 

Once you have [selected your implementation flavor](../step2), it is time to implement it. The steps for implementation depend on your selected flavor. Details for implementing each step are also included below.

SeamlessAccess uses software called "thiss.io", a name derived from THe Identity Selector Software.

## Implementing the "Limited" Flavor

For the "Limited" flavor, you will implement:

* **[Understand the End-User Data Flow](#flow)** - Understand where the data is coming and going to inform your implementation design.
* **[Discovery Service Integration](#discovery)** - Integrate the SeamlessAccess service to use it as your Discovery Service.

## Implementing the "Standard" Flavor

For the "Standard" flavor, you will implement:

* **[Understand the End-User Data Flow](#flow)** - Understand where the data is coming and going to inform your implementation design.
* **[Discovery Service Integration](#discovery)** - Integrate the SeamlessAccess service to use it as your Discovery Service.
* **[Display of SeamlessAccess Login Button](#display)** - Use the SeamlessAccess service to display the login button component on your SP login page.
* **[Integration of Login Button with your SAML SP](#connect)** - Integrate the SeamlessAccess service to use it as your Discovery Service.

## Implementing the "Advanced" Flavor

For the "Advanced" flavor, you will implement:

* **[Understand the End-User Data Flow](#flow)** - Understand where the data is coming and going to inform your implementation design.
* **[Plan your user experience](#ux)** - Understand the SeamlessAccess guidelines for user interface and experience (UI/UX). Review the guidelines, review the usability studies, and plan a conversation with the SeamlessAccess UI/UX team.
* **[Download and edit the SeamlessAccess Discovery service software](#software)** - you will use this set of clients to configure both persistence and discovery services for your custom service
* **[Use the SeamlessAccess API](#api)** - Use these clients to interact with the persistence service when using your own discovery service.
* **[Request production access for your implementation](#prod)** - Before your advanced flavor implementation can go live, you will need to request your service domains to be included in our list of production implementations.

The "Advanced" flavor is significantly more complicated than the other implementations, and should only be used if you are unable to achieve your discovery and/or UX experiences otherwise.

## An Example Implementation

You can see an example of the “Standard” implementation at our [Demo Service](https://service.seamlessaccess.org/). This site provides an example of the standard behavior, and can provide insight for your implementation.

---

# Implementation technical details

---

## Understand the End-User Data Flow <a name="flow"></a>
Each level of integration will have the user data flow through the environment along slightly different paths. Make sure you understand exactly where the data is coming and going via each integration as you design your environment. See [this explanation](/work/SA_User-DataFlow.pdf) of the user data flow for every integration. 

## Discovery Service Integration <a name="discovery"></a>

For the **Limited** and **Standard** integration flavors, you will be using the SeamlessAccess discovery service. This service is based on the [eduGAIN](https://edugain.org/) metadata list. You can see a list of participating organizations at the [eduGAIN technical website](https://technical.edugain.org/).

By far the easiest integration is to use SeamlessAccess service as a standard SAML identity provider discovery service (DS). The DS URL is `https://service.seamlessaccess.org/ds`. You will use this URL in your Service Providers configuration where appropriate. Here is how to do this for some common SP software stacks:

### Shibboleth

In the file /etc/shibboleth/shibboleth.xml modify the SSO element to read:

``` html
<SSO discoveryProtocol="SAMLDS" discoveryURL="https://service.seamlessaccess.org/ds/">
   SAML2
</SSO>
```

For a complete set of options related to discovery see the [shibboleth documentation](https://wiki.shibboleth.net/confluence/display/SP3/Home).

### SimpleSAMLphp

In authsources.php (relative to the SSP config directory) find your SAML authentication source (often named ‘default-sp’) and set the discoURL parameter to https://service.seamlessaccess.org/ds/:

``` php
'default-sp' => array(
    'saml:SP',
    'entityID' => NULL,
    'discoURL' => 'https://service.seamlessaccess.org/ds/',
    ....
),
```

For more details visit the [SSP documentation](https://simplesamlphp.org/docs/stable/).

---

## Display of SeamlessAccess Login Button <a name="display"></a>

### Including the component library

You will need to reference the SeamlessAccess component library before you can use it. For the Standard implementation, you will always reference through a CDN:

``` html
<head>
<!-- Include the SeamlessAccess Sign in Button & Discovery Service -->
<script src="https://service.seamlessaccess.org/thiss.js"></script>
</head>
```

### Rendering the button

Include a `<div>` container that is identified with an id tag where you want the button to appear on your HTML page:

``` html
<body>
  <!-- Location for the SeamlessAccess login button -->
  <div id='putMyLoginButtonHere'></div>
</body>
```

And to display the button into this container, invoke the DiscoveryComponent.render function as a handler for the onload event on the window. This action will cause the button to initialize as soon as the window has finished loading. _(NOTE: while it is possible to initialize the button component earlier, the behavior can be unpredictable and is not recommended.)_

``` html
<script>
window.onload = function() {
  // Render the SeamlessAccess button
  thiss.DiscoveryComponent.render({
    loginInitiatorURL: 'https://sp.example.com/Shibboleth.sso/Login?target=https://sp.example.com/',
  }, '#putMyLoginButtonHere');
};
</script>
```

The `render` function in this code, takes two parameters:

1. **The `loginInitiatorURL`**: - See the next section, “Integration of Login Button with your SAML SP”, for more details
2. **The location where to render the button** - here you will use the id tag that you used for your html `<div>` container, formatted using CSS selector styling in quotes.

### Content-Security-Policy considerations

If your website publishes a [Content-Security-Policy](https://en.wikipedia.org/wiki/Content_Security_Policy) you will need to make provision for the components served from the service.seamlessaccess.org CDN (or from your domain if you deploy your own version of thiss) by merging the following into your existing CSP:

```
Content-Security-Policy: script-src 'unsafe-inline' service.seamlessaccess.org; frame-src service.seamlessaccess.org;
```

The `'unsafe-inline'` is required for the above `DiscoveryComponent.render` example, but could be removed if the onload function was included e.g. from a file.

---

## Integration of Login Button with your SAML SP <a name="connect"></a>

The first step is easy to describe in general but the second step depends on exactly how your SAML implementation works. We provide examples below for the Shibboleth SP but if you run something other than Shibboleth you need to consult your documentation to figure out how the integration works.

The example above works out of the box for Shibboleth assuming you have configured `https://service.seamlessaccess.org/ds` as the discovery service as in the example above. The Shibboleth simplified SP configuration uses the URL `/Shibboleth.sso/Login` to trigger an authentication request using the discovery service configured in the `<SSO>` element.

In general the idea is to provide two hooks for the button component:

1. A way to initialize a SAML discovery protocol request in the SAML SP
2. A way to receive the response from the SAML discovery protocol request

For Shibboleth the loginInitiatorURL serves both purposes but in general you need to provide two parameters discoveryRequest and discoveryResponse which can be either URLs (in which case a redirect is performed) or JavaScript functions that are called by the component.

The discoveryRequest function is called with a single argument containing a JS object representing the chosen IdP - parameters include entity ID, icon, title etc. Normally this function will be used to initialize a SAML authentication request to the identity provider identified by `entity.entityID`.

For Shibboleth this is all handled by providing the single `loginInitiatorURL` parameter as in the example above.

## The SeamlessAccess user experience <a name="ux"></a>

When implementing the "Advanced" flavor, you will need to recreate the SeamlessAccess user experience and interface. SeamlessAccess requires consistency in the user's experience when using the service across different service providers. To this end, we provide several resources:

* **Advisory/Review Meeting** - During the beta period, we are requiring at least one meeting for each service provider with our UI/UX team to review and advise on your plans for incorporating SeamlessAccess into your service. _We highly recommend that you schedule this meeting as early as possible in your planning process._ Approval from this team is required before you'll be able to enable your service to work with the production service. You can contact contact@seamlessaccess.org to set up a meeting.
* **UI/UX guidelines** - The guidelines for the user experience and interface can be found in **section 2.4 - Improve the User Experience of Identity Provider Discovery** of the [Recommended Practices for Improved Access to Institutionally-Provided Information Resources](https://groups.niso.org/apps/group_public/download.php/21892/NISO_RP-27-2019_RA21_Identity_Discovery_and_Persistence.pdf). These guidelines have evolved since their writing, so it will be important to pair your understanding of these practices with the **Advisory/Review Meeting** described above.
* **Usability testing results** - In planning the user experience for SeamlessAccess, the solution went through extensive usability testing. See the insights: [RA21 User Research Summary](https://docs.google.com/presentation/d/1hN-u8CgEzG_9eVf8TGUz29fG876f_UVw9d5GOzA-gbE/edit?usp=sharing)

## Install the SeamlessAccess Service Software <a name="software"></a>

The SeamlessAccess software (`thiss-ds`) is registered as a [package](https://www.npmjs.com/package/@theidentityselector/thiss-ds) on [npm](https://www.npmjs.com/). You can install the latest version of SeamlessAccess with the npm CLI command

```
> npm install [--save] @theidentityselector/thiss-ds
```

The thiss-ds package supports both CommonJS-style and ES6-style import as well as CDN delivery.

**CommonJS:**

``` javascript
var thiss = require("this-ds.js");
```

**ES6-style:**

``` javacript
import {DiscoveryService} from "thiss-ds";
import {PersistenceService} from "thiss-ds";
```

**CDN:**

``` html
<head>
<!-- Include the downloaded SeamlessAccess Discovery Client API -->
<script src="//unpkg.com/browse/@theidentityselector/thiss-ds"></script>
</head>
```

_Also see the [software documentation](https://thiss-ds-js.readthedocs.io/en/latest/install.html) for more information._

## Use the SeamlessAccess software service <a name="api"></a>

To use the SeamlessAccess software (and related API), you will first create an instance of the DiscoveryService and/or PersistenceService object (installed by the package above), and make calls on it to perform the functions of interacting with the service. Note that the DiscoveryService object enables one to add their own MDQ-style lookup for entity objects and include the URL for the SeamlessAccess persistence service.

Please refer to the [full documentation and examples](https://thiss-ds-js.readthedocs.io/en/latest/intro.html) for information on how to use the service software. We recommend that you join the [SeamlessAccess Slack conversation](https://join.slack.com/t/seamlessaccess/shared_invite/zt-f02ee4rb-KUVKmtYWN9TKWClPQbtrjA) to ask technical questions and share experiences with other beta developers.

## Request production access for your implementation <a name="prod"></a>

Before your advanced flavor implementation can go live, you will need to request your service domains to be included in our list of production implementations. Your user experience will [need to have been reviewed](#ux) before moving to production, so, be sure that you have allowed enough time for this process.

Once you are approved to go live, use this [form to submit your production domains](https://airtable.com/shrW1gq06nMazByEt) for access. Your request will be reviewed by the SeamlessAccess team, and you will be notified when everything is ready.

NEXT: [Step 4. Tell your users](../step4)
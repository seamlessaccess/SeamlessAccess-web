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

* **[Discovery Service Integration](#discovery)** - Integrate the SeamlessAccess service to use it as your Discovery Service.

## Implementing the "Standard" Flavor

For the "Standard" flavor, you will implement:

* **[Discovery Service Integration](#discovery)** - Integrate the Seamless Access service to use it as your Discovery Service.
* **[Display of Seamless Access Login Button](#display)** - Use the Seamless Access service to display the login button component on your SP login page.
* **[Integration of Login Button with your SAML SP](#connect)** - Integrate the Seamless Access service to use it as your Discovery Service.

## Implementing the "Advanced" Flavor

For the "Advanced" flavor, you will implement:

* **[Download and edit the Seamless Access Discovery service software](#software)** - you will use this set of clients to configure both persistence and discovery services for your custom service
* **[Use the Seamless Access API](#api)** - Use these clients to interact with the persistence service when using your own discovery service.

The "Advanced" flavor is significantly more complicated than the other implementations, and should only be used if you are unable to achieve your discovery and/or UX experiences otherwise.

## An Example Implementation

You can see an example of the “Standard” implementation at our [Demo Service](https://service.seamlessaccess.org/). This site provides an example of the standard behavior, and can provide insight for your implementation.

---

# Implementation technical details

---

## Discovery Service Integration <a name="discovery"></a>

For the **Limited** and **Standard** integration flavors, you will be using the SeamlessAccess discovery service. This service is based on the [eduGAIN](https://edugain.org/) metadata list. You can see a list of participating organizations at the [eduGAIN technical website](https://technical.edugain.org/).

By far the easiest integration is to use Seamless Access service as a standard SAML identity provider discovery service (DS). The DS URL is `https://service.seamlessaccess.org/ds`. You will use this URL in your Service Providers configuration where appropriate. Here is how to do this for some common SP software stacks:

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

## Display of Seamless Access Login Button <a name="display"></a>

### Including the component library

You will need to reference the Seamless Access component library before you can use it. For the Standard implementation, you will always reference through a CDN:

``` html
<head>
<!-- Include the Seamless Access Sign in Button & Discovery Service -->
<script src="https://service.seamlessaccess.org/thiss.js"></script>
</head>
```

### Rendering the button

Include a `<div>` container that is identified with an id tag where you want the button to appear on your HTML page:

``` html
<body>
  <!-- Location for the Seamless Access login button -->
  <div id='putMyLoginButtonHere'></div>
</body>
```

And to display the button into this container, invoke the DiscoveryComponent.render function as a handler for the onload event on the window. This action will cause the button to initialize as soon as the window has finished loading. _(NOTE: while it is possible to initialize the button component earlier, the behavior can be unpredictable and is not recommended.)_

``` html
<script>
window.onload = function() {
  // Render the Seamless Access button
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

## The Seamless Access Discovery Service Software <a name="software"></a>

Seamless Access is registered as a [package](https://www.npmjs.com/package/@theidentityselector/thiss-ds) on [npm](https://www.npmjs.com/). You can install the latest version of Seamless Access with the npm CLI command

```
> npm install [--save] @theidentityselector/thiss-ds
```

Once downloaded, you can reference the (edited) software in your HTML.

``` html
<head>
<!-- Include the downloaded Seamless Access Discovery Client API -->
<script src="/thiss-ds.js"></script>
</head>
```

## Use the Seamless Access API <a name="api"></a>

The documentation for the API and other details for using the software can be found in the [software documentation](https://thiss-js.readthedocs.io/en/latest/).

NEXT: [Step 4. Tell your users](../step4)
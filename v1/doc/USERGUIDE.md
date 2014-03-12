
<!-- template instructions start -->

This page explains each section of the PPaaS API user guide template and provides examples.

You can also view this template and its examples in [Confluence](https://confluence.paypal.com/cnfl/display/PlatformTeam/PPaaS+API+user+guide+template).

###How to use this template

1. Ensure you have the latest version of the release notes template file, which can be found inside the `/v1/doc/` folder of the [PPaaS service template](https://github.paypal.com/AppPlatform/PPaaS-service-template). Do not change the template file name.
2. Replace [API Name] within the template file with your API name. For example, for the Invoicing API, replace <em>[API Name]</em> with <em>Invoicing</em>.
3. Instructions and examples are provided in each section. Delete the instructions and examples in your final version of the document or surround the instructions and example text with comment tags, &lt;!-- *Place instructions and examples here* --&gt;.
4. This template is written in markdown. Here is a helpful [markdown cheat sheet](http://support.mashery.com/docs/customizing_your_portal/Markdown_Cheat_Sheet).

For questions about PPaaS doc templates, contact the [Developer Documentation Team](mailto:DL-PayPal-Documentation-Team@ebay.com).

<hr/>

<!-- delete these instructions before publishing this file -->

<!-- template instructions end -->

#[API Name] API User Guide

The [API Name] API allows you to ...

###Contents

* [Overview](#overview)
* [Use Cases](#use-cases)
* [Configuration and Setup](#configuration-and-setup)
* [API Details](#api-details)
* [Using the API](#using-the-api)
* [Error Handling](#error-handling)
* [Glossary](#glossary)

<hr/>

<p><a name="overview"></a></p>

##Overview

( __Required__ - *Provide a short summary that describes the functionality, purpose, and benefits of your API and outline the data it requires and returns. The user should know whether or not your API addresses their needs after reading a sentence or two. See the following example.*)

The Developer API simplifies the process of building applications that use PayPal capabilities (or business functions). Using this API, you can create applications with one or more capabilities. Currently, this API only supports the following capabilities:

* Log In with PayPal (Identity): an Identity solution, which allows customers to log in to a third-party website quickly and securely using PayPal log in credentials.
* Payments: provides an easy and secure way to accept online and mobile payments.

The Developer API provides application life cycle management CRUD operations (Create, Retrieve, Update, Delete). An application requires basic information such as name and account number. Every application is associated with base metadata. It can also contain capabilities, which also contain basic information like name, permissions and some optional metadata. Once an application is created successfully via this API, credentials identifying the application are generated. These credentials can then be used to make API calls. Each API call response includes an array of [HATEOAS links](https://github.paypal.com/AppPlatform/Standards/blob/master/doc/api-config.md#hateoas-links). This allows you to construct an API flow solely through the hyperlinks provided in the response.

<p><a name="use-cases"></a></p>

##Use Cases

( __Required__ - *List each use case your API addresses. The list of use cases may be similar to the list of actions that can be performed on the API resources. See the following example.*)

Use the Developer API to:

* Create an application
* Get an application
* List all applications
* Update an application
* Update a capability
* Add a capability
* Delete a capability
* Activate a capability

<p><a name="configuration-and-setup"></a></p>

##Configuration and Setup

( __Recommended__ - *Provide any one-time configuration steps that must be completed in order to use your API, as well as information that is required in every API call. See the following example.*) 

No configuration or setup steps are required for the Developer API in the staging environment.

However, before you can use this API in the Sandbox or live environments, you must do the following:

1. Get your [application credentials](https://github.paypal.com/AppPlatform/Standards/blob/master/doc/api-config.md#application-credentials). 
2. [Obtain an OAuth token](https://github.paypal.com/AppPlatform/Standards/blob/master/doc/api-config.md#authentication-and-headers), used in each API call. 

<p><a name="api-details"></a></p>

##API Details

( __Required__ - *Provide a list of endpoints used by your API in the available environments. Also provide your API's resources, sub-resources, actions the API can perform on these resources and the HTTP method for each action. See the following example.*)

###API Endpoints

Combine one of the following host names with a resource path from the table below to create the endpoint URI:

* Sandbox: [https://api.sandbox.paypal.com](https://api.sandbox.paypal.com)
* Live: [https://api.paypal.com](https://api.paypal.com)
* Stage: [https://stage2p1197.qa.paypal.com:12007](https://stage2p1197.qa.paypal.com:12007)
* Development: [https://localhost:12879](https://localhost:12879)

|Resource Path|<nobr>HTTP Method</nobr>|Action|
|---|---|---|
|`/v1/developer/application/`|`POST`|Create an application|
|`/v1/developer/application/{id}`|`GET`|Get an application|
|`/v1/developer/application?account-number={acctnum}`|`GET`|List all applications|
|`/v1/developer/application/{id}/update`|`POST`|Update an application|
|`/v1/developer/application/{id}/capabilities`|`POST`|Add a capability|
|`/v1/developer/application/{id}/capabilities/PAYMENT/update` <br/>`/v1/developer/application/{id}/capabilities/PAYPAL_ACCESS/update`|`POST`|Update a capability|
|`/v1/developer/application/{id}/capabilities/PAYMENT/` <br/>`/v1/developer/application/{id}/capabilities/PAYPAL_ACCESS/`|`DELETE`|Delete a capability|
|`/v1/developer/application/{id}/capabilities/PAYMENT/activate` <br/>`/v1/developer/application/{id}/capabilities/PAYPAL_ACCESS/activate`|`DELETE`|Activate a capability|

<p><a name="using-the-api"></a></p>

##Using the API

( __Required__ - *For each of the methods in your API, provide a heading which briefly describes the action it performs, a couple of sentences that further describe the action, the endpoint and HTTP method for the action, a list of request fields with any required explanation about them, a sample request and a sample response with any required information about the response fields. The example below is for only one of the Developer API methods.* )

###Add a Capability

This call lets you add a capability to an application after the application is created. For example, you create an application with the Log In with PayPal capability, and later you realize that you need the functionality exposed by the Payment capability. You can then use this call to add the Payment capability.

Use the endpoint below to add the capability:

`POST` `https://stage2p1197.qa.paypal.com:12007/v1/developer/application/AdM_khCgf9p2fgeroGNqGJQJ-iqLCSeJyciW7skyp3svnc5uXlZtUSm_wjg3/capabilities`

####Sample request
> curl -v -1 --insecure -X POST <br/>
> -H 'Content-Type:application/json' <br/> 
> -H 'PAYPAL_SERVICE_VERSION:1.2.0' <br/>
> -d '{"name":"PAYMENT","scopes": <br/>
>     ["https://api.paypal.com/v1/payments/.\*", <br/>
>     "https://api.paypal.com/v1/vault/credit-card/.\*", <br/>
>     "https://api.paypal.com/v1/vault/credit-card", <br/>
>     "https://uri.paypal.com/services/payments/futurepayments"] <br/>
>    }' https://stage2p1197.qa.paypal.com:12007/v1/developer/application/AdM_khCgf9p2fgeroGNqGJQJ-iqLCSeJyciW7skyp3svnc5uXlZtUSm_wjg3/capabilities

If your request is successful, the Developer API returns a HTTP status code of `201 Created` with the JSON response below:

    {
    "name": "PAYMENT",
    "status": "ACTIVE",
    "scopes": [ <br/>
    "https://api.paypal.com/v1/payments/.\*",
    "https://api.paypal.com/v1/vault/credit-card/.\*",
    "https://api.paypal.com/v1/vault/credit-card",
    "https://uri.paypal.com/services/payments/futurepayments"],
    "metadata": [],
    "links": [
    { "href": "https://www.stage2p1197.qa.paypal.com:11888/v1/developer/application/AdM_khCgf9p2fgeroGNqGJQJiqLCSeJyciW7skyp3svnc5uXlZtUSm_wjg3/capabilities/PAYMENT/update", <br/>
    "rel": "update",
    "method": "POST" 
    },
    {"href": "https://www.stage2p1197.qa.paypal.com:11888/v1/developer/application/AdM_khCgf9p2fgeroGNqGJQJiqLCSeJyciW7skyp3svnc5uXlZtUSm_wjg3/capabilities/PAYMENT</a>", <br/>
    "rel": "delete", 
    "method": "DELETE" }
    ], 
    "features": [
    {"name": "ACCEPT_CARD", 
    "status": "NOT-VETTED"}, 
    {"name": "ACCEPT_PAYPAL", 
    "status": "ACTIVE"} 
    ]
    } 
    
<p><a name="error-handling"></a></p> 

##Error Handling

( __Recommended__ - *Provide any information that could prevent problems, reduce support time and improve the overall developer experience. Please provide a list of errors returned by your API in this section, especially if you do not have a JSON file in your API schema that lists these errors. Creating an error details JSON file in your schema is preferred. See the following example.*)

See [error handling](https://github.paypal.com/AppPlatform/Standards/blob/master/doc/api-config.md#error-handling) for general information on errors returned by PPaaS APIs.

####API Errors

|<nobr>HTTP status</nobr>|Error name|Error message|Error details|Possible causes and solutions|
|---|---|---|---|---|
|`401`|`UNAUTHORIZED`|||You sent a request to the live environment without an OAuth token. See [Configuration and Setup](#configuration-and-setup) for more information.|
|`400`|`VALIDATION_ERROR`|`Invalid data provided`|`field: "application_type"`<br/>`issue: "Please enter a valid application type.`<br/>`Valid application types are WEB or MPL"`||

If you encounter any other issues not mentioned in this section, send an email message to: [DL-PP-Pelican](#).

<p><a name="glossary"></a></p>

##Glossary

( __Optional__ - *Provide definitions to lesser known terms, terms that may have multiple meanings or terms that you're using in a specific or unique way. See the following example.*)

The following terms used in this user guide may require additional clarification.

|Term|Definition|
|---|---|
|Applications|REST API applications that you can build via the Developer API, which use one or more PayPal capabilities.|
|Capabilities|Business functions provided by other PayPal APIs. For example, the Developer API exposes the capabilities of the Identity API (PAYPAL_ACCESS) and the Payments API (PAYMENT).|

<hr/>

<!-- do not delete the template version -->
*PPaaS API user guide template v<template-version>1.0</template-version>*

 


<!-- template instructions start -->

This page explains each section of the PPaaS API release notes template and provides examples.

You can also view this template and its examples in [Confluence](https://confluence.paypal.com/cnfl/display/PlatformTeam/PPaaS+API+release+notes+template).

###How to use this template

1. Ensure you have the latest version of the release notes template file, which can be found inside the `/v1/doc` folder of the [PPaaS service template](https://github.paypal.com/AppPlatform/PPaaS-service-template). Do not change the template file name.
2. Replace [API Name] within the template file with your API name. For example, for the Invoicing API, replace *[API Name]* with *Invoicing*.
3. Examples are provided in each section. Delete the examples in the final version of your document or surround the example text with comment tags.
4. This template is written in markdown. Here is a helpful [markdown cheat sheet](http://support.mashery.com/docs/customizing_your_portal/Markdown_Cheat_Sheet). 

For questions about PPaaS doc templates, contact the [Developer Documentation Team](mailto:DL-PayPal-Documentation-Team@ebay.com).

<hr/>

<!-- delete these instructions before publishing this file -->

<!-- template instructions end -->

#[API Name] API Release Notes

Review the release notes to keep up with changes pertaining to the [API Name] API.

* [Updates in v1.2.3](#updates-in-v123)

<hr/>

<p><a name="updates-in-v123"></a></p>

##Updates in v1.2.3

**Release date: mm-dd-yyyy**

These release notes describe the changes to the [API Name] API and related documentation.

* [New Features](#new-features)
* [Changed Functionality](#changed-functionality)
* [Fixed Issues](#fixed-issues)
* [Known Issues](#known-issues)

<hr/>

<p><a name="new-features"></a></p>

###New Features

*(Example 1)*

No new features.

*(Example 2)*

The following new features have been added as of this release. New features include new resources, new sub-resources and/or new fields added to existing resources.

####Reauthorize Payments

|Method|Name|Type of Change|
|---|---|---|
|`POST`|`/v1/payments/authorization/{authorization_id}/reauthorize/`|New endpoint|

The Payment API now allows you to [reauthorize a PayPal account payment](#). We recommend that you reauthorize a payment after the initial 3-day honor period to ensure that funds are still available.

####Merchant Invoice ID

|Name|Type|Added To|Description|Type of Change|
|---|---|---|---|---|
|`invoice_id`|`string`|`payment` object|Merchant's invoice or payment tracking ID|new field|

The Payment API now accepts a merchant invoice ID to help merchants with tracking transactions using their internal invoice or tracking IDs.

<p><a name="changed-functionality"></a></p>

###Changed Functionality

*(Example 1)*

No changed functionality.

*(Example 2)*

The following logical or functional changes have been made to existing functionality. Changed functionality includes new code list values and/or changes in validation rules.

####Support for Additional Countries and Currencies

The Payment API now supports additional currencies and countries for PayPal account payments and direct credit card payments. Refer to [supported countries and currencies](#) for more information.

<p><a name="fixed-issues"></a></p>

###Fixed Issues

*(Example 1)*

No issues were fixed in this release.

*(Example 2)*

The following issues have been fixed in this release:

[JIRA issue 1234](#) - Freight shipping costs are not added to the total transaction cost.

[JIRA issue 1235](#) - Incorrect error code returned for funding failure in payments of type `ORDER`.

<p><a name="known-issues"></a></p>

###Known Issues

*(Example 1)*

No known issues.

*(Example 2)*

The following issues will be addressed in a future release:

[JIRA issue 1234](#) - Freight shipping costs are not added to the total transaction cost.

[JIRA issue 1235](#) - Incorrect error code returned for funding failure in payments of type `ORDER`.

<hr/>

<!-- do not delete the template version -->
*PPaaS API release notes template v<template-version>1.1</template-version>*
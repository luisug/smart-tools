---
layout: doc
---
# Smart Check requirements

The Smart Check feature of Smart Tools enables you to run a variety of health checks on your Virtual Apps and Desktops Site. With Smart Check, you can find and fix issues before your users are impacted.

*  Schedule and run a wide variety of health checks on your Site.
*  Learn about any potential health issues affecting your Site.
*  Find recommended product updates for the Delivery Controllers and Machine Catalogs in your Site.
*  Easily upload Site diagnostics and share them with Citrix Support for analysis.
*  View comprehensive reports about your Site's health.

## Supported environments

Smart Check is supported for use with Virtual Apps and Desktops Sites that meet the following requirements:

*  Uses XenApp and XenDesktop 7.x or Virtual Apps and Desktops 7 1808 or later
*  Deployed on one of the following cloud providers or hypervisors:
    *  Amazon Web Services (AWS)
    *  Microsoft Azure Resource Manager
    *  Citrix XenServer 6.2, 6.5, 7.0, and 7.1
    *  VMware vSphere 5.1, 5.5, and 6.0
*  Machine Catalogs use Machine Creation Services (MCS)

Smart Check is not supported for use with Microsoft Azure Classic or with deployments using the Virtual Apps and Desktops service in Citrix Cloud.

### Supported Site components

Smart Check supports running health checks on the following Site components:

*  Delivery Controllers
*  Delivery Groups (created through Virtual Apps and Desktops or Citrix Provisioning)
*  Machine Catalogs
*  StoreFront
*  Citrix Provisioning
*  Citrix License Server

When you add a Site to Smart Check, Smart Tools runs a [series of checks](/en-us/smart-tools/checks/about-health-checks.html#checks-that-run-automatically) on the Delivery Controllers in your Site by default and displays results only for the Delivery Controllers, Delivery Groups, and Machine Catalogs. Afterward, you can run separate checks for any StoreFront, Citrix Provisioning, and Citrix License Server machines in your Site. For more information about these checks, see [Citrix health checks](/en-us/smart-tools/checks/about-health-checks.html). You can also [schedule](/en-us/smart-tools/checks/perform-health-checks.html#schedule-checks) these checks so that updated results for these components are added to the Health alerts page at regular intervals.

## Agent requirements

To take advantage of all Smart Check functions, you must install the Smart Tools Agent on one or more Delivery Controllers in your Virtual Apps and Desktops Site. For more information about the requirements for installing the Smart Tools Agent, see [Smart Tools Agent and connectivity requirements](/en-us/smart-tools/system-requirements/connectivity-requirements.html)

For instructions to install the Smart Tools Agent, see [Add a Site to Smart Tools](/en-us/smart-tools/install-configure/add-site.html).

## Account requirements

After you install the Smart Tools Agent, you must supply an account that Smart Tools can use to run checks and look for applicable fixes and updates for your Site. This account must meet the following minimum requirements:

*  Member of the Domain Users group in Active Directory.
*  Full Administrator role for the Site in Citrix Studio.

If you use a Domain Users account with Smart Tools, running [checks that target other machines](/en-us/smart-tools/checks/about-health-checks.html#checks-targeting-other-machines) in your environment requires that the account is also a member of the local Administrators group on the Delivery Controllers in the Site and on the targeted machines.

### Requirements for using Smart Check without the agent

If you choose not to install the agent, you can still use Smart Check to perform manual health checks. Smart Tools can discover your Site using Virtual Apps and Desktops Call Home or Citrix Scout. Smart Tools analyzes Call Home and Citrix Scout data and displays potential issues or applicable updates in Smart Check.

For Smart Tools to discover your Site without the agent installed, the following requirements must be met:

*  Diagnostics uploads from your Site using Call Home or Citrix Scout must exist.
*  You must use the same Citrix account that's associated with those diagnostics uploads to access Smart Tools.

To perform health checks, you first use Call Home or Citrix Scout and then allow Smart Tools to rediscover your Site. After Smart Tools analyzes your data, you can address any issues or updates using your own processes, outside of Smart Tools.

> **Important**:
>
> To schedule all available health checks to run on your Site, you must install the Smart Tools Agent.

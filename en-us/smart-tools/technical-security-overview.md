---
layout: doc
---
# Technical Security Overview for Citrix Smart Tools

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

## Security Overview

Citrix Smart Tools manages monitoring and scaling Delivery Groups and performing health checks for Citrix Virtual Apps and Desktops deployments. The machines that comprise these deployments are under the customer’s control in the environment of their choice, either cloud or on-premises.

The customer's Virtual Apps and Desktops Site is connected to the Smart Tools service using the Citrix Smart Tools Agent. The customer installs this agent on at least one Delivery Controller in the Site. The customer can install the agent through the Virtual Apps and Desktops product installer, when the customer initially installs the Delivery Controller and creates a new Site. The customer can also install the agent on a Delivery Controller in an existing Site through the Smart Tools user interface.

### Data Flow

As the components comprising a deployment are hosted in the customer’s resource location, the customer’s application data and any machine image templates used to provision virtual machines are always hosted within the customer’s resource location. Smart Tools has access to metadata such as email addresses, usernames, and machine names. Smart Tools also has access to Site information such as:

*  Delivery Group and Machine Catalog GUIDs and names.
*  Master image VM names associated with Machine Catalogs.
*  Delivery Controller FQDNs, product version, and IP addresses.
*  VDA DNS names, UUIDs, and other information used for power management functions such as load index, power state, and maintenance mode status.
*  Site data uploaded by the customer through Call Home in Virtual Apps and Desktops or Citrix Scout.

Smart Tools stores this information in a separate database instance for each customer.

Data flowing between Smart Tools and the machines in a customer’s resource location (either cloud or on-premises) or a customer's Site uses secure HTTPS outbound connections over port 443. Data flowing between Smart Tools and a customer's Site also uses secure HTTPS outbound connections over port 443.

### Data Isolation

Customer metadata, such as company name and user email address, are stored in a master database. All transactional data is stored in separate database instances so that each customer’s data is isolated from other customers. When customers authenticate against Citrix Cloud, they access only the data in their own account. They cannot access data of any other customer or user.

### Credential Handling

The service handles the following types of credentials:

*  **User and Administrator credentials:** Account administrators and users authenticate against Citrix Cloud. This generates a one-time signed JSON Web Token (JWT) which gives the administrator access to the Smart Tools service.
*  **Citrix administrator credentials:** When manually installing or upgrading to the latest version of Smart Tools Agent, the customer is prompted to supply the username and password of a Citrix Administrator account. If the agent is installed using the Virtual Apps and Desktops product installer, the installation process acquires the Site credentials without customer intervention. During agent installation, the credentials allow Smart Tools to register the Site. After Site registration, the credentials enable Smart Tools to perform the following tasks on the customer's behalf:
    *  Perform health checks on Delivery Controllers, Machine Catalogs, Delivery Groups, License Servers, Provisioning Servers, and StoreFront servers that Smart Tools discovers in the Site.
    *  Perform health checks on the VDAs that the customer specifies.
    *  Coordinate scaling actions to Delivery Controllers and Machine Catalogs in the Site.

    For customers using the latest version of the agent, the username of the Citrix Administrator account is stored in the cloud service database. The password of the Citrix Administrator account is stored, encrypted and salted, in the registry of the Delivery Controller hosting the Smart Tools Agent. Citrix owns the keys used to encrypt these credentials. After the customer supplies a password to Smart Tools, the password is masked and cannot be rendered in plain text.

    For customers using older versions of the agent, the username and password of the Citrix Administrator account is stored, encrypted and salted, in the cloud service database. Citrix owns the keys used to encrypt these credentials. After the customer supplies a password to Smart Tools, the password is masked and cannot be rendered in plain text. When the customer upgrades the older agent to the latest version, the Citrix Administrator credentials previously supplied are transferred to the registry of the Delivery Controller hosting the agent and encrypted. The credentials in the cloud service database are also deleted.

### Agent Network Access Requirements

The Delivery Controllers that host the Smart Tools Agent, as part of a registered Site using the Smart Check or Smart Scale features, require only port 443 outbound traffic to the Internet, and may be hosted behind an HTTP proxy.

## Security Best Practices

**Secure user management:** The Administrator user role in Citrix Cloud has access to all service functions and is responsible for managing new and existing users and assigning user roles. Administrators in Citrix Cloud are administrators of the Smart Tools service by default. Ensure only select account users are assigned the Administrator role in Citrix Cloud to ensure prompt management of users and support requests.

## More Information

*  Citrix Security and Compliance Information: [https://www.citrix.com/about/legal/security-compliance/](https://www.citrix.com/about/legal/security-compliance/)
*  Smart Tools documentation: [http://docs.citrix.com/en-us/smart-tools](http://docs.citrix.com/en-us/smart-tools)
*  Citrix Cloud Secure Deployment Guide (links to Technical Security Overviews for services): [https://docs.citrix.com/en-us/citrix-cloud/overview/secure-deployment-guide-for-the-citrix-cloud-platform.html](https://docs.citrix.com/en-us/citrix-cloud/overview/secure-deployment-guide-for-the-citrix-cloud-platform.html)
*  Deploying Citrix ADC VPX: [https://docs.citrix.com/en-us/netscaler/12/deploying-vpx.html](https://docs.citrix.com/en-us/netscaler/12/deploying-vpx.html)
*  Virtual Apps and Desktops Security: [https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/secure.html](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/secure.html)
*  Amazon Web Services Security Best Practices: [http://aws.amazon.com/whitepapers/aws-security-best-practices/](http://aws.amazon.com/whitepapers/aws-security-best-practices/)
*  Microsoft Trust Center - Security: [https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx)
*  VMware Security Hardening Guides: [https://www.vmware.com/security/hardening-guides.html](https://www.vmware.com/security/hardening-guides.html)
*  Hyper-V Security Guide: [https://technet.microsoft.com/en-us/library/dd569113.aspx](https://technet.microsoft.com/en-us/library/dd569113.aspx)

## Disclaimer

_Note: This document is intended to provide the reader with an introduction to and overview of the security functionality of Citrix Smart Tools; and to define the division of responsibility between Citrix and customers with regard to securing the Smart Tools service and deployed resources. It is not intended to serve as a configuration and administration guidance manual for Smart Tools or any of the components or services that are used in tandem._

## Copyright notice

_© Citrix Systems, Inc. All rights reserved. Citrix, the Citrix logo, Citrix Cloud, Citrix ADC, Citrix Gateway, and other Citrix names marks appearing herein are trademarks of Citrix Systems, Inc. and/or one or more of its subsidiaries, and may be registered in the U.S. Patent and Trademark Office and in other countries. Other marks are the property of their respective owner/s._
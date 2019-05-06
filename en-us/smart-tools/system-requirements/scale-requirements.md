---
layout: doc
---
# Smart Scale requirements

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

The Smart Scale feature in Smart Tools enables proactive scaling and power management of registered machines in a Virtual Apps and Desktops Site based on a schedule you define or the level of demand for user sessions. For more information about how Smart Scale works, see [Smart Scale overview](/en-us/smart-tools/scale/about-scale.html).

This article describes the requirements for using Smart Scale with your Site.

## Supported Sites and Delivery Groups

You can use Smart Scale with the following Virtual Apps and Desktops Sites:

*  XenApp and XenDesktop 7.x Sites
*  Virtual Apps and Desktops 7 1808 Sites
*  Sites using the Virtual Apps and Desktops service of Citrix Cloud

Supported Sites can use the following host connection types with Smart Scale:

*  Amazon EC2
*  Microsoft Azure (Classic and Resource Manager)
*  Citrix XenServer 6.2, 6.5, 7.0

Smart Scale is configured on a per-Delivery Group basis. You can use Smart Scale with Delivery Groups that reference only Machine Catalogs containing power-managed machines. These machines can be Server OS machines or Desktop OS machines.

## Agent requirements

To use Smart Scale with your Site, you must install the Smart Tools Agent on one or more Delivery Controllers in your Virtual Apps and Desktops Site. For installation requirements for the Smart Tools Agent, see [Smart Tools Agent and connectivity requirements](/en-us/smart-tools/system-requirements/connectivity-requirements.html).

For instructions to install the Smart Tools Agent, see [Add a Site to Smart Tools](/en-us/smart-tools/install-configure/add-site.html).

## Account requirements

After you install the Smart Tools Agent, Smart Tools prompts you to enter Citrix administrator credentials to set up Smart Scale. This allows Smart Tools to impersonate the administrator when performing monitoring and scaling activities. The Citrix administrator account you use must meet the following requirements:

*  At a minimum, the account is assigned the Delivery Group Administrator role in Citrix Studio.
*  The account belongs to the Domain Users group in Active Directory.

### Server VDA and VDI support

Smart Scale supports Server OS machines that deliver published applications or hosted shared desktops to users.

### VDI desktop support

Smart Scale supports Desktop OS machines hosting the following VDI desktops:

*  Static persistent (dedicated) VDI desktops
*  Random non-persistent VDI desktops (pooled VDI desktops)

To use Smart Scale with VDI desktop machines, you must disable Virtual Apps and Desktops's built-in power management functions so they don't interfere with Smart Scale's scaling actions.

> **Important**:
>
> The commands in this section disable XenDesktop's built-in power management functions for all Delivery Groups in the Site. This action cannot be undone automatically. Citrix recommends using these commands in a test environment only. Prior to using these commands, consider recording the current Delivery Group settings that the commands will alter when executed.

To do this for a traditional Site, from the Delivery Controller, open the PowerShell command window and enter the following commands:

```
Add-PSSnapin *Citrix*
Set-BrokerDesktopGroup -Name * -AutomaticPowerOnForAssigned $False
Set-BrokerDesktopGroup -Name * -AutomaticPowerOnForAssignedDuringPeak $False
Set-BrokerDesktopGroup -Name * -OffPeakBufferSizePercent 0
Set-BrokerDesktopGroup -Name * -PeakBufferSizePercent 0
Set-BrokerPowerTimeScheme -name * -PoolSize ( 1..24 | %{ -1 } ) -PoolUsingPercentage 0
```

For Sites that use Citrix Virtual Desktops Essentials or the Virtual Apps and Desktops service, perform the following actions:

1.  Download the [Virtual Apps and Desktops Remote PowerShell SDK](/en-us/citrix-virtual-apps-desktops-service/sdk-api.html#citrix-virtual-apps-and-desktops-remote-powershell-sdk) and run it on a machine in your resource location. Citrix recommends running this SDK on machines that do not act as Cloud Connectors in your resource location.
1.  Open a PowerShell command window and run the commands mentioned above.

### Supported scaling options

Depending on the Machine Catalogs associated with your Delivery Groups, some scaling options might not be available. The table below shows the Machine Catalogs that are supported for each scaling option.

| Machine Type | Schedule-based | Load-based  | Load and schedule-based  |
| --- | --- | --- | --- |
| **Server OS** machines hosting published applications or hosted shared desktops (Server VDI) | Supported. | Supported. | Supported. |
| **Desktop OS** machines hosting **static persistent (dedicated)** VDI desktops  | Supported. During periods when machines are powered off (for example, after working hours), users can trigger machines to power on through Citrix Receiver. You can set Smart Scale's [Power Off Delay](/en-us/smart-tools/scale/manage-delivery-group-capacity.html) so Smart Tools does not automatically power machines off before the user can establish a session.  | Not currently supported. | Not currently supported. |
| **Desktop OS **machines hosting **random non-persistent** VDI desktops (pooled VDI desktops) | Supported. | Supported. Use the **Session Count** scaling metric and set the maximum number of sessions to **1**. | Supported. Use the **Session Count** scaling metric and set the minimum number of machines to **1**. |

## Supported scalability

Smart Scale supports power managing Sites using Virtual Apps and Desktops, the Virtual Apps and Desktops service, Virtual Apps Essentials, and Virtual Desktops Essentials.

Power management for a single Site using one of these services is supported as follows:

*  Up to 2,000 VDAs or VDIs per Site can be power managed.
*  Up to 120 Delivery Groups can be power managed.
*  Up to 1,000 VDAs or VDIs per Delivery Group can be power managed.

> **Important**:
>
> If you add a Site to Smart Scale that exceeds these limits, you might not be able to use Smart Scale with your Site. When you add your Site to Smart Scale, Smart Tools verifies the Delivery Groups and machines in the Site are within the supported limit. If the Site exceeds the limit, Smart Scale does not enable the "Get Started" button, preventing you from configuring Smart Scale for the Site. If you need to add a Site that exceeds these limits, contact Citrix Technical Support.
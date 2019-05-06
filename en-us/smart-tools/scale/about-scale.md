---
layout: doc
---
# Smart Scale overview

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

The Smart Scale feature in Smart Tools enables proactive scaling and power management of registered machines in a Virtual Apps and Desktops Site based on a schedule you define or the level of demand for user sessions.

Using Smart Scale you can reduce the costs of running Virtual Apps and Desktops in public clouds, such as Microsoft Azure or Amazon Web Services (AWS). Smart Tools does this by dynamically scaling up or scaling down the number of registered powered-on machines in the Delivery Group. Smart Tools can also estimate your savings based on the per-machine costs and utilization history.

Smart Tools manages machine power and capacity using the following methods:

*  **Schedule-based scaling:** Powers machines on and off based on a schedule you define.
*  **Load-based scaling:** Powers machines on and off based on the level of demand for sessions.
*  **Load and schedule-based scaling:** Keeps a minimum number of machines powered on at time periods you define while accommodating the current level of demand for sessions.

For more information about each scaling option, see [Manage Delivery Group capacity with Smart Scale](/en-us/smart-tools/scale/manage-delivery-group-capacity.html).

## Requirements

For a complete list of requirements for Smart Scale, see [Smart Scale requirements](/en-us/smart-tools/system-requirements/scale-requirements.html).

## Capacity and machine registration

To ensure Smart Tools has an accurate view of machines that can accept session requests, Smart Tools includes only machines that are registered with the Site when determining the capacity for a given Delivery Group. Powered-on machines that are unregistered cannot accept session requests, so they are not included in the overall capacity of the Delivery Group.

## Scaling across multiple Machine Catalogs

In some Virtual Apps and Desktops Sites, multiple Machine Catalogs might be associated with a single Delivery Group to provide high availability across multiple locations. To balance the number of powered on machines in the Delivery Group across all Machine Catalogs, Smart Tools powers on some machines from each associated catalog to meet schedule or session demand requirements. This prevents scaling actions from concentrating in any particular Machine Catalog.

For example, a Delivery Group has two Machine Catalogs: Catalog A has three machines powered on and Catalog B has one machine powered on. If Smart Tools needs to power on five additional machines, it powers on two in Catalog A (totaling five machines on) and three in Catalog B (totaling four machines on).

When machines need to be powered off (because session demand lessens or the schedule requires fewer machines than are powered on), Smart Tools puts the machines in each catalog with the fewest sessions into maintenance mode. While in maintenance mode, Smart Tools waits for remaining sessions to disconnect and terminate (according to Citrix load management policies) before powering off the machines.

## Machine provisioning and session demand

Smart Scale works only with the existing machines in a Delivery Group. So, the Machine Catalog associated with the Delivery Group must have enough machines to power on and off as demand increases and decreases. If session demand exceeds the total number of registered machines in the Delivery Group, Smart Tools only ensures all existing registered machines are powered on or taken out of maintenance mode. Smart Tools does not provision more machines.

## Availability of monitoring data

For all supported Sites, monitoring and event data are available when Smart Scale is enabled for the Delivery Group. Monitoring data continues to be available when Smart Scale is enabled and then disabled for the Delivery Group. Smart Tools collects monitoring data at 5 minute intervals.

> **Note**:
>
> When you initially add a Site to Smart Scale, it might take a few minutes to display monitoring data for your Site.

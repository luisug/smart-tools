---
layout: doc
---
# Troubleshoot Smart Scale issues

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

This topic provides troubleshooting tips for Smart Scale issues.

## Smart Tools cannot retrieve machine details

Smart Tools displays the message "Smart Tools cannot retrieve machine details." This issue occurs because Smart Tools couldn't obtain results from the Get-BrokerMachine cmdlet that it runs.

If you're using Smart Scale with the Virtual Apps and Desktops service or Virtual Desktops Essentials, contact Citrix Technical Support.

If you're using the Smart Tools Agent with your Site, verify the Delivery Controller can retrieve VDA machine details using the Get-BrokerMachine cmdlet.

1.  Log on to the Delivery Controller as a Domain User.
1.  Launch an instance of Windows PowerShell (powershell.exe).
1.  Enter the following PowerShell commands:

    ```powershell
    Add-PSSnapin -Name Citrix.*
    Get-BrokerMachine
    ```

If successful, the output will include VDA machine details such as HostedMachineName, ProvisioningType, and PublishedApplications. Contact Citrix Technical Support with the results of the cmdlet.

## Machines are in an invalid state

Smart Tools displays the message "N machines are in an invalid state," where N indicates the number of machines. Machines are considered to be in an invalid (or unknown) state when they are in a state other than powered on or powered off.

Check whether Studio lists the machines as being in an unknown state. If they are, make sure that a Controller in the Site can obtain the power state of machines from the host connection.

## Smart Scale event was unsuccessful and Smart Tools couldn't retrieve Delivery Group details

Smart Tools displays the message "Smart Scale event was unsuccessful. Smart Tools couldn't retrieve Delivery Group details."

To resolve this issue, contact Citrix Technical Support with the name of the affected Site and the Delivery Group name.

## Smart Tools couldn't refresh the components for the Site

Smart Tools displays the message "Smart Tools couldn't refresh the components for the Site."

To resolve this issue, contact Citrix Technical Support with the name of the affected Site and Delivery Group.

## No machines are available in the Delivery Group to power on or off

Smart Tools displays the message "No machines are available in the Delivery Group to power on or off."

This issue can occur if Smart Scale attempts to power a certain number of machines on or off, but the Machine Catalog associated with the Delivery Group does not contain any machines that are available for the power action to be completed. For example:

*  Smart Scale tries to power on three machines, but all the machines in the Machine Catalog are already powered on.
*  Smart Scale tries to power off three machines, but the Machine Catalog contains only three machines, and the Delivery Group is configured so at least three machines are always powered on.

To resolve this issue, add more machines to the Machine Catalog associated with the affected Delivery Group.

## Smart Scale is not powering machines on or off as expected and no events are displayed

Smart Scale should power a certain number of machines on or off at a specified time, but no scaling actions have occurred. For example, three machines are supposed to power on at 8:00 AM according to the scaling policy, but no machines have been powered on.

To resolve this issue, perform the following actions:

1.  Verify the time zone of the Delivery Group matches the time zone displayed for the Delivery Group in Studio. If they don't match, sync the Site data. To do this, click the **Site Details** tab and then click **Sync Site Data**.
1.  Verify the power state of the VDAs in Studio.

## Smart Tools experienced a temporary error (Bad Gateway) and can't retrieve the machine details

Smart Tools displays the message "Smart Tools experienced a temporary error (Bad Gateway) and can't retrieve the machine details."

This message occurs if Smart Tools can't communicate with the Virtual Apps and Desktops service or Virtual Desktops Essentials. If this error persists, contact Citrix Technical Support with your Citrix Cloud account name (or Citrix ID) and Site name.

## Smart Scale event was unsuccessful. Smart Tools could not perform any power actions

Smart Tools displays the message "Smart Scale event was unsuccessful. Smart Tools could not perform any power actions."

To resolve this issue, contact Citrix Technical Support with the name of the affected Site and Delivery Group.

## Smart Tools can't find any machines in the Delivery Group

Smart Tools displays the message "Smart Tools can't find any machines in the Delivery Group." This message can occur if Smart Tools experiences a server side error or if Smart Tools attempts to retrieve VDA information from the Smart Tools database, but no VDA information exists.

If this error persists, contact Citrix Technical Support with the name of the affected Site and Delivery Groups.
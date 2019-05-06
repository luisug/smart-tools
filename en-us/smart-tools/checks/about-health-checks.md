---
layout: doc
---
# Citrix health checks

With the Smart Tools Agent installed on your Virtual Apps and Desktops Site, Smart Tools can perform a wide variety of health checks that gauge the health and availability of the Delivery Controllers and VDAs in your Site. This article describes the checks available, requirements for running checks, and how to find additional checks.

## Checks that run automatically

When you initially add your Site, Smart Tools runs [Site Health Checks](#site-health-checks) on your Site by default. These checks run on the Delivery Controllers in your Site and display results for the Delivery Controllers, Delivery Groups, and Machine Catalogs.

## Checks targeting other machines

Citrix provides several checks that help you identify possible causes for common issues, verify StoreFront certificates, and optimize the machines in your environment. These checks are:

*  [VDA Health Checks](#vda-health-checks)
*  [StoreFront Checks](#storefront-checks)
*  [Delivery Controller Configuration Checks](#delivery-controller-configuration-checks)
*  [Citrix Optimizer Checks](#citrix-optimizer-checks)
*  [Citrix Provisioning Checks](#citrix-provisioning-checks)
*  [License Server Checks](#license-server-checks)
*  [Product LifeCycle Checks](#product-lifecycle-checks)

These checks appear in the Perform Checks menu by default. To run these checks, either on-demand or on a schedule, you must specify the machines that you want the check to target.

### System requirements for targeted machines

Before running any machine-targeting checks, ensure the machines where you intend to run the check meet the following system requirements:

*  File and Printer Sharing is enabled.
*  Windows Remote Management (WinRM) is enabled. For instructions, see [Installation and Configuration for Windows Remote Management](https://msdn.microsoft.com/en-us/library/aa384372(v=vs.85).aspx) on the Microsoft web site.
*  Windows Management Instrumentation (WMI) is enabled. For instructions, see the section "Automatic agent installation on VMs provisioned on Citrix XenServer" in [Install or remove the Citrix Smart Tools Agent]](en-us/smart-tools/smart-tools-agent/install-remove-smart-tools-agent.html).

Some checks might have additional requirements which are included in the descriptions in this article.

### Required permissions for targeted machines

If you use a Domain Users account with Smart Tools, this account must belong to the local Administrators group on both the Delivery Controllers in the Site and on the targeted machines.

## Site Health Checks

Site Health Checks provide a comprehensive evaluation of all the [FMA services](https://support.citrix.com/article/CTX139415) including their database connectivity on your Delivery Controllers. Citrix recommends you run these checks at least once daily. Site Health Checks verify the following conditions:

*  A recent site database backup exists
*  Citrix broker client is running for environment test
*  Citrix Monitor Service can access its historical database
*  Database connection of each FMA service is configured
*  Database can be reached by each FMA service
*  Database is compatible and working properly for each FMA service
*  Endpoints for each FMA service are registered in the Central Configuration service
*  Configuration Service instances match for each FMA service
*  Configuration Service instances are not missing for each FMA service
*  No extra Configuration Services instance exists for each FMA service
*  Service instance published by each FMA Service matches the service instance registered with the Configuration service
*  Database version matches the expected version for each FMA service
*  Each FMA service can connect to Configuration Logging Service
*  Each FMA service can connect to Configuration Service

> **Note**:
>
> Smart Tools executes all of these checks when Site Health Checks are run on-demand or scheduled to run at a later time. You cannot disable individual items within the checks.

If any of the checks return a negative result, Smart Tools displays an alert for the affected components, recommends a fix to resolve the issue, and provides links to other Citrix resources so you can learn more about the issue and its resolution.

## LTSR Compliance Checks

LTSR Compliance Checks verify that the Delivery Controllers and VDAs in your Site are running the correct version of Virtual Apps and Desktops LTSR.

> **Note**:
>
> LTSR Compliance Checks only evaluate Delivery Controllers and VDAs. To verify LTSR compliance of other components in your Site, run the LTSR Assistant as described in [CTX209577](https://support.citrix.com/article/CTX209577) in the Citrix Knowledge Center.

### Requirements

To run the LTSR Compliance Check successfully, the Delivery Controllers and VDAs in your Site must meet the following requirements:

*  Support for PowerShell 2.0, at a minimum.
*  Windows Firewall allows inbound ICMP Echo requests.
*  Windows Remote Management (WinRM) is enabled.
*  Port 80 allows inbound connections for the Virtual Apps and Desktops PowerShell SDK. (Delivery Controllers only)
*  Port 5985 allows inbound connections for Windows Remote Management. (Delivery Controllers and VDAs)

For a complete list of requirements, see [CTX209577](https://support.citrix.com/article/CTX209577) in the Citrix Knowledge Center.

If the Delivery Controllers and VDAs in your Site don't meet these requirements, Smart Tools will fail to run LTSR Compliance Checks and will display an error status for the checks on the Site's health report.

### How LTSR Compliance Checks are performed

Smart Tools runs the Citrix LTSR Assistant tool on the Delivery Controllers and VDAs in your Site and generates compliance data that is analyzed through Citrix Insight Services. If any Delivery Controllers or VDAs require LTSR updates, Smart Tools displays alerts for the affected machines. Smart Tools does not display compliance reports when performing this check. For more detailed compliance information, run the LTSR Assistant on the affected machines as described in [CTX209577](https://support.citrix.com/article/CTX209577).

By default, Smart Tools runs the latest version of the LTSR Assistant when performing these checks. If your Delivery Controllers already have the latest version of the tool installed, Smart Tools runs the installed tool to perform the checks. If your Delivery Controllers have an older version installed, Smart Tools installs the latest version hosted by Smart Tools on your Delivery Controllers and runs the checks.

When you run LTSR Compliance Checks for the first time (for example, after you add your Site to Smart Tools), Smart Tools sends you an email notification with the check results. The email displays the machines checked and the number of warnings, if any, for each one. Smart Tools sends this notification separately from notifications for Site Health Checks.

### LTSR alerts

Smart Tools displays alerts from LTSR Compliance Checks as Warnings. If any Delivery Controllers are out of compliance, Smart Tools displays an alert for each affected Controller. If any VDAs are out of compliance, Smart Tools displays a single alert for the Machine Catalog to which they belong.

![LTSR Compliance Checks report for Machine Catalogs](/en-us/smart-tools/media/ltsr-checks-machine-cats-report.png)

## VDA Health Checks

VDA Health Checks identify possible root causes for common VDA registration and session launch issues.

> **Important**:
>
> Ensure the machines where you intend to run this check meet the requirements specified in [System requirements for targeted machines](#system-requirements-for-targeted-machines). Otherwise, the check will fail.

For VDA registration, the following checks are performed:

*  VDA software installation
*  VDA machine domain membership
*  VDA communication ports availability
*  VDA services status
*  VDA Windows firewall configuration
*  VDA communication with each Controller
*  VDA registration status

For session launch, the following checks are performed:

*  Session launch communication ports availability
*  Session launch services status
*  Session launch Windows firewall configuration

## StoreFront Checks

StoreFront Checks validate the service status, connectivity to Active Directory, Base URL setting, IIS Application Pool version, and the SSL certificates for StoreFront. This check verifies the following conditions:

*  Citrix Default Domain Services is running
*  Citrix Credential Wallet services is running
*  The connectivity from the StoreFront server to Active Directory port 88
*  The connectivity from the StoreFront server to Active Directory port 389
*  Base URL has a valid FQDN
*  The correct IP address from the Base URL can be retrieved
*  IIS application pool is using .NET 4.0
*  Whether or not the certificate is bound to the SSL port for the host URL
*  Whether or not the certificate chain is complete
*  Whether or not certificates have expired
*  Whether or not a certificate is expiring soon (within 30 days)

> **Important**:
>
> Ensure the machines where you intend to run this check meet the requirements specified in [System requirements for targeted machines](about-health-checks.html#system-requirements-for-targeted-machines). Otherwise, the check will fail.

## Delivery Controller Configuration Checks

This check verifies whether or not the following Delivery Controller issues exist, based on Citrix recommendations for Virtual Apps and Desktops Sites:

*  One or more Delivery Controllers in the Site are in a failed state.
*  There is only one Delivery Controller in the Site.
*  Delivery Controllers are of different versions.

### Delivery Controller requirements

In addition to the [system requirements for targeted machines](#system-requirements-for-targeted-machines), ensure that at least one Delivery Controller in the Site where you intend to run this check is powered on, the Broker Service is running, and the database connection is working.

## Citrix Optimizer Checks

This check recommends optimizations to improve the performance of XenDesktop components on Windows systems. The check includes OS-specific templates for enabling or disabling Windows services, disabling scheduled tasks, removing applications, and so on according to Citrix recommendations and best practices.

> **Important**:
>
> Ensure the machines where you intend to run this check meet the requirements specified in [System requirements for targeted machines](#system-requirements-for-targeted-machines). Otherwise, the check will fail.

The check includes the following templates:

*  Windows 7 SP1
*  Windows 8.1
*  Windows 10 Revision 1703 and 1709
*  Windows 10 LTSB
*  Windows Server 2008 R2
*  Windows Server 2012 R2
*  Windows Server 2016

When you run the check, you must select the Delivery Controllers or VDAs that you want the check to target. After the check runs, any issues that are found appear on the Site's Health Alerts page. The alerts for these items provide guidance and instructions for performing the recommended optimizations. You can also download this guidance as a report by clicking View Reports. For more information about the reports generated from checks, see View reports from health checks.

## Citrix Provisioning Checks

Citrix Provisioning Checks verify Citrix Provisioning status and configuration.

> **Important**:
>
> Ensure the machines where you intend to run this check meet the requirements specified in [System requirements for targeted machines](#system-requirements-for-targeted-machines). Otherwise, the check will fail.

The checks verify the following conditions:

*  Installation of Provisioning Server and Console
*  Whether or not the Inventory executable is running
*  Whether or not the Notifier executable is running
*  Whether or not the MgmtDaemon executable is running
*  Whether or not the StreamProcess executable is running
*  Whether or not the Stream service is running
*  Whether or not the Soap Server service is running
*  Whether or not the TFTP Service is running
*  PowerShell minimum version
*  Database and PVS server availability
*  License Server connectivity
*  PVS Update Check
*  Whether or not the PXE service is running
*  Whether or not the TSB service is running

## License Server Checks

License Server Checks verify License server status, SA eligibility date compatibility, and provides license upgrade suggestions.

These checks verify the following conditions:

*  License Server connectivity from the Delivery Controller
*  License Server firewall remote access status
*  Citrix Licensing service status
*  License Server grace period state
*  License Server ports connectivity
*  Whether or not the CITRIX vendor daemon is running
*  Whether or not system clocks are synchronized
*  Whether or not the Citrix Licensing service is running under the Local Service account
*  Presence of the CITRIX.opt file
*  License SA eligibility date
*  Citrix License Server Update
*  Whether or not the License Server certificate is in the Delivery Controller's trusted root store

### License Server Checks requirements

In addition to [system requirements for targeted machines](#system-requirements-for-targeted-machines), ensure that the License Server where you intend to run this check is joined to a domain. Smart Tools does not support License Servers that are not joined to a domain.

> Important:
>
> License Server Checks do not support DNS aliases for License Servers. If you specify the License Server using a DNS alias, the checks will fail. Instead, specify targeted License Servers using the FQDN.

## Product LifeCycle Checks

Product LifeCycle Checks verify end of life (EOL) and end of maintenance (EOM) status of Delivery Controllers and other Virtual Apps and Desktops components. The checks also provide recommendations for available LTSR Cumulative Updates, new LTSR versions, and new Current Releases. For more information about lifecycle milestones for Virtual Apps and Desktops, see [https://www.citrix.com/support/product-lifecycle/milestones/citrix-virtual-apps-and-desktops.html](https://www.citrix.com/support/product-lifecycle/milestones/citrix-virtual-apps-and-desktops.html).

> **Important**:
>
> Ensure the machines where you intend to run this check meet the requirements specified in [System requirements for targeted machines](#system-requirements-for-targeted-machines). Otherwise, the check will fail.

The following checks are performed:

*  End of maintenance check
*  End of life check
*  Availability of new Current Releases
*  Availability of new Cumulative Updates for LTSR Release
*  Availability of new LTSR Programs

## Add or remove checks

In addition to the checks that are included when you initially add your Site to Smart Tools, Citrix provides more checks that you can add to Smart Check at any time. These checks are stored in the Checks Library.

### To add checks

To add a check from the Checks Library, simply click the plus sign (+) on the check you want to add. The check appears on the **Perform Checks** menu in Smart Check.

![Perform Checks menu with catalog check selected](/en-us/smart-tools/media/custom-check-menu-v2.png)

> **Note**:
>
>After you use the newly added check, the **New** flag disappears from the check item in the **Perform Checks** menu.

You can also jump to the Checks Library easily from within Smart Check. Use one of the following methods:

*  Click **Configure** and then click **Find more checks**.
*  Click the **Perform Checks** menu and then click **Find More Checks**.

### Remove checks from the Perform Checks menu

If you no longer want to use a check you added from the Checks Library, you can remove it. When you remove checks from one Site, Smart Tools removes them for all Sites that you use with Smart Check. After you remove a check, it no longer appears in the Perform Checks menu or on the Configuration page for your Site. Additionally, the check tile in the Checks Library displays the Add (plus sign) icon, indicating you can add it again to Smart Check.

1.  From the Smart Tools menu, click **Smart Check**, locate the Site you want, and click **View**.
1.  From the **Health Alerts** page, click **Configure** and then select the check you want to remove.
1.  Click the trash can icon to remove the check. A message appears, asking you to confirm you want to remove the check.
1.  Click **Remove**.
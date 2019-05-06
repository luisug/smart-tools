---
layout: doc
---
# What's new in Smart Tools

## December 4, 2018

**Smart Scale deprecation** -- Smart Scale has been deprecated and will reach End of Life on May 31, 2019. At that time, Smart Scale will be removed from Smart Tools. All articles in the Smart Tools documentation that mention Smart Scale now display a deprecation notice. After May 31, 2019, all Smart Scale content will be removed from the documentation.

## October 24, 2018

**Smart Tools Agent enhancements** -- The Smart Tools Agent includes the following enhancements:

*  When installing the latest version of the agent, Site credentials are encrypted and salted and stored in the registry on the Delivery Controller where the agent is installed.
*  For older agents that are upgraded through the Smart Tools interface, Smart Tools acquires the Site credentials without the need for customer interaction. The Site credentials are encrypted and stored in the Delivery Controller registry. Site credentials that were previously stored in the Smart Tools service database are removed.
*  To update existing Site credentials, customers can use either the Smart Tools interface or run a PowerShell cmdlet for additional security.

**Smart Check notification enhancements** -- If checks can't run due to invalid Site credentials or connection issues between Smart Tools and the Delivery Controller, Smart Check email notifications include additional information for resolving these issues, including the affected Delivery Controllers.

**Additional requirement for License Server Checks** -- To run License Server Checks, the License Servers you target must be joined to a domain. See [License Server Checks requirements](/en-us/smart-tools/checks/about-health-checks.html#license-server-checks-requirements).

## August 28, 2018

**Manually add Site components** -- Instead of using Citrix Checks to locate StoreFront, License, and Provisioning servers that are used with a Virtual Apps and Desktops Site, you can add these components manually from either the Site's Health Alerts page or the Site Details page. For more information, see [Add Site components](/en-us/smart-tools/checks/add-site-components.html).

## July 12, 2018

**Save check configurations manually** -- When configuring checks, the Configuration page in Smart Check now includes a Save button so you can save all changes to schedules or targeted machines manually. This allows Smart Tools to save changes more efficiently, making only one call to the service database instead of multiple calls for each change made. Smart Tools also displays a banner to remind you to save your changes.

## June 14, 2018

### Smart Build and Smart Migrate features deprecated

The following functions are no longer available in Smart Tools:

*  Creating and modifying blueprints with the Blueprint Designer
*  Creating and modifying scripts with the script editor
*  Storing blueprints and scripts in the Library
*  Deploying blueprints and scripts
*  Creating and modifying resource locations
*  Installing the Smart Tools Agent on a machine to act as a connector
*  Connecting to Smart Tools to migrate a XenApp 6.x farm to a XenApp and XenDesktop 7.x deployment
*  Running migration scripts for migrating from a XenApp 6.x deployment to a XenApp and XenDesktop 7.x deployment
*  Creating custom checks and custom alerts
*  Unmanaging machines

### Deprecated REST APIs

The following REST APIs related to Smart Build functions and are no longer available in Smart Tools:

*  Blueprint API
*  Deployment Profile API
*  Download API
*  Jobs API
*  Process Instance API
*  Provider API
*  Scripts API
*  Servers API
*  Share API

### Deprecated documentation content

Articles related to Smart Build and Smart Migrate functions have been removed from the Smart Tools product documentation. The remaining articles have been restructured to enhance customers' ability to find information quickly. Content in certain articles has been consolidated or reworked as appropriate to remove references to Smart Build or Smart Migrate functions.

### Terminology and user interface changes

The following changes have been made due to deprecation of Smart Build and Smart Migrate features:

*  References to "Site Agent" in Smart Tools documentation have been changed to "Smart Tools Agent." Any remaining references to the Site Agent in the Smart Tools browser interface will be changed in a subsequent release.
*  The Checks and Blueprints catalog has been renamed to "Checks Library."

### Deprecated known issues

The following known issues are no longer present in Smart Tools due to deprecation of Smart Build and Smart Migrate features:

*  Smart Tools does not send email notifications for server registrations, default monitoring alerts, and blueprint and script deployment status, even if email notifications are enabled. (CAM-8649)
*  When selecting a XenApp 7.x controller for migration, Smart Tools might display controllers that are powered off as well as controllers that are powered on. (CAM-4178)
*  When deploying a blueprint, the deployment times out if it takes longer than 24 hours to complete. (CAM-6980)
*  When a blueprint containing a **Mount Volume** step is deployed to a Citrix CloudPlatform resource location, the Mount Volume configuration steps are not displayed in the Smart Tools UI.
*  For non-root user accounts, agent installation fails on a machine that runs Ubuntu operating system on vSphere resource location.
*  Error message appears after you add a check or blueprint to your account and click **Actions > View**:  `This blueprint is invalid and it cannot be loaded`
*  If a blueprint deployment is unsuccessful, the step output does not refresh and display the appropriate error message in the Smart Tools UI.

### Additional changes

*  **Smart Tools Agent installer renamed** -- The Smart Tools Agent executable file is now called **CitrixSmartToolsAgent.exe**.

*  **LTSR Compliance Checks no longer run by default** -- When you add a Site to Smart Tools and then click **Get Started** in Smart Check, Smart Tools no longer runs LTSR Compliance Checks by default. Only Site Health Checks are run. If your Site uses an LTSR version of Virtual Apps and Desktops, you can run LTSR Compliance Checks on demand or schedule them to run at regular intervals.

*  **Update Checks and Apps and Desktops Checks have been removed** -- When you add a new Site to Smart Tools, Smart Check runs only Site Health Checks and LTSR Checks by default.

*  **Additional checks in the Perform Checks menu** -- Checks such as VDA Checks, StoreFront Checks, and Delivery Controller Configuration Checks now appear in the Perform Checks menu in Smart Check alongside Site Health Checks. For the complete list of added checks, see [Checks targeting other machines](/en-us/smart-tools/checks/about-health-checks.html#checks-targeting-other-machines).

*  **Updated issue totals in Smart Check** -- The total number of issues that Smart Check displays on the Health Alerts page now includes only Warnings and Errors. Notifications are not included in the total.

*  **Enhanced Smart Check notification emails** -- Smart Check notification emails now include the issues found for all components that Smart Check can evaluate. If a component isn't present in a Site (for example, Citrix Provisioning), the email displays no issues found for that component. For more information, see [Manage notifications](/en-us/smart-tools/checks/manage-alerts-notification-checks.html#manage-notifications)

*  **Increased visibility for newly added checks** -- When you add a check from the Checks Library to Smart Check, the check appears in the Perform Checks menu with the "New" flag. This allows you to find new checks easily in the menu. The flag disappears after you use the check.

## April 26, 2018

*  **New Citrix Checks available for Smart Check** -- Several new Citrix Checks help you perform in-depth checks for Site components as well as Citrix License Server and Citrix Provisioning. These checks are:
    *  **Citrix StoreFront Checks**: Replaces StoreFront Certificate Checks. In addition to validating SSL certificates for StoreFront, this check validates StoreFront service status, Active Directory connectivity, Base URL setting, and IIS Application Pool version.
    *  **Citrix Provisioning Checks:** Verifies Citrix Provisioning status and checks several aspects of Citrix Provisioning configuration.
    *  **Citrix License Server Checks:** Verifies License server status, SA eligibility date compatibility, and provides license upgrade suggestions.
    *  **Citrix Life Cycle Checks:** Verifies End-of-Life and End-of-Maintenance status on Delivery Controllers and other Site components and provides LTSR and Current Release update recommendations.

    For complete descriptions of these checks, see [About health checks](/en-us/smart-tools/checks/about-health-checks.html).

*  **Notification alerts in Smart Check** -- In addition to Warning and Error alerts, Smart Check now includes a new Notification alert type that provides additional information about a particular condition in your Site, without the urgency that a Warning or Error alert might convey.
*  **Streamlined Perform Checks menu** -- The **Perform Checks** menu in Smart Check now includes default checks and checks added from the Checks and Blueprints catalog in a simple uncategorized list. For more details, see [Citrix health checks](/en-us/smart-tools/checks/about-health-checks.html#checks-targeting-other-machines).
*  **Enhanced Alert Definition Template** -- When you create custom alerts in Smart Check, you can add environment-specific data such as service instances, user account SIDs, database server names, and so on to the Fix Description field in the Alert Definition Template, as well as the Issue Description field. The template also includes Static Description and Static Fix Description fields so you can supply actionable content in the event the instance data can't be acquired.
*  **Enhanced Smart Check emails** -- The notification emails that Smart Check sends now have an improved look and feel and are sent only once daily after the last scheduled check of the day finishes running.
*  **Citrix Checks reports** -- Several Citrix-provided checks now provide summary reports after they finish running. These reports include a concise breakdown of the conditions that were checked and whether or not an alert was generated. Simply click View Reports and select the report you want to view after the checks finish running. For more information about these reports, see [View reports from health checks](/en-us/smart-tools/checks/view-reports-health-checks.html).

## December 21, 2017

*  **Blueprint Catalog renamed** -- The Blueprint Catalog has been renamed to Checks and Blueprints.
*  **Easier catalog navigation of custom checks** -- Citrix Checks now appear at the top of the Checks and Blueprints catalog. It's now easier to locate Citrix-provided custom checks and add them to Smart Check.
*  **Catalog link added to Smart Check** -- Smart Check now included links to the Checks and Blueprints catalog so you can find custom checks more easily. You can find these links in the Perform Checks menu and on the Smart Check Configuration page.

## October 10, 2017

*  **Smart Scale enhancement for multiple Machine Catalogs** -- When powering on machines in a Delivery Group that is associated with multiple machine catalogs, Smart Scale balances the number of machines powered on across all associated machine catalogs. For customers who use multiple machine catalogs in Delivery Groups for high availability, this enhancement prevents Smart Scale from concentrating power-on actions in a single machine catalog. For more information, see [Scaling across multiple machine catalogs](/en-us/smart-tools/scale/about-scale.html#scaling-across-multiple-machine-catalogs).
*  **Smart Check enhancements** -- The following enhancements have been added to Smart Check:
*  Controlling automatic Site discovery -- Customers can control automatic discovery of Virtual Apps and Desktops Sites from Call Home or Citrix Scout diagnostics uploads in Citrix Insight Services. Customers can enable or disable discovery from uploads or select which Sites to hide without disabling discovery entirely. Customers can easily manage the Sites that appear in Smart Check and ensure that any non-functional Sites are removed. For more information, see [Remove a Site discovered through Call Home or Citrix Scout](/en-us/smart-tools/install-configure/discover-site.html#remove-a-site-discovered-through-call-home-or-citrix-scout).
*  **Custom check removal** -- Smart Tools users who use custom checks from the Blueprint Catalog can remove those checks from Smart Check when they are no longer needed. Once removed, the custom checks no longer appear in the Perform Checks menu or on the Configuration page in Smart Check.
    > **Note**:
    >
    > The custom checks and alerts features have been deprecated and are no longer available in Smart Tools. For more information, see [Smart Build and Smart Migrate features deprecated](#smart-build-and-smart-migrate-features-deprecated) in this article.

## September 11, 2017

*  **Smart Scale capacity and registration enhancements** -- When determining capacity for a given Delivery Group, Smart Scale only considers machines that are currently registered with the Site for powering on or off. Machines that are unregistered are ignored. Additionally, Smart Scale records registration events and maintenance mode status in the new Machine Status tab. For more information, see [About Smart Scale](/en-us/smart-tools/scale/about-scale.html) and [View Site details](/en-us/smart-tools/install-configure/view-modify-site.html#smart-scale-site-information).
*  **Smart Check enhancements** -- The following enhancements have been added to Smart Check:
    *  **Custom alerts limit increase and easier uploading** -- You can upload up to 500 custom alerts to your Smart Tools account. You can upload your alerts all at once or incrementally. Smart Check only overwrites alerts if you upload content that matches an existing UUID.
    *  **Custom check removal** -- When a custom check is deleted from Smart Tools or unpublished from the Blueprint Catalog, Smart Tools removes the custom check from users who previously added the check to their Smart Tools account. Any reports produced by the custom check are retained for the Site.
        > **Note**:
        >
        > The custom checks and alerts features have been deprecated and are no longer available in Smart Tools. For more information, see [Smart Build and Smart Migrate features deprecated](#smart-build-and-smart-migrate-features-deprecated) in this article.
    *  **Last run checks on Health Report** -- The Health Report for a Site now displays the 10 most recent health checks that were run.
*  **Platform monitoring, operations, and scaling functions removed** -- Platform functions involving operational tasks and monitoring and scaling blueprint deployments have been removed from Smart Tools. These functions include:
    *  Adding manual or auto-scaling actions, operational tasks, and monitoring actions to blueprints in the Blueprint Designer. The Operations and Scale & Redundancy tabs and the Monitor built-in step have been removed.
    *  Configuring a blueprint deployment. The Scale page is no longer displayed in the deployment wizard.
    *  Adding monitoring actions to a completed blueprint deployment using the **Manage > Monitor** tab. This includes creating server metrics and creating and using alerts to run scripts or blueprints.
    *  Creating and scheduling operational tasks to a completed blueprint deployment using the **Manage > Operations** tab.
    *  Configuring manual or automatic scaling of machines in a completed blueprint deployment using the **Manage > Scale & Redundancy** tab.
    *  Monitoring API. The Smart Tools REST API no longer includes monitoring functions or parameters. If you currently use the REST API in an application, any monitoring calls that are made to Smart Tools are no longer recognized.
    *  Existing monitoring, operations, and scaling actions in active deployments. These actions have been stopped and cannot be restarted. If email notifications were configured as part of a monitoring action or operational task, these notifications will no longer be sent.

## August 7, 2017

*  **Custom health check support for Storefront, Citrix Provisioning, and License Server** -- Perform health checks for the Storefront, Provisioning, and License Server machines associated with your Site using custom health checks. When you run the custom check, you can target the machines you want to evaluate. Results from these checks are displayed on the Health Alerts page and are included in summary email notifications, along with the Delivery Controllers, machine catalogs, and Delivery Groups in your Site.
    ![Health Alerts diagram with Storefront, Provisioning, and Licensing servers highlighted](/en-us/smart-tools/media/lic-sf-pvs-health-alerts-page.png)

*  **Power off delay for Smart Scale** -- Smart Scale now enables you to delay powering off machines for a predefined period of time. If users need to use their dedicated desktops after-hours, this delay ensures they can create a session without having Smart Scale power it off automatically. Smart Scales only powers off the machine after users have logged off.
    ![Smart Scale Advanced Settings menu with Power Off Delay option highlighted](/en-us/smart-tools/media/power-off-delay.png)

*  **Smart Scale support for scheduling minimum percentage of machines** -- When creating schedules in Smart Scale, you can specify the percentage of machines in the Delivery Group to keep powered on. As the number of machines in your Delivery Group changes, Smart Scale increases or decreases the minimum number automatically.
    ![Smart Scale Edit Schedule dialog with Min % of Machines On option highlighted](/en-us/smart-tools/media/min-percent-machines.png)

*  **VDI-in-a-Box migration support removed** -- Support for migrating from VDI-in-a-Box 5.4 to XenDesktop 7.x has been removed from Smart Migrate.
*  **Failover and failback blueprint and management functions removed** -- Failover and failback actions that were available in Smart Build's Blueprint Designer and in the Manage tab have been removed.

## June 28, 2017

*  **Smart Check custom checks enhancements** -- If you use custom tools to perform health checks on your Site, Smart Tools now includes a check blueprint you can use specifically for deploying your custom tools. When creating your custom check, you can specify the machine types that users can target (for example, Delivery Controllers or VDAs). Additionally, you can publish the check blueprint to the Blueprint Catalog and ensure only the Smart Tools users you specify can use it. When those users add your custom check to Smart Check, they can select the machines they want to target and enter any parameters that your check requires.
    > **Note**:
    >
    > This feature has been deprecated and is no longer available in Smart Tools. For more information, see [Smart Build and Smart Migrate features deprecated](#smart-build-and-smart-migrate-features-deprecated) in this article.
*  **Smart Check alerts enhancement** -- Smart Check alerts now include additional Site information in alert descriptions such as machine names, SIDs, service instance names, and database names. For example, an alert for backing up Site databases now displays the affected database names, database server, and the number of days since the last backup. Smart Check acquires this data from the Site's information in Citrix Insight Services. If Smart Check can't find this data when needed, Smart Check displays a general description of the issue.
*  **Email notification enhancements for Smart Scale** -- Email notifications for Smart Scale have been enhanced to reflect when Smart Scale is experiencing errors (for example, powering on machines failed or is taking longer than expected) and when Smart Scale has recovered from those issues. Smart Tools sends a notification only once for each issue state (error or recovered). By default, email notifications are turned off.
*  **XenApp SDK requirements for Smart Migrate** -- To successfully migrate from XenApp 6.x to XenApp 7.x, Smart Tools requires the XenApp 6.5 PowerShell SDK be present on the XenApp 7.x Controllers. When migrating to XenApp 7.13, this SDK is not installed by default when installing XenApp 7.13, so you must install the SDK manually before using Smart Migrate.

## May 22, 2017

*  **Smart Check custom checks and alerts** -- If you use custom tools to perform health checks on your Site, you can deploy them to your Site using a blueprint and use Smart Check to display triggered alerts. You can create your own custom alerts and add them to Smart Check or use Smart Check's library of alerts for your custom tools.
    > **Note**:
    >
    > This feature has been deprecated and is no longer available in Smart Tools. For more information, see [Smart Build and Smart Migrate features deprecated](#smart-build-and-smart-migrate-features-deprecated) in this article.
*  **Smart Check custom reports** -- For checks that include reporting, like LTSR Checks, Smart Check now displays those reports on a separate page. Navigate the report list using search-as-you-type and column sorting and download reports as PDF files. For more information, see [View reports from health checks](/en-us/smart-tools/checks/view-reports-health-checks.html).
*  **Smart Scale monitoring enhancements** -- When you add your Site to Smart Scale, monitoring begins by default. You can now turn off monitoring for your Site and continue to access previously-collected monitoring data. Smart Scale can also stop monitoring automatically if you're not using Smart Scale to power manage your Delivery Groups. For more information, see [Turn off Smart Scale](/en-us/smart-tools/install-configure/view-modify-site.html#turn-off-smart-scale).
*  **Enhancements to Smart Check diagnostics uploads** -- Smart Check now makes it easier for you to navigate the Diagnostic Uploads list and locate specific uploads. Use search-as-you-type and column sorting to filter your list and find past uploads fast. For more information, see [Find and modify uploads](/en-us/smart-tools/checks/upload-site-diagnostics-citrix-support.html#find-and-modify-uploads).

## March 29, 2017

*  **Smart Check support for uploading Site diagnostics** -- If you experience an issue with your Site and need assistance, Smart Check now provides a way to securely upload Site diagnostics file to Citrix Insight Services and share it with Citrix Technical Support. For more information, see [Upload Site diagnostics to Citrix Technical Support](/en-us/smart-tools/checks/upload-site-diagnostics-citrix-support.html).
*  **LTSR Checks** -- Smart Check adds LTSR Checks to its growing arsenal of health and update checks for Virtual Apps and Desktops Sites. Using the LTSR Assistant, Smart Check generates compliance data for the Site and displays alerts showing the Delivery Controllers and VDAs that are out of compliance. For more information, see [About health checks](/en-us/smart-tools/checks/about-health-checks.html).

## February 8, 2017

*  **Smart Scale support for Windows Desktop VDI** -- Smart Scale now supports Delivery Groups that include machine catalogs with Windows static persistent or random non-persistent desktops. For more information, see [Smart Scale requirements](/en-us/smart-tools/system-requirements/scale-requirements.html#supported-scaling-options).
*  **Smart Scale support for zero minimum machines** -- When creating scaling schedules for Delivery Groups, you can specify that Smart Scale keep a minimum of 0 (zero) machines powered on for the scheduled time period. Previously, Smart Scale required a minimum of one machine to be powered on for all scaling schedules.
*  **Support for XenServer 7.1** -- Smart Tools now supports resource locations using XenServer 7.1\. Customers can design new blueprints for this new version of XenServer and make them available for deployment.

## December 22, 2016

*  **Service name changes --** Citrix Lifecycle Management is now known as **Citrix Smart Tools**. The following features have also been renamed as services within Smart Tools:

    *  **Design & Deploy is now Smart Build**. This service includes all the current blueprint design and deployment features in Lifecycle Management.
    *  **Update is now Smart Check**. This service includes the current Update feature and pairs it with diagnostic health checks to help you keep your Virtual Apps and Desktops Sites running smoothly.
    *  **Migrate is now Smart Migrate**. This service includes all the current functions for easing migration of your application and policy data from XenApp 6 and 6.5 and VDI-in-a-Box 5.4 to Virtual Apps and Desktops 7.x. Smart Migrate can automate your migration or create scripts you can run to manually migrate your farm or grid.

*  **Smart Check service released** -- Smart Check is a new service that includes all the functions of the former Update feature and adds proactive health checks that help you keep your Virtual Apps and Desktops Sites running smoothly. You can schedule health checks to monitor your Site and Delivery Groups for potential problems and to notify you of applicable updates. For more information about Smart Check, see [Smart Check requirements](/en-us/smart-tools/system-requirements/check-requirements.html).
*  **Windows Server 2016 support** -- Smart Tools supports installing the Smart Tools Agent on servers running Windows Server 2016\. Additionally, the following proof of concept blueprints have been updated to support using Windows Server 2016 machine images:

    *  Virtual Apps and Desktops Proof of Concept blueprint
    *  Simple Virtual Apps and Desktops Proof of Concept blueprint

## September 19, 2016

*  **Support for Citrix CloudPlatform deprecated** -- New resource locations running Citrix CloudPlatform can no longer be added to Lifecycle Management. For existing CloudPlatform resource locations, the following functions continue to be supported:

    *  Modify server details
    *  Create, deploy, and share custom blueprints that are compatible with CloudPlatform resource locations.
    *  Deploy existing Citrix blueprints that are compatible with CloudPlatform resource locations.

*  **On-demand update sync** -- The list of updates for a registered Virtual Apps and Desktops site can be refreshed when needed by clicking **Sync Site Data** on the Site Details tab. Previously, the updates list was refreshed only once per day with no option to refresh on-demand.
*  **Snapshots added to Update task details** -- When installing scheduled updates that include taking a snapshot of the machine beforehand, Lifecycle Management includes a "Create Snapshot" step in the Task Installation Details for the update task.

## September 7, 2016

Lifecycle Management includes Smart Scale support for sites using the Virtual Apps and Desktops service of Citrix Cloud. To learn more, see [Add a Site to Smart Tools](/en-us/smart-tools/install-configure/add-site.html).

## August 1, 2016

*  **Support for multiple Site Agents per site** -- To promote high availability for Virtual Apps and Desktops sites, customers can install the Lifecycle Management Site Agent on each delivery controller in the site. Lifecycle Management designates one Site Agent as "active" while the other Site Agents stand by. If the active Site Agent becomes unvailable, Lifecycle Management can designate another Site Agent as active, so monitoring, scaling, and updating actions can continue uninterrupted.
*  **New Load Index and Session Count scale metrics** -- With load-based scaling or load and schedule-based scaling, customers have a choice of using load index or session count as the criteria for managing load in a selected delivery group. If "Load index" is selected, the default index of 10000 is used to determine when machines are at full load. If "Session count" is selected, the specified maximum number of sessions is used. When all the powered-on machines in a delivery group are at full load, Lifecycle Management uses the buffer capacity
*  **Snapshots for delivery controllers on different host connections** -- When applying updates to Virtual Apps and Desktops delivery controllers, Lifecycle Management offers the option of taking a snapshot before the update is actually applied. If the delivery controllers are not on the same host connection as the VDAs, Lifecycle Management now prompts customers for the resource location where the snapshot should be stored.
*  **Support for XenServer 7.0** -- Lifecycle Management now supports setting up resource locations that are running Citrix XenServer 7.0\. Additionally, blueprint authors can specify XenServer 7.0 as a supported platform when creating or updating blueprints with the Blueprint Designer.
*  **Automatic sharing enabled for Virtual Apps and Desktops Resource Location Setup blueprint** -- When a Citrix Cloud administrator selects the "Use Lifeycle Management" option from within the Virtual Apps and Desktops service to set up a resource location, Lifecycle Management adds the Virtual Apps and Desktops Resource Location Setup blueprint to the administrator's library and shares the blueprint with all other account administrators.
*  **Enhanced REST API Support** -- REST APIs have been added for the following tasks:

*  Publishing or republishing a blueprint to the Blueprint Catalog
*  Removing a published blueprint from the Blueprint Catalog

## June 13, 2016

With Lifecycle Management’s collection of Virtual Apps and Desktops Proof of Concept blueprints, many customers have created their own basic Virtual Apps and Desktops deployments while learning more about the potential for Lifecycle Management.

![Blueprint tile with New Version flag](/en-us/smart-tools/media/clm-xad-bp-new-version.png)

Now, these blueprints have been updated so customers have even more deployment options:

*  **Support for XenApp and XenDesktop 7.9** – Customers can now deploy a Virtual Apps and Desktops proof of concept with XenApp and XenDesktop 7.9 by default.
*  **Support for Microsoft Azure** – The Simple Virtual Apps and Desktops Proof of Concept blueprint now includes support for resource locations using **Microsoft Azure**, as well as Amazon Web Services.
*  **Auto-registration for Smart Scale and Updates** – New sites that are deployed with these blueprints are automatically registered with Lifecycle Management so customers can use them with Smart Scale and Update features. After deployment, these sites appear automatically on the Smart Scale and Upgrades & Updates pages of Lifecycle Management. Customers don’t have to manually add their sites and can start scaling or perusing available updates right away.

Previously, Workspace Cloud customers learned how Lifecycle Management could help them deploy a resource location using the Apps and Desktops Resource Location Setup blueprint.

![Blueprint tile for Virtual Apps and Desktops Resource Location blueprint](/en-us/smart-tools/media/clm-xad-svc-rlcu-bp-new-version.png)

In the new era of Citrix Cloud, Lifecycle Management is once again helping customers using the Virtual Apps and Desktops service to rapidly deploy new resource locations with minimal configuration. With the **Virtual Apps and Desktops service Resource Location Setup** blueprint, customers can:

*  Set up a Citrix Cloud resource location on **Microsoft Azure, or Amazon Web Services**.
*  Deploy a domain controller, two Cloud Connectors, Citrix ADC VPX appliance, and Citrix Gateway.
*  Add optional components such as StoreFront and VDA machines configured for RDS desktops or Server VDI.

## May 16, 2016

Smart Scale enables proactive scaling and power management of machines in a Virtual Apps and Desktops site based on a schedule you define or the level of demand for user sessions. Smart Scale works with the machines in your delivery group to ensure users can connect to their applications and desktops when needed while helping you control machine utilization costs.

![smart-scale-page.jpg](/en-us/smart-tools/media/smart-scale-page.jpg)

Smart Scale includes the following functions:

*  Schedule-based scaling helps you keep a minimum number of machines available on specified days.
*  Load-based scaling ensures you have enough machines powered on for increases in session demand and powers down machines when demand lessens.
*  Schedule- and load-based scaling ensures you have a minimum number of machines available on specified days, increasing that number when demand increases and decreasing that number (to the minimum scheduled) when demand lessens.
*  Adjustable session capacity buffer helps you fine-tune the balance between having machines available to accommodate spikes in demand and reducing machine costs.
*  Delivery group monitoring metrics include number of machines in use, capacity utilization, number of sessions in use, machines in maintenance mode, and load index. If Virtual Apps and Desktops resides in a cloud powered by Amazon Web Services, Smart Scale tracks estimated savings based on the per-instance cost and scaling activity period that you define.
*  Events tab tracks the execution of scheduled events, such as powering machines on or off, and machines entering maintenance mode.
*  Machine Activity tab tracks whether machines are powered on or off.

The Upgrade feature has received the following enhancements:

*  Feature name changed from "Upgrade" to "Update" in the Lifecycle Management menu bar.
*  Feature expanded to include the following functions:
    *  **Upgrades & Updates:** Finds and applies relevant product updates for delivery controllers and VDA machines in a Virtual Apps and Desktops site.
    *  **Migrations** (formerly known as "Upgrades"): Includes the ability to migrate VDI-in-a-Box 5.4 deployments to XenDesktop 7.6, in addition to migrating from XenApp 6.x to XenApp 7.6.

Upgrades & Updates includes the following functions:

*  Find relevant updates for the delivery controller and VDA machines in your site and select the ones you want to apply. Applicable update listing includes links to relevant CTX articles in the Citrix Support Knowledge Center.
*  Use scripts from your Library to execute pre- and post-installation actions during the update process.
*  Specify whether or not to take a snapshot of the delivery controller or master image being updated. If the delivery controller or master image resides in a public cloud, an image template is created instead.
*  Specify a date and time for applying updates and define when to roll out an updated master image to VDA machines.
*  Tasks tab displays status of update actions so you can monitor progress or cancel the action.

REST APIs have been added for the following tasks:

*  Create a script with single or multiple file attachments
*  Update an existing script with single or multiple file attachments
*  Get the content of a script attachment file in the byte array format

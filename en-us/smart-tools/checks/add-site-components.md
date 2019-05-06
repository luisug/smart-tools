---
layout: doc
---
# Add Site components to Smart Tools

By default, Smart Tools can automatically detect the StoreFront, Provisioning, or License servers used with your Site. After you [add your Site](/en-us/smart-tools/install-configure/add-site.html), Smart Tools lists these components in the following locations:

*  On the **Health Alerts** page, Smart Tools displays the number of detected components. Click each component for machine information and alert details.
*  On the **Site Details** page, Smart Tools displays a list of the components detected, including machine name and component type.

If Smart Tools can't detect these components when you add your Site, you can add the missing components using Citrix Checks or you can add them individually.

## Locate components using Citrix Checks

1.  Familiarize yourself with the requirements for running [StoreFront Checks](/en-us/smart-tools/checks/about-health-checks.html#storefront-checks), [Citrix Provisioning Checks](/en-us/smart-tools/checks/about-health-checks.html#citrix-provisioning-checks), or [License Server Checks](/en-us/smart-tools/checks/about-health-checks.html#license-server-checks) to locate the components you want.
1.  Verify the components you want to target meet the [system requirements](/en-us/smart-tools/checks/about-health-checks.html#system-requirements-for-targeted-machines) for running these checks.
1.  Run the checks as described in [Run checks on demand](/en-us/smart-tools/checks/perform-health-checks.html#run-checks-on-demand) or [Schedule checks](/en-us/smart-tools/checks/perform-health-checks.html#schedule-checks).

## Add individual components

To add components of the same type, perform the following steps:

1.  From the Health Alerts page for your Site, click **Add Server** for the StoreFront, Provisioning, or License server you want to add.
    ![Health Alerts page with components highlighted](/en-us/smart-tools/media/health-alerts-diagram-add-components.png)
1.  Enter the FQDN or IP address of the machine. If you want to add multiple machines, click **Add another component**.
    ![Add component dialog with Add another component highlighted](/en-us/smart-tools/media/add-component-dialog.png)
1.  To remove a machine from the list, click the trash icon. The trash icon appears only when you enter data in the field.
1.  Click **Done** to save your changes. Smart Tools displays the added machine on the Health Alerts page.

To add components of differing types, perform the following steps:

1.  From the Health Alerts page for your Site, click **Site Details** and then click **Add Component**.
    ![Add components from Site Details page](/en-us/smart-tools/media/add-components-site-details.png)
1.  Enter the following information:
    ![Add component dialog](/en-us/smart-tools/media/add-component-dialog-2.png)
    *  Enter the FQDN or IP address of the machine you want to add.
    *  Select the machine type: StoreFront, Provisioning, or License Server.
    *  To add more machines, click **Add another component**.
1.  To remove a machine from the list, click the trash icon. The trash icon appears only when you enter data in the field.
1.  Click **Done** to save your changes. Smart Tools displays the added machines under **Components** on the **Site Details** page.

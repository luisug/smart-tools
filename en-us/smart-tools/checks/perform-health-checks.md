---
layout: doc
---
# Perform health checks

## Run initial checks on your Site

After you [add your Site](/en-us/smart-tools/install-configure/add-site.html) to Smart Tools, you can start running health checks by clicking **Get Started** on the Virtual Apps and Desktops Sites page.

![Get Started button highlighted on Smart Check Site card](/en-us/smart-tools/media/smart-check-get-started-card-v2.png)

By default, Smart Tools runs [Site Health Checks](/en-us/smart-tools/checks/about-health-checks.html#site-health-checks) on your Site.

Smart Tools creates a default schedule for running these checks on a daily basis, selecting a time at random between 12:00 AM and 5:00 AM. The time zone for this schedule is the time zone of the first Delivery Controller that Smart Tools discovers.

### Results of initial checks

After a few minutes, Smart Tools discovers the components in your Site and runs the initial checks. When the analysis is finished, Smart Tools displays the Health Alerts page which shows the number of items found for each Site component.

![Health Alerts page with issues count highlighted](/en-us/smart-tools/media/health-alerts-page-with-issues-v2.png)

To view the alerts for the items found, click the Site component with the items you want to see. For more information about managing these alerts, see [Manage Smart Check alerts and notifications](/en-us/smart-tools/checks/manage-alerts-notification-checks.html).

To view your Site's health report after the initial check run, click **View**.

![Site cards on Smart Check Sites page](/en-us/smart-tools/media/smart-check-sites-page-v2.png)

## Run checks on demand

You can run checks on your Site at any time, on demand. You can also create a schedule for your Site to ensure checks are performed on days and at times you specify. The default time zone for determining when scheduled checks will run is the time zone of the first Delivery Controller that Smart Tools discovered when you initially added your Site to Smart Tools.

> **Note**:
>
> If you are running a check that targets specific machines such as VDA Health Checks or Delivery Controller Configuration Checks, ensure the machines meet the requirements described in [System requirements for targeted machines](/en-us/smart-tools/checks/about-health-checks.html#system-requirements-for-targeted-machines).

1.  Click **Smart Check**.
1.  On the **Virtual Apps and Desktops Sites** page, select the Site you want to manage and click **View**. The Health Alerts summary for your Site appears.
1.  Click **Perform Checks** and select the check you want to run.
1.  When prompted, click **Perform Checks Now**.

To view the individual alerts that Smart Tools finds, click a component on the Health Alerts page.

## Schedule checks

1.  From the menu bar, click **Smart Check**.
1.  On the **Virtual Apps and Desktops Sites** page, select the Site you want to manage and click **View**. The Health Alerts summary for your Site appears.
1.  Click **Configure**. The Configuration page appears.
1.  Select checks, such as Site Health Checks, and then click **Run on a schedule**. Citrix recommends scheduling checks to run between midnight and 5:00 AM.
1.  If you selected checks that target specific machines, click **Select Machines** and then select the machines you want to include each time the checks run.
1.  Select the interval (Every day or Every week), time, and day of the week, if applicable, to run the selected checks.
1.  Click **Save Changes** to save your schedule.
1.  When finished, click **Return to Health Report**.

## Perform checks without the Smart Tools Agent

If you choose not to install the Smart Tools Agent on Delivery Controllers in  your Site, you can still use Smart Check to perform manual checks at any time.

To do this, first use Call Home or Citrix Scout to generate diagnostics data. Afterward, in Smart Check, allow Smart Tools to rediscover your Site. Smart Tools uses your Site data to analyze your Site and displays any issues or notifications it finds. You can then address the alerts using your own processes, outside of Smart Tools.

## Failed checks

If Smart Tools cannot run the selected checks, Smart Tools displays the status "Could not run checks." To view the error output for troubleshooting, click **Get error output** for the affected checks. After you correct the issue, you can rerun the checks or wait until the next scheduled run occurs.

In each set of checks, there are a certain number of critical checks that Smart Tools runs. If Smart Tools runs a critical check and it returns a failed response, Smart Tools uses Call Home to perform a diagnostic check on your Site. If any errors are detected, Smart Tools displays them on your Site's health report. If you do not want to enable Call Home for your Site, use Citrix Scout to generate current diagnostics from your Site and then run the checks again.
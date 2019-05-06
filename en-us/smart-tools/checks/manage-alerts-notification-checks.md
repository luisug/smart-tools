---
layout: doc
---
# Manage Smart Check alerts and notifications

After Smart Tools runs checks on your Virtual Apps and Desktops Site, Smart Tools displays the results on your Site's Health Alerts page.

![Health Alerts tab on Smart Check page with check results displayed](/en-us/smart-tools/media/smart-check-health-alerts-page-v2.png)

The Health Alerts page displays the following information:

*  The number of Errors, Warnings, and Notifications from the most recent health checks. Only warnings and errors are included in the Total Issues number.
*  The number of health checks that were completed and when they were performed. You can expand this notification to view more details such as which checks were run, completion status, and the time of the next scheduled run.
*  A visual representation of your Site and the number of items found for each component. Click a component's icon to view more details about the issues or notifications for that component.

> **Note**:
>
> The visual representation of your Site includes only the components that Smart Tools can analyze. Checks for License Servers, StoreFront, and Provisioning Servers must be run either on-demand or according to a schedule you configure. For Sites discovered through Call Home or Citrix Scout, Smart Tools displays issues and notifications only for the Delivery Controllers and Machine Catalogs in the Site. Delivery Groups are not included.

## View your Site's health alerts summary

1.  From the command bar, click **Smart Check**.
1.  On the **Virtual Apps and Desktops Sites** page, locate the site you want to view and click **View**. The Health Alerts page appears.

## Manage alerts

Alerts indicate that Smart Tools has found items of note in your Site after running checks. Smart Tools displays alerts using the following categories:

*  **Errors:** Issues that indicate a problem in your Site. Errors are displayed in red.
*  **Warnings:** Issues that can potentially affect your Site's availability to users or optimal functioning. Warnings are displayed in orange.
*  **Notifications:** Information about available hotfixes, product updates, or other information that might be helpful in keeping your Site healthy. Notifications are displayed in blue.

### View alerts

Alerts are displayed on the Health Alerts page by component. To view the alerts for a component, click the component's icon on the Health Alerts page and then click the component's machine name to expand the list. When you select an alert, Smart Tools displays the alert description, fix recommendations, and links to applicable Citrix Knowledge Center articles.

### Hide alerts

Hiding alerts allows you to manage what Smart Tools displays at any given time. If you want to defer addressing an issue or notification, you can hide the alert so Smart Tools won't remind you of it each time checks are run.

When you hide an alert, Smart Tools removes it from view for all affected components in your Site. Also, all users in your Smart Tools account can no longer see the alert. Hidden alerts are not deleted, but they are subtracted from the total number that Smart Tools displays on the Health Alerts page. Hidden alerts are not included in Smart Tools' email notifications.

To hide alerts, select an alert and then click **Hide Alert**.

To view the hidden alerts for each component in your Site:

1.  From the Health Alerts page, select the component with the hidden alerts you want to view.
1.  Expand the machine with the hidden alerts you want to show.
1.  Click the menu button and then select **Show Hidden Alerts**.

    ![Show Hidden Alerts menu option](/en-us/smart-tools/media/smart-check-site-options-hide-alerts.png)

In the alerts list for each component, Smart Tools displays hidden alerts as dimmed, shaded entries. To stop displaying hidden alerts for the component, click the menu button and select **Don't Show Hidden Alerts**.

### Restore hidden alerts

Restoring a hidden alert displays all occurrences of the alert as normal entries in the alerts list. Restored alerts are also added to the total number of errors and warnings. Restored alerts are also included in Smart Tools' email notifications.

1.  From the Health Alerts page, select the component with the hidden alerts you want to restore.
1.  Expand the machine with the hidden alerts and then click the menu button and select **Show Hidden Alerts**.
1.  Select the alert and click **Restore Alert**. Smart Tools refreshes the alerts list and displays the restored alert as a normal, undimmed entry for each affected component.

## Manage notifications

By default, Smart Tools sends you a daily email notification after the last scheduled health check of the day finishes running. This email includes the total number of warnings and errors found for the following components:

*  Delivery Controllers
*  Machine Catalogs
*  Delivery Groups
*  License Servers
*  StoreFront servers
*  Provisioning Servers

You can disable these notifications at any time.

### To disable Smart Check notifications

1.  From the Smart Tools management console, click **Settings** > **Notifications**.
1.  For **Smart Check issues summary**, click the green toggle button. The button changes to gray and displays "Disabled."

To disable all Smart Tools notifications, including Smart Check, clear the **Send me notifications** check box.

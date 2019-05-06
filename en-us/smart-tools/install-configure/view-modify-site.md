---
layout: doc
---
# View or modify Site details

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

## View Site information

1.  From the Smart Tools management console, click **Smart Check** or **Smart Scale**.
1.  On the **Virtual Apps and Desktops Sites** page, locate the Site you want to manage.
1.  Click **View** (Smart Check) or **View Site** (Smart Scale).

> **Note**:
>
> In Smart Check, Site details are not available for Sites without the Smart Tools Agent installed.

### Smart Check Site information

Smart Check displays updates and task information for the Delivery Controllers and Machine Catalogs in your Site. Select one of the following tabs:

*  **Health Alerts:** Displays the alerts and applicable notifications for the Site components that you select.
*  **Site Details:** Displays the Delivery Controllers in your Site, the Smart Tools Agent version and status for each Delivery Controller, and the Delivery Groups in your Site. On this page, you can install the Smart Tools Agent on the other Delivery Controllers in your Site, update the Full Administrator credentials for the Site, refresh the Site data Smart Check uses, and remove the Site from view on the Smart Check and Smart Scale pages.

### Smart Scale Site information

In Smart Scale, the monitoring, event information, and power status for registered machines in each Delivery Group is displayed. Select one of the following tabs:

*  **Monitoring:** Displays sessions in use, number of machines powered on, number of machines in maintenance mode, and load index. By default, data is displayed for the previous four hours. You can show data up to the previous 30 days.
*  **Events:** Displays the success or failure of executing scheduled items, powering machines on or off, and entering maintenance mode.
*  **Machine Activity:** Displays the current state of events for registered machines in the Delivery Group.
*  **Machine Status:** Displays the following information for machines in the Delivery Group:
    *  Registration and power status
    *  Whether or not the registration or power status was changed by Smart Tools
    *  Maintenance mode status
    *  Whether or not the maintenance mode status was changed by Smart Tools
*  **Site Details:** Displays the Delivery Controllers and the Smart Tools Agent version and status for each Delivery Controller. You can also update the Full Administrator credentials for the Site, synchronize your Site's data with Smart Tools, and remove the Site from the Smart Scale page.

## Edit Site credentials

Your Site credentials are the Citrix administrator credentials that Smart Tools uses to impersonate the Site administrator and execute health checks or monitoring and scaling actions. You might need to edit your Site credentials if your Site did not register successfully when you added it to Smart Tools or if the account credentials were changed in Citrix Studio. You can edit Site credentials through the **Site Details** page or using the Citrix.SmartTools PowerShell module.

> **Notes:**
>
> *  If your Site uses the Virtual Apps and Desktops service in Citrix Cloud, this function is not available.
> *  If you are using the latest version of the Smart Tools Agent, your Site credentials are encrypted and stored in the registry on the Delivery Controller. This registry entry is located at HKLM/Software/WOW6432Node/Citrix/Smart Checks. Smart Tools does not store your Site credentials.
> *  If you are currently using an older version of the Smart Tools Agent, Smart Tools continues to store your credentials. Citrix recommends [upgrading](/en-us/smart-tools/smart-tools-agent/install-remove-smart-tools-agent.html#upgrade-the-agent) to the latest version of the agent so your Site credentials are securely stored on the Delivery Controller. For more information, see [Site credentials for the Smart Tools Agent](/en-us/smart-tools/smart-tools-agent/install-remove-smart-tools-agent.html#site-credentials-for-the-smart-tools-agent).

### To edit Site credentials using Site Details

1.  From the Smart Tools management console, click **Smart Check** or **Smart Scale**.
1.  On the **Virtual Apps and Desktops Sites** page, locate the Site you want to manage and click **View** or **View Site**.
1.  Click the **Site Details** tab and then click **Edit Site Credentials**.
1.  On the **Edit Site** page, enter the username (in _domain\username_ format) and password of the Citrix administrator account you want to use.
1.  Click **Done** to save your changes.

### To edit Site credentials using PowerShell

The Citrix.SmartTools PowerShell module is installed when you install or upgrade to the latest version of the Smart Tools Agent. This module enables you to enter your Site credentials without needing to use the Smart Tools interface.

1.  On the Delivery Controller, open a PowerShell command window.
1.  At the command prompt, type the following commands:

    ```
    import-module Citrix.SmartTools
    Set-SmartToolsCredentials
    ```

1.  When prompted, enter the username (in _domain\username_ format) and password of the Citrix administrator account you want to use.
1.  Close the PowerShell command window. The module does not provide additional feedback when the change is successful.

## Enable or disable event or issue notifications

Smart Tools can send you email notifications when health checks are performed and when Smart Scale experiences or resolves errors. By default, email notifications are disabled.

When enabled, Smart Tools sends email once per day, after the last scheduled check of the day finishes running.

1.  From the Smart Tools command bar, click **Settings**.
1.  Click **Notifications**.
1.  In **Smart Check issues summary**, click the toggle button to enable or disable notifications for Smart Check only.
1.  In **Smart Scale error events**, click the toggle button to enable or disable notifications for Smart Scale only.

To enable or disable all Smart Tools notifications, select or clear **Send me notifications**.

## Sync Site data

By default, Smart Tools syncs the Site data in Smart Check or Smart Scale every four hours. You can manually force Smart Tools to sync the Site data at any time. For example, if you change the time zone of the Delivery Controllers in the Site, you can sync the Site data so Smart Check can reflect the change. However, no checks are performed and health reports are not updated.

1.  From the Smart Tools management console, click **Smart Check** or **Smart Scale**.
1.  On the **Virtual Apps and Desktops Sites** page, locate the Site you want to refresh and click **View** or **View Site**.
1.  Click the **Site Details** tab and then click **Sync Site Data**.

Smart Tools displays a progress bar and refreshes the Site data. This process typically takes a few minutes to complete.

## Remove a Site from Smart Tools

To remove a Site from Smart Tools, uninstall the Smart Tools Agent from all Delivery Controllers as described in [Remove the agent](/en-us/smart-tools/smart-tools-agent/install-remove-smart-tools-agent.html). Afterward, Smart Tools no longer monitors the Site, runs checks, or carries out scaling actions. Also, the Site no longer appears on the Virtual Apps and Desktops Sites page in Smart Check and Smart Scale.

> **Note**:
>
> When you remove a Site, Smart Tools doesn't store any Smart Check alerts that were previously generated from health checks.

### To remove a Site without uninstalling the agent

Use these steps if:

*  Smart Tools still displays the Site even after all agents have been uninstalled.
*  Your Site has many Delivery Controllers and you want to quickly remove the Site without uninstalling all agents.

From Smart Check:

1.  On the Site's card, click the menu button and then click **Remove Site**.
    ![Remove Site on site card](/en-us/smart-tools/media/remove-site-card-smart-check.png)
1.  Click **Remove**.

From Smart Check or Smart Scale:

1.  On the Site's card, click **View** or **View Site**.
1.  Use one of the following methods:
    *  Click the menu button and then click **Remove Site**.
        ![Remove Site menu option](/en-us/smart-tools/media/remove-site-menu.png)
    *  Select **Site Details** and then click **Delete Site**.
1.  Click **Remove**.

### Virtual Apps and Desktops service Sites

Currently, Smart Tools does not provide a function for removing Sites that use the Virtual Apps and Desktops service in Citrix Cloud. If you no longer want to use Smart Scale with your Site, click **Site Details > Disable Scaling** to turn off Smart Scale.

## Turn off Smart Scale

When Smart Scale is turned off, monitoring and power management actions are disabled for all Delivery Groups in the Site. Although new monitoring data is no longer collected, you can still view previously-collected monitoring data.

Smart Tools turns off Smart Scale automatically if none of your Delivery Groups are configured for power management or no Smart Scale events (such as powering machines on or off) have been generated in the last 30 days.

### To turn off Smart Scale manually

1.  From the **Smart Scale** page, locate the Site you want to modify and click **View Site**.
1.  Select **Site Details** and then click **Disable Scaling**.
1.  Click **Turn Off**.

To turn Smart Scale back on, click **Turn ON Smart Scale** from any tab (Monitoring, Site Details, and so on). Afterward, Smart Scale resumes monitoring your Delivery Groups and you can re-enable power management for each Delivery Group in the Site.

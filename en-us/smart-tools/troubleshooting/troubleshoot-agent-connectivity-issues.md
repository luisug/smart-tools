---
layout: doc
---
# Troubleshoot agent and Site connectivity issues

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

This topic provides troubleshooting tips for agent connectivity issues.

## Smart Tools can't connect to agent or agent is offline

If Smart Tools displays the message "Could not connect to agent" or "Agent is offline, verify the following items:

*  The Smart Tools Agent is installed on the affected Delivery Controller.
*  The Smart Tools Agent Service is running.
*  The Smart Tools Agent can connect to Smart Tools.

To verify the Smart Tools Agent is installed on the Delivery Controller, click **Start > Control Panel > Programs > Programs and Features** and locate the **Citrix Smart Tools Agent** entry in the programs list.

To verify the Smart Tools Agent is running, launch the Services console (services.msc) and locate the Smart Tools Agent Service. Verify the Status is **Started** and the Startup Type is **Automatic**.

To verify the Smart Tools Agent can connect to Smart Tools, perform the following actions:

1.  Review [Smart Tools Agent and connectivity requirements](/en-us/smart-tools/system-requirements/connectivity-requirements.html) and ensure your network environment meets the stated port, firewall, and proxy requirements as appropriate.
1.  On the affected Delivery Controller, navigate to C:\Program Files (x86)\Citrix\LifecycleManagement.
1.  Locate the connector.log files and search for the phrase "Could not connect to the Discovery Server." If this phrase is not present, the agent is able to connect to Smart Tools.

## Smart Tools can't connect to the Delivery Controller

Smart Tools displays the message "Smart Tools couldn't connect to the Delivery Controller. Please verify the Delivery Controller is online." To resolve this issue, verify the Delivery Controller is powered on and will accept connections. Verify the connection to the affected Delivery Controller using RDP and enter valid credentials when prompted.

## Username and password for the Delivery Controller are incorrect

Smart Tools displays the message "Username and password for the Delivery Controller are incorrect."

To resolve this issue, re-enter valid Full Administrator credentials by performing the following actions:

1.  From the Smart Tools command bar, click **Smart Scale** and then select the affected Site.
1.  Click **Site Details** and then click **Edit Site Credentials**.
1.  Enter the username and password of a valid Full Administrator account. For more information, see the "Account requirements" section in [Smart Check requirements](/en-us/smart-tools/system-requirements/check-requirements.html#account-requirements) and [Smart Scale requirements](/en-us/smart-tools/system-requirements/scale-requirements.html#account-requirements).

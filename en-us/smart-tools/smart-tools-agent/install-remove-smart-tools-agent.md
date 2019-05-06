---
layout: doc
---
# Install or remove the Citrix Smart Tools Agent

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

The Smart Tools Agent enables communication between Smart Tools and your on-premises Virtual Apps and Desktops Site. You can install the agent using the following methods:

*  Installing through the XenApp and XenDesktop installation media (Version 7.14 through 7.18)
*  Installing through the Virtual Apps and Desktops installation media (Version 7 1808 or later)
*  Installing manually through the Add Site wizard in Smart Check or Smart Scale

To use Smart Check or Smart Scale with your Site, you must install the Smart Tools Agent on at least one Delivery Controller. For more information, refer to the following articles:

*  Agent requirements: [Smart Tools Agent and connectivity requirements](/en-us/smart-tools/system-requirements/connectivity-requirements)
*  Installation instructions: [Add a Site to Smart Tools](/en-us/smart-tools/install-configure/add-site.html)

> **Important**:
>
> Install the Smart Tools Agent only on Delivery Controllers in an on-premises Virtual Apps and Desktops deployment. Do not install the agent on a machine that hosts other Citrix product or cloud service components such as Citrix Cloud Connectors.

## Site credentials for the Smart Tools Agent

When you manually install or upgrade to the latest version of the Smart Tools Agent, you are prompted to enter the credentials of a Citrix Administrator account for the Site. You can enter these credentials using the following methods:

*  Through the Smart Tools Add Site wizard
*  Using the Citrix.SmartTools PowerShell module

The PowerShell module is installed during agent installation. The default location for these modules is C:\Program Files (x86)\Citrix\LifecycleManagement\Modules.

After you enter the Site credentials, they are encrypted and stored in the registry on the Delivery Controller. The registry location is HKLM\Software\WOW6432Node\Citrix\Smart Checks. Smart Tools does not store these credentials.

> **Important:**
>
> If you are using an older version of the Smart Tools Agent, Smart Tools continues to store your Site credentials. Citrix strongly recommends [upgrading the agent](#upgrade-the-agent) so your Site credentials are stored securely on the Delivery Controller.

### To enter Site credentials using PowerShell

1.  On the Delivery Controller, open a PowerShell command window.
1.  At the command prompt, type the following commands:

    ```
    import-module Citrix.SmartTools
    Set-SmartToolsCredentials
    ```

1.  When prompted, enter the username (in _domain\username_ format) and password of the Citrix administrator account you want to use.
1.  Close the PowerShell command window. The module does not provide additional feedback when the change is successful.

## Ensure high availability for the Smart Tools Agent

To ensure Smart Tools can update your Site without interruption, Citrix recommends installing the Smart Tools Agent on multiple Delivery Controllers in your Site.

When you install the Smart Tools Agent on multiple Delivery Controllers, Smart Tools designates one of the Smart Tools Agents as the "active" agent. The active agent monitors the Site and coordinates the actions you specify. The agents residing on the other Delivery Controllers are idle and do not perform any of these activities. However, if the active agent is not available, Smart Tools designates an agent on another Delivery Controller as "active" so monitoring, scaling, and health check tasks can continue.

### To install the Smart Tools Agent on multiple Delivery Controllers

1.  From the Smart Tools management console, go to **Smart Check** or **Smart Scale**.
1.  From the **Virtual Apps and Desktops Sites** page, locate the Site you want to manage and click **View** (Smart Check) or **View Site** (Smart Scale).
1.  Click the **Site Details** tab and then locate the Delivery Controller where you want to install the agent.
1.  Click **Install Agent**. Smart Tools installs the agent on the selected Delivery Controller.

On the Site Details page, the Delivery Controller displays "Online" for the agent status. Additionally, the Delivery Controller displays "Available" to indicate the agent is available to be the active agent if the currently active agent is offline.

## Upgrade the agent

Citrix recommends upgrading the agent when:

*  A new version is released that contains security updates and bug fixes to prevent issues from occurring.
*  The currently installed agent is experiencing issues and preventing other Smart Tools features from working correctly.

To verify the version of the agents currently installed in your Site, click **View > Site Details**. The Site Details page displays a list of all Delivery Controllers in the Site and the agent version installed on each one.

![Site Details with agent version selected](/en-us/smart-tools/media/site-details-ddc-lic-sf-1.png)

### To upgrade the agent

Perform these steps on all Delivery Controllers that have the Agent installed. For a list of Delivery Controllers with the Smart Tools Agent installed, go to **Smart Check** (or **Smart Scale**), click **View** on the Site you want to manage, and then click **Site Details**. The Site Details page also displays the agent version installed.

1.  Log on as an administrator user to the Delivery Controller hosting the agent you want to upgrade.
1.  From a web browser, visit [https://citrix.cloud.com](https://citrix.cloud.com) and sign in to Citrix Cloud using your account credentials.
1.  From the Citrix Cloud management console, locate the Smart Tools tile and click **Manage**.
1.  From the Smart Tools management console, click **Smart Check** or **Smart Scale**.
1.  Click **Add Site**.
1.  Click **Download agent** and save the agent package.
1.  Install the agent: Locate the **CitrixSmartToolsAgent.exe** file and double-click it to launch the installation. Click **Run** when prompted and accept the End User Licensing Agreement. Click **Install**. After installation, the agent registers the Delivery Controller with Smart Tools. After registering successfully, the Add Site wizard displays a green check mark. Click **Finish**.
1.  When prompted, enter the username and password of the Citrix Administrator account for your Site. To ensure your Site credentials are entered in the most secure manner, use the Citrix.SmartTools PowerShell module as described in [To enter Site credentials using PowerShell](#to-enter-site-credentials-using-powershell) in this article.

> **Important:**
>
> Smart Tools does not store the Citrix Administrator password that you supply. Instead, the password is encrypted and stored in the registry on the Delivery Controller. This registry entry is located at HKLM/Software/WOW6432Node/Citrix/Smart Checks.

After you complete the installation, a message appears indicating the agent components have been updated.

## Remove the agent

Removing the agent effectively disables all Smart Tools features. During removal, the agent signals Smart Tools to deregister the Delivery Controller on which it was installed. Because Smart Tools is no longer aware of the Delivery Controller, Smart Check and Smart Scale can no longer locate or monitor machines.

1.  From the Control Panel, under **Programs**, click **Uninstall a program**. The Programs and Features list of applications appears.
1.  Select **Citrix Smart Tools Agent** and click **Uninstall**. When prompted to confirm, click **Yes**.

## Troubleshooting

If you experience a problem with installing the Smart Tools Agent, the **CitrixSmartToolsAgent.log** file contains information that can help you troubleshoot the issue. This file is created during agent installation and is located in the same directory from which the installer is launched.

If removing the agent from your Windows server fails, ensure the Citrix Smart Tools service is stopped and then retry the removal.

If you continue to experience problems, you can [contact Citrix Technical Support](/en-us/smart-tools/help-and-support.html#technical-support) for troubleshooting assistance. The Citrix Support team might request a copy of the agent log files to determine the problem.

### To share Smart Tools Agent log files

1.  Log in to the Delivery Controller that is unable to connect to Citrix Smart Tools.
1.  Open the Command Prompt window and navigate to the log file location: C:\Program Files (x86)\Citrix\LifecycleManagement
1.  Copy the agent log file to your local machine: **copy connector.log log.txt**
1.  Send the log.txt file to `support@citrix.com`.
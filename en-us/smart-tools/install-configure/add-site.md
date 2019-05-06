---
layout: doc
---
# Add a Site to Smart Tools

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

You can add a Site to Smart Tools using the following methods:

*  [Add a Site through the product installer](#add-a-site-through-the-citrix-product-installer) for XenApp and XenDesktop 7.14 through 7.18 or Virtual Apps and Desktops 7 1808 and later.
*  [Add a Site manually](#add-a-site-manually) from within Smart Tools.

When you add a Site to Smart Tools, your Site appears in both Smart Check and Smart Scale. However, these features are not active until you complete the setup for each one.

> **Important**:
>
> Only on-premises Sites are compatible with both Smart Check and Smart Scale. For more information about supported Sites, see [Smart Check requirements](/en-us/smart-tools/system-requirements/check-requirements.html) and [Smart Scale requirements](/en-us/smart-tools/system-requirements/scale-requirements.html).

## Add a Site through the Citrix product installer

> **Note**:
>
> This section applies only to adding Sites with XenApp and XenDesktop 7.14 through 7.18 or Virtual Apps and Desktop 7 1808 and later. If you want to add a Site with an earlier supported version of XenApp and XenDesktop or Virtual Apps and Desktops, see [Add a Site manually](#add-a-site-manually).

To add your Site to Smart Tools using the Citrix product installer, you perform the following tasks:

1.  Install the Delivery Controller and connect to Smart Tools through the product installer.
1.  Complete your Site setup in Smart Tools.

### Install the Delivery Controller and connect to Smart Tools

1.  Log on as an administrator on the machine where you install the Delivery Controller for your Virtual Apps and Desktops Site.
1.  Launch the Virtual Apps and Desktops installation media and select **Delivery Controller**.
1.  Follow the installation wizard until you arrive at the Smart Tools screen.
1.  Select **I want to connect to Smart Tools and Call Home** and click **Connect**.
    ![Virtual Apps and Desktops metainstaller with Connect to Smart Tools option selected](/en-us/smart-tools/media/xaxd-installer-smart-tools-connect.png)

1.  When prompted, enter your Citrix Cloud credentials and click **Sign in**.
    ![Virtual Apps and Desktops metainstaller with Citrix Cloud signin page](/en-us/smart-tools/media/xaxd-smart-tools-connect-citrix-cloud.png)

1.  When you have connected successfully, click **Next** and finish the installer.
    ![Virtual Apps and Desktops installer connected successfully to Smart Tools](/en-us/smart-tools/media/xaxd-smart-tools-connected-v1.png)

1.  After finishing the installation, open Citrix Studio and configure your Site.

> **Important**:
>
> Configuring your Site is required **before** you complete the setup for either Smart Check or Smart Scale. This includes creating the Site and databases as well as creating Machine Catalogs and Delivery Groups. If you try to set up Smart Check or Smart Scale without completing the Site configuration process, adding your Site to Smart Tools fails.

### Complete setup in Smart Tools

1.  Open a web browser and sign in to [Citrix Cloud](https://citrix.cloud.com).
1.  From the Citrix Cloud management console, locate the Smart Tools tile and click **Manage**.
1.  From the Smart Tools management console, click **Smart Check** or **Smart Scale**. The Virtual Apps and Desktops Sites page displays a card for your Site.
1.  On your Site's card, click **Complete Setup**.
    ![Complete Setup button highlighted on Smart Check Site card with machine name](/en-us/smart-tools/media/smart-check-xaxd-site-machine-name-v1.png)
1.  In **Username**, enter the username for the Citrix Administrator account for your Site in *domain/username* format. For Smart Check, this account is a Full Administrator. For Smart Scale, this account is either a Delivery Group Administrator or a Full Administrator.
1.  In **Password**, enter the password for the Citrix Administrator account for your Site.
1.  Click **Done**. Smart Tools verifies your Citrix administrator credentials and updates the Site.

After you add your Site, Smart Tools displays your Site on the Virtual Apps and Desktops Sites page.

## Add a Site manually

If you didn't connect to Smart Tools when you installed XenApp and XenDesktop (7.14 through 7.18) or Virtual Apps and Desktops, or your Site is running a supported version of XenApp and XenDesktop earlier than Version 7.14, you can add your Site by manually installing the Smart Tools Agent.

### Prerequisites

Before you add your Site to Smart Tools, verify at least one Delivery Controller meets the following requirements:

*  Supports PowerShell 3.0, at a minimum.
*  No other Smart Tools Agents are installed. For instructions, see [Remove the agent](/en-us/smart-tools/smart-tools-agent/install-remove-smart-tools-agent.html#remove-the-agent).

> **Important**:
>
> The Smart Tools Agent is supported for use only on Delivery Controllers in an on-premises Virtual Apps and Desktops deployment. The agent is not supported for use on machines that host other Citrix product or cloud service components, such as Citrix Cloud Connectors.

### To install the Smart Tools Agent

1.  Log on to a Delivery Controller in your Virtual Apps and Desktops Site. If you log on as a domain user that does not belong to the Domain Admins group, Windows might prompt you for administrator credentials during agent installation. Windows requests these credentials if your account does not have sufficient permission to install the agent. Smart Tools does not store or transmit these credentials.
1.  Open a web browser and sign in to [Citrix Cloud](https://citrix.cloud.com).
1.  From the Citrix Cloud management console, locate the Smart Tools tile and click **Manage**.
1.  From the Smart Tools management console, click **Smart Check** or **Smart Scale**.
1.  Click **Add Site**. The Add Site wizard appears.
1.  Click **Download Agent** and then run the **CitrixSmartToolsAgent.exe** file. Follow the wizard to install the agent. After installation, the agent registers the Delivery Controller with Smart Tools. After registering successfully, the **Add Site** wizard displays a green check mark. Click **Finish**.
    ![Agent installed successfully dialog](/en-us/smart-tools/media/agent-install-success.png)

1.  On your Site's card, click **Complete Setup** and enter the username (in _domain\username_ format) and password for the Site's Delivery Group Administrator (Smart Scale only) or Full Administrator account (Smart Check and Smart Scale) and then click **Done**. Smart Tools validates the credentials, which can take a few moments to complete. Afterward, Smart Tools displays your Site on the Virtual Apps and Desktops Sites page.

> **Important:**
>
> Smart Tools does not store the Citrix Administrator password that you supply. Instead, the password is encrypted and stored in the registry on the Delivery Controller. This registry entry is located at HKLM/Software/WOW6432Node/Citrix/Smart Checks.

## Next steps

### Start using Smart Check or Smart Scale

After you add your Site, the Virtual Apps and Desktops page displays your Site with the **Get Started** button.

In Smart Check, clicking **Get Started** triggers an initial run of health checks on your Site. For more information, see [Run initial checks on your Site](/en-us/smart-tools/checks/perform-health-checks.html#run-initial-checks-on-your-site).

In Smart Scale, clicking **Get Started** starts monitoring for your Delivery Groups. After a few minutes, Smart Scale displays the data it collects on the **Monitoring** tab. You can then configure scaling actions for your Delivery Groups. For more information, see [Manage Delivery Group capacity with Smart Scale](/en-us/smart-tools/scale/manage-delivery-group-capacity.html).

### Add other Delivery Controllers in your Site to Smart Tools

After you have added your Site to Smart Tools, you can add the Smart Tools Agent to the other Delivery Controllers in your Site. This ensures your Site is connected to Smart Tools in the event one agent becomes unvailable. For instructions, see [Ensure high availability for the Smart Tools Agent](/en-us/smart-tools/smart-tools-agent/install-remove-smart-tools-agent.html#ensure-high-availability-for-the-smart-tools-agent).

### Add StoreFront, Provisioning, and License servers in your Site

By default, Smart Check doesn't automatically detect the StoreFront, Provisioning, or License servers used with your Site. To allow Smart Tools to locate these components, you can target them with Citrix Checks or you can add them individually. For instructions, see [Add Site components to Smart Tools](/en-us/smart-tools/checks/add-site-components.html).
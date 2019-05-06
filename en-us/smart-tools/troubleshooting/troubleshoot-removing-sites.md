---
layout: doc
---
# Troubleshoot removing Sites from Smart Tools

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

This topic provides troubleshooting tips for issues when removing a Virtual Apps and Desktops Site from Smart Tools:

## Smart Tools rediscovers Site from Citrix Insight Services

After removing a Site from Smart Check, the Site re-appears on the Virtual Apps and Desktops Sites page.

Smart Check auto-discovers and displays Sites that either have the Smart Tools Agent installed or that have Site information available in Citrix Insight Services.

![smart-tools-discover-site-cards.png](/en-us/smart-tools/media/smart-tools-discover-site-cards.png)

If the Smart Tools Agent is not installed on any Delivery Controllers in your Site, perform the following tasks:

1.  Log on to your Citrix Insight Services account and check to see if there is any Site data from Citrix Scout or Call Home. If there is, remove the Site data from your account.
1.  Return to Smart Check and refresh the Virtual Apps and Desktops Sites page. The Site should no longer be displayed because there is no Site data available for Smart Check to access.

If Citrix Scout or Call Home upload new Site data at a later time, Smart Tools might discover and display the Site again. To disable discovery of these Sites, see "Remove a Site discovered through Call Home or Citrix Scout" in the article [View or modify Site details](/en-us/smart-tools/install-configure/view-modify-site.html).

## Virtual Apps and Desktops service Site cannot be removed from Smart Scale

After removing a Virtual Apps and Desktops service Site from Smart Scale using the Remove Site button, the Site re-appears on the Virtual Apps and Desktops Sites page.

In Smart Scale, Sites that use the Virtual Apps and Desktops service appear as "CloudXdSite" by default.

Ordinarily, the Remove Site button in Smart Scale removes a Site from view on the Virtual Apps and Desktops Sites page. However, with Sites that use the Virtual Apps and Desktops service, this effect is temporary and lasts only until the Virtual Apps and Desktops Sites page is refreshed. By default, Smart Scale automatically discovers Sites that use the Virtual Apps and Desktops service. However, there is currently no way to turn off auto-discovery or prevent display of these Sites.

## Smart Tools still displays Site even though the Smart Tools Agent is no longer installed

After uninstalling the Smart Tools Agent, Smart Check and Smart Scale still display the Site on the Virtual Apps and Desktops Sites page.

When uninstalling the Smart Tools Agent, the agent communicates with Smart Tools to unregister the Site so Smart Check and Smart Scale will no longer display it on the Virtual Apps and Desktops Sites page. In some cases, the firewall protecting the Site can prevent this communication from occurring. So, even though the Smart Tools Agent is no longer present, Smart Check and Smart Scale still display the Site.

If this happens, perform the following actions:

1.  From the Virtual Apps and Desktops Sites page, select the Site you want to remove.
1.  Click **Site Details > Remove Site**.
1.  When prompted to confirm removal, click **Remove**.

The Site is removed from the Virtual Apps and Desktops Sites page.

## Smart Tools displays duplicate Site even though the Smart Tools Agent is not installed

Uninstalling the Smart Tools Agent while the Delivery Controller is offline and then reinstalling the agent when the Controller is online causes Smart Scale to display duplicate Sites on the Virtual Apps and Desktops Sites page. On one Site, the **Complete Setup** button is still displayed, indicating setup was not completed and no Site credentials were supplied. On the second Site, the View Site button is displayed, indicating setup was completed and Site credentials were supplied. The first Site is not functional for Smart Scale, but cannot be removed from the page.

Typically, when uninstalling the Smart Tools Agent, the agent communicates with Smart Tools to unregister the Site so Smart Scale will no longer display it on the Virtual Apps and Desktops page. However, if the Delivery Controller is unavailable to the network when the uninstallation occurs, the agent installer can't communicate with Smart Tools to unregister the Site. So, even though the Smart Tools Agent is no longer present on the machine, Smart Scale still displays the Site.

If the Smart Tools Agent is installed again on the same Controller (by clicking the **Add Site** button), Smart Tools registers the Site as a new instance and displays a separate tile for the Site in Smart Scale. Because Smart Tools can't communicate with the first instance of the Site, the tile for that instance can't be removed from the Virtual Apps and Desktops Sites page.

To resolve this issue, perform the following actions:

1.  From the Virtual Apps and Desktops Sites page, locate the Site you want to remove.
1.  Click the **More options** button and select **Remove Site**. A confirmation message appears, prompting you to confirm you want to remove the Site.
1.  Click **Remove**.

The Site is removed from the Virtual Apps and Desktops Sites page.

## Smart Tools displays duplicate Sites when the agent is installed on two Delivery Controllers

After installing the Smart Tools Agent on two Delivery Controllers, Smart Tools displays duplicate Sites on the Virtual Apps and Desktops Sites page in Smart Check and Smart Scale. This issue occurs when the agent is installed on each Controller using the **Add Sites** button.

When you install the Smart Tools Agent using the Add Sites button, the agent is assigned a certificate which serves as a unique identifier for the Site in Smart Tools. If you install the agent in this manner on Controllers in the same Site, Smart Tools treats each agent instance as a new Site and displays separate tiles for each one on the Virtual Apps and Desktops Sites page.

To resolve this issue, perform the following actions:

1.  Log on to one of the Delivery Controllers as an administrator.
1.  Launch the Windows Control Panel and uninstall the Citrix Smart Tools Agent.
1.  In Smart Check or Smart Scale, refresh the Virtual Apps and Desktops Sites page. The duplicate Site no longer appears on the page.
1.  Click the **Site Details** tab and locate the Controller where you want to install the Smart Tools Agent.
1.  Click **Install Agent**. Smart Tools installs the agent with the same certificate so the Controller registers as part of the same Site instead of as a separate one.
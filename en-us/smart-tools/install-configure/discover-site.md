---
layout: doc
---
# Discover Sites in Smart Tools

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

Site discovery refers to the methods that Smart Tools uses to become aware of Virtual Apps and Desktops Sites. Smart Tools discovers all Sites that have the Smart Tools Agent installed on at least one Delivery Controller. This article describes how Smart Tools can also discover certain Sites that don't have the agent installed.

For **Smart Check**, Smart Tools can automatically discover the presence of the following Sites:

*  Sites that have [Call Home](/en-us/citrix-virtual-apps-desktops/manage-deployment/cis.html#citrix-call-home) enabled through the Virtual Apps and Desktops installer or through Studio. Smart Tools discovers these Sites by default.
*  Sites for which you've created diagnostic files with [Citrix Scout](/en-us/citrix-virtual-apps-desktops/manage-deployment/cis/scout.html) and uploaded to Citrix. By default, automatic discovery is turned off for these Sites. To turn on automatic discovery, see [Enable or disable Site discovery](#enable-or-disable-site-discovery) in this article.

For **Smart Scale**, Smart Tools automatically discovers Sites that use the Virtual Apps and Desktops service in Citrix Cloud.

All discovered Sites are automatically displayed in both Smart Check and Smart Scale.

> **Important**:
>
> Even though Smart Check displays Sites using the Virtual Apps and Desktops service, Smart Check is not supported for use with these Sites.

## Enable or disable Site discovery

> **Note**:
>
> Site discovery in Smart Scale can't be disabled.

In Smart Check, you can enable and disable discovery for Sites that use Call Home or Citrix Scout to upload diagnostics information to Citrix. When discovery is enabled, Smart Tools discovers Sites based on any diagnostic uploads that are associated with your Citrix ID and displays them on the Virtual Apps and Desktops Sites page. When discovery is disabled, these Sites no longer appear in Smart Check.

If you want to enable discovery for all Sites with diagnostic uploads, but you don't want Smart Check to show certain Sites, you can selectively hide these Sites. For instructions, see [To hide a Site without disabling discovery](#to-hide-a-site-without-disabling-discovery).

> **Note**:
>
> For Sites that are discovered through Call Home or Citrix Scout, Smart Check displays issues and notifications only for the Delivery Controllers and Machine Catalogs in the Site. Delivery Groups in these Sites are not discovered.

### To automatically discover Sites with Call Home or Citrix Scout

1.  From the Smart Tools management console, click **Smart Check**.
1.  Click the **Site Options** menu button and then select **Turn On Site Discovery**. A confirmation message appears.
    ![Turn on Site Discovery menu option](/en-us/smart-tools/media/smart-check-turn-on-discovery-menu.png)
1.  Click **Turn On**. Any Sites with diagnostic uploads associated with your Citrix ID appear on the Virtual Apps and Desktops Sites page.
1.  To turn off discovery for all Sites:
    1.  Click **Site Options** and then select **Turn Off Site Discovery**. A confirmation message appears.
    1.  Click **Turn Off**. Any previously-discovered Sites no longer appear on the Virtual Apps and Desktops Sites page.

## Remove a Site discovered through Call Home or Citrix Scout

You can remove Sites from Smart Check that are discovered through Call Home or Citrix Scout using the following methods:

*  **Delete the diagnostic uploads associated with the Site.** This prevents the Site from being discovered (if enabled) and removes the Site from Smart Check and Smart Scale. However, Smart Check might discover the Site again if a diagnostics file is uploaded at a later time.
*  **Disable discovery in Smart Check.** This prevents all Sites with diagnostics uploads from being discovered and removes any Sites already discovered from uploads.
*  **Hide the Site in Smart Check.** This prevents Smart Check from displaying the selected Site without affecting discovery of other Sites with diagnostic uploads.

### To disable discovery for all Sites

1.  On the Virtual Apps and Desktops Sites page, click the **More options** button and select **Turn Off Site Discovery**. A message appears, prompting you to confirm you want to turn off discovery.
1.  Click **Turn Off**.

Smart Check removes any Sites that were previously discovered from diagnostics uploads.

### To hide a Site without disabling discovery

1.  On the **Virtual Apps and Desktops Sites** page, locate the Site you want to remove and click **View**.
1.  On the **Health Alerts** page, click **Site Options** and then click **Hide Site**.
1.  When prompted, click **Remove**.
1.  To unhide previously-hidden Sites, perform the following actions:
    1.  From the **Virtual Apps and Desktops Sites** page, click **Site Options** and then select **Show Hidden Discovered Sites**.
    1.  Select the Sites you want to unhide and click **Show**.
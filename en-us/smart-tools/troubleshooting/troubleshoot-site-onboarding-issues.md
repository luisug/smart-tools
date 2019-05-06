---
layout: doc
---
# Troubleshoot Site onboarding issues

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

This topic provides troubleshooting tips for issues that might be encountered when adding a Virtual Apps and Desktops Site to Smart Check or Smart Scale.

## Verify credentials are correct

When adding a Site to Smart Check or Smart Scale, Smart Tools prompts you for account credentials for installing the Smart Tools Agent and onboarding the Site. The account credentials you specify must meet the following requirements:

*  The account credentials are entered in _domain\username_ format.
*  The account credentials have the appropriate permissions. The following table lists the minimum required permissions:

    ||Smart Check | Smart Scale |
    | --- | --- | --- |
    | **Citrix administrator role** | Full Administrator | Delivery Group Administrator |
    | **Active Directory group** | Domain Users | Domain Users |

To view the Citrix administrator role delegated to the account, launch Studio, click **Configuration > Administrators** from the navigation pane, and then click the **Administrators** tab in the upper middle pane.

For more information:

*  For Smart Check, see [Account requirements](/en-us/smart-tools/system-requirements/check-requirements.html#account-requirements).
*  For Smart Scale, see [Account requirements](/en-us/smart-tools/system-requirements/scale-requirements.html#account-requirements).

## Verify the Delivery Controller can be reached

For Smart Check to communicate with your Site, the Delivery Controller must meet the following requirements:

*  The Delivery Controller is powered on.
*  The Delivery Controller is configured to allow outbound communication on port 443 (HTTPS).
*  The Smart Tools Agent is installed and running on the Delivery Controller.
*  The Studio console is accessible on the Delivery Controller.

To verify the Smart Tools Agent is running, launch the Services console (services.msc) and locate the Smart Tools Agent Service. Verify the Status is **Started** and the Startup Type is **Automatic**.

To verify the Studio console is accessible on the Delivery Controller, launch Studio and check that it displays all the Machine Catalogs and Delivery Groups in your Site. Studio should launch smoothly and display no errors.

## Verify the Delivery Controller can reach Smart Tools

1.  On the Delivery Controller hosting the Smart Tools Agent, open a web browser and enter [https://smart.cloud.com](https://smart.cloud.com) in the address bar.
1.  When prompted, enter your Citrix Cloud username and password and click **Sign In**.
1.  If applicable, select a customer account. The Smart Tools home page displays.

## Verify the Delivery Controller has the correct PowerShell version installed and can run scripts

To use Smart Check or Smart Scale, Delivery Controllers in the Site must have PowerShell 3.0 installed, at a minimum, and be capable of running PowerShell scripts.

To verify the current version of PowerShell installed:

1.  On the Delivery Controller, open a PowerShell command window.
1.  At the command prompt, type **Get-Host** and press **ENTER**.
1.  In **Version**, confirm the output is **3.0** or later.

To verify the Delivery Controller is capable of running PowerShell scripts:

1.  Log on to the Delivery Controller using the same credentials you used to add the Site to Smart Check.
1.  Launch an instance of Windows PowerShell (powershell.exe).
1.  Enter the following PowerShell commands:

    ```powershell
    Add-PSSnapin -Name Citrix.* -ErrorAction Stop
    Get-ConfigSite
    ```

    The commands load all Citrix PowerShell modules and return the Site instance. Confirm these commands complete successfully with the expected results.

## Additional assistance

If you've tried these troubleshooting tips and your Site continues to experience an issue, contact [Citrix Support](https://www.citrix.com/support/open-a-support-case/) for assistance.

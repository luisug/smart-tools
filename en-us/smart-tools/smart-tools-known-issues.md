---
layout: doc
---
# Known issues

## July 13, 2018

When attempting to run Citrix checks that target other machines, the checks fail if a Domain User account is used with Smart Check. This issue occurs if the Domain User account is not a member of the local Administrators group on the Delivery Controllers in the Site or on the targeted machines. To resolve this issue, ensure the Domain User account belongs to the local Administrators group on both the Delivery Controllers and on the targeted machines. (CAM-14031)

## June 14, 2018

When using the **Show Hidden Alerts** option from the Health Alerts page, hidden alerts might not be shown consistently for a selected component. As a workaround, select the component from the Health Alerts page, expand the machine you want to view, and then click the menu button and select **Show Hidden Alerts**. (CAM-12789)

![Show Hidden Alerts menu option](/en-us/smart-tools/media/smart-check-site-options-hide-alerts.png)

## December 22, 2016

### Smart Check

*  Sites discovered through Call Home or Citrix Scout cannot be removed from Smart Check through the Smart Tools web site. To remove these Sites from the Virtual Apps and Desktops Sites page in Smart Check, log on to Citrix Insight Services and remove the Site's data uploads. Afterward, refresh the Virtual Apps and Desktops Sites page in Smart Check. (CAM-7525)
*  Smart Check might display two separate listings for the same Site if the Smart Tools Agent is first installed, then uninstalled, and then re-installed. This issue can occur if the Smart Tools Agent is uninstalled very quickly after the Site was added, or if the Smart Tools Agent is re-installed very quickly after it was uninstalled. Because Smart Check requires an interval to discover Sites when the Smart Tools Agent is installed or uninstalled, this issue can occur if the agent is being uninstalled or re-installed while Smart Check is discovering the Site. To avoid this issue, wait a few minutes before uninstalling or re-installing the Smart Tools Agent. (CAM-8080)
*  The date that Smart Check displays for when an update was found might not match the current date or the date listed on the update's article in the Citrix Support Knowledge Center. To determine when an update was released, click the link to the Knowledge Center article, supplied in the update's description in Smart Check. (CAM-8137)
*  Smart Check might not display alerts for XenDesktop services that are disabled. This issue occurs because Smart Check runs checks only on enabled services. Disabled services are skipped when running checks. (CAM-8155)
*  When a new Virtual Apps and Desktops Site is added to Smart Check and checks are attempted, Smart Check might display "No issues found" on the Site's Health Report tab, even if the checks could not be completed. To work around this issue, click **Get error output** for information to help resolve any Site errors that might be preventing successful checks. (CAM-8193)
*  Smart Check email notifications might have the subject line "Smart Check did not find any issues," even if some checks do not run successfully. However, the body of the email notification specifies which checks could not be completed. As a workaround, open the Smart Check email notification to verify all checks ran successfully. If the notification lists any checks that could not be completed, log on to Smart Tools, view your Site's Health Report, and click **Get error output** for more information about the incomplete checks. (CAM-8196)
*  Smart Check might report differing numbers of issues and updates for a Site with the Smart Tools Agent installed and with no Site Agent installed. For example, when the Site has the Smart Tools Agent installed, Smart Check displays 20 issues in the Site's report. However, without the Smart Tools Agent installed, Smart Check reports only 5 issues. When the Smart Tools Agent is installed, Smart Check runs checks on all the Delivery Controllers, Machine Catalogs, and Delivery Groups that are detected in the Site. Without the Smart Tools Agent, Smart Check relies on Site data from Call Home or Citrix Scout, which might include only components selected by the Citrix administrator.  (CAM-8239)
*  After changing the time zone on a Delivery Controller, Smart Check temporarily displays differing times for scheduled health checks. If the time zone on a Delivery Controller is changed to a different time zone and the Site data is synced in Smart Check, Smart Check displays the updated time and time zone for the next run of health checks on the Site's Health Report page. However, the schedule for each set of health checks remains set at the original time, even though the time zone is updated. To resolve this issue, allow Smart Check to run checks at the next scheduled time (the earlier of the differing times). After the checks run successfully, the schedule for each set of checks is updated to match the time and time zone displayed on the Site's Health Report page. (CAM-8249)
*  Smart Check incorrectly flags the Citrix administrator account `*MachineName*_scalextreme_user` and displays the alert "Citrix administrator missing from domain user group." This issue might occur with Sites that were previously deployed using a Smart Tools blueprint. To work around this issue, dismiss the alert, which hides it for the entire Site. (CAM-8256)
*  After "Perform all Checks" is selected for a Site, Smart Check might experience an error and display the following error output: `Smart Tools experienced a problem. Please retry your action or refresh your browser. If the issue persists, contact Citrix Support for assistance.` This issue can occur when Smart Check attempts to perform all checks on a XenApp and XenDesktop 7.6 Site for a prolonged period of time, but times out. As a workaround, restart the Citrix Broker Service and the Citrix Environment Test Service and then run the checks again. To restart these services, perform the following actions:

    1.  On the affected machine, click **Start**, type **services.msc**, and then press **ENTER**.
    1.  From the Services console, select **Citrix Broker Service** and then click **Restart**.
    1.  Repeat Step 2 for the Citrix Environment Test Service.

(CAM-8375)
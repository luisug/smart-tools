---
layout: doc
---
# Manage Delivery Group capacity with Smart Scale

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

## Enable or disable Smart Scale for a Delivery Group

1.  From the Smart Tools management console, click **Smart Scale**.
1.  On the **Smart Scale** page, locate the Site you want to manage and click **View Site**.
1.  On the Site's details page, click **Configure**.
1.  On the **Smart Scale configuration** page, select the Delivery Group you want to manage.
1.  To enable Smart Scale, click the **Smart Scale Disabled** toggle button. The toggle button turns green to indicate Smart Scale is enabled for the selected Delivery Group.
1.  To disable Smart Scale, click the **Smart Scale Enabled** toggle button. The toggle button turns grey to indicate Smart Scale is disabled for the selected Delivery Group.

> **Important**:
>
> Virtual Apps and Desktops's native power management functions for VDI desktops might interfere with Smart Scale's scaling activities. If your Site has these power management actions already configured, you must disable them when using Smart Scale.

## Scale machines based on a schedule

Schedule-based scaling enables you to keep a minimum number or percentage of registered machines, including no (zero) machines, in the Delivery Group powered on at certain times of day that you define. If you have multiple Machine Catalogs associated with the Delivery Group, Smart Tools attempts to balance the minimum value you specify across all catalogs.

The schedule is based on the time zone of the Delivery Group. By default, Smart Tools keeps a single machine powered on during intervals when no other schedule is defined.

> **Important**:
>
> Smart Scale works only with machines in a Delivery Group that are registered with the Site. This ensures that only machines that can accept user sessions are included in the capacity for the Delivery Group. If there are powered-on machines in the Delivery Group, but they are not registered with the Site, Smart Tools does not include those machines in the Delivery Group capacity because they are not able to accept user sessions.

When you define a schedule and specify a minimum number or percentage of registered machines, Smart Tools powers on or off machines to meet the minimum you specify. If you specify a minimum number, Smart Tools keeps the exact number of machines specified powered on. If you specify a minimum percentage, Smart Tools calculates the number of machines to keep powered on based on the total number of machines in the Delivery Group. Smart Tools also displays the actual number of machines that will be kept powered on. This number can change as the total number of machines in the Delivery Group changes.

### Scaling up

If the schedule period requires more machines than are currently powered on, Smart Tools powers on additional machines to meet the minimum number specified. If there are multiple Machine Catalogs associated with the Delivery Group, Smart Tools powers on machines from each catalog to meet the minimum number specified. If there are any registered powered-on machines currently in maintenance mode in each Machine Catalog, Smart Tools takes them out of maintenance mode before powering on more machines.

### Scaling down

If the schedule period requires fewer machines than are currently powered on, Smart Tools puts the excess machines with the fewest sessions into maintenance mode. If the Delivery Group has multiple Machine Catalogs associated with it, Smart Tools puts the excess machines from each catalog into maintenance mode. During maintenance mode, Citrix policies take effect to disconnect and terminate any remaining sessions. When all sessions have been terminated, Smart Tools powers off the machine.

### **Citrix policies for terminating sessions**

To ensure disconnected and idle sessions are terminated appropriately, configure the following Citrix policies for your Site:

*  Disconnected session timer
*  Disconnected session timer interval
*  Session idle timer
*  Session idle timer interval

For more information about these policy settings, see [Session limits policy settings](/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/session-limits-policy-settings.html) on the Citrix Product Documentation web site.

### Considerations for schedule-based scaling

*  Smart Scale works only with the registered machines in a given Delivery Group. If there are powered-on machines in the Delivery Group, but they are not registered with the Site, Smart Scale does not include those machines in the total number of available machines in the Delivery Group.
*  If you define multiple schedules for a Delivery Group, ensure the schedules begin and end sequentially. For example, Schedule A is 8 AM-5 PM weekdays; Schedule B is 5 PM-11 PM weekdays; and so on. Smart Scale does not support overlapping schedules defined for the same Delivery Group.
*  When defining times for a schedule, you can specify any time between 12:00 AM and 11:59 PM on any given day. For example, weekdays from 2:00 AM to 6:00 PM. However, you cannot specify times in a single schedule that cross over into the next day. For example, weekdays from 6:00 PM to 1:00 AM is not supported. If you need to define a time period that crosses into the next day, you need to define at least two schedules. For example, Schedule A is 5:00 AM to 11:59 PM and Schedule B is 12:00 AM to 8:00 AM.
*  Ensure the Minimum # or % of Machines On value is smaller than the total number or percentage of machines in the Delivery Group. If this value is larger than the total number, Smart Tools powers on all the machines in the Delivery Group. Smart Tools does not provision additional machines to the Machine Catalog associated with the Delivery Group.

### To enable schedule-based scaling

1.  From the Smart Tools management console, click **Smart Scale**.
1.  On the **Smart Scale** page, locate the Site you want to manage and click **View Site**.
1.  On the Site's details page, click **Configure**.
1.  On the **Smart Scale configuration** page, select the Delivery Group you want to manage.
1.  Under **Capacity Management**, select **Schedule-based scaling only**.
1.  Click **Create New**. The **Create Schedule** box appears.
1.  In **Name**, enter a name for the schedule item.
1.  In **Min # of Machines On**, select one of the following options:
    *  **Min # of Registered Machines On:** Enter the minimum number of registered machines that should be powered on during the schedule period. If you don't want any machines on during the period, enter **0** (zero). By default, the minimum number is **1**.
    *  **Min % of Registered Machines On:** Enter the percentage of registered machines that should be powered on during the schedule period. If you don't want any machines on during the period, enter **0** (zero).
1.  Enter the starting and ending times when the machines should remain powered on. Additionally, select one of the following durations:

    *  **All Workweek days:** Keeps machines powered on for a 5-day work week (Monday through Friday).
    *  **All Weekend days:** Keeps machines powered on for a 2-day weekend (Saturday and Sunday).
    *  **Entire week:** Keeps machines powered on for a 7-day period (Sunday through Saturday).
    *  **Custom:** Keeps machines powered on for the days you select.

1.  Click **Create**.

## Scale machines based on load and schedule

_Load-based scaling_ ensures a sufficient number of registered machines are powered on to meet the demand for user sessions at any given time. _Load-based and schedule-based scaling_ enables you to keep a minimum number or percentage of registered machines powered on during certain times of day that you define and to accommodate increases or decreases in demand during those times. If you have multiple Machine Catalogs associated with the Delivery Group, Smart Tools attempts to balance the number of machines currently powered on or off across all catalogs.

As with schedule-based only scaling, the schedule is based on the time zone of the Delivery Group.

> **Important**:
>
> Smart Scale works only with machines in a Delivery Group that are registered with the Site. This ensures that only machines that can accept user sessions are included in the capacity for the Delivery Group. If there are powered-on machines in the Delivery Group, but they are not registered with the Site, Smart Tools does not include those machines in the Delivery Group capacity because they are not able to accept user sessions.

### Scale metrics

To use load-based scaling (with or without schedules), you need to specify the scale metric you want to use for determining when machines are at full load and triggering scaling actions.

Smart Tools uses the scale metric you select (either Session count or Load index) to direct users to the machine best suited to host the sessions they request. When you select a scale metric, you will also need to configure the **Load per machine** setting which establishes the level at which Smart Tools considers a machine at full load.

#### Session count

The Session count metric enables you to set a maximum number of sessions that are allowed on each machine in the Delivery Group. When the maximum number of sessions is reached, Smart Tools directs new session requests to other machines in the Delivery Group.

When you select this metric, you also specify the maximum number of sessions each machine in your Delivery Group can support. Smart Tools uses this value to calculate the capacity of powered-on machines in the Delivery Group. It does not affect any Citrix load management policy settings that you have configured.

#### Load index

The Load index metric determines how likely a machine is to receive connections. Load index is calculated using the Citrix Load Management policy settings configured for concurrent logon, session, CPU, disk, and memory use. By default, a machine is considered at full load if there are at least two session requests waiting to be resolved or the machine is hosting 250 sessions.

When you select this metric, Smart Tools uses the value 10000 as the maximum load index by default.

### Capacity and scaling

Smart Tools adds a _capacity buffer_ to the current session demand to accommodate any sudden spikes in demand. By default, the capacity buffer is 10% of the current demand. For example, if the current demand is 100 sessions, Smart Tools accounts for 110 sessions. You can modify this buffer, increasing or decreasing it based on your session needs and resource cost considerations.

### Scaling up with demand

If session demand exceeds the maximum load that the currently registered powered-on machines can bear, Smart Tools powers on additional machines to meet the demand. If the Delivery Group has multiple Machine Catalogs associated with it, Smart Tools powers on machines from each Machine Catalog to meet the demand. If there are any registered powered-on machines currently in maintenance mode in any of the Machine Catalogs for the Delivery Group, Smart Tools takes the machines out of maintenance mode before powering on more machines.

### Scaling down with demand

If the session demand decreases, the excess machines with the fewest sessions are put into maintenance mode. If the Delivery Group has multiple Machine Catalogs associated with it, Smart Tools puts the excess machines from each catalog into maintenance mode. During maintenance mode, Citrix policies take effect to disconnect and terminate any remaining sessions. After all sessions have been terminated, Smart Tools powers off the machine. This process can take up to 15 minutes to complete.

For a list of the policies you configure for terminating sessions in your Virtual Apps and Desktops Site, see [Citrix policies for terminating sessions](#citrix-policies-for-terminating-sessions) in this article.

### Considerations for accommodating demand

Smart Scale works with existing machines in the Delivery Group, so you must ensure the Machine Catalog associated with the Delivery Group has sufficient machines available to accommodate increases in session demand. If demand for sessions is greater than the total number of machines can accommodate, Smart Tools powers on all machines in the Delivery Group and records on the [Events tab](/en-us/smart-tools/install-configure/view-modify-site.html#smart-scale-site-information) that no more machines are available to power on.

### To enable load-based scaling or load and schedule-based scaling

1.  From the Smart Tools management console, click **Smart Scale**.
1.  On the **Smart Scale** page, locate the Site you want to manage and click **View details**.
1.  On the Site's details page, click **Configure**.
1.  On the **Smart Scale configuration** page, select the Delivery Group you want to manage.
1.  Under **Capacity Management**, select **Load-based scaling only** or **Load-based and schedule-based scaling**.
1.  In **Scale metric**, select the metric you want to use for managing load in your Delivery Group. To manage load using number of sessions, select **Session count**. To manage load using load index, select **Load index**.
1.  In **Load per machine**, if you use session count for the scale metric, enter the **Max number of sessions** that each machine in the Delivery Group is allowed to host. Entering a lower value can improve performance for logged on sessions, but powers on more machines when session demand rises. If you use load index for the scale metric, the default maximum load index is 10000.
1.  If applicable, under **Schedules**, click **Create New** and enter a name, the minimum number or percentage of registered machines to keep powered on, time period, and duration. Click **Create**.
1.  To modify the capacity buffer, click **Advanced**. Adjust the slider to increase or decrease the number of spare sessions that Smart Tools accounts for in addressing sudden demand. Increasing the buffer results in more machines powered on and waiting for session requests. Click **OK** to save your changes.

## Delay powering off machines

Smart Tools can help you ensure machines in your Delivery Groups that host dedicated desktops are available to your users outside working hours. Typically, administrators schedule these machines to be powered off outside working hours. If a user accesses their desktop using Citrix Receiver during that time, the machine hosting the desktop powers on, but Smart Tools immediately powers it off again. Because Smart Tools powers off the machine before a session can be established, users cannot access their desktops outside of working hours. Using the Power Off Delay in Smart Scale, you can control how long Smart Tools must wait before powering off machines, allowing users enough time to establish sessions when needed.

To configure Power Off Delay, you specify the number of minutes that must elapse before Smart Tools can power off the machine. By default, 30 minutes are specified. When a machine has been powered on, the delay period ensures the machine remains powered on, even if there's no session. After the delay period has elapsed and Smart Tools verifies there is no session, the machine is powered off.

### To configure Power-off Delay

1.  On the **Smart Scale** page, select the Site you want to manage and click **View Details**. The Site Details page appears.
1.  Click **Configure**. The Smart Scale Configuration page appears.
1.  Select the Delivery Group you want to manage and then click **Advanced**.
1.  In **Mins**, enter the number of minutes that Smart Tools should wait before powering off the machine.

## Configure estimated savings for cloud instances

If your Site consists of machines deployed in the cloud, Smart Tools can estimate the amount you save in resource costs based on the per-instance cost and the utilization history of the Site.

> **Note**:
>
> Smart Tools calculates the estimated savings for all instances in the Delivery Group, regardless of whether or not they are registered with the Site.

1.  On the **Smart Scale** page, select the Site you want to manage and click **View Details**. The Site details page appears.
1.  Click **Configure**. The Smart Scale Configuration page appears.
1.  Under **Monitoring**, enter the hourly price in US dollars for each instance in your Site. Click **Done**.

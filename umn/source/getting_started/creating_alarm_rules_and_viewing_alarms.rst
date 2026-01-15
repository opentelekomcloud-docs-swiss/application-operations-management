:original_name: aom_05_0006.html

.. _aom_05_0006:

Creating Alarm Rules and Viewing Alarms
=======================================

You can set threshold conditions for resource metrics by setting alarm rules. When the value of a metric reaches the threshold, an alarm is generated. If no metric data is reported, an insufficient data event is generated so that you can detect and handle exceptions in a timely manner.

There are three modes for creating metric alarm rules: **Select by resource type**, **Select by full metrics**, and **Run Prometheus command**. The following uses **Select by resource type** as an example to describe how to add an alarm rule and view alarms.

Creating a Metric Alarm Rule
----------------------------

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. On the rule list page, click **Create Alarm Rule**.

#. Set basic information about the alarm rule by referring to :ref:`Table 1 <aom_05_0006__table1249723616548>`.

   .. _aom_05_0006__table1249723616548:

   .. table:: **Table 1** Basic information

      +-------------+--------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Description                                                                                                        |
      +=============+====================================================================================================================+
      | Rule Name   | Rule name. Enter a maximum of 255 characters. The following special characters are not allowed: "$# ``%&'+;<=>?\`` |
      +-------------+--------------------------------------------------------------------------------------------------------------------+
      | Description | Description of the rule. Enter up to 1,000 characters.                                                             |
      +-------------+--------------------------------------------------------------------------------------------------------------------+

#. Set the detailed information about the alarm rule.

   a. Set **Rule Type** to **Metric alarm rule**.

   b. Set **Configuration Mode** to **Select by resource type** and specify **Resource Type** and **Monitored Object**.

      -  **Resource Type**: Select a desired resource type from the drop-down list.

      -  **Monitored Object**: Click **Select Monitored Object** to select a desired monitored object.

         If you enable **Apply to All** when selecting monitored objects, an alarm rule will be created for all metrics of the type you select under an application or service. For example, if you select **CCE/Host/Host/CPU Usage** and enable **Apply to All**, an alarm rule will be created for all hosts in CCE.

   c. Set an alarm condition. Customize alarm conditions or create them by importing a template. The following describes how to customize an alarm condition.

      -  .. _aom_05_0006__li192716462914:

         **Custom**

         Click **Custom** and set the statistical period, consecutive periods, and alarm condition. :ref:`Table 2 <aom_05_0006__table77001133203019>` describes the parameters.


         .. figure:: /_static/images/en-us_image_0000002254869044.png
            :alt: **Figure 1** Setting an alarm condition

            **Figure 1** Setting an alarm condition

         .. _aom_05_0006__table77001133203019:

         .. table:: **Table 2** Parameters for setting an alarm condition

            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | Category              | Parameter                          | Description                                                                                                                                                                                                                                                                                 |
            +=======================+====================================+=============================================================================================================================================================================================================================================================================================+
            | Alarm Condition       | Metric                             | Metric to be monitored.                                                                                                                                                                                                                                                                     |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Consecutive Periods                | When the metric value meets the alarm condition for a specified number of consecutive periods, a metric alarm will be generated.                                                                                                                                                            |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Statistical Period                 | Metric data is aggregated based on the configured statistical period, which can be 1 minute, 5 minutes, 15 minutes, or 1 hour.                                                                                                                                                              |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Statistic                          | Method used to measure metrics. Options: **Avg**, **Min**, **Max**, **Sum**, and **Samples**.                                                                                                                                                                                               |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Threshold Condition                | Trigger condition of a metric alarm. An alarm condition consists of two parts: operators (>=, <=, >, and <) and threshold value. For example, if the trigger condition is set to **> 85** and an actual metric value exceeds 85, a metric alarm will be generated.                          |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Alarm Severity                     | Severity of a metric alarm. Options: **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                   |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | ``-``                 | Check Interval                     | Interval at which metric query and analysis results are checked.                                                                                                                                                                                                                            |
            |                       |                                    |                                                                                                                                                                                                                                                                                             |
            |                       |                                    | -  Hourly: Query and analysis results are checked every hour.                                                                                                                                                                                                                               |
            |                       |                                    |                                                                                                                                                                                                                                                                                             |
            |                       |                                    | -  Daily: Query and analysis results are checked at a fixed time every day.                                                                                                                                                                                                                 |
            |                       |                                    |                                                                                                                                                                                                                                                                                             |
            |                       |                                    | -  Weekly: Query and analysis results are checked at a fixed time point on a specified day of a week.                                                                                                                                                                                       |
            |                       |                                    |                                                                                                                                                                                                                                                                                             |
            |                       |                                    | -  Custom interval: The query and analysis results are checked at a fixed interval.                                                                                                                                                                                                         |
            |                       |                                    |                                                                                                                                                                                                                                                                                             |
            |                       |                                    | -  Cron: A cron expression is used to specify a time interval. Query and analysis results are checked at the specified interval.                                                                                                                                                            |
            |                       |                                    |                                                                                                                                                                                                                                                                                             |
            |                       |                                    |    The time specified in the cron expression can be accurate to the minute and must be in the 24-hour notation. Example: **0/5 \* \* \* \***, which indicates that the check starts from 0th minute and is performed every 5 minutes.                                                       |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | Advanced Settings     | Alarm Clearance                    | An alarm will be cleared if the monitored object does not meet the trigger condition within the monitoring period. By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                         |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Action Taken for Insufficient Data | Action to be taken when no metric data is generated or metric data is insufficient within the monitoring period. You can configure this option based on your requirements.                                                                                                                  |
            |                       |                                    |                                                                                                                                                                                                                                                                                             |
            |                       |                                    | By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                                                                                                                                            |
            |                       |                                    |                                                                                                                                                                                                                                                                                             |
            |                       |                                    | The system supports the following actions: changing the status to **exceeded** and sending an alarm, changing the status to **insufficient data** and sending an event, maintaining the previous status, and changing the status to **normal** and sending an alarm clearance notification. |
            +-----------------------+------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   d. Set alarm tags and annotations as required. For details, see :ref:`Alarm Tags and Annotations <mon_01_0044>`.

      Click **Add Tag** or **Add Annotation**.

#. Set an alarm notification policy. **Direct Alarm Reporting**: An alarm is directly sent when the alarm condition is met.

   a. Specify whether to enable an alarm action rule. After an alarm action rule is enabled, the system sends notifications based on the associated SMN topic and message template. If the existing alarm action rules cannot meet your requirements, click **Create Rule** to create one. For details, see :ref:`Creating an Alarm Action Rule <mon_01_0015>`.
   b. After an alarm action rule is selected, specify whether to enable alarm clearance notification. After alarm clearance notification is enabled, if the alarm clearance condition set in :ref:`Advanced Settings > Alarm Clearance <aom_05_0006__li192716462914>` is met, alarm clearance notifications are sent based on the selected action rule.


   .. figure:: /_static/images/en-us_image_0000002289469305.png
      :alt: **Figure 2** Setting an alarm notification policy

      **Figure 2** Setting an alarm notification policy

#. Click **Confirm**. Then, click **Back to Alarm Rule List** to view the created alarm rule.

   As shown in the following figure, a metric alarm rule is created. Click |image1| in front of the rule name to view its details.

   In the expanded list, if a metric value meets the configured alarm condition, a metric alarm is generated on the alarm page. To view it, choose **Alarm Management** > **Alarm List** in the navigation pane.


   .. figure:: /_static/images/en-us_image_0000002254812068.png
      :alt: **Figure 3** Creating a Metric Alarm Rule

      **Figure 3** Creating a Metric Alarm Rule

Viewing Alarms
--------------

#. In the navigation pane, choose **Alarm Management** > **Alarm List**.

#. Click the **Alarms** tab to view the alarm information.

   a. Set a time range to view alarms. There are two methods to set a time range:

      Method 1: Use a predefined time label, such as **Last hour** or **Last 6 hours** in the upper right corner of the page. You can select a time range as required.

      Method 2: Specify the start time and end time to customize a time range. You can specify up to 31 days.

   b. Set the interval for refreshing alarms. Click |image2| and select a value from the drop-down list as required, such as **Refresh manually** or **1 minute auto refresh**.

   c. Set filter criteria and click |image3| to view the alarms generated in the period.

#. Perform the operations listed in :ref:`Table 3 <aom_05_0006__table48312734713>` as required.

   .. _aom_05_0006__table48312734713:

   .. table:: **Table 3** Operations

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                         | Description                                                                                                                                       |
      +===================================+===================================================================================================================================================+
      | Viewing alarm statistics          | Click |image4|, and view alarm statistics that meet filter criteria within a specific time range on a bar graph.                                  |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | Clearing alarms                   | -  To clear an alarm, click |image5| in the **Operation** column of the target alarm.                                                             |
      |                                   | -  To clear one or more alarms, select them and click **Clear** in the displayed dialog box.                                                      |
      |                                   |                                                                                                                                                   |
      |                                   |    .. note::                                                                                                                                      |
      |                                   |                                                                                                                                                   |
      |                                   |       You can clear an alarm after the corresponding problem is resolved.                                                                         |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing alarm details             | Click an alarm name to view the alarm details and handling suggestions.                                                                           |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing cleared alarms            | Click **Active Alarms** in the upper right corner and select **Historical Alarms** from the drop-down list to view alarms that have been cleared. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002289469309.png
.. |image2| image:: /_static/images/en-us_image_0000002254869032.png
.. |image3| image:: /_static/images/en-us_image_0000002289469297.png
.. |image4| image:: /_static/images/en-us_image_0000002254812104.png
.. |image5| image:: /_static/images/en-us_image_0000002254812084.png

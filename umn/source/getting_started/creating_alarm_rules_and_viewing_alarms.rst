:original_name: aom_05_0006.html

.. _aom_05_0006:

Creating Alarm Rules and Viewing Alarms
=======================================

You can set threshold conditions for resource metrics by setting alarm rules. When the value of a metric reaches the threshold, an alarm is generated. If no metric data is reported, an insufficient data event is generated so that you can detect and handle exceptions in a timely manner.

Metric alarm rules can be created in three modes: **Select by resource type**, **Select from all metrics**, and **PromQL**. The following uses **Select from all metrics** as an example to describe how to add an alarm rule and view alarms.

Creating a Metric Alarm Rule
----------------------------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. Click **Create Alarm Rule**.

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

   b. Set **Configuration Mode** to **Select from all metrics**.

   c. Select a target Prometheus instance from the drop-down list.

   d. Set alarm rule details. :ref:`Table 2 <aom_05_0006__en-us_topic_0000001582534348_table8512161614337>` describes the parameters.

      After the setting is complete, the monitored metric data is displayed in a line graph above the alarm condition. Click the line icon before each metric data record to hide the metric data in the graph. You can click **Add Metric** to add metrics and set the statistical period and detection rules for the metrics.

      After moving the cursor to the metric data and the corresponding alarm condition, you can perform the following operations as required:

      -  Click |image1| next to an alarm condition to hide the corresponding metric data record in the graph.
      -  Click |image2| next to an alarm condition to convert the metric data and alarm condition into a Prometheus command.
      -  Click |image3| next to an alarm condition to quickly copy the metric data and alarm condition and modify them as required.
      -  Click |image4| next to an alarm condition to remove a metric data record from monitoring.

      .. _aom_05_0006__en-us_topic_0000001582534348_table8512161614337:

      .. table:: **Table 2** Alarm rule details

         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                                                                                                                                                                                                 |
         +===================================+=============================================================================================================================================================================================================================================================================================================================================================+
         | Multiple Metrics                  | Calculation is performed based on the preset alarm conditions one by one. An alarm is triggered when one of the conditions is met.                                                                                                                                                                                                                          |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | For example, if three alarm conditions are set, the system performs calculation respectively. If any of the conditions is met, an alarm will be triggered.                                                                                                                                                                                                  |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Combined Operations               | The system performs calculation based on the expression you set. If the condition is met, an alarm will be triggered.                                                                                                                                                                                                                                       |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | For example, if there is no metric showing the CPU core usage of a host, do as follows:                                                                                                                                                                                                                                                                     |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | -  Set the metric of alarm condition "a" to **aom_node_cpu_used_core** and retain the default values for other parameters. This metric is used to count the number of CPU cores used by a measured object.                                                                                                                                                  |
         |                                   | -  Set the metric of alarm condition "b" to **aom_node_cpu_limit_core** and retain the default values for other parameters. This metric is used to count the total number of CPU cores that have been applied for a measured object.                                                                                                                        |
         |                                   | -  If the expression is set to "a/b", the CPU core usage of the host can be obtained.                                                                                                                                                                                                                                                                       |
         |                                   | -  Set **Rule** to **Max > 0.2**.                                                                                                                                                                                                                                                                                                                           |
         |                                   | -  In the trigger condition, set **Consecutive Periods** to **3**.                                                                                                                                                                                                                                                                                          |
         |                                   | -  Set **Alarm Severity** to **Critical**.                                                                                                                                                                                                                                                                                                                  |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | If the maximum CPU core usage of a host is greater than 0.2 for three consecutive periods, a critical alarm will be generated.                                                                                                                                                                                                                              |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Metric                            | Metric to be monitored. When **Select from all metrics** is selected, enter keywords to search for metrics.                                                                                                                                                                                                                                                 |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | Click the **Metric** text box. In the resource tree on the right, you can also select a target metric by resource type.                                                                                                                                                                                                                                     |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Statistical Period                | Metric data is aggregated based on the configured statistical period, which can be 1 minute, 5 minutes, 15 minutes, or 1 hour.                                                                                                                                                                                                                              |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Conditions                        | Metric monitoring scope. If this parameter is left blank, all resources are covered.                                                                                                                                                                                                                                                                        |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | Each condition is in a key-value pair. You can select a dimension name from the drop-down list. The dimension value varies according to the matching mode.                                                                                                                                                                                                  |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | -  **=**: Select a dimension value from the drop-down list. For example, if **Dimension Name** is set to **Host name** and **Dimension Value** is set to **192.168.16.4**, only host **192.168.16.4** will be monitored.                                                                                                                                    |
         |                                   | -  **!=**: Select a dimension value from the drop-down list. For example, if **Dimension Name** is set to **Host name** and **Dimension Value** is set to **192.168.16.4**, all hosts excluding host **192.168.16.4** will be monitored.                                                                                                                    |
         |                                   | -  **=~**: The dimension value is determined based on one or more regular expressions. Separate regular expressions by vertical bar (|). For example, if **Dimension Name** is set to **Host name** and **Regular Expression** is set to **192.*|172.\***, only hosts whose names are **192.\*** and **172.\*** will be monitored.                          |
         |                                   | -  **!~**: The dimension value is determined based on one or more regular expressions. Separate regular expressions by vertical bar (|). For example, if **Dimension Name** is set to **Host name** and **Regular Expression** is set to **192.*|172.\***, all hosts excluding hosts **192.\*** and **172.\*** will be monitored.                           |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | For details about how to enter a regular expression, see `Regular Expression Examples <https://prometheus.io/docs/prometheus/latest/querying/examples/>`__.                                                                                                                                                                                                 |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | You can also click |image5| and select **AND** or **OR** to add more conditions for the metric.                                                                                                                                                                                                                                                             |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Grouping Condition                | Aggregate metric data by the specified field and calculate the aggregation result. Options: **Not grouped**, **avg by**, **max by**, **min by**, and **sum by**. For example, **avg by clusterName** indicates that metrics are grouped by cluster name, and the average value of the grouped metrics is calculated and displayed in the graph.             |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Rule                              | Detection rule of a metric alarm, which consists of the statistical mode (**Avg**, **Min**, **Max**, **Sum**, and **Samples**), determination criterion (**>=**, **<=**, **>**, and **<**), and threshold value. For example, if the detection rule is set to **Avg >10**, a metric alarm will be generated if the average metric value is greater than 10. |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Trigger Condition                 | When the metric value meets the alarm condition for a specified number of consecutive periods, a metric alarm will be generated. Range: 1 to 30.                                                                                                                                                                                                            |
         |                                   |                                                                                                                                                                                                                                                                                                                                                             |
         |                                   | For example, if **Consecutive Periods** is set to **2**, a metric alarm will be triggered if the trigger condition is met for two consecutive periods.                                                                                                                                                                                                      |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Alarm Severity                    | Severity of a metric alarm. Options: **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                                                                                   |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Advanced Settings** and set information such as **Check Interval** and **Alarm Clearance**. For details about the parameters, see :ref:`Table 3 <aom_05_0006__table55151160338>`.

   .. _aom_05_0006__table55151160338:

   .. table:: **Table 3** Advanced settings

      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                          | Description                                                                                                                                                                                                                                                                                 |
      +====================================+=============================================================================================================================================================================================================================================================================================+
      | Check Interval                     | Interval at which metric query and analysis results are checked.                                                                                                                                                                                                                            |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | -  **Hourly**: Query and analysis results are checked every hour.                                                                                                                                                                                                                           |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | -  **Daily**: Query and analysis results are checked at a fixed time every day.                                                                                                                                                                                                             |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | -  **Weekly**: Query and analysis results are checked at a fixed time point on a specified day of a week.                                                                                                                                                                                   |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | -  **Custom interval**: The query and analysis results are checked at a fixed interval.                                                                                                                                                                                                     |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | -  **Cron**: A cron expression is used to specify a time interval. Query and analysis results are checked at the specified interval.                                                                                                                                                        |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    |    The time specified in the cron expression can be accurate to the minute and must be in the 24-hour notation. Example: **\*/5 \* \* \* \***, which indicates that the check starts from 0th minute and is performed every 5 minutes.                                                      |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Clearance                    | The alarm will be cleared when the alarm condition is not met for a specified number of consecutive periods. By default, AOM monitors metrics in only one period. You can set up to five monitoring periods.                                                                                |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | For example, if **Consecutive Periods** is set to **2**, the alarm will be cleared when the alarm condition is not met for two consecutive periods.                                                                                                                                         |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Action Taken for Insufficient Data | Action to be taken when no metric data is generated or metric data is insufficient within the monitoring period. You can set this option based on your requirements.                                                                                                                        |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | By default, AOM monitors metrics in only one period. You can set up to five monitoring periods.                                                                                                                                                                                             |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | The system supports the following actions: changing the status to **Exceeded** and sending an alarm, changing the status to **Insufficient data** and sending an event, maintaining **Previous status**, and changing the status to **Normal** and sending an alarm clearance notification. |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Tag                          | Click |image6| to add an alarm tag. Alarm identification attribute. It is in the format of "key:value".                                                                                                                                                                                     |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | For details, see :ref:`Alarm Tags and Annotations <mon_01_0044>`.                                                                                                                                                                                                                           |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Annotation                   | Click |image7| to add an alarm annotation. Alarm non-identification attribute. It is used in alarm notification and message template scenarios. It is in the format of "key:value".                                                                                                         |
      |                                    |                                                                                                                                                                                                                                                                                             |
      |                                    | For details, see :ref:`Alarm Tags and Annotations <mon_01_0044>`.                                                                                                                                                                                                                           |
      +------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Set an alarm notification policy. For details, see :ref:`Table 4 <aom_05_0006__en-us_topic_0000001582534348_table823515532545>`.

   .. _aom_05_0006__en-us_topic_0000001582534348_table823515532545:

   .. table:: **Table 4** Parameters for setting an alarm notification policy

      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                |
      +===================================+============================================================================================================================================================================================================================================================+
      | Notify When                       | Set the scenario for sending alarm notifications.                                                                                                                                                                                                          |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | -  **Alarm triggered**: If the alarm trigger condition is met, the system sends an alarm notification to the specified personnel by email or SMS.                                                                                                          |
      |                                   | -  **Alarm cleared**: If the alarm clearance condition is met, the system sends an alarm notification to the specified personnel by email or SMS.                                                                                                          |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Mode                        | **Direct alarm reporting**: An alarm is directly sent when the alarm condition is met. If you select this mode, set an interval for notification and specify whether to enable an action rule.                                                             |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | **Frequency**: interval for sending alarm notifications. Select a desired value from the drop-down list.                                                                                                                                                   |
      |                                   |                                                                                                                                                                                                                                                            |
      |                                   | After an alarm action rule is enabled, the system sends notifications based on the associated SMN topic and message template. If the existing alarm action rules cannot meet your requirements, click **Create Rule** in the drop-down list to create one. |
      +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **Confirm**. Then click **View Rule** to view the created alarm rule.

   In the expanded list, if a metric value meets the configured alarm condition, a metric alarm is generated on the alarm page. To view it, choose **Alarm Management** > **Alarm List** in the navigation pane. If a metric value meets the preset notification policy, the system sends an alarm notification to the specified personnel by email or SMS.

Viewing Alarms
--------------

#. In the navigation pane, choose **Alarm Management** > **Alarm List**.

#. Click the **Alarms** tab to view the alarm information.

   a. Set a time range to view alarms. There are two methods to set a time range:

      Method 1: Use a predefined time label, such as **Last hour** or **Last 6 hours** in the upper right corner of the page. You can select a time range as required.

      Method 2: Specify the start time and end time to customize a time range. You can specify up to 31 days.

   b. Set the interval for refreshing alarms. Click |image8| and select a value from the drop-down list as required, such as **Refresh manually** or **1 minute auto refresh**.

   c. Set filter criteria and click |image9| to view the alarms generated in the period.

#. Perform the operations listed in :ref:`Table 5 <aom_05_0006__table48312734713>` as required.

   .. _aom_05_0006__table48312734713:

   .. table:: **Table 5** Operations

      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                         | Description                                                                                                                                                        |
      +===================================+====================================================================================================================================================================+
      | Viewing alarm statistics          | Click |image10|, and view alarm statistics that meet filter criteria within a specific time range on a bar graph.                                                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Clearing alarms                   | -  To clear an alarm, click |image11| in the **Operation** column of the target alarm.                                                                             |
      |                                   | -  To clear one or more alarms, select them and click **Clear** in the displayed dialog box.                                                                       |
      |                                   |                                                                                                                                                                    |
      |                                   |    .. note::                                                                                                                                                       |
      |                                   |                                                                                                                                                                    |
      |                                   |       You can clear an alarm after the corresponding problem is resolved.                                                                                          |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing alarm details             | Click an alarm name to view alarm details, including alarm information and handling suggestions. You can also view an alarm action rule bound with the alarm rule. |
      |                                   |                                                                                                                                                                    |
      |                                   | On the **Alarm Info** tab page, click the text in blue to view more details.                                                                                       |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing cleared alarms            | Click **Active Alarms** in the upper right corner and select **Historical Alarms** from the drop-down list to view alarms that have been cleared.                  |
      +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002482912896.png
.. |image2| image:: /_static/images/en-us_image_0000002482792924.png
.. |image3| image:: /_static/images/en-us_image_0000002514992895.png
.. |image4| image:: /_static/images/en-us_image_0000002482792926.png
.. |image5| image:: /_static/images/en-us_image_0000002515112903.png
.. |image6| image:: /_static/images/en-us_image_0000002482792894.png
.. |image7| image:: /_static/images/en-us_image_0000002515112891.png
.. |image8| image:: /_static/images/en-us_image_0000002515112875.png
.. |image9| image:: /_static/images/en-us_image_0000002482912886.png
.. |image10| image:: /_static/images/en-us_image_0000002515112889.png
.. |image11| image:: /_static/images/en-us_image_0000002514992881.png

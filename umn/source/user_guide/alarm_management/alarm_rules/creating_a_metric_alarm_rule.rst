:original_name: mon_01_0008.html

.. _mon_01_0008:

Creating a Metric Alarm Rule
============================

You can set threshold conditions in metric alarm rules for resource metrics. If a metric value meets a threshold condition, a threshold alarm will be reported. If there is no metric data, an insufficient data event will be reported.

Functions
---------

-  You can set the consecutive periods, statistical period, and threshold condition. For details, see :ref:`4.c <mon_01_0008__en-us_topic_0000001258590587_li1427514496416>`.
-  You can set whether to send a notification when an alarm is cleared. For details, see :ref:`4.c <mon_01_0008__en-us_topic_0000001258590587_li1427514496416>`.

Creation Mode
-------------

Metric alarm rules can be created in three modes: :ref:`Select by resource type <mon_01_0008__en-us_topic_0000001258590587_section1730413195014>`, :ref:`Select from all metrics <mon_01_0008__en-us_topic_0000001258590587_section55514016355>`, and :ref:`Run Prometheus statement <mon_01_0008__en-us_topic_0000001258590587_section66611555183414>`.

When creating metric alarm rules by resource type, you can set an alarm condition using two methods: :ref:`Custom <mon_01_0008__en-us_topic_0000001258590587_li192716462914>` and :ref:`Template <mon_01_0008__en-us_topic_0000001258590587_li53652251015>`. If you select the second method, first create an alarm template by referring to :ref:`Creating an Alarm Template <mon_01_0009>`.

Precautions
-----------

If you need AOM to send email or SMS notifications when the metric alarm rule status (**Exceeded**, **Normal**, **Insufficient**, or **Disabled**) changes, set an alarm action rule according to :ref:`Creating an Alarm Action Rule <mon_01_0015>`.

.. _mon_01_0008__en-us_topic_0000001258590587_section1730413195014:

Creating Metric Alarm Rules by Resource Type
--------------------------------------------

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. On the **Alarm Rules** tab page, click **Create Alarm Rule**.

#. Set basic information about the alarm rule by referring to :ref:`Table 1 <mon_01_0008__en-us_topic_0000001258590587_table1249723616548>`.

   .. _mon_01_0008__en-us_topic_0000001258590587_table1249723616548:

   .. table:: **Table 1** Basic information

      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Description                                                                                                             |
      +=============+=========================================================================================================================+
      | Rule Name   | Name of a rule. Enter a maximum of 255 characters. The following special characters are not allowed: "$# ``%&'+;<=>?\`` |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Description | Description of the rule. Enter up to 1,000 characters.                                                                  |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+

#. Set the detailed information about the alarm rule.

   a. Set **Rule Type** to **Metric alarm rule**.

   b. Set **Configuration Mode** to **Select by resource type** and set **Resource Type** and **Monitored Object**. :ref:`Table 2 <mon_01_0008__en-us_topic_0000001258590587_table1544185172315>` describes the parameters.

      .. _mon_01_0008__en-us_topic_0000001258590587_table1544185172315:

      .. table:: **Table 2** Parameter description

         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                                                                                                                                                                                                            |
         +===================================+========================================================================================================================================================================================================================================================================================================================================================================+
         | Resource Type                     | Select a desired resource type from the drop-down list.                                                                                                                                                                                                                                                                                                                |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                        |
         |                                   | -  When you click the **Application Metrics** tab, you can select resources based on the following dimensions:                                                                                                                                                                                                                                                         |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                        |
         |                                   |    -  **Host**: Select resources by host, including host, host disk, host network, host file system, and host GPU.                                                                                                                                                                                                                                                     |
         |                                   |    -  **Application**: Select resources by application.                                                                                                                                                                                                                                                                                                                |
         |                                   |    -  **Component**: Select resources by component.                                                                                                                                                                                                                                                                                                                    |
         |                                   |    -  **Process**: Select resources by process.                                                                                                                                                                                                                                                                                                                        |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                        |
         |                                   | -  When you click the **Cloud Service Metrics** tab, you can select resources by cloud service.                                                                                                                                                                                                                                                                        |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                        |
         |                                   | For example, if you select CCE from the cloud service list and then choose **Host** > **Host Disk**, the resource type will be **CCE/Host/Host Disk**, indicating that the disk of a CCE host is to be monitored.                                                                                                                                                      |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Monitored Object                  | Click **Select Monitored Object**. All existing resources of the type you select will be displayed. Select target resources as required.                                                                                                                                                                                                                               |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                        |
         |                                   | If you enable **Apply to All** when selecting monitored objects, an alarm rule will be created for all resources of the type you select under an application or service. When this type of resources are added or modified, they will be automatically bound to the created alarm rule. When they are deleted, they will be automatically unbound from the alarm rule. |
         |                                   |                                                                                                                                                                                                                                                                                                                                                                        |
         |                                   | For example, if **Resource Type** is set to **CCE/Host/Host Disk** and the **Apply to All** option is enabled when you select monitored objects, an alarm rule will be created for all CCE host disks. If a CCE host disk is added to the system, the new host disk will be automatically bound to the alarm rule.                                                     |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   c. .. _mon_01_0008__en-us_topic_0000001258590587_li1427514496416:

      Set an alarm condition. Customize an alarm condition or import an alarm condition from a template.

      -  .. _mon_01_0008__en-us_topic_0000001258590587_li192716462914:

         **Custom**

         Click **Custom** and set the statistical period, consecutive periods, and alarm condition. :ref:`Table 3 <mon_01_0008__en-us_topic_0000001258590587_table77001133203019>` describes the parameters.


         .. figure:: /_static/images/en-us_image_0000002289469477.png
            :alt: **Figure 1** Setting an alarm condition

            **Figure 1** Setting an alarm condition

         .. _mon_01_0008__en-us_topic_0000001258590587_table77001133203019:

         .. table:: **Table 3** Alarm condition parameters

            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | Category              | Parameter                          | Description                                                                                                                                                                                                                                                                                     |
            +=======================+====================================+=================================================================================================================================================================================================================================================================================================+
            | Alarm Condition       | Metric                             | Metric to be monitored.                                                                                                                                                                                                                                                                         |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Consecutive Periods                | When the metric value meets the alarm condition for a specified number of consecutive periods, a metric alarm will be generated.                                                                                                                                                                |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Statistical Period                 | Metric data is aggregated based on the configured statistical period, which can be 1 minute, 5 minutes, 15 minutes, or 1 hour.                                                                                                                                                                  |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Statistic                          | Method used to measure metrics. Options: **Avg**, **Min**, **Max**, **Sum**, and **Samples**.                                                                                                                                                                                                   |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Alarm Condition                    | Trigger condition of a metric alarm. An alarm condition consists of two parts: operators (>=, <=, >, and <) and threshold value. For example, if the trigger condition is set to **> 85** and an actual metric value exceeds 85, a metric alarm will be generated.                              |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Alarm Severity                     | Severity of a metric alarm. Options: **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                       |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | ``-``                 | Check Interval                     | Interval at which metric query and analysis results are checked.                                                                                                                                                                                                                                |
            |                       |                                    |                                                                                                                                                                                                                                                                                                 |
            |                       |                                    | -  **Hourly**: Query and analysis results are checked every hour.                                                                                                                                                                                                                               |
            |                       |                                    |                                                                                                                                                                                                                                                                                                 |
            |                       |                                    | -  **Daily**: Query and analysis results are checked at a fixed time every day.                                                                                                                                                                                                                 |
            |                       |                                    |                                                                                                                                                                                                                                                                                                 |
            |                       |                                    | -  **Weekly**: Query and analysis results are checked at a fixed time point on a specified day of a week.                                                                                                                                                                                       |
            |                       |                                    |                                                                                                                                                                                                                                                                                                 |
            |                       |                                    | -  **Custom interval**: The query and analysis results are checked at a fixed interval.                                                                                                                                                                                                         |
            |                       |                                    |                                                                                                                                                                                                                                                                                                 |
            |                       |                                    | -  **Cron**: A cron expression is used to specify a time interval. Query and analysis results are checked at the specified interval.                                                                                                                                                            |
            |                       |                                    |                                                                                                                                                                                                                                                                                                 |
            |                       |                                    |    The time specified in the cron expression can be accurate to the minute and must be in the 24-hour notation. Example: **0/5 \* \* \* \***, which indicates that the check starts from 0th minute and is performed every 5 minutes.                                                           |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            | Advanced Settings     | Alarm Clearance                    | An alarm will be cleared if the monitored object does not meet the trigger condition within the monitoring period. By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                             |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
            |                       | Action Taken for Insufficient Data | Action to be taken when no metric data is generated or metric data is insufficient within the monitoring period. You can set this option based on your requirements.                                                                                                                            |
            |                       |                                    |                                                                                                                                                                                                                                                                                                 |
            |                       |                                    | By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                                                                                                                                                |
            |                       |                                    |                                                                                                                                                                                                                                                                                                 |
            |                       |                                    | The system supports the following actions: changing the status to **exceeded** and sending an alarm, changing the status to **insufficient data** and sending an event, maintaining the **previous status**, and changing the status to **normal** and sending an alarm clearance notification. |
            +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

      -  .. _mon_01_0008__en-us_topic_0000001258590587_li53652251015:

         **Template**

         Select **Template** and set related parameters. Ensure that you have created an alarm template. For details, see :ref:`Creating an Alarm Template <mon_01_0009>`.

         .. table:: **Table 4** Alarm condition parameters

            +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
            | Parameter                          | Description                                                                                                                                   |
            +====================================+===============================================================================================================================================+
            | Bind Template                      | Specifies whether to bind an alarm profile.                                                                                                   |
            +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
            | Alarm Template                     | Select an alarm template. If the existing templates do not meet requirements, click :ref:`Create Alarm Template <mon_01_0009>` to create one. |
            +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
            | Alarm Condition                    | The system automatically imports the preset alarm condition in the template. Note that the condition cannot be modified.                      |
            +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
            | Check Interval                     | The system automatically imports the check interval set in the template. Note that the check interval cannot be modified.                     |
            +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
            | Alarm Clearance                    | The system automatically imports the alarm clearance setting in the template. Note that it cannot be modified.                                |
            +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
            | Action Taken for Insufficient Data | The system automatically imports the action setting in the template. Note that it cannot be modified.                                         |
            +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+

   d. Set alarm tags and annotations to group alarms. For details, see :ref:`Alarm Tags and Annotations <mon_01_0044>`.

      Click **Add Tag** or **Add Annotation**.

#. Set an alarm notification policy.

   -  **Direct alarm reporting**: An alarm is directly sent when the alarm condition is met.

      a. Specify whether to enable an alarm action rule. After an alarm action rule is enabled, the system sends notifications based on the associated SMN topic and message template. If the existing alarm action rules cannot meet your requirements, click **Create Rule** to create one. For details, see :ref:`Creating an Alarm Action Rule <mon_01_0015>`.
      b. After an alarm action rule is selected, specify whether to enable alarm clearance notification. After alarm clearance notification is enabled, if the alarm clearance condition set in :ref:`Advanced Settings > Alarm Clearance <mon_01_0008__en-us_topic_0000001258590587_li192716462914>` is met, alarm clearance notifications are sent based on the selected action rule.


      .. figure:: /_static/images/en-us_image_0000002289582549.png
         :alt: **Figure 2** Setting an alarm notification policy

         **Figure 2** Setting an alarm notification policy

#. Click **Confirm**. Then, click **Back to Alarm Rule List** to view the created alarm rule.

   Click |image1| in front of the rule name to check its details.

   In the expanded list, if a metric value meets the configured alarm condition, a metric alarm is generated on the alarm page. To view it, choose **Alarm Management** > **Alarm List** in the navigation pane. If a host meets the preset notification policy, the system sends an alarm notification to the specified personnel by email or SMS.

.. _mon_01_0008__en-us_topic_0000001258590587_section55514016355:

Creating Metric Alarm Rules by Selecting Metrics from All Metrics
-----------------------------------------------------------------

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. On the **Alarm Rules** tab page, click **Create Alarm Rule**.

#. Set basic information about the alarm rule by referring to :ref:`Table 5 <mon_01_0008__en-us_topic_0000001258590587_en-us_topic_0000001258590587_table1249723616548>`.

   .. _mon_01_0008__en-us_topic_0000001258590587_en-us_topic_0000001258590587_table1249723616548:

   .. table:: **Table 5** Basic information

      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Description                                                                                                             |
      +=============+=========================================================================================================================+
      | Rule Name   | Name of a rule. Enter a maximum of 255 characters. The following special characters are not allowed: "$# ``%&'+;<=>?\`` |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Description | Description of the rule. Enter up to 1,000 characters.                                                                  |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+

#. Set the detailed information about the alarm rule.

   a. Set **Rule Type** to **Metric alarm rule**.

   b. Set **Configuration Mode** to **Select from all metrics**.

      .. note::

         -  When **All metrics** is selected, you can only enter English keywords to search and only English content is displayed.
         -  **Scope**: Metric monitoring scope. The scope is in the key-value pair format. Directly select an option from the drop-down list or use **AND**, **OR**, and **NOT** to specify scopes for metrics.
         -  **Group Condition**: Aggregate metric data by the specified field and calculate the aggregation result. Options: **Not grouped**, **avg by**, **max by**, **min by**, and **sum by**. For example, **avg by clusterName** indicates that metrics are grouped by cluster name, and the average value of the grouped metrics is calculated and displayed in the graph.

   c. .. _mon_01_0008__en-us_topic_0000001258590587_li15983164491:

      Set parameters such as the metric, environment, and check interval. :ref:`Table 6 <mon_01_0008__en-us_topic_0000001258590587_table7603130141213>` describes the parameters.

      After an alarm condition is set, the monitored metric data is displayed in a line graph above the alarm condition. You can click **Hide Graph**, |image2| before a metric name, or the line icon before each metric data record to hide the metric data in the graph.

      .. _mon_01_0008__en-us_topic_0000001258590587_table7603130141213:

      .. table:: **Table 6** Alarm condition parameters

         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Category              | Parameter                          | Description                                                                                                                                                                                                                                                                                                                                     |
         +=======================+====================================+=================================================================================================================================================================================================================================================================================================================================================+
         | Alarm Condition       | Metric                             | Select the metric to be monitored.                                                                                                                                                                                                                                                                                                              |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Scope                              | Metric monitoring scope.                                                                                                                                                                                                                                                                                                                        |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | The scope is in the key-value pair format. Directly select an option from the drop-down list or use **AND**, **OR**, and **NOT** to specify scopes for metrics.                                                                                                                                                                                 |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Grouping Condition                 | Aggregate metric data by the specified field and calculate the aggregation result. Options: **Not grouped**, **avg by**, **max by**, **min by**, and **sum by**. For example, **avg by clusterName** indicates that metrics are grouped by cluster name, and the average value of the grouped metrics is calculated and displayed in the graph. |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Alarm Condition                    | Condition for triggering a metric alarm. It consists of the grouping condition (not grouped), judgment condition (>=, <=, >, and <), and threshold. For example, if the trigger condition is set to **> 85** and an actual metric value exceeds 85, a metric alarm will be generated.                                                           |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | Move the cursor to the graph area above the alarm condition. The ID, IP address, and unit of the current metric are displayed.                                                                                                                                                                                                                  |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Alarm Severity                     | Severity of a metric alarm. Options: **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                                                                       |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | ``-``                 | Check Interval                     | Interval at which metric query and analysis results are checked.                                                                                                                                                                                                                                                                                |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Hourly**: Query and analysis results are checked every hour.                                                                                                                                                                                                                                                                               |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Daily**: Query and analysis results are checked at a fixed time every day.                                                                                                                                                                                                                                                                 |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Weekly**: Query and analysis results are checked at a fixed time point on a specified day of a week.                                                                                                                                                                                                                                       |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Custom interval**: The query and analysis results are checked at a fixed interval.                                                                                                                                                                                                                                                         |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Cron**: A cron expression is used to specify a time interval. Query and analysis results are checked at a specified interval.                                                                                                                                                                                                              |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    |    The time specified in the cron expression can be accurate to the minute and must be in the 24-hour notation. Example: **0/5 \* \* \* \***, which indicates that the check starts from 0th minute and is performed every 5 minutes.                                                                                                           |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | ``-``                 | Statistical Period                 | Metric data is aggregated based on the configured statistical period and statistical mode. If the threshold condition is met for a specified number of consecutive periods, a metric alarm is generated. By default, metrics in the last minute are collected.                                                                                  |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Advanced Settings     | Alarm Clearance                    | An alarm will be cleared if the monitored object does not meet the trigger condition within the monitoring period. By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                                                                             |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Action Taken for Insufficient Data | Action to be taken when no metric data is generated or metric data is insufficient within the monitoring period. You can set this option based on your requirements.                                                                                                                                                                            |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                                                                                                                                                                                                |
         |                       |                                    |                                                                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | The system supports the following actions: changing the status to **exceeded** and sending an alarm, changing the status to **insufficient data** and sending an event, maintaining the **previous status**, and changing the status to **normal** and sending an alarm clearance notification.                                                 |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   d. Set alarm tags and annotations to group alarms. For details, see :ref:`Alarm Tags and Annotations <mon_01_0044>`.

      Click **Add Tag** or **Add Annotation**.

#. Set an alarm notification policy.

   -  **Direct alarm reporting**: An alarm is directly sent when the alarm condition is met.

      a. Specify whether to enable an alarm action rule. After an alarm action rule is enabled, the system sends notifications based on the associated SMN topic and message template. If the existing alarm action rules cannot meet your requirements, click **Create Rule** to create one. For details, see :ref:`Creating an Alarm Action Rule <mon_01_0015>`.
      b. After an alarm action rule is selected, specify whether to enable alarm clearance notification. After alarm clearance notification is enabled, if the alarm clearance condition set in :ref:`Advanced Settings > Alarm Clearance <mon_01_0008__en-us_topic_0000001258590587_li15983164491>` is met, alarm clearance notifications are sent based on the selected action rule.


      .. figure:: /_static/images/en-us_image_0000002254812292.png
         :alt: **Figure 3** Setting an alarm notification policy

         **Figure 3** Setting an alarm notification policy

#. Click **Confirm**. Then, click **Back to Alarm Rule List** to view the created alarm rule.

   Click |image3| in front of the rule name to check its details.

   In the expanded list, if a metric value meets the configured alarm condition, a metric alarm is generated on the alarm page. To view it, choose **Alarm Management** > **Alarm List** in the navigation pane. If a host meets the preset notification policy, the system sends an alarm notification to the specified personnel by email or SMS.

.. _mon_01_0008__en-us_topic_0000001258590587_section66611555183414:

Creating Metric Alarm Rules by Running Prometheus Statements
------------------------------------------------------------

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. On the **Alarm Rules** tab page, click **Create Alarm Rule**.

#. Set basic information about the alarm rule by referring to :ref:`Table 5 <mon_01_0008__en-us_topic_0000001258590587_en-us_topic_0000001258590587_table1249723616548>`.

   .. table:: **Table 7** Basic information

      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Description                                                                                                             |
      +=============+=========================================================================================================================+
      | Rule Name   | Name of a rule. Enter a maximum of 255 characters. The following special characters are not allowed: "$# ``%&'+;<=>?\`` |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Description | Description of the rule. Enter up to 1,000 characters.                                                                  |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+

#. Set the detailed information about the alarm rule.

   a. Set **Rule Type** to **Metric alarm rule**.

   b. Set **Configuration Mode** to **Run Prometheus statement**.

   c. Enter a Prometheus statement. There are two modes: manual input and auto input.

      -  Manual input: used when you know the metric name and IP address, and you are familiar with Prometheus statement formats. Click **Search**. Related metric graphs are displayed in the lower part of the page in real time.

      -  Auto input: used when you do not know the metric information or are unfamiliar with the Prometheus format. The command can only be automatically filled when you switch from the **Metric Browsing** page.

         Specifically, choose **Metric Browsing** in the navigation pane. Set **Add By** to **Metric type**, **All Metrics**, or **Resource type** and select one or more metrics from the resource tree. Next, click |image4| in the **Operation** column. The system automatically switches to the metric alarm rule creation page and autocompletes the Prometheus command.

      -  You can click **View Example** to get more information. For details, see :ref:`Prometheus Statements <mon_01_0043>`.

   d. .. _mon_01_0008__en-us_topic_0000001258590587_li340217116357:

      Set an alarm condition. Set alarm condition parameters, such as consecutive periods, statistical period, and threshold condition. :ref:`Table 8 <mon_01_0008__en-us_topic_0000001258590587_table1540212120350>` describes the parameters.


      .. figure:: /_static/images/en-us_image_0000002254869244.png
         :alt: **Figure 4** Setting an alarm condition

         **Figure 4** Setting an alarm condition

      .. _mon_01_0008__en-us_topic_0000001258590587_table1540212120350:

      .. table:: **Table 8** Alarm condition parameters

         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Category              | Parameter                          | Description                                                                                                                                                                                                                                                                                     |
         +=======================+====================================+=================================================================================================================================================================================================================================================================================================+
         | Alarm Condition       | Consecutive Periods                | When the metric value meets the alarm condition for a specified number of consecutive periods, a metric alarm will be generated.                                                                                                                                                                |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Statistical Period                 | Metric data is aggregated based on the configured statistical period, which can be 1 minute, 5 minutes, 15 minutes, or 1 hour.                                                                                                                                                                  |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Statistic                          | Method used to measure metrics. Options: **Avg**, **Min**, **Max**, **Sum**, and **Samples**.                                                                                                                                                                                                   |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Alarm Condition                    | Trigger condition of a metric alarm. An alarm condition consists of two parts: operators (>=, <=, >, and <) and threshold value. For example, if the trigger condition is set to **> 85** and an actual metric value exceeds 85, a metric alarm will be generated.                              |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Alarm Severity                     | Severity of a metric alarm. Options: **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                       |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | ``-``                 | Check Interval                     | Interval at which metric query and analysis results are checked.                                                                                                                                                                                                                                |
         |                       |                                    |                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Hourly**: Query and analysis results are checked every hour.                                                                                                                                                                                                                               |
         |                       |                                    |                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Daily**: Query and analysis results are checked at a fixed time every day.                                                                                                                                                                                                                 |
         |                       |                                    |                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Weekly**: Query and analysis results are checked at a fixed time point on a specified day of a week.                                                                                                                                                                                       |
         |                       |                                    |                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Custom interval**: The query and analysis results are checked at a fixed interval.                                                                                                                                                                                                         |
         |                       |                                    |                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | -  **Cron**: A cron expression is used to specify a time interval. Query and analysis results are checked at a specified interval.                                                                                                                                                              |
         |                       |                                    |                                                                                                                                                                                                                                                                                                 |
         |                       |                                    |    The time specified in the cron expression can be accurate to the minute and must be in the 24-hour notation. Example: **0/5 \* \* \* \***, which indicates that the check starts from 0th minute and is performed every 5 minutes.                                                           |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Advanced Settings     | Alarm Clearance                    | An alarm will be cleared if the monitored object does not meet the trigger condition within the monitoring period. By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                             |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Action Taken for Insufficient Data | Action to be taken when no metric data is generated or metric data is insufficient within the monitoring period. You can set this option based on your requirements.                                                                                                                            |
         |                       |                                    |                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                                                                                                                                                |
         |                       |                                    |                                                                                                                                                                                                                                                                                                 |
         |                       |                                    | The system supports the following actions: changing the status to **exceeded** and sending an alarm, changing the status to **insufficient data** and sending an event, maintaining the **previous status**, and changing the status to **normal** and sending an alarm clearance notification. |
         +-----------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   e. Set alarm tags and annotations to group alarms. For details, see :ref:`Alarm Tags and Annotations <mon_01_0044>`.

      Click **Add Tag** or **Add Annotation**.

#. Set an alarm notification policy.

   -  **Direct alarm reporting**: An alarm is directly sent when the alarm condition is met.

      a. Specify whether to enable an alarm action rule. After an alarm action rule is enabled, the system sends notifications based on the associated SMN topic and message template. If the existing alarm action rules cannot meet your requirements, click **Create Rule** to create one. For details, see :ref:`Creating an Alarm Action Rule <mon_01_0015>`.
      b. After an alarm action rule is selected, specify whether to enable alarm clearance notification. After alarm clearance notification is enabled, if the alarm clearance condition set in :ref:`Advanced Settings > Alarm Clearance <mon_01_0008__en-us_topic_0000001258590587_li340217116357>` is met, alarm clearance notifications are sent based on the selected action rule.


      .. figure:: /_static/images/en-us_image_0000002289469505.png
         :alt: **Figure 5** Setting an alarm notification policy

         **Figure 5** Setting an alarm notification policy

#. Click **Confirm**. Then, click **Back to Alarm Rule List** to view the created alarm rule.

   Click |image5| in front of the rule name to check its details.

   In the expanded list, if a metric value meets the configured alarm condition, a metric alarm is generated on the alarm page. To view it, choose **Alarm Management** > **Alarm List** in the navigation pane. If a host meets the preset notification policy, the system sends an alarm notification to the specified personnel by email or SMS.

.. |image1| image:: /_static/images/en-us_image_0000002289582537.png
.. |image2| image:: /_static/images/en-us_image_0000002254869216.png
.. |image3| image:: /_static/images/en-us_image_0000002289582553.png
.. |image4| image:: /_static/images/en-us_image_0000002254812272.png
.. |image5| image:: /_static/images/en-us_image_0000002254869204.png

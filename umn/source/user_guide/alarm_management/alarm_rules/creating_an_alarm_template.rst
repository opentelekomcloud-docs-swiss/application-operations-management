:original_name: mon_01_0009.html

.. _mon_01_0009:

Creating an Alarm Template
==========================

An alarm template is a group of alarm rules for a resource. You can create alarm rules for multiple metrics of the same resource in batches. Ensure that an alarm template is available before you use a template to create alarm rules.

Precautions
-----------

You can create up to 150 alarm templates. If the number of alarm templates reaches 150, delete unnecessary templates and create new ones.

Background
----------

AOM presets default alarm templates for key metrics (including CPU usage, physical memory usage, host status, and service status) of all hosts and services. You can locate the desired default alarm template and click |image1| in the **Operation** column to quickly customize your own alarm template.

Procedure
---------

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. On the **Alarm Templates** tab page, click **Create Alarm Template**.

#. Customize an alarm template. For details, see :ref:`Table 1 <mon_01_0009__en-us_topic_0000001258510521_table4622183617485>`.


   .. figure:: /_static/images/en-us_image_0000002254869128.png
      :alt: **Figure 1** Customizing an alarm template

      **Figure 1** Customizing an alarm template

   .. _mon_01_0009__en-us_topic_0000001258510521_table4622183617485:

   .. table:: **Table 1** Alarm template parameters

      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Category                        | Parameter                          | Description                                                                                                                                                                                                                                                                                     |
      +=================================+====================================+=================================================================================================================================================================================================================================================================================================+
      | Template Info                   | Template Name                      | Name of the template. Enter a maximum of 64 characters. The following special characters are not allowed: ``"$#%&'+;<=>?\``                                                                                                                                                                     |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                                 | Description                        | Description of the template. Enter up to 256 characters.                                                                                                                                                                                                                                        |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Rules                     | Monitored Object                   | Select a monitored object from the resource tree.                                                                                                                                                                                                                                               |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Rules > Alarm Condition   | Metrics                            | Metrics to be monitored.                                                                                                                                                                                                                                                                        |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                                 | Consecutive Periods                | When the metric value meets the alarm condition for a specified number of consecutive periods, a metric alarm will be generated.                                                                                                                                                                |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                                 | Statistical Period                 | Metric data is aggregated based on the configured statistical period, which can be 1 minute, 5 minutes, 15 minutes, or 1 hour.                                                                                                                                                                  |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                                 | Statistic                          | Method used to measure metrics. Options: **Avg**, **Min**, **Max**, **Sum**, and **Samples**.                                                                                                                                                                                                   |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                                 | Alarm Condition                    | Trigger condition of a metric alarm. An alarm condition consists of two parts: operators (>=, <=, >, and <) and threshold value. For example, if the trigger condition is set to **> 85** and an actual metric value exceeds 85, a metric alarm will be generated.                              |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                                 | Alarm Severity                     | Severity of a metric alarm. Options: **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                       |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Rules                     | Check Interval                     | Interval at which metric query and analysis results are checked.                                                                                                                                                                                                                                |
      |                                 |                                    |                                                                                                                                                                                                                                                                                                 |
      |                                 |                                    | -  **Hourly**: Query and analysis results are checked every hour.                                                                                                                                                                                                                               |
      |                                 |                                    |                                                                                                                                                                                                                                                                                                 |
      |                                 |                                    | -  **Daily**: Query and analysis results are checked at a fixed time every day.                                                                                                                                                                                                                 |
      |                                 |                                    |                                                                                                                                                                                                                                                                                                 |
      |                                 |                                    | -  **Weekly**: Query and analysis results are checked at a fixed time point on a specified day of a week.                                                                                                                                                                                       |
      |                                 |                                    |                                                                                                                                                                                                                                                                                                 |
      |                                 |                                    | -  **Custom interval**: The query and analysis results are checked at a fixed interval.                                                                                                                                                                                                         |
      |                                 |                                    |                                                                                                                                                                                                                                                                                                 |
      |                                 |                                    | -  **Cron**: A cron expression is used to specify a time interval. Query and analysis results are checked at a specified interval.                                                                                                                                                              |
      |                                 |                                    |                                                                                                                                                                                                                                                                                                 |
      |                                 |                                    |    The time specified in the cron expression can be accurate to the minute and must be in the 24-hour notation. Example: **0/5 \* \* \* \***, which indicates that the check starts from 0th minute and is performed every 5 minutes.                                                           |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Rules > Advanced Settings | Alarm Clearance                    | An alarm will be cleared if the monitored object does not meet the trigger condition within the monitoring period. By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                             |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                                 | Action Taken for Insufficient Data | Action to be taken when no metric data is generated or metric data is insufficient within the monitoring period. You can configure this option based on your requirements.                                                                                                                      |
      |                                 |                                    |                                                                                                                                                                                                                                                                                                 |
      |                                 |                                    | By default, metrics in only one period are monitored. You can set up to five monitoring periods.                                                                                                                                                                                                |
      |                                 |                                    |                                                                                                                                                                                                                                                                                                 |
      |                                 |                                    | The system supports the following actions: changing the status to **exceeded** and sending an alarm, changing the status to **insufficient data** and sending an event, maintaining the **previous status**, and changing the status to **normal** and sending an alarm clearance notification. |
      +---------------------------------+------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

More Operations
---------------

After the alarm template is created, you can also perform the operations listed in :ref:`Table 2 <mon_01_0009__en-us_topic_0000001258510521_en-us_topic_0169698339_table15831736105910>`.

.. _mon_01_0009__en-us_topic_0000001258510521_en-us_topic_0169698339_table15831736105910:

.. table:: **Table 2** Related operations

   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                                                                                                                                                        |
   +===================================+====================================================================================================================================================================================================================================================+
   | Viewing an alarm template         | In the template list, you can view information such as the template name, monitored object, and bound rules. Click |image2| on the left of the template name. In the expanded list, you can view details about the bound rule and alarm condition. |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Modifying an alarm template       | Click |image3| in the **Operation** column.                                                                                                                                                                                                        |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Copying an alarm template         | Click |image4| in the **Operation** column.                                                                                                                                                                                                        |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting alarm templates          | -  To delete an alarm template, click |image5| in the **Operation** column.                                                                                                                                                                        |
   |                                   | -  To delete one or more alarm templates, select them and click **Delete** above the template list.                                                                                                                                                |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Unbinding an alarm rule           | Click |image6| next to the template name. On the **Bound Rule** tab page, click **Unbind** in the row that contains the desired rule to unbind it from the alarm template.                                                                         |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for an alarm template   | Enter a template name in the search box in the upper right corner and click |image7|.                                                                                                                                                              |
   +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002254812184.png
.. |image2| image:: /_static/images/en-us_image_0000002254869144.png
.. |image3| image:: /_static/images/en-us_image_0000002289582473.png
.. |image4| image:: /_static/images/en-us_image_0000002254812176.png
.. |image5| image:: /_static/images/en-us_image_0000002254812192.png
.. |image6| image:: /_static/images/en-us_image_0000002254869136.png
.. |image7| image:: /_static/images/en-us_image_0000002289469385.png

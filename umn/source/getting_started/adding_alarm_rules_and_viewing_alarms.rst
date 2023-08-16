:original_name: aom_05_0006.html

.. _aom_05_0006:

Adding Alarm Rules and Viewing Alarms
=====================================

You can set threshold conditions for metrics by using alarm rules. If metric values meet threshold conditions, AOM will generate threshold alarms. If no metric data is reported, AOM will report insufficient data events. In this way, you can identify and handle exceptions at the earliest time.

For example, during routine O&M, a host may break down or restart due to an excessively-high CPU usage. To avoid the problem, set an alarm rule. For example, when the CPU usage of a host exceeds 85%, an alarm is reported, so that you can quickly obtain the resource running status and take measures to prevent service loss. This section describes how to add alarm rules and view alarms.

Procedure
---------

#. In the navigation pane, choose **Alarm Center** > **Alarm Rule** and click **Add Threshold**.

#. Customize alarm rules.

   a. Select resources: Enter a rule name, select a resource type, select the resources to be monitored from the resource tree, and click **Next**.

      .. note::

         -  You can select a maximum of 100 resources from the resource tree.
         -  When multiple resources are selected, multiple alarm rules will be created after the creation is complete. Each resource is monitored by an alarm rule. A rule name consists of the alarm rule name you enter in the **Threshold Name** text box, and a sequence number ranging from 0 to 99. The earlier a resource is selected, the smaller its sequence number.

   b. Customize a threshold: Select the metric to be monitored, and set parameters such as **Threshold Condition**, **Consecutive Period (s)**, **Alarm Severity**, and **Statistic Method**.

      .. note::

         -  **Threshold Condition**: Trigger condition of a threshold alarm. A threshold condition consists of two parts: determination condition (>=, <=, >, or <) and threshold value. For example, if **Threshold Condition** is set to **> 85** and an actual metric value exceeds 85, a threshold alarm will be generated.
         -  **Consecutive Period (s)**: If a metric value meets the threshold condition for a specified number of consecutive periods, a threshold alarm will be generated.
         -  **Alarm Severity**: **Critical**, **Major**, **Minor**, or **Warning**.
         -  **Statistic Method**: Method used to measure metric values.
         -  **Statistical Cycle**: Interval at which metric data is collected.

#. Click **Submit**. As shown in the following figure, multiple alarm rules are created. Each resource is monitored by an independent rule.

   For example, when a monitored component uses more than 3 CPU cores, a threshold alarm is generated on the alarm page. You can choose **Alarm Center** > **Alarm Rule** in the navigation pane to view the alarm rule.

#. In the navigation pane, choose **Alarm Center** > **Alarm List**.

#. View alarms on the **Alarm List** page.

   a. Set a time range to view alarms. There are two methods to set a time range:

      Method 1: Use a predefined time label, such as **Last 1 hour**, **Last 6 hours**, or **Last 1 day** in the upper right corner of the page. You can select a time range as required.

      Method 2: Specify the start time and end time in the upper right corner of the page to customize a time range. You can specify up to 30 days.

   b. Set filter criteria and click |image1| to view the alarms generated in the specified time range.

#. Perform the operations listed in :ref:`Table 1 <aom_05_0006__table48312734713>` as required.

   .. _aom_05_0006__table48312734713:

   .. table:: **Table 1** Operations

      +--------------------------+---------------------------------------------------------------------------------------------------+------------------------------------------------------------------------+
      | Operation                | Method                                                                                            | Description                                                            |
      +==========================+===================================================================================================+========================================================================+
      | Viewing alarm statistics | View alarm statistics that meet filter criteria within a specific time range through a bar graph. | ``-``                                                                  |
      +--------------------------+---------------------------------------------------------------------------------------------------+------------------------------------------------------------------------+
      | Clearing alarms          | In the alarm list, click |image2| in the **Operation** column of the target alarm.                | -  You can clear an alarm after the corresponding problem is resolved. |
      |                          |                                                                                                   | -  You can view the cleared alarms on the **History** tab page.        |
      +--------------------------+---------------------------------------------------------------------------------------------------+------------------------------------------------------------------------+
      | Viewing alarm details    | Click an alarm name to view alarm details.                                                        | ``-``                                                                  |
      +--------------------------+---------------------------------------------------------------------------------------------------+------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001448562717.png
.. |image2| image:: /_static/images/en-us_image_0000001448802713.png

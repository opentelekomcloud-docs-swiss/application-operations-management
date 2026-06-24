:original_name: mon_01_0011.html

.. _mon_01_0011:

Viewing Alarms
==============

Alarms are reported when AOM or an external service is abnormal or may cause exceptions. You need to take measures accordingly. Otherwise, service exceptions may occur. The **Alarms** tab page allows you to query and handle alarms, so that you can quickly detect, locate, and rectify faults.

Functions
---------

The alarm list provides the following key functions:

-  Alarm list: View alarm information by alarm severity in a graph.
-  Advanced filtering: You can filter alarms by alarm severity, source, or keyword in the search box. By default, alarms are filtered by alarm severity.
-  Alarm deletion: Delete alarms one by one or in batches.
-  Alarm details: View the alarm object and handling suggestions in the alarm details. Handling suggestions are provided for all alarms.

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane, choose **Alarm Management** > **Alarm List**.

#. Click the **Alarms** tab to view the alarm information.

   a. Set a time range to view alarms. There are two methods to set a time range:

      Method 1: Use the predefined time label, such as **Last hour** or **Last 6 hours**. You can select a time range as required.

      Method 2: Specify the start time and end time (max. 31 days).

   b. Set the interval for refreshing alarms. Click |image1| and select a value from the drop-down list, such as **Refresh manually** or **1 minute auto refresh**.

   c. Set filter criteria and click |image2| to view the alarms generated in the period.

#. Perform the operations listed in :ref:`Table 1 <mon_01_0011__en-us_topic_0000001258350597_table48312734713>` as required:

   .. _mon_01_0011__en-us_topic_0000001258350597_table48312734713:

   .. table:: **Table 1** Operations

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                         | Description                                                                                                                                                   |
      +===================================+===============================================================================================================================================================+
      | Viewing alarm statistics          | Click |image3|, and view alarm statistics that meet filter criteria within a specific time range on a bar graph.                                              |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Clearing alarms                   | -  To clear an alarm, click |image4| in the **Operation** column of the target alarm.                                                                         |
      |                                   | -  To clear one or more alarms, select them and click **Clear** in the displayed dialog box.                                                                  |
      |                                   |                                                                                                                                                               |
      |                                   |    .. note::                                                                                                                                                  |
      |                                   |                                                                                                                                                               |
      |                                   |       You can clear alarms after the problems that cause them are resolved.                                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing alarm details             | Click an alarm name to view alarm details, including alarm information and handling suggestions. You can also view a bound alarm action rule if there is any. |
      |                                   |                                                                                                                                                               |
      |                                   | On the **Alarm Info** tab page, click the alarm rule in blue to drill down to view details.                                                                   |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing cleared alarms            | Click **Active Alarms** in the upper right corner and select **Historical Alarms** from the drop-down list to view alarms that have been cleared.             |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002514992927.png
.. |image2| image:: /_static/images/en-us_image_0000002515112931.png
.. |image3| image:: /_static/images/en-us_image_0000002482792958.png
.. |image4| image:: /_static/images/en-us_image_0000002515112933.png

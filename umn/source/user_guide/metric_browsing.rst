:original_name: mon_01_0026.html

.. _mon_01_0026:

Metric Browsing
===============

The **Metric Browsing** page displays metric data of each resource. You can monitor metric values and trends in real time, and create alarm rules for real-time service data monitoring and analysis.

Monitoring Metrics
------------------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane, choose **Metric Browsing**.

#. Select a target Prometheus instance from the drop-down list.

#. Choose **Metric Sources** > **Metric List**.

#. Click **Metric type**, **All metrics**, or **Resource type** and then select one or more metrics from the resource tree. You can also add metrics by running a Prometheus statement. For details, see :ref:`Prometheus Statements <mon_01_0043>`.

   .. note::

      -  When **All metrics** is selected, enter keywords to search for metrics.
      -  **Scope**: Metric monitoring scope. The scope is in the key-value pair format. Directly select an option from the drop-down list or use **AND**, **NOT**, and **OR** to specify scopes for metrics.
      -  **Group Condition**: Aggregate metric data by the specified field and calculate the aggregation result. Options: **Not grouped**, **avg by**, **max by**, **min by**, and **sum by**. For example, **avg by clusterName** indicates that metrics are grouped by cluster name, and the average value of the grouped metrics is calculated and displayed in the graph.

#. Click **Add Metric** to add up to 12 metrics.

   .. note::

      If more than 1000 resource metrics are queried, you are advised to use the following methods to monitor metric data so that accurate and comprehensive metric data can be displayed:

      a. Adjust the metric query mode to query metric data of a specified resource.
      b. Select a top N graph.

#. Set metric parameters by referring to :ref:`Table 1 <mon_01_0026__en-us_topic_0000001213710710_d0e3947>`, view the metric graph in the upper part of the page, and analyze metric data from multiple perspectives.

   .. _mon_01_0026__en-us_topic_0000001213710710_d0e3947:

   .. table:: **Table 1** Metric parameters

      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                         |
      +===================================+=====================================================================================================================================================================================================+
      | Statistic                         | Method used to measure metrics. Options: **Avg**, **Min**, **Max**, **Sum**, and **Samples**.                                                                                                       |
      |                                   |                                                                                                                                                                                                     |
      |                                   | .. note::                                                                                                                                                                                           |
      |                                   |                                                                                                                                                                                                     |
      |                                   |    **Samples**: the number of data points.                                                                                                                                                          |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Statistical Period                | Interval at which metric data is collected.                                                                                                                                                         |
      |                                   |                                                                                                                                                                                                     |
      |                                   | The available statistical period options vary according to the time range you select. For details, see :ref:`What Is the Relationship Between the Time Range and Statistical Period <mon_01_0062>`. |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Time Range                        | Time range in which metric data is collected. Options: **Last 30 minutes**, **Last hour**, **Last 6 hours**, **Last day**, **Last week**, and **Custom**.                                           |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Refresh Frequency                 | Interval at which the metric data is refreshed. Options: **Refresh manually**, **30 seconds auto refresh**, **1 minute auto refresh**, and **5 minutes auto refresh**.                              |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Graph Type                        | Options: line, digit, top N, table, digital line, and bar graphs                                                                                                                                    |
      +-----------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

8. (Optional) Choose **Metric Sources** > **Graph Settings** to modify the display settings (such as X/Y axis titles and values) of the metric graph. For details, see :ref:`Metric Data Graphs (Line/Digit/Top N/Table/Bar/Digital Line Graphs) <mon_01_0048__en-us_topic_0000001264423926_section781281957>`.

More Operations
---------------

You can also perform the operations listed in :ref:`Table 2 <mon_01_0026__en-us_topic_0000001213710710_table18762012174619>`.

.. _mon_01_0026__en-us_topic_0000001213710710_table18762012174619:

.. table:: **Table 2** Related operations

   +--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                            | Description                                                                                                                                                                                                                          |
   +======================================+======================================================================================================================================================================================================================================+
   | Hiding metric data                   | After selecting a metric, click |image1| next to the metric to hide the metric data in the current graph. To show the metric data again, click |image2| next to the metric. |image3| or |image4| indicate the status of metric data. |
   +--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Adding an alarm rule for a metric    | After selecting a metric, click |image5| in the upper right corner of the metric list to add an alarm rule for the metric.                                                                                                           |
   |                                      |                                                                                                                                                                                                                                      |
   |                                      | .. note::                                                                                                                                                                                                                            |
   |                                      |                                                                                                                                                                                                                                      |
   |                                      |    When you are redirected to the **Create Alarm Rule** page, your settings made on the **Metric Browsing** page will be automatically applied to **Alarm Rule Settings** and **Alarm Rule Details** areas.                          |
   +--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting a metric                    | Click |image6| next to the target metric.                                                                                                                                                                                            |
   +--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Adding a metric graph to a dashboard | After selecting a metric, click |image7| in the upper right corner of the metric list.                                                                                                                                               |
   +--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Viewing early metrics                | If there was metric data generated within 30 days before the version upgrade, click **View Early Metric** in the upper right corner of the **Metric Browsing** page to view and analyze the historical data and graphs.              |
   +--------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002482912998.png
.. |image2| image:: /_static/images/en-us_image_0000002515112985.png
.. |image3| image:: /_static/images/en-us_image_0000002514992981.png
.. |image4| image:: /_static/images/en-us_image_0000002514992987.png
.. |image5| image:: /_static/images/en-us_image_0000002482793022.png
.. |image6| image:: /_static/images/en-us_image_0000002514992989.png
.. |image7| image:: /_static/images/en-us_image_0000002482793016.png

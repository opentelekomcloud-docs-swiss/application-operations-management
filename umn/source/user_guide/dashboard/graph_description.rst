:original_name: mon_01_0048.html

.. _mon_01_0048:

Graph Description
=================

The dashboard displays the query and analysis results of metric or system data in graphs (such as line/digit/status graphs).

.. _mon_01_0048__en-us_topic_0000001264423926_section781281957:

Metric Data Graphs (Line/Digit/Top N/Table/Bar Graphs)
------------------------------------------------------

-  **Line graph**: used to analyze the data change trend in a certain period. Use this type of graph when you need to monitor the metric data trend of one or more resources within a period.

   .. table:: **Table 1** Line graph parameters

      +-------------------+-------------------+----------------------------------------------------------------+
      | Category          | Parameter         | Description                                                    |
      +===================+===================+================================================================+
      | ``-``             | X Axis Title      | Title of the X axis.                                           |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Y Axis Title      | Title of the Y axis.                                           |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Fit as Curve      | Whether to fit a smooth curve.                                 |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Hide X Axis Label | Whether to hide the X axis label.                              |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Hide Y Axis Label | Whether to hide the Y axis label.                              |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Y Axis Range      | Value range of the Y axis.                                     |
      +-------------------+-------------------+----------------------------------------------------------------+
      | Advanced Settings | Left Margin       | Distance between the axis and the left boundary of the graph.  |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Right Margin      | Distance between the axis and the right boundary of the graph. |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Top Margin        | Distance between the axis and the upper boundary of the graph. |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Bottom Margin     | Distance between the axis and the lower boundary of the graph. |
      +-------------------+-------------------+----------------------------------------------------------------+

-  **Digit Graph**: used to highlight a single value. Use this type of graph to monitor the latest value of a metric in real time.

   .. table:: **Table 2** Digit graph parameters

      +----------------+-------------------------------------------------------------------------------------------------------------------------+
      | Parameter      | Description                                                                                                             |
      +================+=========================================================================================================================+
      | Show Miniature | After this function is enabled, the icon will be zoomed out based on a certain proportion. Also, a line graph is added. |
      +----------------+-------------------------------------------------------------------------------------------------------------------------+
      | Dimension      | Select the desired metric from the drop-down list.                                                                      |
      +----------------+-------------------------------------------------------------------------------------------------------------------------+

-  **Top N**: The statistical unit is a cluster and statistical objects are resources such as hosts, components, or instances in the cluster. The top N graph displays top N resources in a cluster. By default, top 5 resources are displayed.

   To view the top N resources, add a top N graph to the dashboard. You only need to select resources and metrics, for example, host CPU usage. AOM then automatically singles out top N hosts for display. If the number of resources is less than N, actual resources are displayed.

   .. table:: **Table 3** Top N graph parameters

      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      | Category          | Parameter            | Description                                                                            |
      +===================+======================+========================================================================================+
      | ``-``             | Column Width         | Column width. Options: **auto** (default), **16**, **22**, **32**, **48**, and **60**. |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      |                   | Unit                 | Unit of the data to be displayed. Default: **%**.                                      |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      |                   | Display X-Axis Scale | After this function is enabled, the scale of the X axis is displayed.                  |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      |                   | Show Value           | After this function is enabled, the value on the Y axis is displayed.                  |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      |                   | Display Y-Axis Line  | After this function is enabled, the line on the Y axis is displayed.                   |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      | Advanced Settings | Left Margin          | Distance between the axis and the left boundary of the graph.                          |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      |                   | Right Margin         | Distance between the axis and the right boundary of the graph.                         |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      |                   | Top Margin           | Distance between the axis and the upper boundary of the graph.                         |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+
      |                   | Bottom Margin        | Distance between the axis and the lower boundary of the graph.                         |
      +-------------------+----------------------+----------------------------------------------------------------------------------------+

-  **Table**: A table lists content in a systematic, concise, centralized, and comparative manner, and intuitively shows the relationship between different categories or makes comparison, ensuring accurate display of data.

   .. table:: **Table 4** Table parameters

      ============ ===========================================
      Parameter    Description
      ============ ===========================================
      Field Name   Name of a field.
      Field Rename Rename a table header field when necessary.
      ============ ===========================================

-  **Bar graph**: A vertical or horizontal bar graph compares values between categories. It shows the data of different categories and counts the number of elements in each category. You can also draw multiple rectangles for the same type of attributes. Grouping and cascading modes are available so that you can analyze data from different dimensions.

   .. table:: **Table 5** Bar graph parameters

      +-------------------+-------------------+----------------------------------------------------------------+
      | Category          | Parameter         | Description                                                    |
      +===================+===================+================================================================+
      | ``-``             | X Axis Title      | Title of the X axis.                                           |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Y Axis Title      | Title of the Y axis.                                           |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Y Axis Range      | Value range of the Y axis.                                     |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Hide X Axis Label | Whether to hide the X axis label.                              |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Hide Y Axis Label | Whether to hide the Y axis label.                              |
      +-------------------+-------------------+----------------------------------------------------------------+
      | Advanced Settings | Top Margin        | Distance between the axis and the upper boundary of the graph. |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Right Margin      | Distance between the axis and the right boundary of the graph. |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Left Margin       | Distance between the axis and the left boundary of the graph.  |
      +-------------------+-------------------+----------------------------------------------------------------+
      |                   | Bottom Margin     | Distance between the axis and the lower boundary of the graph. |
      +-------------------+-------------------+----------------------------------------------------------------+

.. _mon_01_0048__en-us_topic_0000001264423926_section35261436151218:

Alarm Statistics Graphs (Ring)
------------------------------

The number and proportion of alarms of each severity are displayed in a ring.

.. table:: **Table 6** Ring graph parameters

   +-----------------------+-------------------------------------------------------------------------------------------------------+
   | Parameter             | Description                                                                                           |
   +=======================+=======================================================================================================+
   | Display Latest Alarms | If this function is enabled, the latest alarm will be displayed. This function is enabled by default. |
   +-----------------------+-------------------------------------------------------------------------------------------------------+
   | Alarms to Display     | Set the number of alarms to be displayed on a dashboard. Options: **4**, **10**, and **20**.          |
   +-----------------------+-------------------------------------------------------------------------------------------------------+

Health Status Graphs (Tables)
-----------------------------

You can monitor the statuses of one or more threshold rules, hosts, or components in one health status graph. The graph can be a table.

-  **Threshold status graph**: monitors the status of threshold rules in real time. Threshold statuses can be displayed in a table. You can add up to 10 threshold data records.

   .. note::

      Before adding a threshold status graph, :ref:`create a metric alarm rule <mon_01_0008>`.

-  **Host status graph**: monitors the host status in real time. Host statuses can be displayed in a table. You can add up to 10 host data records.
-  **Component status graph**: monitors the component status in real time. Component statuses can be displayed in a table. You can add up to 10 component data records.

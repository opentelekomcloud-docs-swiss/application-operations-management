:original_name: aom_02_0041.html

.. _aom_02_0041:

O&M
===

The **O&M** page provides a full-link, multi-layer, and one-stop O&M page for resources, applications, and user experience. It displays the following cards: infrastructure monitoring, alarm statistics, component monitoring (CPU and memory), host monitoring (disk), cluster monitoring (CPU and memory), application monitoring, host monitoring (CPU and memory), container instance monitoring (CPU and memory), host monitoring (network), and cluster monitoring (disk).

Infrastructure Monitoring
-------------------------


.. figure:: /_static/images/en-us_image_0000001398562788.png
   :alt: **Figure 1** Infrastructure monitoring

   **Figure 1** Infrastructure monitoring

This card mainly displays infrastructure metrics. You can select one or all clusters to view their details. When you select all clusters, the following information is displayed:

-  Host running status, CPU usage, and physical memory usage.
-  Trend graph of network traffic in the last hour. The values of each point in the graph respectively indicate the total downlink/uplink rates of all clusters in one minute. The values displayed above the trend graph respectively indicate the total downlink/uplink rates of all clusters at the latest time point.
-  Trend graph of CPU and memory usage in the last hour. The values of each point in the graph respectively indicate the average CPU and memory usage of all clusters in one minute. The values displayed above the trend graph respectively indicate the average CPU and memory usage of all clusters at the latest time point.

Application Monitoring
----------------------


.. figure:: /_static/images/en-us_image_0000001398402796.png
   :alt: **Figure 2** Application monitoring

   **Figure 2** Application monitoring

This card mainly displays application metrics:

#. Running status of applications, components, containers, and instances.
#. The following information is displayed when you select an application:

   -  Trend graph of network traffic in the last hour. The values of each point in the graph respectively indicate the receive rate (BPS) and send rate (BPS) of the selected application in one minute. The values above the graph respectively indicate the receive rate (BPS) and send rate (BPS) of the selected application at the latest time point.
   -  Trend graph of CPU and memory usage in the last hour. The values of each point in the graph respectively indicate the CPU and memory usage of the selected application in one minute. The values above the graph respectively indicate the CPU and memory usage of the selected application at the latest time point.

Alarm Statistics
----------------


.. figure:: /_static/images/en-us_image_0000001398083084.png
   :alt: **Figure 3** Alarm statistics

   **Figure 3** Alarm statistics

This card mainly displays alarms, alarm rules, and trends of alarms and hosts.

Component Monitoring (CPU and Memory)
-------------------------------------


.. figure:: /_static/images/en-us_image_0000001597393182.png
   :alt: **Figure 4** Component monitoring (CPU and memory)

   **Figure 4** Component monitoring (CPU and memory)

This card mainly displays:

-  The top 5 components with high CPU and memory usage in the last minute.
-  Trend graph of the CPU and memory usage of the selected component in the last hour. The values of each point in the graph respectively indicate the average CPU and memory usage of the component in one minute.
-  CPU and memory usage of the selected component at the latest time point, which is displayed above the trend graph.
-  Option **Hide system container components**, which can be selected to hide system container components.

Host Monitoring (Disk)
----------------------


.. figure:: /_static/images/en-us_image_0000001448562761.png
   :alt: **Figure 5** Host monitoring (disk)

   **Figure 5** Host monitoring (disk)

This card mainly displays:

-  The top 5 hosts with high disk read/write rate in the last minute.
-  Trend graph of the disk read/write rate of the selected host in the last hour. The values of each point in the graph respectively indicate the average disk read/write rate of the selected host in one minute.
-  Disk read/write rate of the selected host at the latest time point, which is displayed above the trend graph.

Cluster Monitoring (CPU and Memory)
-----------------------------------


.. figure:: /_static/images/en-us_image_0000001398562800.png
   :alt: **Figure 6** Cluster monitoring (CPU and memory)

   **Figure 6** Cluster monitoring (CPU and memory)

This card mainly displays:

-  The top 5 clusters with high CPU and memory usage in the last minute.
-  Trend graph of the CPU and memory usage of the selected cluster in the last hour. The values of each point in the graph respectively indicate the average CPU and memory usage of the cluster in one minute.
-  CPU and memory usage of the selected cluster at the latest time point, which is displayed above the trend graph.

Host Monitoring (CPU and Memory)
--------------------------------


.. figure:: /_static/images/en-us_image_0000001398562804.png
   :alt: **Figure 7** Host monitoring (CPU and memory)

   **Figure 7** Host monitoring (CPU and memory)

This card mainly displays:

-  The top 5 hosts with high CPU and memory usage in the last minute.
-  Trend graph of the CPU and memory usage of the selected host in the last hour. The values of each point in the graph respectively indicate the average CPU and memory usage of the host in one minute.
-  CPU and memory usage of the selected host at the latest time point, which is displayed above the trend graph.

Container Instance Monitoring (CPU and Memory)
----------------------------------------------


.. figure:: /_static/images/en-us_image_0000001646475277.png
   :alt: **Figure 8** Container instance monitoring (CPU and memory)

   **Figure 8** Container instance monitoring (CPU and memory)

This card mainly displays:

-  The top 5 container instances with high CPU and memory usage in the last minute.
-  Trend graph of the CPU and memory usage of the selected container instance in the last hour. The values of each point in the graph respectively indicate the average CPU and memory usage of the container instance in one minute.
-  CPU and memory usage of the selected container instance at the latest time point, which is displayed above the trend graph.
-  Option **Hide system container instances**, which can be selected as required.

Host Monitoring (Network)
-------------------------


.. figure:: /_static/images/en-us_image_0000001448562741.png
   :alt: **Figure 9** Host monitoring (network)

   **Figure 9** Host monitoring (network)

This card mainly displays:

-  The top 5 hosts with high uplink/downlink network rate in the last minute.
-  Trend graph of the uplink/downlink network rate of the selected host in the last hour. The values of each point in the graph respectively indicate the average uplink/downlink network rate of the selected host in one minute.
-  Uplink/downlink network rate of the selected host at the latest time point, which is displayed above the trend graph.

Cluster Monitoring (Disk)
-------------------------


.. figure:: /_static/images/en-us_image_0000001448802741.png
   :alt: **Figure 10** Cluster monitoring (disk)

   **Figure 10** Cluster monitoring (disk)

This card mainly displays:

-  The top 5 clusters with high disk usage in the last minute.
-  Trend graph of the disk usage of the selected cluster in the last hour. The value of each point in the graph indicates the average disk usage of the cluster in one minute.
-  Disk usage of the selected cluster at the latest time point, which is displayed above the trend graph.

More Operations
---------------

You can also perform the operations described in :ref:`Table 1 <aom_02_0041__table62191141172620>`.

.. _aom_02_0041__table62191141172620:

.. table:: **Table 1** Related operations

   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                  | Description                                                                                                                                                                                                                     |
   +============================+=================================================================================================================================================================================================================================+
   | Adding a card to favorites | To hide a card, click |image3| in the upper right corner of the card and choose **Add to Favorites**. After a card is added to favorites, it is hidden from the **O&M** page. To view the card later, obtain it from favorites. |
   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Enlarging a graph          | Click |image4| in the upper right corner of the metric graph.                                                                                                                                                                   |
   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Drilling down blue texts   | Click the blue texts, such as **Host**, **Application**, or **Component** to drill down to the details page.                                                                                                                    |
   +----------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001448482889.png
.. |image2| image:: /_static/images/en-us_image_0000001448643081.png
.. |image3| image:: /_static/images/en-us_image_0000001448482889.png
.. |image4| image:: /_static/images/en-us_image_0000001448643081.png

:original_name: mon_01_0037.html

.. _mon_01_0037:

Cluster Monitoring
==================

Clusters deployed using CCE are monitored. The **Cluster Monitoring** page displays the pod status and CPU usage of the clusters in real time.

Precautions
-----------

-  A maximum of five tags can be added to a host, and each tag must be unique.
-  The same tag can be added to different hosts.
-  For hosts created on the CCE console, you cannot select clusters or create aliases for them.
-  The host status can be **Normal**, **Abnormal**, **Warning**, **Silent**, or **Deleted**. The running status of a host is displayed as **Abnormal** when the host is faulty due to network failures, and power-off or shut-down of the host, or a threshold alarm is reported on the host.

Procedure
---------

#. In the navigation pane, choose **Container Insights** > **Cluster Monitoring**.
#. In the upper right corner of the page, set cluster filter criteria.

   a. Set a time range to view the CCE clusters that report information. There are two methods to set a time range:

      Method 1: Use the predefined time label, such as **Last hour** or **Last 6 hours**. You can select a time range as required.

      Method 2: Specify the start time and end time to customize a time range. You can specify 30 days at most.

   b. Set the interval for refreshing information. Click |image1| and select a value from the drop-down list as required, such as **Refresh manually** or **1 minute auto refresh**.

#. Set search criteria (such as the creation time, CPU usage, and cluster name) to find the target cluster.
#. Click the cluster name. On the displayed details page, view the node list, workloads, monitoring views, events, and alarms of the cluster.

   -  On the **Node List** tab page, view information about all hosts in the cluster.

      -  Click |image2| in the upper right corner to obtain the latest information about all nodes in real time.
      -  Click |image3| in the upper right corner and select or deselect columns to display.
      -  Click a node to view its alarms, GPUs, and NICs.
      -  If a node name is complex and difficult to identify, click **Add Alias** in the **Operation** column to add an alias.
      -  Choose **More** > **Add Tag** in the **Operation** column to add a tag to a node. Add up to 5 tags.
      -  Choose **More** > **Sync Host Info** in the **Operation** column to synchronize host information in real time.

   -  On the **Workloads** tab page, check the status and resource usage of all workloads in the cluster.
   -  On the **Monitoring Views** tab page, check the resource usage of the cluster.
   -  On the **Alarms** tab page, check the alarm details of the cluster. For details, see :ref:`Viewing Alarms <mon_01_0011>`.
   -  On the **Events** tab page, check the event details of the cluster. For details, see :ref:`Viewing Events <mon_01_0012>`.

.. |image1| image:: /_static/images/en-us_image_0000002289582461.png
.. |image2| image:: /_static/images/en-us_image_0000002254869124.png
.. |image3| image:: /_static/images/en-us_image_0000002254812168.png

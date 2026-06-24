:original_name: mon_01_0037.html

.. _mon_01_0037:

Cluster Monitoring
==================

Clusters deployed using CCE are monitored. On the **Cluster Monitoring** page, you can view multiple basic metrics (such as cluster status, CPU usage, memory usage, and node status), and related alarms and events in real time. Based on them, you can monitor cluster statuses and handle risks in a timely manner, ensuring stable cluster running.

Precautions
-----------

The host status can be **Normal**, **Abnormal**, **Warning**, **Silent**, or **Deleted**. The running status of a host is displayed as **Abnormal** when the host is faulty due to network failures or host power-off or shut-down, or when a threshold alarm is reported on the host.

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane, choose **Container Insights** > **Cluster Monitoring**.
#. In the upper right corner of the page, set cluster filter criteria.

   a. Set a time range to view the CCE clusters that report information. There are two methods to set a time range:

      Method 1: Use the predefined time label, such as **Last hour** or **Last 6 hours**. You can select a time range as required.

      Method 2: Specify the start time and end time to customize a time range. You can specify 15 days at most.

   b. Set the interval for refreshing information. Click |image1| and select a value from the drop-down list, such as **Refresh manually** or **1 minute auto refresh**.

#. Set search criteria (such as the creation time, CPU usage, and cluster name) to find the target cluster.

5. Click a cluster to go to its details page. In the navigation pane on the left, monitor cluster running conditions by cluster or alarm.

   -  View information about nodes, workloads, pods (container groups), and containers by cluster.

      -  In the navigation pane on the left, choose **Insights** > **Node** to view information about all nodes in the cluster in real time, including the status, IP address, pod status, CPU usage, and memory usage.

         -  In the upper part of the node list, filter nodes by node name.
         -  Click |image2| in the upper right corner and select or deselect options as required.
         -  Click a node to view its related resources, alarms, and events, and common system devices such as GPUs and NICs.

            -  On the **Overview** tab page, **Cloud-Native Monitoring (New)** is selected by default. You can view metrics such as CPU, memory, and network. Click **Using ICAgent (Old)** and select a target Prometheus instance from the drop-down list. You can view metrics such as CPU, physical memory, and host status.

               .. note::

                  To use cloud-native monitoring, connect your cluster to a Prometheus instance for CCE first.

                  If there is no Prometheus instance for CCE, click **Prometheus Monitoring** to create a Prometheus instance by referring to :ref:`Prometheus Instance for CCE <mon_01_0073>`. After the instance is created, click its name. On the instance details page, choose **Integration Center** and then connect the CCE cluster.

               Click |image3| in the upper right corner and select a predefined time label or customize a time range from the drop-down list to view resource information.

               Click |image4| in the upper right corner to obtain the latest resource information in real time.

               Click |image5| in the upper right corner of the page to view resource information in full screen.

            -  On the **Related Resources** tab page, the pod (container group) to which the node belongs is displayed.

      -  In the navigation pane on the left, choose **Insights** > **Workload** to view the status and resource usage of all workloads in the cluster.

         -  In the upper part of the workload list, filter workloads by workload type or name.
         -  Click |image6| in the upper right corner and select or deselect options as required.
         -  Click a workload to view its related resources, alarms, events, and dashboards.

            -  On the **Overview** tab page, **Cloud-Native Monitoring (New)** is selected by default. You can view metrics such as CPU, memory, and network. Click **Using ICAgent (Old)** and select a target Prometheus instance from the drop-down list. You can view metrics such as CPU, physical memory, and file system.
            -  On the **Related Resources** tab page, the pod (container group) to which the workload belongs is displayed.

      -  In the navigation pane on the left, choose **Insights** > **Pod** to view the status and resource usage of all pods in the cluster.

         -  In the upper part of the container group list, filter container groups by name.
         -  Click |image7| in the upper right corner and select or deselect options as required.
         -  Click a container group to view its related resources, alarms, events, and dashboards.

            -  On the **Overview** tab page, **Cloud-Native Monitoring (New)** is selected by default. You can view metrics such as CPU, memory, and network. Click **Using ICAgent (Old)** and select a target Prometheus instance from the drop-down list. You can view metrics such as CPU, physical memory, and file system.
            -  On the **Related Resources** tab page, view nodes, workloads, and containers by name.

      -  In the navigation pane on the left, choose **Insights** > **Container** to view the status and resource usage of all containers in the cluster.

         -  In the upper part of the container list, filter containers by name.
         -  Click |image8| in the upper right corner and select or deselect options as required.
         -  Click a container to view its related resources, alarms, events, and dashboards. On the **Related Resources** tab page, the container group to which the container belongs is displayed by default. View nodes, workloads, and container groups by name.

   -  View the cluster running status from the alarm management perspective.

      -  In the navigation pane on the left, choose **Alarm Management** > **Alarm List** to view alarm details of the cluster. For details, see :ref:`Viewing Alarms <mon_01_0011>`.
      -  In the navigation pane on the left, choose **Alarm Management** > **Event List** to view event details of the cluster. For details, see :ref:`Viewing Events <mon_01_0012>`.
      -  In the navigation pane on the left, choose **Alarm Management** > **Alarm Rules** to view the alarm rules related to the cluster. Modify the alarm rules as required. For details, see :ref:`Managing Alarm Rules <mon_01_0050>`.

.. |image1| image:: /_static/images/en-us_image_0000002515113063.png
.. |image2| image:: /_static/images/en-us_image_0000002482913050.png
.. |image3| image:: /_static/images/en-us_image_0000002515113061.png
.. |image4| image:: /_static/images/en-us_image_0000002482793094.png
.. |image5| image:: /_static/images/en-us_image_0000002515113067.png
.. |image6| image:: /_static/images/en-us_image_0000002482793090.png
.. |image7| image:: /_static/images/en-us_image_0000002514993051.png
.. |image8| image:: /_static/images/en-us_image_0000002482913048.png

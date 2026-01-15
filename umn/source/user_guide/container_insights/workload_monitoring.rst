:original_name: mon_01_0025.html

.. _mon_01_0025:

Workload Monitoring
===================

Workload monitoring is for CCE workloads. It enables you to monitor the resource usage, status, and alarms of workloads in a timely manner so that you can quickly handle alarms or events to ensure smooth workload running. Workloads are classified into Deployments, StatefulSets, DaemonSets, Jobs, and Pods.

Functions
---------

-  The workload monitoring solution is ready-to-use. After AOM is enabled, the workload status, CPU usage, and physical memory usage of CCE are displayed on the workload monitoring page by default.
-  Workload monitoring adopts the layer-by-layer drill-down design. The hierarchy is as follows: workload > Pod instance > container > process. You can view their relationships on the UI. Metrics and alarms are monitored at each layer.

Procedure
---------

#. In the navigation pane, choose **Container Insights** > **Workload Monitoring**.
#. In the upper right corner of the page, set filter criteria.

   a. .. _mon_01_0025__en-us_topic_0000001258510527_li108291342820:

      Set a time range to view the workloads reported. There are two methods to set a time range:

      Method 1: Use the predefined time label, such as **Last hour** or **Last 6 hours**. You can select a time range as required.

      Method 2: Specify the start time and end time to customize a time range. You can specify 30 days at most.

   b. Set the interval for refreshing information. Click |image1| and select a value from the drop-down list as required, such as **Refresh manually** or **1 minute auto refresh**.

#. Click any workload tab to view information, such as workload name, status, cluster, and namespace.

   -  In the upper part of the workload list, filter workloads by cluster, namespace, or pod name.
   -  Click |image2| in the upper right corner to obtain the information about the workload within the time range set in :ref:`the preceding step <mon_01_0025__en-us_topic_0000001258510527_li108291342820>`.
   -  Click |image3| in the upper right corner and select or deselect columns to display.
   -  Click the name of a workload to view its details.

      -  On the **Pods** tab page, view information about all pods. Click a pod name to view the resource usage and health status of all containers in the pod.
      -  On the **Monitoring Views** tab page, view the resource usage of the workload.
      -  On the **Alarms** tab page, check the alarm details of the workload. For details, see :ref:`Viewing Alarms <mon_01_0011>`.
      -  On the **Events** tab page, check the event details of the workload. For details, see :ref:`Viewing Events <mon_01_0012>`.

.. |image1| image:: /_static/images/en-us_image_0000002254868772.png
.. |image2| image:: /_static/images/en-us_image_0000002289469033.png
.. |image3| image:: /_static/images/en-us_image_0000002254811828.png

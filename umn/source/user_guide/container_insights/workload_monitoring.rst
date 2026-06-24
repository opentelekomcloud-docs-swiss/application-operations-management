:original_name: mon_01_0025.html

.. _mon_01_0025:

Workload Monitoring
===================

Workload monitoring is for CCE workloads. It enables you to monitor the resource usage, status, and alarms of workloads in a timely manner so that you can quickly handle alarms or events to ensure smooth workload running. Workloads are classified into Deployments, StatefulSets, DaemonSets, Jobs, and Pods.

Functions
---------

-  The workload monitoring solution is ready-to-use. After AOM is enabled, the workload status, CPU usage, and physical memory usage of CCE are displayed on the workload monitoring page by default.
-  For customer-built Kubernetes containers, only Prometheus remote write is supported. After container metrics are written into AOM's metric library, you can query metric data by following instructions listed in :ref:`Metric Browsing <mon_01_0026>`.
-  Workload monitoring adopts the layer-by-layer drill-down design. The hierarchy is as follows: workload > Pod instance > container > process. You can view their relationships on the UI. Metrics and alarms are monitored at each layer.

Precaution
----------

ICAgent reports pod metrics only after a pod is running for at least one minute.

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane, choose **Container Insights** > **Workload Monitoring**.
#. In the upper right corner of the page, set filter criteria.

   a. .. _mon_01_0025__en-us_topic_0000001258510527_li108291342820:

      Set a time range to view the workloads reported. There are two methods to set a time range:

      Method 1: Use the predefined time label, such as **Last hour** or **Last 6 hours**. You can select a time range as required.

      Method 2: Specify the start time and end time to customize a time range. You can specify 15 days at most.

   b. Set the interval for refreshing information. Click |image1| and select a value from the drop-down list, such as **Refresh manually** or **1 minute auto refresh**.

#. Click any workload tab to view information, such as workload name, status, cluster, and namespace.

   -  In the upper part of the workload list, filter workloads by cluster, pod, or namespace name.
   -  Click |image2| in the upper right corner to obtain the latest workload information within the time range specified in :ref:`3.a <mon_01_0025__en-us_topic_0000001258510527_li108291342820>`.
   -  Click |image3| in the upper right corner and select or deselect columns to display.
   -  Click the name of a workload to view its details.

      -  On the **Pods** tab page, view the all pod conditions of the workload. Click a pod name to view the resource usage and health status of the pod's containers.
      -  On the **Monitoring Views** tab page, view the resource usage of the workload.
      -  On the **Alarms** tab page, view the alarm details of the workload. For details, see :ref:`Viewing Alarms <mon_01_0011>`.
      -  On the **Events** tab page, view the event details of the workload. For details, see :ref:`Viewing Events <mon_01_0012>`.

.. |image1| image:: /_static/images/en-us_image_0000002514992901.png
.. |image2| image:: /_static/images/en-us_image_0000002482792928.png
.. |image3| image:: /_static/images/en-us_image_0000002482792930.png

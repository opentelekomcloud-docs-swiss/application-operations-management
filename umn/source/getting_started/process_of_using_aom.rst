:original_name: aom_05_0007.html

.. _aom_05_0007:

Process of Using AOM
====================

AOM is a one-stop, multi-dimensional O&M management platform for cloud applications. It monitors applications and related cloud resources in real time, analyzes application health status, and provides flexible alarm reporting and data visualization functions. It helps you detect faults in a timely manner and monitor running status of applications, services, and other resources in real time. This section describes how to get started with AOM. The following figure shows the process.


.. figure:: /_static/images/en-us_image_0000001448482821.jpg
   :alt: **Figure 1** Process of using AOM

   **Figure 1** Process of using AOM

#. Creating a cloud host

   Each host corresponds to a VM on the cloud, for example, an Elastic Cloud Server (ECS). A host can be directly created on the ECS console, or indirectly created on the Cloud Container Engine (CCE) console.

#. Installing an ICAgent

   An ICAgent is a data collector of AOM. It collects metrics, logs, and application performance data in real time. For hosts created on the ECS console, manually install ICAgents. For hosts created on the CCE console, ICAgents are automatically installed.

#. Configuring an alarm rule

   You can set threshold conditions for metrics by using alarm rules. If metric values meet threshold conditions, AOM generates threshold alarms. If no metric data is reported, AOM will report insufficient data events. In this way, you can identify and handle exceptions at the earliest time.

#. Viewing alarms

   AOM provides the dashboard and alarm list for you to perform routine O&M.

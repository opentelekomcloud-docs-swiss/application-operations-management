:original_name: aom_06_0005.html

.. _aom_06_0005:

Functions
=========

Application Monitoring
----------------------

Application monitoring allows you to view application resource usage, trends, and alarms in real time, so that you can make fast responses to ensure smooth running for applications.

This function adopts the hierarchical drill-down design. The hierarchy is as follows: Application list > Application details > Component details > Instance details > Process details. Applications, components, instances, and processes are visually associated with each other on the console.

Host Monitoring
---------------

Host monitoring allows you to view host resource usage, trends, and alarms in real time, so that you can make fast responses and ensure smooth running for hosts.

Like application monitoring, this function also adopts the hierarchical drill-down design. The hierarchy is as follows: Host list > Host details. The details page contains all the instances, GPUs, NICs, disks, and file systems of the current host.

Automatic Discovery of Applications
-----------------------------------

After you deploy applications on hosts, the ICAgent installed on the hosts automatically collects information, including names of processes, components, containers, and Kubernetes pods. Applications are automatically discovered and their graphs are displayed on the console. You can then set aliases and groups for better resource management.

Dashboard
---------

With a dashboard, different graphs can be displayed on the same screen. Various graphs, such as line graphs, digit graphs, and top N resource graphs enable you to monitor data comprehensively.

For example, you can add key metrics to a dashboard for real-time monitoring. You can also compare the same metric of different resources on one screen. In addition, by adding common O&M metrics to a dashboard, you do not need to reselect them when re-opening the AOM console during routine O&M.

Alarm Management
----------------

The alarm list helps you manage alarms and events.

You can create alarm rules for key resource metrics. When the metric value reaches the threshold, AOM will generate alarms. An event alarm will be generated if the resource data meets an event condition. A threshold-crossing alarm will be generated if the metric data meets a threshold condition. An insufficient data event will be generated if no metric data is reported. Therefore, you can discover and handle exceptions at the earliest time. When an alarm is reported, alarm information will be sent to specified personnel by email or SMS based on alarm action rules. Therefore, O&M personnel can rectify faults in time to avoid service loss.

Log Management
--------------

AOM provides powerful log management capabilities. Log search enables you to quickly search for required logs from massive quantities of logs. Log dump enables you to store logs for a long period. By configuring delimiters, you can divide log content into multiple words and use these words to search for logs.

Metric Browsing
---------------

The **Metric Browsing** page displays metric data of each resource. You can monitor metric values and trends in real time, and create alarm rules for desired metrics. In this way, you can monitor services in real time and perform data correlation analysis.

Prometheus Monitoring
---------------------

AOM is fully interconnected with the open-source Prometheus ecosystem. It monitors many types of components, provides multiple ready-to-use dashboards, and supports flexible expansion of cloud-native component metric plug-ins. After installing the Prometheus add-on on the CCE console, you can connect metric data to AOM for unified management.

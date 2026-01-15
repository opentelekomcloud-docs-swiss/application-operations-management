:original_name: aom_06_0002.html

.. _aom_06_0002:

Glossary
========

Metric
------

Metrics reflect resource performance data or status. A metric consists of a namespace, dimension, name, and unit.

Metric namespaces can be regarded as containers for storing metrics. Metrics in different namespaces are independent of each other so that metrics of different applications will not be aggregated to the same statistics information. Each metric has certain features, and a dimension may be considered as a category of such features. :ref:`Figure 1 <aom_06_0002__fig6988195513133>` describes the relationships among namespaces, dimensions, and cluster metrics.

.. _aom_06_0002__fig6988195513133:

.. figure:: /_static/images/en-us_image_0000002254811520.png
   :alt: **Figure 1** Cluster metrics

   **Figure 1** Cluster metrics

Host
----

Each host of AOM corresponds to a VM or physical machine. A host can be your own VM or physical machine, or a VM (for example, an ECS) that you created. A host can only be connected to AOM for monitoring when its OS is supported by AOM and an ICAgent has been installed on the host.

ICAgent
-------

ICAgent is the collector of AOM. It runs on hosts to collect metrics, logs, and application performance data in real time. Before using AOM, ensure that the ICAgent has been installed. Otherwise, AOM cannot be used.

Log
---

AOM supports log collection, search, analysis, download, and dump. It also reports alarms based on keyword statistics and enables you to export reports, query SQL statements, and monitor data in real time.

Alarm
-----

Alarms are reported when AOM or an external service such as or Cloud Container Engine (CCE) is abnormal or may cause exceptions. Alarms will cause service exceptions and need to be handled.

There are two alarm clearance modes:

-  Automatic clearance: After a fault is rectified, AOM automatically clears the corresponding alarm, for example, a threshold alarm.
-  Manual clearance: After a fault is rectified, AOM does not automatically clear the corresponding alarm, for example, ICAgent installation failure alarm. In such a case, manually clear the alarm.

Event
-----

Events generally carry some important information. They are reported when AOM or an external service, such as or CCE encounters some changes. Such changes do not necessarily cause service exceptions. Events do not need to be handled.

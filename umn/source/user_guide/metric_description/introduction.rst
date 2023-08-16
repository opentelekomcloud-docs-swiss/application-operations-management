:original_name: aom_02_1015.html

.. _aom_02_1015:

Introduction
============

Metrics reflect resource performance data or status. A metric consists of the :ref:`namespace <aom_02_1015__en-us_topic_0175590441_section15138195111105>`, :ref:`dimension <aom_02_1015__en-us_topic_0175590441_section157916821815>`, name, and unit. Metrics are classified into system metrics and custom metrics.

-  System metrics: basic metrics provided by AOM, such as CPU usage and used CPU cores.
-  Custom metrics: self-defined metrics. Custom metrics can be reported using the following methods:

   -  Method 1: Use the AOM API for reporting monitoring data.
   -  Method 2: Connect to the Prometheus platform when creating container applications on Cloud Container Engine (CCE).

.. _aom_02_1015__en-us_topic_0175590441_section15138195111105:

Metric Namespaces
-----------------

Metric namespaces indicate containers for storing metrics. Metrics in different namespaces are independent of each other so that metrics of different applications will not be aggregated to the same statistics information.

-  Namespaces of system metrics cannot be changed. These namespaces must start with **PAAS.**, as shown in :ref:`Table 1 <aom_02_1015__en-us_topic_0175590441_table1834203313399>`.

   .. _aom_02_1015__en-us_topic_0175590441_table1834203313399:

   .. table:: **Table 1** Namespaces of system metrics

      +----------------+----------------------------------------------------------------+
      | Namespace      | Description                                                    |
      +================+================================================================+
      | PAAS.AGGR      | Namespace of cluster metrics                                   |
      +----------------+----------------------------------------------------------------+
      | PAAS.NODE      | Namespace of host, network, disk, and file system metrics      |
      +----------------+----------------------------------------------------------------+
      | PAAS.CONTAINER | Namespace of service, instance, process, and container metrics |
      +----------------+----------------------------------------------------------------+

-  Namespaces of custom metrics must be in the **XX.XX** format (excluding **PAAS.XX**, **SYS.XX**, or **SRE.XX**). Each namespace must be 3 to 32 characters long and start with a letter. Only digits, uppercase letters, lowercase letters, and underscores (_) are allowed. For example, **aom.host_01**.

.. _aom_02_1015__en-us_topic_0175590441_section157916821815:

Metric Dimensions
-----------------

Metric dimensions indicate the categories of metrics. Each metric has certain features, and a dimension may be considered as a category of relevant features.

-  Dimensions of system metrics cannot be changed. Different types of metrics have different dimensions. For more information, see :ref:`Network Metrics and Dimensions <aom_02_1016>` to :ref:`Service Metrics and Dimensions <aom_02_1024>`.

   .. note::

      The dimensions listed in :ref:`Network Metrics and Dimensions <aom_02_1016>` to :ref:`Service Metrics and Dimensions <aom_02_1024>` are the dimensions of metrics collected and reported by the AOM backend. You can select these dimensions when calling APIs. Resources are filtered and displayed by dimensions on the AOM frontend.

-  Dimensions of custom metrics must be 1 to 32 characters long, which need to be customized.

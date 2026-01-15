:original_name: aom_06_0014.html

.. _aom_06_0014:

Description
===========

Metrics reflect resource performance data or status. A metric consists of a :ref:`namespace <aom_06_0014__section15138195111105>`, :ref:`dimension <aom_06_0014__section157916821815>`, name, and unit. Metrics can be divided into:

-  System metrics: basic metrics provided by AOM, such as CPU usage and used CPU cores.
-  Custom metrics: user-defined metrics. You can report custom metrics using the following methods:

   -  Method 1: Use AOM APIs. For details, see "Adding Monitoring Data" and "Querying Monitoring Data" in the *Application Operations Management (AOM) API Reference*.
   -  Method 2: When creating containerized applications on CCE, interconnect with Prometheus to report custom metrics. For details, see "Custom Monitoring" in *Cloud Container Engine (CCE) User Guide*.

.. _aom_06_0014__section15138195111105:

Metric Namespaces
-----------------

A namespace is an abstract collection of resources and objects. Metrics in different namespaces are independent of each other so that metrics of different applications will not be aggregated to the same statistics information.

-  Namespaces of system metrics are fixed and started with **PAAS.**. For details, see :ref:`Table 1 <aom_06_0014__table1834203313399>`.

   .. _aom_06_0014__table1834203313399:

   .. table:: **Table 1** Namespaces of system metrics

      +----------------+------------------------------------------------------------------+
      | Namespace      | Description                                                      |
      +================+==================================================================+
      | PAAS.AGGR      | Namespace of cluster metrics                                     |
      +----------------+------------------------------------------------------------------+
      | PAAS.NODE      | Namespace of host, network, disk, and file system metrics        |
      +----------------+------------------------------------------------------------------+
      | PAAS.CONTAINER | Namespace of component, instance, process, and container metrics |
      +----------------+------------------------------------------------------------------+

-  Namespaces of custom metrics must be in the XX.XX format. Each namespace must be 3 to 32 characters long, starting with a letter (excluding **PAAS.**, **SYS.**, and **SRE.**). Only digits, letters, and underscores (_) are allowed.

.. _aom_06_0014__section157916821815:

Dimension
---------

Metric dimensions indicate the categories of metrics. Each metric has certain features, and a dimension may be considered as a category of such features.

-  Dimensions of system metrics are fixed. Different types of metrics have different dimensions. For more details, see the following sections.
-  Dimensions of custom metrics must be 1 to 32 characters long, which need to be customized.

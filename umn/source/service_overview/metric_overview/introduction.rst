:original_name: aom_06_0014.html

.. _aom_06_0014:

Introduction
============

Metrics reflect resource performance data or status. A metric consists of a :ref:`namespace <aom_06_0014__en-us_topic_0000001342564489_section15138195111105>`, :ref:`dimension <aom_06_0014__en-us_topic_0000001342564489_section157916821815>`, name, and unit.

.. _aom_06_0014__en-us_topic_0000001342564489_section15138195111105:

Metric Namespaces
-----------------

A namespace is an abstract collection of resources and objects. Metrics in different namespaces are independent of each other so that metrics of different applications will not be aggregated to the same statistics information.

-  Namespaces of system metrics are fixed and started with **PAAS.**. For details, see :ref:`Table 1 <aom_06_0014__en-us_topic_0000001342564489_table1834203313399>`.

   .. _aom_06_0014__en-us_topic_0000001342564489_table1834203313399:

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
      | PAAS.SLA       | Namespace of SLA metrics                                         |
      +----------------+------------------------------------------------------------------+

-  Namespaces of custom metrics must be in the XX.XX format. Each namespace must be 3 to 32 characters long, starting with a letter (excluding **PAAS.**, **SYS.**, and **SRE.**). Only digits, letters, and underscores (_) are allowed.

.. _aom_06_0014__en-us_topic_0000001342564489_section157916821815:

Metric Dimensions
-----------------

Metric dimensions indicate the categories of metrics. Each metric has certain features, and a dimension may be considered as a category of such features.

-  Dimensions of system metrics are fixed. Different types of metrics have different dimensions. For details, see :ref:`Metric Dimensions <aom_06_0018>`.
-  Dimensions of custom metrics must be 1 to 32 characters long, which need to be customized.

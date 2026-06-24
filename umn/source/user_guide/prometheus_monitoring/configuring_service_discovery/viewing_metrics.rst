:original_name: mon_01_0080.html

.. _mon_01_0080:

Viewing Metrics
===============

This section describes how to view the metrics of Prometheus instances for CCE.

Prerequisites
-------------

-  Both your service and CCE cluster have been connected to a Prometheus instance for CCE. For details, see :ref:`Prometheus Instance for CCE <mon_01_0073>`.

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**.

#. In the instance list, click a Prometheus instance for CCE.

#. In the navigation pane on the left, choose **Service Discovery.** On the **Metrics** tab page, view the metric names and types of the current Prometheus instance.

   You can also filter metrics by cluster name, job name, or metric type, or enter a keyword for fuzzy search.

   .. table:: **Table 1** Metric parameters

      +-------------+--------------------------------------------------------------------+
      | Parameter   | Description                                                        |
      +=============+====================================================================+
      | Metric Name | Name of a metric.                                                  |
      +-------------+--------------------------------------------------------------------+
      | Metric Type | Type of a metric. Options: **Basic metric** and **Custom metric**. |
      +-------------+--------------------------------------------------------------------+

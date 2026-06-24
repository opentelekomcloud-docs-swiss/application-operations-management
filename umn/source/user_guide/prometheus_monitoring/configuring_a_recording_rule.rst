:original_name: mon_01_0082.html

.. _mon_01_0082:

Configuring a Recording Rule
============================

Recording rules can be used for secondary development of metric data. Some queries may require a large amount of computing on the query end, resulting in high pressure on this end. By setting recording rules, you can move the computing process to the write end, reducing resource usage on the query end. Especially in large-scale clusters and complex service scenarios, recording rules can reduce PromQL complexity, thereby improving the query performance and preventing slow user configuration and queries.

Prerequisite
------------

Both your service and CCE cluster have been connected to a Prometheus instance for CCE. For details, see :ref:`Prometheus Instance for CCE <mon_01_0073>`.


Configuring a Recording Rule
----------------------------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**.

#. In the instance list, click a Prometheus instance for CCE.

#. In the navigation pane on the left, choose **Settings**. In the **Recording Rules** area, click **Edit RecordingRule.yaml**.

#. In the dialog box that is displayed, delete the default content and enter a custom recording rule.

   .. note::

      Only one **RecordingRule.yaml** file needs to be configured for a cluster. Each rule group name must be unique.


   .. figure:: /_static/images/en-us_image_0000002482793138.png
      :alt: **Figure 1** Configuring a recording rule

      **Figure 1** Configuring a recording rule

   .. table:: **Table 1** Recording rule parameters

      +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter | Description                                                                                                                                                                 |
      +===========+=============================================================================================================================================================================+
      | groups    | Rule group. You can set multiple rule groups in one **RecordingRule.yaml** file.                                                                                            |
      +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | name      | Rule group name. Each rule group name must be unique.                                                                                                                       |
      +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | interval  | (Optional) Execution interval of a rule group. The default value is **60s**.                                                                                                |
      +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | rules     | Rule. A rule group can contain multiple rules.                                                                                                                              |
      +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | record    | Name of a rule. The name must comply with `Prometheus metric name specifications <https://prometheus.io/docs/concepts/data_model/#metric-names-and-labels>`__.              |
      +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | expr      | Calculation expression. It is used to calculate metric values. It must comply with `PromQL requirements <https://prometheus.io/docs/prometheus/latest/querying/basics/>`__. |
      +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | labels    | (Optional) Label of a metric.                                                                                                                                               |
      +-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   Example of a recording rule:

   .. code-block::

      groups:
        - name: apiserver_request_total
          interval: 60s
          rules:
            - record: apiserver_request_rate
              expr: avg by (job, instance, mode) (rate(apiserver_request_total[5m]))
              labels:
                team: operations
            - record: job:apiserver_request_total:sum_rate10m
              expr: sum by (job)(rate(apiserver_request_total[10m]))
              labels:
                team: operations

#. Click **OK**.

Viewing Recording Rule Metrics
------------------------------

After a recording rule is configured, you can view its metrics on the :ref:`Metric Browsing <mon_01_0026>` page of AOM or using Grafana.

Method 1: Viewing Metrics on the :ref:`Metric Browsing <mon_01_0026>` Page of AOM

#. On the **Metric Browsing** page, select a Prometheus instance for which a recording rule has been configured from the drop-down list.
#. Click **All metrics** and enter the name of a recording rule metric in the search box to view its details.

**Method 2: Viewing Metrics Using Grafana**

For details, see :ref:`Viewing Metric Data in AOM Using Grafana <mon_01_0077>`.

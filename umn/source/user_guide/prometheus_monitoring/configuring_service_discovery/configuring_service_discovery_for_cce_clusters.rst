:original_name: mon_01_0081.html

.. _mon_01_0081:

Configuring Service Discovery for CCE Clusters
==============================================

By adding ServiceMonitor or PodMonitor, you can configure Prometheus collection rules to monitor the applications deployed in CCE clusters.

Prerequisite
------------

Both your service and CCE cluster have been connected to a Prometheus instance for CCE. For details, see :ref:`Prometheus Instance for CCE <mon_01_0073>`.

Adding ServiceMonitor
---------------------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**.

#. In the instance list, click a Prometheus instance for CCE.

#. In the navigation pane on the left, choose **Service Discovery**. On the **Settings** tab page, click **ServiceMonitor**.

#. Click **Add ServiceMonitor**. In the displayed dialog box, set related parameters and click **OK**.


   .. figure:: /_static/images/en-us_image_0000002514992915.png
      :alt: **Figure 1** Adding ServiceMonitor

      **Figure 1** Adding ServiceMonitor

   After the configuration is complete, the new collection rule is displayed in the service discovery list.

Adding PodMonitor
-----------------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**.

#. In the instance list, click a Prometheus instance for CCE.

#. In the navigation pane on the left, choose **Service Discovery**. On the **Settings** tab page, click **PodMonitor**.

#. Click **Add PodMonitor**. In the displayed dialog box, set related parameters and click **OK**.

   After the configuration is complete, the new collection rule is displayed in the service discovery list.

More Operations
---------------

Perform the operations listed in :ref:`Table 1 <mon_01_0081__en-us_topic_0000001655765880_en-us_topic_0169698339_table15831736105910>` if needed.

.. _mon_01_0081__en-us_topic_0000001655765880_en-us_topic_0169698339_table15831736105910:

.. table:: **Table 1** Related operations

   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                                                                                                |
   +===================================+============================================================================================================================================================================================+
   | Viewing service discovery         | -  In the service discovery list, view information such as the name, tag, namespace, and configuration mode. You can filter information by cluster name, namespace, or configuration mode. |
   |                                   | -  Click |image1| in the **Operation** column. In the displayed dialog box, view details about the ServiceMonitor or PodMonitor collection rule.                                           |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting service discovery        | Click |image2| in the **Operation** column.                                                                                                                                                |
   +-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002482792940.png
.. |image2| image:: /_static/images/en-us_image_0000002515112919.png

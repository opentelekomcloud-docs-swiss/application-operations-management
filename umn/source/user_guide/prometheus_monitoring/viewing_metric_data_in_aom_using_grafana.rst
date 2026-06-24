:original_name: mon_01_0077.html

.. _mon_01_0077:

Viewing Metric Data in AOM Using Grafana
========================================

After connecting a cloud service or CCE cluster to a Prometheus instance, you can use Grafana to view the metrics of the cloud service or cluster.

Prerequisites
-------------

-  You have created an ECS.
-  You have created an EIP and bound it to the created ECS.
-  Your service has been connected for Prometheus monitoring. For more details, see:

   -  :ref:`Prometheus Instance for CCE <mon_01_0073>`
   -  :ref:`Prometheus Instance for Remote Write <mon_01_0070>`

Procedure
---------

#. Install and start Grafana. For details, see the `Grafana official documentation <https://grafana.com/docs/grafana/latest/installation/>`__.

#. Add an access code.

   a. On the menu bar, choose **Monitoring Center**.
   b. In the navigation pane, choose **Global Configuration**.
   c. In the navigation pane on the left, choose **Authentication**. Click **Add Access Code**.
   d. In the dialog box that is displayed, click **OK**. The system then automatically generates an access code.

   .. note::

      -  You can create up to two access codes for each project.
      -  An access code is an identity credential for calling APIs. Keep your access code secure.

#. .. _mon_01_0077__en-us_topic_0000001593470258_li1380513353552:

   Obtain the Grafana data source configuration code.

   a. On the menu bar, choose **Monitoring Center**.

   b. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**. In the instance list, click the target Prometheus instance.

   c. On the displayed page, choose **Settings** in the navigation pane and obtain the Grafana data source information from the **Grafana Data Source Info** area.


      .. figure:: /_static/images/en-us_image_0000002482792908.png
         :alt: **Figure 1** Grafana data source information

         **Figure 1** Grafana data source information

#. Configure Grafana.

   a. Log in to Grafana.

   b. In the navigation pane, choose **Configuration** > **Data Sources**. Then click **Add data source**.


      .. figure:: /_static/images/en-us_image_0000002482912882.png
         :alt: **Figure 2** Configuring Grafana

         **Figure 2** Configuring Grafana

   c. Click **Prometheus** to access the configuration page.


      .. figure:: /_static/images/en-us_image_0000002482912884.png
         :alt: **Figure 3** Prometheus configuration page

         **Figure 3** Prometheus configuration page

   d. Set Grafana data source parameters.

      -  **URL**: HTTP URL obtained in :ref:`3 <mon_01_0077__en-us_topic_0000001593470258_li1380513353552>`.
      -  **User**: username obtained in :ref:`3 <mon_01_0077__en-us_topic_0000001593470258_li1380513353552>`.
      -  **Password**: password obtained in :ref:`3 <mon_01_0077__en-us_topic_0000001593470258_li1380513353552>`.

      .. note::

         The **Basic auth** and **Skip TLS Verify** options under **Auth** must be enabled.


      .. figure:: /_static/images/en-us_image_0000002482912874.png
         :alt: **Figure 4** Setting parameters

         **Figure 4** Setting parameters

   e. Click **Save&Test** to check whether the configuration is successful.

      If the configuration is successful, you can use Grafana to configure dashboards and view metric data.


      .. figure:: /_static/images/en-us_image_0000002482792904.png
         :alt: **Figure 5** Checking whether the configuration is successful

         **Figure 5** Checking whether the configuration is successful

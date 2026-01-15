:original_name: aom_02_0923.html

.. _aom_02_0923:

Viewing Metric Data in AOM Using Grafana
========================================

Prerequisites
-------------

-  You have created an ECS.
-  An EIP has been created and bound to the ECS.

Procedure
---------

#. Install and start Grafana. For details, see the `Grafana official documentation <https://grafana.com/docs/grafana/latest/installation/>`__.

#. .. _aom_02_0923__li543218492584:

   Add an access code.

   a. Log in to the AOM console. In the navigation pane, choose **Global Configuration**.
   b. In the right pane, click **Add Access Code**.
   c. In the dialog box that is displayed, click **OK**. The system automatically generates an access code.

      .. note::

         -  You can create up to two access codes for each project.
         -  An access code is an identity credential for calling APIs. Keep your access code secure.

   d. After the access code is added, click |image1| to view it. To delete the access code, click **Delete** in the **Operation** column. Deleted access codes cannot be recovered. Exercise caution when performing this operation.

#. Configure Grafana.

   a. Log in to Grafana.

   b. In the navigation pane, choose **Configuration** > **Data Sources**. Then, click **Add data source**.


      .. figure:: /_static/images/en-us_image_0000002289469049.png
         :alt: **Figure 1** Configuring Grafana

         **Figure 1** Configuring Grafana

   c. Click **Prometheus** to access the configuration page.


      .. figure:: /_static/images/en-us_image_0000002254811852.png
         :alt: **Figure 2** Entering the Prometheus configuration page

         **Figure 2** Entering the Prometheus configuration page

   d. Set parameters according to the following figure.

      -  **Password**: access code generated in :ref:`2 <aom_02_0923__li543218492584>`
      -  **User**: aom_access_code
      -  **URL**: {*URI-scheme*}://{*Endpoint*}/v1/{*project_id*}/aom

         -  **URI-scheme**: protocol used to transmit requests. Currently, all APIs use HTTPS.
         -  **Endpoint**: Domain name or IP address of the server where the REST service is deployed. The endpoint varies depending on services and regions.
         -  **project_id**: project ID.

      .. note::

         -  The **Basic auth** and **Skip TLS Verify** options under **Auth** must be enabled.
         -  Access codes correspond to project IDs. Confirm their mapping when entering information.


      .. figure:: /_static/images/en-us_image_0000002289582137.png
         :alt: **Figure 3** Setting parameters

         **Figure 3** Setting parameters

   e. Click **Save&Test** to check whether the configuration is successful.

      If the configuration is successful, you can use Grafana to configure dashboards and view metric data.


      .. figure:: /_static/images/en-us_image_0000002289582117.png
         :alt: **Figure 4** Checking whether the configuration is successful

         **Figure 4** Checking whether the configuration is successful

.. |image1| image:: /_static/images/en-us_image_0000002289582129.png

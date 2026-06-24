:original_name: mon_01_0078.html

.. _mon_01_0078:

Obtaining the Service Address of a Prometheus Instance
======================================================

In the **Service Addresses** area on the **Settings** tab page of the default Prometheus instance or of the Prometheus instance for CCE, and remote write, you can obtain the configuration code for Prometheus remote read and write.

Prerequisites
-------------

Your service has been connected for Prometheus monitoring. For more details, see:

-  :ref:`Prometheus Instance for CCE <mon_01_0073>`
-  :ref:`Prometheus Instance for Remote Write <mon_01_0070>`

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**. In the instance list, click the created Prometheus instance.

#. On the instance details page, choose **Settings** in the navigation pane to obtain the service address of the current instance.

   The following describes how to obtain the service address of a Prometheus instance for CCE.

   -  Obtain the configuration code for Prometheus remote read.


      .. figure:: /_static/images/en-us_image_0000002514992805.png
         :alt: **Figure 1** Configuration code for Prometheus remote read

         **Figure 1** Configuration code for Prometheus remote read

      Remote read address:

      .. code-block::

         url: 'https://aom.{region_name}.{Site domain name suffix}:443/v1/{project_id}/aom/api/v1/read'

      Remote read address parameters:

      -  **region_name**: domain name or IP address of the server where the REST service is deployed. The value varies depending on services and regions.
      -  **Site domain name suffix**: site domain name suffix.
      -  **project_id**: project ID.

   -  Obtain the configuration code for Prometheus remote write.


      .. figure:: /_static/images/en-us_image_0000002515112809.png
         :alt: **Figure 2** Configuration code for Prometheus remote write

         **Figure 2** Configuration code for Prometheus remote write

      .. code-block::

      Remote write address:

      .. code-block::

         url: 'https://aom-access.{region_name}.{Site domain name suffix}:443/v1/{project_id}/push'

      Remote write address parameters:

      -  **region_name**: domain name or IP address of the server where the REST service is deployed. The value varies depending on services and regions.
      -  **Site domain name suffix**: site domain name suffix.
      -  **project_id**: project ID.

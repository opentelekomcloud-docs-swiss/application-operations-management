:original_name: mon_01_0067.html

.. _mon_01_0067:

Prometheus Instance for Cloud Services
======================================

This type of instance is recommended when you need to monitor multiple metrics of cloud services.

Creating a Prometheus Instance for Cloud Services
-------------------------------------------------

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**. On the displayed page, click **Add Prometheus Instance**.
#. Set the instance name and instance type.

   .. table:: **Table 1** Parameters for creating a Prometheus instance

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                 |
      +===================================+=============================================================================================================================================================+
      | Instance Name                     | Prometheus instance name.                                                                                                                                   |
      |                                   |                                                                                                                                                             |
      |                                   | Enter a maximum of 100 characters and do not start or end with an underscore (_) or hyphen (-). Only letters, digits, underscores, and hyphens are allowed. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Instance Type                     | Type of the Prometheus instance. Select **Prometheus for Cloud Services**.                                                                                  |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

Connecting Cloud Services to AOM
--------------------------------

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**.
#. On the Prometheus instance list page, click a Prometheus instance for cloud services.
#. Click **Connect Cloud Service** to connect desired cloud services.

   .. note::

      Cloud service metrics are synchronized from Cloud Eye. If AOM does not display data after services are connected, check whether there is data on Cloud Eye.

#. Click **Confirm**.

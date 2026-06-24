:original_name: mon_01_0073.html

.. _mon_01_0073:

Prometheus Instance for CCE
===========================

This type of instance is recommended when you need to monitor CCE clusters and applications running on them. By default, CCE clusters are monitored. You can also add cluster components for monitoring through the access center.

Precautions
-----------

-  You can connect clusters only when the kube-prometheus-stack add-on exists on the **Add-ons** page of CCE.
-  Before installing the kube-prometheus-stack add-on, ensure that there are at least 4 vCPUs and 8 GiB memory. Otherwise, this add-on cannot work.

Creating a Prometheus Instance for CCE
--------------------------------------

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
      | Instance Type                     | Type of the Prometheus instance. Select **Prometheus for CCE**.                                                                                             |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Click **OK**.

Connecting a CCE Cluster
------------------------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**.

#. In the instance list, click a Prometheus instance for CCE.

#. On the **Integration Center** page, click **Connect Cluster**. In the cluster list, you can view the cluster information, installation status, and collection status.

#. Locate a target cluster and click **Install** in the **Operation** column to install the Prometheus add-on.

#. After the installation is complete, click **Close** to connect the CCE cluster and bind it with the current Prometheus instance.

   To disconnect the CCE cluster, click **Uninstall**.

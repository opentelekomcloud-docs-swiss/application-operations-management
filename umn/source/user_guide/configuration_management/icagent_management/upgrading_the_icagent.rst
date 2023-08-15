:original_name: aom_02_0013.html

.. _aom_02_0013:

Upgrading the ICAgent
=====================

To ensure better collection experience, AOM will continuously upgrade ICAgent versions. When the system displays a message indicating that a new ICAgent version is available, perform the following operations:

.. note::

   If the ICAgent has a critical bug, the system will upgrade the ICAgent version.

#. In the navigation pane, choose **Configuration Management** > **Agent Management**.

#. .. _aom_02_0013__lf53afe92b28749b8be5a3ee0491c691a:

   Select **Cluster: XXX** or **Other: user-defined nodes** from the drop-down list on the right of the page.

#. Upgrade the ICAgent. If you select **Cluster: xxx** in :ref:`2 <aom_02_0013__lf53afe92b28749b8be5a3ee0491c691a>`, directly click **Upgrade ICAgent**. In this way, the ICAgent on all hosts in the cluster can be upgraded at a time. If you select **Other: user-defined nodes** in :ref:`2 <aom_02_0013__lf53afe92b28749b8be5a3ee0491c691a>`, select a desired host and then click **Upgrade ICAgent**.

#. Wait for about 1 minute to complete the upgrade. When the ICAgent status changes from **Updating** to **Running**, the ICAgent is successfully upgraded.

   .. note::

      If the upgrade fails, log in to the node and run the installation command to reinstall the ICAgent. The overwrite installation is supported. Therefore, you can reinstall the ICAgent without uninstallation.

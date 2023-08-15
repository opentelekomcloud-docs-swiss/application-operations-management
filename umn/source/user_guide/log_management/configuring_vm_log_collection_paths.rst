:original_name: aom_02_0039.html

.. _aom_02_0039:

Configuring VM Log Collection Paths
===================================

AOM can collect and display VM logs. VM refers to an Elastic Cloud Server (ECS) running Linux. Before collecting logs, configure a log collection path according to the following procedure.

Prerequisites
-------------

You have installed an ICAgent on a VM. For details, see :ref:`Installing the ICAgent <aom_02_0012>`. About five minutes after the ICAgent is installed, you can view your VM in the VM list on the **Path Configuration** page.

Precautions
-----------

-  An ICAgent collects **\*.log**, **\*.trace**, and **\*.out** log files only. For example, **/opt/yilu/work/xig/debug_cpu.log**.
-  Ensure that an absolute path of the log directory or file is configured and the path exists. For example, **/opt/yilu/work/xig** or **/opt/yilu/work/xig/debug_cpu.log**.
-  An ICAgent does not collect log files from subdirectories. For example, the ICAgent does not collect log files from the **/opt/yilu/work/xig/debug** subdirectory of **/opt/yilu/work/xig**.
-  A maximum of 20 log collection paths can be configured for a VM.
-  For ECSs in the same resource set, only the latest log collection configuration in the system will be used. AOM and LTS log collection configurations cannot take effect at the same time. For example, if you configure log collection paths in AOM for ECSs, the previous LTS collection configurations of all ECSs under the resource set become invalid.

Configuring Log Collection Paths for a Single VM Through the Console
--------------------------------------------------------------------

#. Log in to the AOM console. In the navigation pane, choose **Log** > **Path Configuration** and click the **Host Log** tab.

#. In the VM list, click **Configure** in the **Operation** column to configure one or more log collection paths for a VM.

   You can use the paths automatically identified by the ICAgent or manually configure paths.

   -  **Using the paths automatically identified by the ICAgent**

      The ICAgent automatically scans the log files of your VM, and displays all the log files that have file handles and are suffixed with **.log**, **.trace**, or **.out** on the page.

      You can click |image1| in the **Operation** column to add a path automatically identified by the ICAgent to the log collection path list. To configure multiple paths, repeat this operation.


      .. figure:: /_static/images/en-us_image_0000001448643005.png
         :alt: **Figure 1** Using the paths automatically identified by the ICAgent

         **Figure 1** Using the paths automatically identified by the ICAgent

   -  **Manually configuring log collection paths**

      If the paths automatically identified by the ICAgent cannot meet your requirements, enter a log directory or file (for example, **/opt/yilu/work/xig/debug_cpu.log**) in the **Log Collection Path** text box, and then click |image2| to add the path to the log collection path list. To configure multiple paths, repeat this operation.


      .. figure:: /_static/images/en-us_image_0000001448802673.png
         :alt: **Figure 2** Manually configuring log collection paths

         **Figure 2** Manually configuring log collection paths

#. Click **OK**.

Configuring Log Collection Paths for Multiple VMs in Batches Through the Console
--------------------------------------------------------------------------------

You can configure log collection paths for multiple VMs in batches. When your component is deployed on multiple VMs, configuring log collection paths in batches helps you greatly reduce workload.

#. Log in to the AOM console. In the navigation pane, choose **Log** > **Path Configuration** and click the **Host Log** tab.

#. Configure one or more log collection paths for multiple VMs in batches.

   Select one or more VMs in the list, click **Batch Configure**, and enter a log directory or file (for example, **/opt/yilu/work/xig/debug_cpu.log**) in the **Log Collection Path** text box. To configure multiple paths, click **Add Log Collection Path**.

   .. note::

      If you configure log collection paths for your VM and then configure log collection paths in batches, new paths will be added to the existing path list.

#. Click **OK**.

   By default, the log collection paths configured for the VM are displayed in the **Log Collection Path** column of the VM list. If more than three log collection paths have been configured, click **Query More** to view all the paths configured for the VM.

Viewing VM Logs
---------------

After a log collection path is configured, the ICAgent collects log files from the configured path. The collection takes about 1 minute. After the collection is complete, you can perform the following operations:

-  **Viewing VM log files**

   In the navigation pane, choose **Log** > **Log Files**. Click the **Host** tab to view the collected log files. For details, see :ref:`Viewing Log Files <aom_02_0010>`.

-  **Viewing and analyzing VM logs**

   In the navigation pane, choose **Log** > **Log Search**. Click the **Host** tab to view and analyze the collected logs by time range, keyword, and context. For details, see :ref:`Searching for Logs <aom_02_0009>`.

.. |image1| image:: /_static/images/en-us_image_0000001448643009.png
.. |image2| image:: /_static/images/en-us_image_0000001448643009.png

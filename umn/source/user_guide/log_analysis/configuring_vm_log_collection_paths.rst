:original_name: aom_02_0039.html

.. _aom_02_0039:

Configuring VM Log Collection Paths
===================================

AOM can collect and display VM logs. VM refers to an Elastic Cloud Server (ECS) running Linux. Before collecting logs, ensure that you have set a log collection path.

Prerequisites
-------------

You have installed an ICAgent on a VM. For details, see :ref:`Installing an ICAgent <aom_02_0012>`. About five minutes after the ICAgent is installed, you can view your VM in the VM list on the **Path Configuration** page.

Precautions
-----------

-  An ICAgent collects **\*.log**, **\*.trace**, and **\*.out** log files only. For example, **/opt/yilu/work/xig/debug_cpu.log**.
-  Ensure that an absolute path of the log directory or file is configured and the path exists. For example, **/opt/yilu/work/xig** or **/opt/yilu/work/xig/debug_cpu.log**.
-  An ICAgent does not collect log files from subdirectories. For example, the ICAgent does not collect log files from the **/opt/yilu/work/xig/debug** subdirectory of **/opt/yilu/work/xig**.
-  A maximum of 20 log collection paths can be configured for a VM.
-  For ECSs in the same resource set, only the latest log collection configuration in the system will be used. AOM and LTS log collection configurations cannot take effect at the same time. For example, if you configure log collection paths in AOM for ECSs, the previous LTS collection configurations of all ECSs under the resource set become invalid.

Configuring Log Collection Paths
--------------------------------

#. In the navigation pane, choose **Log Analysis** > **Path Configuration**.

#. In the VM list, click |image1| in the **Operation** column to configure one or more log collection paths for a VM.

   You can use the paths automatically identified by the ICAgent or manually configure paths.

   -  **Using the paths automatically identified by the ICAgent**

      The ICAgent automatically scans the log files of your VM, and displays all the log files that have file handles and are suffixed with **.log**, **.trace**, or **.out** on the page.

      You can click |image2| in the **Operation** column to add a path automatically identified by the ICAgent to the log collection path list. To configure multiple paths, repeat this operation.

   -  **Manually configuring log collection paths**

      If the paths automatically identified by the ICAgent cannot meet your requirements, enter a log directory or file (for example, **/usr/local/uniagentd/log/agent.log**) in the **Log Collection Path** text box, and then add the path to the log collection path list. To configure multiple paths, repeat this operation.

#. Click **Confirm**.

Viewing VM Logs
---------------

After a log collection path is configured, the ICAgent collects log files from the configured path. The collection takes about 1 minute. After the collection is complete, you can perform the following operations:

-  **Viewing VM log files**

   In the navigation pane, choose **Log Analysis** > **Log Files**. Click the **Host** tab to view the collected log files. For details, see :ref:`Viewing Log Files <aom_02_0010>`.

-  **Viewing and analyzing VM logs**

   In the navigation pane, choose **Log Analysis** > **Log Search**. Click the **Host** tab to view and analyze the collected logs by time range, keyword, and context. For details, see :ref:`Searching for Logs <aom_02_0009>`.

.. |image1| image:: /_static/images/en-us_image_0000002289582109.png
.. |image2| image:: /_static/images/en-us_image_0000002289469029.png

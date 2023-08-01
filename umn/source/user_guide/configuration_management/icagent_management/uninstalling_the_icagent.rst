:original_name: aom_02_0014.html

.. _aom_02_0014:

Uninstalling the ICAgent
========================

If the ICAgent on a server is uninstalled, server O&M will be affected, making Application Operations Management (AOM) functions unavailable. Exercise caution when performing this operation.

You can uninstall the ICAgent using either of the following methods:

-  :ref:`Uninstalling the ICAgent Through the AOM Console <aom_02_0014__section13185626133716>`: Applies to the scenario where the ICAgent has been successfully installed and needs to be uninstalled.
-  :ref:`Uninstalling the ICAgent Through Logging In to the Server <aom_02_0014__section1218782615374>`: Applies to the scenario where the ICAgent fails to be installed and needs to be uninstalled for reinstallation.
-  :ref:`Remotely Uninstalling the ICAgent <aom_02_0014__section76581424194316>`: Applies to the scenario where the ICAgent has been successfully installed and needs to be remotely uninstalled.
-  :ref:`Uninstalling the ICAgent in Batches <aom_02_0014__section19497111135712>`: Applies to the scenario where the ICAgent has been successfully installed and needs to be uninstalled in batches.

.. _aom_02_0014__section13185626133716:

Uninstalling the ICAgent Through the AOM Console
------------------------------------------------

#. In the navigation pane, choose **Configuration Management** > **Agent Management**.

#. Select **Other: user-defined nodes** from the drop-down list on the right of the page.

#. Select one or more servers where the ICAgent is to be uninstalled, and click **Uninstall ICAgent**. In the **Uninstall ICAgent** dialog box, click **Yes**.

   The ICAgent begins to be uninstalled. This operation takes about 1 minute to complete. If the involved server is removed from the node list, the ICAgent is successfully uninstalled.

.. _aom_02_0014__section1218782615374:

Uninstalling the ICAgent Through Logging In to the Server
---------------------------------------------------------

#. Log in to the server where the ICAgent is to be uninstalled as the **root** user.

#. Run the following command to uninstall the ICAgent:

   **bash /opt/oss/servicemgr/ICAgent/bin/manual/uninstall.sh;**

#. If the message **ICAgent uninstall success.** is displayed, the ICAgent is successfully uninstalled.

.. _aom_02_0014__section76581424194316:

Remotely Uninstalling the ICAgent
---------------------------------

#. Run the following command (**x.x.x.x** indicates the server IP address) on the server where the ICAgent has been installed:

   **bash /opt/oss/servicemgr/ICAgent/bin/remoteUninstall/remote_uninstall.sh -ip x.x.x.x**

#. Enter the password of the **root** user of the server where the ICAgent is to be uninstalled as prompted.

   .. note::

      -  If both the Expect tool and the ICAgent have been installed on the server, the ICAgent will be uninstalled from the remote server after the preceding command is executed. If the ICAgent has been installed on the server, but the Expect tool has not, enter the information as prompted.
      -  Ensure that the **root** user can run the **SSH** or **SCP** command on the server where the ICAgent has been installed to remotely communicate with the server where the ICAgent is to be uninstalled.
      -  If the message **ICAgent uninstall success** is displayed, the ICAgent is successfully uninstalled. After the ICAgent is successfully uninstalled, choose **Configuration Management** > **Agent Management** to view the ICAgent status.

.. _aom_02_0014__section19497111135712:

Uninstalling the ICAgent in Batches
-----------------------------------

If the ICAgent has been installed on a server and the **ICProbeAgent.zip** installation package exists in the **/opt/ICAgent/** directory of this server, use this method to uninstall the ICAgent from multiple remote servers in batches with a few clicks.

.. important::

   The servers must belong to the same Virtual Private Cloud (VPC) and network segment.

**Prerequisites**

The IP addresses and passwords of all servers from which the ICAgent is to be uninstalled have been collected, sorted in the **iplist.cfg** file, and uploaded to the **/opt/ICAgent/** directory on the server where the ICAgent has been installed. The following is an example of the **iplist.cfg** file, where IP addresses and passwords are separated by spaces.

*192.168.0.109 password* (Set the password as required.)

*192.168.0.39 password* (Set the password as required.)

.. note::

   -  Because the **iplist.cfg** file contains sensitive information, you are advised to clear the information after use.

   -  If the passwords of all servers are the same, only list IP addresses in the **iplist.cfg** file and enter the password once during execution. If the password of an IP address is different from those of the other ones, list both passwords and IP addresses in the **iplist.cfg** file.
   -  You need to press **Enter** at the end of each line in the **iplist.cfg** file.

**Procedure**

#. Run the following command on the server where the ICAgent has been installed:

   **bash /opt/oss/servicemgr/ICAgent/bin/remoteUninstall/remote_uninstall.sh -batchModeConfig /opt/ICAgent/iplist.cfg**

   Enter the default password of the **root** user as prompted. If the passwords of all IP addresses have been configured in the **iplist.cfg** file, press **Enter** to skip this step. Otherwise, enter the default password.

   .. code-block::

      batch uninstall begin
      Please input default passwd:
      send cmd to 192.168.0.109
      send cmd to 192.168.0.39
      2 tasks running, please wait...
      End of uninstall agent: 192.168.0.109
      End of uninstall agent: 192.168.0.39
      All hosts uninstall icagent finish.

   Wait until the message **All hosts uninstall icagent finish.** is displayed, which indicates that the ICAgent is successfully uninstalled from all the hosts listed in the configuration file.

#. After the ICAgent is successfully uninstalled, choose **Configuration Management** > **Agent Management** to view the ICAgent status.

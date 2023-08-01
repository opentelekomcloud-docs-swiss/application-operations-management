:original_name: aom_02_0012.html

.. _aom_02_0012:

Installing the ICAgent
======================

The following table describes the ICAgent status.

.. table:: **Table 1** ICAgent status

   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Status              | Description                                                                                                                                                                                       |
   +=====================+===================================================================================================================================================================================================+
   | Running             | The ICAgent is running properly.                                                                                                                                                                  |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Uninstalled         | The ICAgent is not installed. For details about how to install the ICAgent, see :ref:`Installing the ICAgent <aom_02_0012>`.                                                                      |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Installing          | The ICAgent is being installed. This operation takes about 1 minute to complete.                                                                                                                  |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Installation failed | Failed to install the ICAgent. Uninstall the ICAgent according to :ref:`Uninstalling the ICAgent Through Logging In to the Server <aom_02_0014__section1218782615374>` and then install it again. |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Upgrading           | The ICAgent is being upgraded. This operation takes about 1 minute to complete.                                                                                                                   |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Upgrade failed      | Failed to upgrade the ICAgent. Uninstall the ICAgent according to :ref:`Uninstalling the ICAgent Through Logging In to the Server <aom_02_0014__section1218782615374>` and then install it again. |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Offline             | The Access Key ID/Secret Access Key (AK/SK) are incorrect. Obtain the correct AK/SK and install the ICAgent again.                                                                                |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Abnormal            | The ICAgent is abnormal. Contact technical support.                                                                                                                                               |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Restricted          | The AOM license is restricted. Check the license and update it in a timely manner.                                                                                                                |
   +---------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Prerequisites
-------------

Before installing the ICAgent, ensure that the time and time zone of the local browser are consistent with those of the server. If multiple servers are deployed, ensure that the local browser and multiple servers use the same time zone and time. Otherwise, metric data of applications and servers displayed on the console may be inaccurate.

Installation Methods
--------------------

There are two methods to install the ICAgent. Note that the two methods are not applicable to container nodes created using ServiceStage or Cloud Container Engine (CCE). For container nodes, you do not need to manually install the ICAgent. Instead, you only need to perform certain operations when creating clusters or deploying applications.

For details, see :ref:`Table 2 <aom_02_0012__td567fa2f6ccc421ca2e6a4b8a51ee8c6>`.

.. _aom_02_0012__td567fa2f6ccc421ca2e6a4b8a51ee8c6:

.. table:: **Table 2** Installation methods

   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Method                            | Application Scenario                                                                                                                                                                                                                                                                  |
   +===================================+=======================================================================================================================================================================================================================================================================================+
   | Initial installation              | This method is used when the following conditions are met:                                                                                                                                                                                                                            |
   |                                   |                                                                                                                                                                                                                                                                                       |
   |                                   | #. An elastic IP address (EIP) has been bound to the server.                                                                                                                                                                                                                          |
   |                                   | #. The ICAgent has never been installed on the server.                                                                                                                                                                                                                                |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Inherited installation            | This method is used when the following conditions are met:                                                                                                                                                                                                                            |
   |                                   |                                                                                                                                                                                                                                                                                       |
   |                                   | You have multiple servers on which the ICAgent is to be installed. One server is bound to an EIP, but others are not bound to an EIP. You have installed the ICAgent on the server bound with an EIP. For the servers that are not bound with an EIP, perform inherited installation. |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Initial Installation
--------------------

After you apply for a server and install the ICAgent for the first time, perform the following operations:

#. Obtain an AK/SK.

   -  If you have obtained the AK/SK, skip this step.
   -  If no AK/SK are available, :ref:`obtain them first <aom_02_1100>`.

#. In the navigation pane, choose **Configuration Management** > **Agent Management**.

#. Select **Other: user-defined nodes**, and click **Install ICAgent**.

#. .. _aom_02_0012__li927610465501:

   Copy the generated ICAgent installation command.

#. Use a remote login tool to log in to the server as a **root** user.

#. Run the command copied in :ref:`4 <aom_02_0012__li927610465501>` and enter the obtained AK/SK as prompted to install the ICAgent.

.. note::

   -  If the message **ICAgent install success.** is displayed, the ICAgent is successfully installed in the **/opt/oss/servicemgr/** directory. After the ICAgent is successfully installed, choose **Configuration Management** > **Agent Management** to view the ICAgent status.
   -  If the ICAgent fails to be installed, uninstall it according to :ref:`Uninstalling the ICAgent Through Logging In to the Server <aom_02_0014__section1218782615374>` and then install it again. If the problem persists, contact technical support.

Inherited Installation
----------------------

If the ICAgent has been installed on a server and the **ICProbeAgent.tar.gz** installation package exists in the **/opt/ICAgent/** directory of this server, use this method to install the ICAgent on a remote server with a few clicks.

.. important::

   After the ICAgent is upgraded, the **/opt/ICAgent/** directory and the files stored in it will be deleted. Therefore, reinstall the ICAgent and then perform inherited installation.

#. Run the following command (**x.x.x.x** indicates the server IP address) on the server where the ICAgent has been installed:

   **bash /opt/oss/servicemgr/ICAgent/bin/remoteInstall/remote_install.sh -ip** **x.x.x.x**

#. Enter the password of the **root** user of the server where the ICAgent is to be installed as prompted.

   .. note::

      -  If both the Expect tool and the ICAgent have been installed on the server, the ICAgent will be installed on the remote server after the preceding command is executed. If the ICAgent has been installed on the server, but the Expect tool has not, enter the information as prompted.
      -  Ensure that the **root** user can run the **SSH** or **SCP** command on the server where the ICAgent has been installed to remotely communicate with the server where the ICAgent is to be installed.
      -  Ensure that the **ICProbeAgent.tar.gz** installation package is transmitted to the server to be installed.
      -  If the message **ICAgent install success** is displayed, the ICAgent is successfully installed in the **/opt/oss/servicemgr/** directory. After the ICAgent is successfully installed, choose **Configuration Management** > **Agent Management** to view the ICAgent status.
      -  If the ICAgent fails to be installed, uninstall it according to :ref:`Uninstalling the ICAgent Through Logging In to the Server <aom_02_0014__section1218782615374>` and then install it again. If the problem persists, contact technical support.

Inherited Batch Installation
----------------------------

If the ICAgent has been installed on a server and the **ICProbeAgent.zip** installation package exists in the **/opt/ICAgent/** directory of this server, use this method to install the ICAgent on multiple remote servers in batches with a few clicks.

.. important::

   #. Ensure that you can run the **SSH** and **SCP** commands on the ECS server where the ICAgent has been installed to communicate with the remote ECS servers where the ICAgent is to be installed.
   #. If you have installed the ICAgent in a server through an agency, you also need to set an agency for other servers where the ICAgent is to be installed.
   #. Batch installation scripts depend on Python versions. You are advised to implement batch installation on hosts running Python 2.x. Python 3.x does not support batch installation.
   #. You need to press **Enter** at the end of each line in the **iplist.cfg** file.
   #. After the ICAgent is upgraded, the **/opt/ICAgent/** directory and the files stored in it will be deleted. Therefore, reinstall the ICAgent and then perform inherited batch installation.

**Prerequisites**

The IP addresses and passwords of all servers for which the ICAgent is to be installed have been collected, sorted in the **iplist.cfg** file, and uploaded to the **/opt/ICAgent/** directory on the server where the ICAgent has been installed. The following is an example of the **iplist.cfg** file, where IP addresses and passwords are separated by spaces.

*192.168.0.109 password* (Set the password as required.)

*192.168.0.39 password* (Set the password as required.)

.. note::

   -  Because the **iplist.cfg** file contains sensitive information, you are advised to clear the information after use.

   -  If the passwords of all servers are the same, only list IP addresses in the **iplist.cfg** file and enter the password once during execution. If the password of an IP address is different from those of the other ones, list both passwords and IP addresses in the **iplist.cfg** file.
   -  The batch installation function depends on Python 2.7.*. If the system displays a message indicating that Python cannot be found during the installation, install Python 2.7.\* and try again.

**Procedure**

#. Run the following command on the server where the ICAgent has been installed:

   **bash /opt/oss/servicemgr/ICAgent/bin/remoteInstall/remote_install.sh -batchModeConfig /opt/ICAgent/iplist.cfg**

   Enter the default password of the **root** user as prompted. If the passwords of all IP addresses have been configured in the **iplist.cfg** file, press **Enter** to skip this step. Otherwise, enter the default password.

   .. code-block::

      batch install begin
      start to install python pexpect module
      use local pyexpect package
      Please input default passwd:
      send cmd to 192.168.0.109
      send cmd to 192.168.0.39
      2 tasks running, please wait...
      2 tasks running, please wait...
      2 tasks running, please wait...
      End of install agent: 192.168.0.39
      End of install agent: 192.168.0.109
      All hosts install icagent finish.

   Wait until the message **All hosts install icagent finish.** is displayed, which indicates that the ICAgent is successfully installed on all the hosts listed in the configuration file.

#. After the ICAgent is successfully installed, choose **Configuration Management** > **Agent Management** to view the ICAgent status.

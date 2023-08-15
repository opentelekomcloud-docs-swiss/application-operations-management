:original_name: aom_04_1100.html

.. _aom_04_1100:

What Can I Do If an ICAgent Is Offline?
=======================================

After an ICAgent is installed, its status is offline.

Problem Analysis
----------------

-  **Cause:** The AK/SK are incorrect or ports 30200 and 30201 are disconnected.
-  **Impact:** The ICAgent cannot work.

Solution
--------

#. Log in to the server where the ICAgent is installed as the **root** user.

#. Run the following command to check whether the AK/SK configuration is correct:

   .. code-block::

      cat /var/ICAgent/oss.icAgent.trace | grep proxyworkflow.go

   -  If no command output is displayed, the AK/SK configuration is incorrect. Go to :ref:`3 <aom_04_1100__li089634131819>`.
   -  If a command output is displayed, the AK/SK configuration is correct. Go to :ref:`4 <aom_04_1100__li77391656131917>`.

#. .. _aom_04_1100__li089634131819:

   After configuring the AK/SK, reinstall the ICAgent. For details, see :ref:`Installing the ICAgent <aom_02_0012>`. If the installation still fails, go to :ref:`4 <aom_04_1100__li77391656131917>`.

#. .. _aom_04_1100__li77391656131917:

   Check port connectivity.

   a. Run the following command to obtain the access IP address:

      .. code-block::

         cat /opt/oss/servicemgr/ICAgent/envs/ICProbeAgent.properties | grep ACCESS_IP

   b. Run the following command to respectively check the connectivity of ports 30200 and 30201:

      .. code-block::

         curl -k https://ACCESS_IP:30200
         curl -k https://ACCESS_IP:30201

      -  If **404** is displayed, the port is connected. In this case, contact technical support.
      -  If the command output is not **404**, the port is not connected. Contact the network administrator to open the port and reinstall ICAgent. If the installation still fails, contact technical support.

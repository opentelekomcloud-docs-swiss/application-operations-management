:original_name: aom_05_0005.html

.. _aom_05_0005:

Installing an ICAgent
=====================

This section describes how to install an ICAgent on an ECS.

Prerequisites
-------------

-  An ECS has been created.
-  An EIP has been bound to the ECS.
-  The browser time is the same as the ECS time.

Procedure
---------

#. .. _aom_05_0005__li19841023131:

   Obtain an AK/SK of a public account. Do not use those of an individual account.

   .. important::

      Ensure that the public account and AK/SK will not be deleted or disabled. If the AK/SK is deleted, the ICAgent cannot report data to AOM or LTS.

   -  If you have obtained an AK/SK, skip this step.
   -  If you do not have an AK/SK, :ref:`obtain them <aom_02_1100>` first.

#. In the navigation pane, choose **Configuration Management** > **Agent Management**.

#. Select **Other: custom hosts**, and click **Install ICAgent**.

#. .. _aom_05_0005__li927610465501:

   Click **Copy Command**.

#. Use a remote login tool, such as PuTTY, to log in as the **root** user to the server where the ICAgent is to be installed, run the command copied in :ref:`4 <aom_05_0005__li927610465501>`, and enter the AK/SK obtained in :ref:`1 <aom_05_0005__li19841023131>` as prompted to install the ICAgent.

   .. note::

      -  If the message **ICAgent install success** is displayed, the ICAgent is successfully installed in the **/opt/oss/servicemgr/** directory. After the ICAgent is successfully installed, choose **Configuration Management** > **Agent Management** in the navigation pane on the left, and select **Other: custom hosts** to view the ICAgent status of the server.
      -  If the ICAgent fails to be installed, uninstall it according to :ref:`Uninstalling the ICAgent Through Logging In to the Server <aom_02_0014__section1218782615374>` and then install it again. If the problem persists, contact technical support.

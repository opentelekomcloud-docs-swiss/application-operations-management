:original_name: aom_05_0005.html

.. _aom_05_0005:

Installing an ICAgent
=====================

This section describes how to install an ICAgent on an ECS.

Prerequisites
-------------

-  An ECS has been created.
-  An EIP has been bound to the ECS.
-  An AK/SK have been obtained. For details, see :ref:`Obtaining an AK/SK <aom_02_1100>`.
-  The time zone and time of the browser are the same as those of the ECS.

Procedure
---------

#. Log in to the AOM console and choose **Configuration Management** > **Agent Management** in the navigation pane.

#. Select **Other: user-defined nodes**, and click **Install ICAgent**.

#. .. _aom_05_0005__li927610465501:

   Copy the generated ICAgent installation command.

#. Use a remote login tool to log in to the server as a **root** user.

#. Run the command copied in :ref:`3 <aom_05_0005__li927610465501>` and enter the obtained AK/SK as prompted to install the ICAgent.

   .. note::

      -  If the message **ICAgent install success** is displayed, the ICAgent is successfully installed in the **/opt/oss/servicemgr/** directory. After the ICAgent is successfully installed, choose **Configuration Management** > **Agent Management** in the navigation pane on the left, and select **Other: user-defined nodes** to view the ICAgent status of the server.
      -  If the ICAgent fails to be installed, uninstall it by referring to :ref:`Uninstalling the ICAgent Through Logging In to the Server <aom_02_0014__section1218782615374>` and then install it again. If the problem persists, contact technical support.

Follow-up Operations
--------------------

For more information about how to install, upgrade, and uninstall the ICAgent, see :ref:`ICAgent Management <aom_02_0011>`.

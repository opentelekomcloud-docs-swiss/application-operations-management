:original_name: aom_02_0007.html

.. _aom_02_0007:

Component Monitoring
====================

Components refer to the services that you deploy, including containers and common processes. For example, a workload on the Cloud Container Engine (CCE) is a component, and the Tomcat running on the VM is also a component.

The component list displays information such as type, CPU usage, and memory usage of each component. You can click a component name to learn more information about the component. AOM supports drill-down from a component to an instance, and then to a container. You can implement multi-dimensional monitoring.

.. note::

   The ICAgent reports resource information every ten minutes. The resource status changes are described as follows:

   -  If the ICAgent on a host does not report resource information **for three consecutive times**, the system determines that the resource has been deleted. Therefore, the host status is displayed as **Deleted** within 30 minutes after the ICAgent is uninstalled or the resource is deleted.
   -  When the ICAgent on a host reports resource information **for one time**, the system determines that the resource is restored. The host status is displayed as **Normal** ten minutes after the ICAgent is reinstalled or the resource is restored.

#. In the navigation pane, choose **Monitoring** > **Component Monitoring**.

   -  The component list displays information such as **Component Name**, **Status**, **Application**, and **Deployment Mode**.
   -  Click |image1| in the upper right corner and select **Hide system component**.

#. Perform the following operations as required:

   -  **Adding an alias**

      If a component name is complex and difficult to identify, you can add an alias for the component.

      Click **Add alias** in the **Operation** column. The added alias can be modified but cannot be deleted.

   -  **Adding a tag**

      Tags are used to identify components. You can distinguish system components from non-system ones by using tags. By default, AOM adds the **System Service** tag to system components, including icagent, css-defender, nvidia-driver-installer, nvidia-gpu-device-plugin, kube-dns, org.tanukisoftware.wrapper.WrapperSimpleApp, evs-driver, obs-driver, sfs-driver, icwatchdog, and sh. You can click |image2| in the upper right corner and select or deselect **Hide system component**. You can also customize tags to facilitate component management.

      .. note::

         The **Tags** column of the component list is hidden by default. You can click |image3| in the upper right corner and select or deselect **Tags** to show or hide them.

#. Set filter criteria to search for the desired component.

   .. note::

      Components cannot be searched by alias.

#. Click the component name to go to the **Component Details** page.

   -  Click **View Log** next to the component name to go to the log search page and view the logs of the component. Logs of ServiceStage components cannot be viewed on the **Component Details** page.
   -  On the **Instance List** tab page, view the instance details.

      .. note::

         Click an instance to monitor information such as resource usage and health status.

   -  On the **Host List** tab page, view the host details.
   -  On the **Alarm Analysis** tab page, view the alarm details.

   -  Click the **View Monitor Graphs** tab to monitor the metrics of the component.

.. |image1| image:: /_static/images/en-us_image_0000001448643029.png
.. |image2| image:: /_static/images/en-us_image_0000001398402756.png
.. |image3| image:: /_static/images/en-us_image_0000001398562744.png

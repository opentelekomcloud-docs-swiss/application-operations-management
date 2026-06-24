:original_name: aom_02_0007.html

.. _aom_02_0007:

Component Monitoring
====================

Components refer to the services that you deploy, including containers and common processes. For example, a workload on the Cloud Container Engine (CCE) is a component, and the Tomcat running on the VM is also a component.

The component list displays information such as the type, CPU usage, and memory usage of each component. You can click a component name to learn more information about the component. AOM supports drill-down from a component to an instance, and then to a container. You can implement multi-dimensional monitoring.

.. note::

   The ICAgent reports resource information every ten minutes. The resource status changes are described as follows:

   -  If the ICAgent on a host does not report resource information **for three consecutive times**, the system determines that the resource has been deleted. Therefore, the host status is displayed as **Deleted** within 30 minutes after the ICAgent is uninstalled or the resource is deleted.
   -  When the ICAgent on a host reports resource information **for one time**, the system determines that the resource exists. The host status is displayed as **Normal** ten minutes after the resource is created or the ICAgent is installed.

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane, choose **Infrastructure Monitoring** > **Component Monitoring**.

   -  The component list displays information such as **Component Name**, **Application**, **Deployment Mode**, and **Application Discovery Rules**.
   -  To view target components, you can set filter criteria (such as the running status, application, cluster name, deployment mode, and component name) above the component list.
   -  Enable or disable **Hide System Components** to hide or show system components. By default, system components are hidden.
   -  In the upper right corner of the page, set component filter criteria.

      a. Set a time range to view the components reported. There are two methods to set a time range:

         Method 1: Use the predefined time label, such as **Last 30 minutes**, **Last hour**, **Last 6 hours**, **Last day**, or **Last week**. Select one as required.

         Method 2: Specify the start time and end time (max. 15 days).

      b. Set the interval for refreshing information. Click |image1| and select a value from the drop-down list as required, such as **Refresh manually**, **30 seconds auto refresh**, **1 minute auto refresh**, or **5 minutes auto refresh**.

      c. Click |image2| in the upper right corner and select or deselect **the columns to display**.

#. Perform the following operations as required:

   -  **Adding an alias**

      If a component name is complex and difficult to identify, you can add an alias for the component.

      In the component list, click |image3| in the **Operation** column of the target component, enter an alias, and click **OK**. The added alias can be modified but cannot be deleted.

   -  **Adding a tag**

      Tags are component identifiers. You can distinguish system components from non-system components based on tags. By default, system components (including icagent, css-defender, nvidia-driver-installer, nvidia-gpu-device-plugin, kube-dns, org.tanukisoftware.wrapper.WrapperSimpleApp, evs-driver, obs-driver, sfs-driver, icwatchdog, and sh) are tagged as **System Service**. You can also customize tags for easier component management.

      In the component list, click |image4| in the **Operation** column of the target component. In the displayed dialog box, enter a tag key and value, click |image5|, select the **Mark as system component** check box, and click **OK**.

#. Set filter criteria to search for the desired component.

   .. note::

      Components cannot be searched by alias.

#. Click the component name to go to the **Component Details** page.

   -  On the **Component Details** page, view the running status, ID, creation time, application, cluster, and namespace of the component.
   -  In the upper right corner of the page, set a time range and refresh frequency.
   -  On the **Instance List** tab page, view basic information such as the instance type, status, node IP address, usage, and creation time. Click an instance name to view its metrics on the **Instance Details** page.
   -  Enter an instance name in the search box in the upper right corner and click |image6| to search.
   -  Click |image7| to refresh the instance list.
   -  On the **Host List** tab page, view the name, IP address, status, and resource usage of the host where the component is located. Click a host name to view its metrics on the **Host Details** page.
   -  On **Monitoring View** tab page, monitor key metrics of the component, such as the total number of CPU cores, used CPU cores, and CPU core usage.
   -  On the **Event** tab page, view the event details of the component. For details, see :ref:`Viewing Events <mon_01_0012>`.
   -  On the **Alarms** tab page, view the alarm details of the component. For details, see :ref:`Viewing Alarms <mon_01_0011>`.

.. |image1| image:: /_static/images/en-us_image_0000002482912892.png
.. |image2| image:: /_static/images/en-us_image_0000002515112897.png
.. |image3| image:: /_static/images/en-us_image_0000002482912894.png
.. |image4| image:: /_static/images/en-us_image_0000002514992899.png
.. |image5| image:: /_static/images/en-us_image_0000002515112905.png
.. |image6| image:: /_static/images/en-us_image_0000002514992897.png
.. |image7| image:: /_static/images/en-us_image_0000002514992893.png

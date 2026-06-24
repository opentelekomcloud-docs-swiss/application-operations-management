:original_name: aom_02_0008.html

.. _aom_02_0008:

Host Monitoring
===============

Hosts include Elastic Cloud Servers (ECSs). AOM monitors the hosts created during Cloud Container Engine (CCE) cluster creation and the hosts that are directly created. Ensure that the directly created hosts meet operating system (OS) and version requirements and install the ICAgent on these hosts according to :ref:`Installing an ICAgent <aom_02_0012>`. Otherwise, these hosts cannot be monitored by AOM. In addition, the hosts support both IPv4 and IPv6 addresses.

AOM monitors the resource usage and health status of hosts, common system devices such as disks and file systems of hosts, and service processes or instances running on hosts.

.. note::

   The ICAgent reports resource information every ten minutes. The resource status changes are described as follows:

   -  If the ICAgent on a host does not report resource information **for three consecutive times**, the system determines that the resource has been deleted. Therefore, the host status is displayed as **Deleted** within 30 minutes after the host is stopped or the ICAgent is uninstalled.
   -  When the ICAgent on a host reports resource information **for one time**, the system determines that the resource exists. The host status is displayed as **Normal** ten minutes after the host is started or the ICAgent is installed.

Precautions
-----------

-  A maximum of five tags can be added to a host, and each tag must be unique.
-  The same tag can be added to different hosts.
-  The host status can be **Normal**, **Abnormal**, **Warning**, **Silent**, or **Deleted**. The running status of a host is displayed as **Abnormal** when the host is faulty due to network failures, and power off or shut down of the host, or when the host generates a threshold alarm. For more information, see :ref:`What Can I Do If Resources Are Not Running Properly? <aom_02_1012>`.

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane, choose **Infrastructure Monitoring** > **Host Monitoring**.

   -  To view desired hosts, set filter criteria (such as the running status, host type, host name, and IP address) above the host list.
   -  You can enable or disable **Hide master host**. By default, master hosts are hidden.
   -  Click |image1| next to **Hide master host** to synchronize host information.
   -  In the upper right corner of the page, set host filter criteria.

      a. Set a time range to view the hosts reported. There are two methods to set a time range:

         Method 1: Use the predefined time label, such as **Last 30 minutes**, **Last hour**, **Last 6 hours**, **Last day**, or **Last week**. Select one as required.

         Method 2: Specify the start time and end time (max. 15 days).

      b. Set the interval for refreshing information. Click |image2| and select a value from the drop-down list as required, such as **Refresh manually**, **30 seconds auto refresh**, **1 minute auto refresh**, or **5 minutes auto refresh**.

      c. Click |image3| in the upper right corner and select or deselect **the columns to display**.

#. Perform the following operations as required:

   -  **Adding an alias**

      If a host name is too complex to identify, you can add an alias, which makes it easy to identify a host as required.

      In the host list, click |image4| in the **Operation** column of the target host, enter an alias, and click **OK**. The added alias can be modified but cannot be deleted.

   -  **Adding a tag**

      Tags are identifiers of hosts. You can manage hosts using tags. After a tag is added, you can quickly identify and select a host.

      In the host list, click |image5| in the **Operation** column of the target host. In the displayed dialog box, enter a tag key and value, and click |image6| and **OK**.

   -  **Synchronizing host data**

      In the host list, locate the target host and click |image7| in the **Operation** column to synchronize host information.

#. Set filter criteria to search for the desired host.

   .. note::

      Hosts cannot be searched by alias.

#. Click a host name. The **Host Details** page is displayed.

   -  On the **Host Details** page, view the running status and ID of the host.
   -  In the upper right corner of the page, set a time range and refresh frequency.
   -  Click the **Instance List** tab to view the basic information (such as the instance name and IP address). Click an instance to view its metrics on the details page.
   -  Enter an instance name in the search box in the upper right corner and click |image8| to search.
   -  Click |image9| to refresh the instance list.
   -  On **Monitoring View** tab page, monitor key metrics of the host, such as the total number of CPU cores, used CPU cores, and CPU core usage.
   -  On the **Event** tab page, view the event details of the host. For details, see :ref:`Viewing Events <mon_01_0012>`.
   -  On the **Alarms** tab page, view the alarm details of the host. For details, see :ref:`Viewing Alarms <mon_01_0011>`.
   -  On the **File Systems** tab page, view the basic information about the file system of the host. Click a disk file partition to monitor its metrics on the **Monitoring View** page.
   -  On the **Disk** tab page, view the basic information about the disks of the host. Click a disk to monitor its metrics on the **Monitoring View** page.
   -  On the **Disk Partition** tab page, view the disk partition information about the host. Click a disk partition to monitor its metrics on the **Monitoring View** page.
   -  On the **NIC** tab page, view the basic information about the NICs of the host. Click a NIC to monitor its metrics on the **Monitoring View** page.
   -  On the **GPU** tab page, view the basic information about the GPUs of the host. Click a GPU to monitor its metrics on the **Monitoring View** page.

.. |image1| image:: /_static/images/en-us_image_0000002482912812.png
.. |image2| image:: /_static/images/en-us_image_0000002482912820.png
.. |image3| image:: /_static/images/en-us_image_0000002515112821.png
.. |image4| image:: /_static/images/en-us_image_0000002515112825.png
.. |image5| image:: /_static/images/en-us_image_0000002482912814.png
.. |image6| image:: /_static/images/en-us_image_0000002515112827.png
.. |image7| image:: /_static/images/en-us_image_0000002515112819.png
.. |image8| image:: /_static/images/en-us_image_0000002482912816.png
.. |image9| image:: /_static/images/en-us_image_0000002515112815.png

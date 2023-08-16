:original_name: aom_02_0008.html

.. _aom_02_0008:

Host Monitoring
===============

AOM monitors the resource usage and health status of hosts, common system devices such as disks and file systems of hosts, and service processes or instances running on hosts.

.. note::

   The ICAgent reports resource information every ten minutes. The resource status changes are described as follows:

   -  If the ICAgent on a host does not report resource information **for three consecutive times**, the system determines that the resource has been deleted. Therefore, the host status is displayed as **Deleted** within 30 minutes after the host is stopped or the ICAgent is uninstalled.
   -  When the ICAgent on a host reports resource information **for one time**, the system determines that the resource is restored. The host status is displayed as **Normal** ten minutes after the host is started or the ICAgent is reinstalled.

Precautions
-----------

-  A maximum of five tags can be added to a host, and each tag must be unique.
-  The same tag can be added to different hosts.
-  The host status can be **Normal**, **Abnormal**, **Warning**, **Silent**, or **Deleted**. The running status of a host is displayed as **Abnormal** when the host is faulty due to network failures, and power off or shut down of the host, or when the host generates a threshold alarm. For other statuses, see :ref:`What Can I Do If Resources Are Not Running Properly? <aom_02_1012>`.

Procedure
---------

#. In the navigation pane, choose **Monitoring** > **Host Monitoring**.

   Click |image1| in the upper right corner and select whether to show hosts.

#. Perform the following operations as required:

   -  **Adding an alias**

      If a host name is too complex to identify, you can add an alias, which makes it easy to identify a host as required.

      Click **Add alias** in the **Operations** column of the target host. The added alias can be modified but cannot be deleted.

   -  **Adding a tag**

      Tags are identifiers of hosts. You can manage hosts using tags. After a tag is added, you can quickly identify and select a host.

      In the host list, locate the row that contains the target host, choose **More** > **Add tags** in the **Operation** column. Then, enter a tag, click |image2|, and click **OK**. The **Tags** column in the host list is hidden by default. You can click |image3| in the upper right corner and select or deselect **Tags** to show or hide them.

#. Set filter criteria to search for the desired host.

   .. note::

      Hosts cannot be searched by alias.

#. Click the host name to enter the **Host Details** page. In the instance list, monitor the resource usage and health status of the instances running on the host. Click the **View Monitor Graphs** tab to monitor all the metrics of the host.

   -  **Creating a view template**

      AOM provides the default view template (**Host Template**) that you can modify. You can also click the plus sign (+) next to **View Template** to add you own template.

   -  **Adding a metric graph**

      You can click |image4| to add a line graph or |image5| to add a digit graph to the view template. You can also delete, move, and copy metric graphs in the view template according to :ref:`Dashboard <aom_02_0003>`.

   -  **Adding a view template to a dashboard**

      On the host details page, choose **More** > **Add To Dashboard** in the upper right corner to add the view template to a dashboard for monitoring.

#. Monitor common system devices such as GPUs and NICs of the host.

   -  Click the **Instance List** tab to view the basic information such as the instance status and type. Click an instance to view its metrics on the details page.
   -  Click the **GPUs** tab to view the basic information about the GPUs of the host. Click a GPU to monitor its metrics on the **View Monitor Graphs** page.
   -  Click the **NIC** tab to view the basic information about the NICs of the host. Click a NIC to monitor its metrics on the **View Monitor Graphs** page.
   -  Click the **Disks** tab to view the basic information about the disks of the host. Click a disk to monitor its metrics on the **View Monitor Graphs** page.
   -  Click the **File System** tab to view the basic information about the file system of the host. Click a disk file partition to monitor its metrics on the **View Monitor Graphs** page.
   -  Click the **Alarm Analysis** tab to view the alarm details.

.. |image1| image:: /_static/images/en-us_image_0000001448562829.png
.. |image2| image:: /_static/images/en-us_image_0000001448802817.png
.. |image3| image:: /_static/images/en-us_image_0000001398402892.png
.. |image4| image:: /_static/images/en-us_image_0000001448483009.png
.. |image5| image:: /_static/images/en-us_image_0000001398083204.png

:original_name: aom_02_0050.html

.. _aom_02_0050:

Application Monitoring
======================

An application is a group of identical or similar components divided based on business requirements. Applications are classified into system applications and custom applications. System applications are discovered based on built-in discovery rules, and custom applications are discovered based on custom rules.

.. note::

   The ICAgent reports resource information every ten minutes. The resource status changes are described as follows:

   -  If the ICAgent on a host does not report resource information **for three consecutive times**, the system determines that the resource has been deleted. Therefore, the host status is displayed as **Deleted** within 30 minutes after the ICAgent is uninstalled or the resource is deleted.
   -  When the ICAgent on a host reports resource information **for one time**, the system determines that the resource exists. The host status is displayed as **Normal** ten minutes after the resource is created or the ICAgent is installed.

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane, choose **Infrastructure Monitoring** > **Application Monitoring**.

   -  The application list displays parameters such as the application name, deployment mode, application discovery rule, and number of components.
   -  To view target applications, set filter criteria (such as the deployment mode, running status, and application name) above the application list.
   -  In the upper right corner of the page, set application filter criteria.

      a. Set a time range to view the applications reported. There are two methods to set a time range:

         Method 1: Use a predefined time label, such as **Last 30 minutes** or **Last hour** in the upper right corner of the page. You can select a time range as required.

         Method 2: Specify the start time and end time (max. 15 days).

      b. Set the interval for refreshing information. Click |image1| and select a value from the drop-down list as required, such as **Refresh manually** or **1 minute auto refresh**.

      c. Click |image2| in the upper right corner and select or deselect **the columns to display**.

   -  Click **Create Application**. On the page that is displayed, configure an application discovery rule. Applications that meet the rule can be automatically discovered and related metrics can be monitored. For details, see :ref:`Configuring Application Discovery <aom_02_0023>`.

#. Set filter criteria to search for the desired application.
#. Click the application name. The **Application Details** page is displayed.

   -  On the **Application Details** page, view the running status, ID, and creation time of the application.
   -  In the upper right corner of the page, set a time range and refresh frequency.
   -  On the **Component List** tab page, view the name, status, and resource usage of components. You can click a component name to view its metrics on the **Component Details** page.
   -  Enter an instance name in the search box in the upper right corner and click |image3| to search.
   -  Click |image4| to refresh the component list.
   -  On the **Host List** tab page, view the name, IP address, status, and resource usage of hosts. You can click a host name to view its metrics on the **Host Details** page.
   -  On the **Monitoring View** tab page, view key metrics of the target application, such as the CPU usage.
   -  On the **Alarms** tab page, view the alarm details of the application. For details, see :ref:`Viewing Alarms <mon_01_0011>`.

.. |image1| image:: /_static/images/en-us_image_0000002482793054.png
.. |image2| image:: /_static/images/en-us_image_0000002482913020.png
.. |image3| image:: /_static/images/en-us_image_0000002515113025.png
.. |image4| image:: /_static/images/en-us_image_0000002515113029.png

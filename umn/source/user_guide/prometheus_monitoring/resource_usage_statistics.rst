:original_name: mon_01_0125.html

.. _mon_01_0125:

Resource Usage Statistics
=========================

After metric data is reported to AOM through Prometheus monitoring, you can view the number of reported basic and custom metric samples on the **Resource Usage** page.

Prerequisites
-------------

-  Your service has been connected for Prometheus monitoring. For more details, see:

   -  :ref:`Prometheus Instance for CCE <mon_01_0073>`
   -  :ref:`Prometheus Instance for Remote Write <mon_01_0070>`

Precautions
-----------

-  The **Resource Usage** page does not display the number of basic and custom metric samples reported by Prometheus instances for cloud services.
-  Metric samples are reported every hour. If you specify a time range shorter than one hour, the query result of total metric samples may be 0.
-  The number of metric samples displayed on the **Resource Usage** page may be different from the actual number.

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane, choose **Prometheus Monitoring** > **Resource Usage**.

#. In the upper left corner of the page, select a desired Prometheus instance.

#. In the upper right corner of the page, set filter criteria.

   a. Set a time range in either of the following ways:

      Method 1: Use a predefined time label, such as **Last hour** or **Last 6 hours**. You can select a time range as required.

      Method 2: Specify the start time and end time to customize a time range. You can specify 30 days at most.

   b. Set the interval for refreshing information. Click |image1| and select a value from the drop-down list, such as **Refresh manually** or **1 minute auto refresh**.

#. View the number of current metric samples of the Prometheus instance.


   .. figure:: /_static/images/en-us_image_0000002515112865.png
      :alt: **Figure 1** Number of current metric samples

      **Figure 1** Number of current metric samples

   Metric report rates:

   -  Small specifications (500 vCPUs): 50,000 metric samples per minute
   -  Middle specifications (1,000 vCPUs): 100,000 metric samples per minute
   -  Large specifications (3,000 vCPUs): 300,000 metric samples per minute

#. View the number of basic metrics and that of custom metrics reported by the Prometheus instance.

   -  **Custom Metric Samples**: include the number of custom metric samples reported within 24 hours and that reported within a specified time range.
   -  **Basic Metric Samples**: include the number of basic metric samples reported within 24 hours and that reported within a specified time range.
   -  **Custom Metrics**: indicates the number of custom metric types reported within a specified time range.
   -  **Basic Metrics**: indicates the number of basic metric types reported within a specified time range.
   -  **Top 10 Custom Metric Samples**: displays the top 10 custom metric samples within a specified time range.

#. In the **Instance Info** area, view **Total Custom Metric Samples (Million)**, **Total Basic Metric Samples (Million)**, **Custom Metric Samples in 24 Hours (Million)**, **Basic Metric Samples in 24 Hours (Million)**, **Custom Metrics**, and **Basic Metrics**.

.. |image1| image:: /_static/images/en-us_image_0000002482792882.png

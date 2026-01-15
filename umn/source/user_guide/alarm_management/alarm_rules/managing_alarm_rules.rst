:original_name: mon_01_0050.html

.. _mon_01_0050:

Managing Alarm Rules
====================

After an alarm rule is created, you can view the rule name, type, status, and monitored object of the alarm rule in the rule list. You can also modify, enable, or disable the alarm rule as required.

Procedure
---------

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. On the **Alarm Rules** tab page, view all created alarm rules and perform the following operations as required. For details, see :ref:`Table 1 <mon_01_0050__en-us_topic_0000001322170841_en-us_topic_0169698491_table289773015816>`.


   .. figure:: /_static/images/en-us_image_0000002289582377.png
      :alt: **Figure 1** Viewing alarm rules

      **Figure 1** Viewing alarm rules

   .. _mon_01_0050__en-us_topic_0000001322170841_en-us_topic_0169698491_table289773015816:

   .. table:: **Table 1** Operations related to alarm rules

      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation                            | Description                                                                                                                                                                             |
      +======================================+=========================================================================================================================================================================================+
      | Filtering and displaying alarm rules | In the rule list, filter alarm rules by rule name, type, status, or other criteria.                                                                                                     |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Refreshing alarm rules               | Click |image1| in the upper right corner of the rule list to obtain the latest information about all alarm rules.                                                                       |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Customizing columns to display       | Click |image2| in the upper right corner of the rule list and select or deselect the columns to display.                                                                                |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Modifying alarm rules                | Click |image3| in the **Operation** column. For details, see :ref:`Creating a Metric Alarm Rule <mon_01_0008>` and :ref:`Creating an Event Alarm Rule <mon_01_0010>`.                   |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Deleting alarm rules                 | -  To delete an alarm rule, click |image4| in the **Operation** column.                                                                                                                 |
      |                                      | -  To delete one or more alarm rules, select them, click **Batch Operation** above the rule list, and select **Delete** from the drop-down list.                                        |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Enabling or disabling alarm rules    | -  Enable or disable an alarm rule in the **Status** column.                                                                                                                            |
      |                                      | -  To enable or disable one or more alarm rules, select them, click **Batch Operation** above the rule list, and select **Enable** or **Disable** from the drop-down list.              |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Searching for alarm rules            | You can search for alarm rules by rule names. Enter a keyword in the search box in the upper right corner and click |image5| to search.                                                 |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing detailed alarm information   | Click |image6| before a rule name to view rule details, including the basic information and alarm conditions. You can also view the monitored objects and the list of triggered alarms. |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing alarms                       | When the metric value of a resource meets threshold conditions during the configured consecutive periods, the system reports a threshold alarm.                                         |
      |                                      |                                                                                                                                                                                         |
      |                                      | In the navigation pane, choose **Alarm Management** > **Alarm List**. On the **Alarms** tab page, view alarms. For details, see :ref:`Viewing Alarms <mon_01_0011>`.                    |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing events                       | When no metric data of a resource is reported during the configured consecutive periods, the system reports an insufficient data event.                                                 |
      |                                      |                                                                                                                                                                                         |
      |                                      | In the navigation pane, choose **Alarm Management** > **Alarm List**. On the **Events** tab page, view events. For details, see :ref:`Viewing Events <mon_01_0012>`.                    |
      +--------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002254812096.png
.. |image2| image:: /_static/images/en-us_image_0000002289582389.png
.. |image3| image:: /_static/images/en-us_image_0000002254869052.png
.. |image4| image:: /_static/images/en-us_image_0000002254812092.png
.. |image5| image:: /_static/images/en-us_image_0000002289469301.png
.. |image6| image:: /_static/images/en-us_image_0000002289582361.png

:original_name: aom_02_0010.html

.. _aom_02_0010:

Viewing Log Files
=================

You can quickly view log files of component instances or hosts to locate faults.


Viewing Log Files
-----------------

#. In the navigation pane, choose **Log Analysis** > **Log Files**.

#. On the page that is displayed, click the **Component** or **Host** tab and click a name. Information such as the log file name and latest written time is displayed on the right of the page.

#. Click **View** in the **Operation** column of the desired instance. :ref:`Table 1 <aom_02_0010__table186411152115819>` shows how to view log file details.

   .. _aom_02_0010__table186411152115819:

   .. table:: **Table 1** Operations

      +-----------------------+------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Operation             | Setup                  | Description                                                                                                                                                                                                                                                                          |
      +=======================+========================+======================================================================================================================================================================================================================================================================================+
      | Setting a time range  | Date                   | Click |image1| to select the date and time.                                                                                                                                                                                                                                          |
      +-----------------------+------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Viewing log files     | Clear                  | Click **Clear** to clear the logs displayed on the screen. This operation clears only the logs displayed on the screen but does not delete them.                                                                                                                                     |
      +-----------------------+------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      |                       | Viewing real-time logs | The function of real-time monitoring is disabled by default. To enable it, click **Enable Real-Time Viewing**. After this function is enabled, the latest written logs can be viewed.                                                                                                |
      |                       |                        |                                                                                                                                                                                                                                                                                      |
      |                       |                        | For real-time log viewing, AOM automatically highlights exception keywords in logs, facilitating fault locating. Such keywords are case-sensitive. For example, when you enter **format** to search, **format** in logs will be highlighted, but **Format** and **FORMAT** will not. |
      +-----------------------+------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. (Optional) Click **Configure Dumps** in the **Operation** column of the target instance to dump its logs to the same log file in the OBS bucket at a time. For details, see :ref:`Adding One-Off Dumps <aom_02_0080__en-us_topic_0169698290_section1130151415546>`.

.. |image1| image:: /_static/images/en-us_image_0000002254868904.png

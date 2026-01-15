:original_name: mon_01_0016.html

.. _mon_01_0016:

Creating a Message Template
===========================

You can create message templates to customize notifications. When a preset notification rule is triggered, notifications can be sent to specified personnel by email or SMS. If no message template is created, the default message template will be used.

Functions
---------

-  Message templates for email and SMS are supported.
-  Message templates can be customized. For details, see :ref:`2.c <mon_01_0016__en-us_topic_0000001258590589_li153081748171720>`.

Precautions
-----------

-  You can create up to 100 message templates. If the number of templates exceeds the upper limit, delete unnecessary templates and create new ones.
-  By default, one message template is preset and cannot be deleted or edited. If there is no custom message template, notifications are sent based on a preset message template by default.


Creating a Message Template
---------------------------

#. In the navigation pane, choose **Alarm Management** > **Alarm Action Rules**.

#. On the **Message Templates** tab page, click **Create**.


   .. figure:: /_static/images/en-us_image_0000002289582409.png
      :alt: **Figure 1** Creating a message template

      **Figure 1** Creating a message template

   a. Enter the template name, and description.

   b. Select a language (for example, English).

   c. .. _mon_01_0016__en-us_topic_0000001258590589_li153081748171720:

      Customize the template content (default fields are automatically filled in when a message template is created). There are templates for email, and SMS. For details, see :ref:`Table 1 <mon_01_0016__en-us_topic_0000001258590589_table630854861713>`.

      .. note::

         -  In addition to the message fields in the default template, the message template also supports custom fields. You need to specify the fields when reporting event alarms. For details, see the alarm reporting structs in the following message template.
         -  Custom fields support the JSONPath format. Example: **$event.metadata.case1** or **$event.metadata.case[0]**.
         -  In the upper right corner of the **Body** area, click **Add Variables** to add required variables.
         -  If you select **Emails**, you can click **Preview** to view the final effect. On the **Preview** page, change the message topic if necessary.

      .. _mon_01_0016__en-us_topic_0000001258590589_table630854861713:

      .. table:: **Table 1** Variables in the default message template

         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Variable            | Description                                                                               | Definition                 |
         +=====================+===========================================================================================+============================+
         | Account             | Account used to log in to the management console.                                         | ${domain_name}             |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Notification Type   | Type selected when an alarm rule is created, which can be **Alarm** or **Event**.         | ${event_type}              |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Severity            | Alarm or event severity, which can be **Critical**, **Major**, **Minor**, or **Warning**. | ${event_severity}          |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Name                | Name of the alarm rule that is triggered.                                                 | ${event_name}              |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Occurred            | Time when the alarm or event is triggered.                                                | ${starts_at}               |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Source              | Name of the service that triggers the alarm or event.                                     | ${resource_provider}       |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Resource Type       | Type of the resource selected when you customize an alarm rule or define alarm reporting. | ${resource_type}           |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Resource Identifier | Resource that triggers the alarm or event.                                                | ${resources}               |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Custom tag          | Extended tag.                                                                             | $event.metadata.key1       |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Possible Cause      | Cause of the alarm. For non-custom reporting, "NA" is displayed.                          | ${alarm_probableCause_zh}  |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Additional Info     | Additional alarm description, such as the metric name and alarm rule status change.       | ${message}                 |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Suggestion          | Suggestion on how to handle the alarm. For non-custom reporting, "NA" is displayed.       | ${alarm_fix_suggestion_zh} |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+
         | Custom annotation   | Extended annotation.                                                                      | $event.annotations.key2    |
         +---------------------+-------------------------------------------------------------------------------------------+----------------------------+

      Alarm reporting structs corresponding to the message template

      .. code-block::

         {
             "events": [{
                 "starts_at": 1579420868000,       //${starts_at}
                         "ends_at": 1579420868000,
                 "timeout": 60000,
                 "resource_group_id": "5680587ab6*******755c543c1f",
                 "metadata": {
                     "event_name": "test",         //${metadata.event_name}
                     "event_severity": "Major",    //${metadata.event_severity}
                     "event_type": "alarm",        //${metadata.event_type}
                     "resource_provider": "ecs",   //${metadata.resource_provider}
                     "resource_type": "vm",        //${metadata.resource_type}
                     "resource_id": "ecs123",
                     "key1": "Custom field"          //$event.metadata.key1
                 },
                 "annotations": {
                     "alarm_probableCause_zh_cn": "possible cause",     //${annotations.alarm_probableCause_zh}
                     "alarm_fix_suggestion_zh_cn": "fix suggestion",    //${annotations.alarm_fix_suggestion_zh}
                     "key2": "Custom field"    //$event.annotations.key2
                 }
             }]
         }

   d. Click **Confirm**. The message template is created.

More Operations
---------------

After creating a message template, you can perform the operations listed in :ref:`Table 2 <mon_01_0016__en-us_topic_0000001258590589_en-us_topic_0169698264_table14918185010104>`.

.. _mon_01_0016__en-us_topic_0000001258590589_en-us_topic_0169698264_table14918185010104:

.. table:: **Table 2** Related operations

   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                                                                               |
   +===================================+===========================================================================================================================================================================+
   | Editing a message template        | Click **Edit** in the **Operation** column.                                                                                                                               |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Copying a message template        | Click **Copy** in the **Operation** column.                                                                                                                               |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting a message template       | -  To delete a single message template, click **Delete** in the **Operation** column in the row that contains the template, and then click **Yes** on the displayed page. |
   |                                   | -  To delete one or more message templates, select them, click **Delete** above the template list, and then click **Yes** on the displayed page.                          |
   |                                   |                                                                                                                                                                           |
   |                                   |    .. note::                                                                                                                                                              |
   |                                   |                                                                                                                                                                           |
   |                                   |       Before deleting a message template, you need to delete the alarm action rules bound to it.                                                                          |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for a message template  | Enter a template name in the search box in the upper right corner and click |image1|.                                                                                     |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002289582421.png

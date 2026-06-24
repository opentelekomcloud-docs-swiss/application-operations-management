:original_name: mon_01_0016.html

.. _mon_01_0016:

Creating a Message Template
===========================

In AOM, you can create message templates to customize notifications. When a preset notification rule is triggered, notifications can be sent to specified personnel by email, SMS, HTTP, or HTTPS. If no message template is created, the default message template will be used.

Functions
---------

-  Message templates for emails, SMS, HTTP, and HTTPS are supported.
-  Message templates can be customized. For details, see :ref:`3.c <mon_01_0016__en-us_topic_0000001258590589_li153081748171720>`.

Precautions
-----------

-  You can create a maximum of 100 message templates. If the number of message templates reaches 100, delete unnecessary ones.
-  By default, one message template is preset and cannot be deleted or edited. If there is no custom message template, notifications are sent based on a preset message template by default.


Creating a Message Template
---------------------------

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane, choose **Alarm Management** > **Alarm Action Rules**.
#. On the **Message Templates** tab page, click **Create**.

   a. Enter a template name and description.

      .. table:: **Table 1** Parameter description

         +---------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter     | Description                                                                                                                                                                      |
         +===============+==================================================================================================================================================================================+
         | Template Name | Name of a message template. Enter up to 100 characters and do not start or end with an underscore (_) or hyphen (-). Only digits, letters, underscores, and hyphens are allowed. |
         +---------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Description   | Description of the template. Enter up to 1024 characters.                                                                                                                        |
         +---------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   b. Select a language. Currently, only English is supported.

   c. .. _mon_01_0016__en-us_topic_0000001258590589_li153081748171720:

      Customize the template content (default fields are automatically filled in when a message template is created). There are templates for emails and SMS. For details, see :ref:`Table 2 <mon_01_0016__en-us_topic_0000001258590589_table12639440194518>`.

      .. note::

         -  In addition to the message fields in the default template, the message template also supports custom fields. You need to specify the fields when reporting event alarms. For details, see the alarm reporting structs in the following message template.
         -  Custom fields support the JSONPath format. Example: **$event.metadata.case1** or **$event.metadata.case[0]**.
         -  In the upper right corner of the **Body** area, click **Add Variables** to add required variables.
         -  If you select **Emails**, you can click **Preview** to view the final effect. On the **Preview** page, change the message topic if necessary.

      .. _mon_01_0016__en-us_topic_0000001258590589_table12639440194518:

      .. table:: **Table 2** Variables in the default message template

         +---------------------+----------------------------------------------------------------------------------------+----------------------------+
         | Variable            | Description                                                                            | Definition                 |
         +=====================+========================================================================================+============================+
         | Alarm Name          | Name of the alarm rule that is triggered.                                              | ${event_name}              |
         +---------------------+----------------------------------------------------------------------------------------+----------------------------+
         | Alarm ID            | ID of the alarm rule that is triggered.                                                | ${id}                      |
         +---------------------+----------------------------------------------------------------------------------------+----------------------------+
         | Action Rule         | Name of the alarm action rule that triggers notification.                              | ${action_rule}             |
         +---------------------+----------------------------------------------------------------------------------------+----------------------------+
         | Occurred            | Time when the alarm or event is triggered.                                             | ${starts_at}               |
         +---------------------+----------------------------------------------------------------------------------------+----------------------------+
         | Event Severity      | Alarm or event severity. Options: **Critical**, **Major**, **Minor**, and **Warning**. | ${event_severity}          |
         +---------------------+----------------------------------------------------------------------------------------+----------------------------+
         | Alarm Info          | Detailed alarm information.                                                            | ${alarm_info}              |
         +---------------------+----------------------------------------------------------------------------------------+----------------------------+
         | Resource Identifier | Resource for which the alarm or event is triggered.                                    | ${resources}               |
         +---------------------+----------------------------------------------------------------------------------------+----------------------------+
         | Suggestion          | Suggestion about handing the alarm. For non-custom reporting, "NA" is displayed.       | ${alarm_fix_suggestion_zh} |
         +---------------------+----------------------------------------------------------------------------------------+----------------------------+

   d. Click **Confirm**. The message template is created.

More Operations
---------------

After creating a message template, you can perform the operations listed in :ref:`Table 3 <mon_01_0016__en-us_topic_0000001258590589_en-us_topic_0169698264_table14918185010104>`.

.. _mon_01_0016__en-us_topic_0000001258590589_en-us_topic_0169698264_table14918185010104:

.. table:: **Table 3** Related operations

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
   |                                   |       Before deleting a message template, delete the alarm action rules bound to it.                                                                                      |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for a message template  | Enter a template name in the search box in the upper right corner and click |image1|.                                                                                     |
   +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002482792876.png

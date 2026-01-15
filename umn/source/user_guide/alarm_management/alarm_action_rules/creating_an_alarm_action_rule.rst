:original_name: mon_01_0015.html

.. _mon_01_0015:

Creating an Alarm Action Rule
=============================

You can create an alarm action rule and associate it with an SMN topic and a message template. When the resource or metric data meets the alarm condition, the system sends an alarm notification based on the associated SMN topic and message template.

Prerequisites
-------------

-  A topic has been created.
-  A topic policy has been set.
-  **APM** has been selected for **Services that can publish messages to this topic**. If **APM** is not selected, notifications cannot be sent.
-  A subscriber, that is, an email or SMS message recipient has been added for the topic.

Precautions
-----------

You can create a maximum of 1000 alarm action rules. If this number has been reached, delete unnecessary rules.

Procedure
---------

#. In the navigation pane, choose **Alarm Management** > **Alarm Action Rules**.

#. On the **Action Rules** tab page, click **Create**.

#. Set parameters such as **Rule Name** and **Action Type** by referring to :ref:`Table 1 <mon_01_0015__en-us_topic_0000001213870678_table133819502309>`.

   .. _mon_01_0015__en-us_topic_0000001213870678_table133819502309:

   .. table:: **Table 1** Parameters of an alarm action rule

      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                   |
      +===================================+===============================================================================================================================================================================+
      | Rule Name                         | Name of an action rule. Enter up to 100 characters and do not start or end with an underscore (_). Only digits, letters, and underscores are allowed.                         |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description                       | Description of the action rule. Enter up to 1024 characters.                                                                                                                  |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Action Type                       | Type of action that is associated with the SMN topic and message template. Select your desired action from the drop-down list. Currently, only **Notification** is supported. |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Topic                             | SMN topic. Select your desired topic from the drop-down list.                                                                                                                 |
      |                                   |                                                                                                                                                                               |
      |                                   | If there is no topic you want to select, create one on the SMN console.                                                                                                       |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Message Template                  | Notification message template. Select your desired template from the drop-down list.                                                                                          |
      |                                   |                                                                                                                                                                               |
      |                                   | If there is no message template you want to select, create one by referring to :ref:`Creating a Message Template <mon_01_0016>`.                                              |
      +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

4. Click **OK**.

More Operations
---------------

After an alarm action rule is created, you can perform operations described in :ref:`Table 2 <mon_01_0015__en-us_topic_0000001213870678_en-us_topic_0169698264_table14918185010104>`.

.. _mon_01_0015__en-us_topic_0000001213870678_en-us_topic_0169698264_table14918185010104:

.. table:: **Table 2** Related operations

   +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                          | Description                                                                                                                                               |
   +====================================+===========================================================================================================================================================+
   | Modifying an alarm action rule     | Click **Modify** in the **Operation** column.                                                                                                             |
   +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting an alarm action rule      | -  To delete a single rule, click **Delete** in the **Operation** column in the row that contains the rule, and then click **Yes** on the displayed page. |
   |                                    | -  To delete one or more rules, select them, click **Delete** above the rule list, and then click **Yes** on the displayed page.                          |
   |                                    |                                                                                                                                                           |
   |                                    |    .. note::                                                                                                                                              |
   |                                    |                                                                                                                                                           |
   |                                    |       Before deleting an alarm action rule, you need to delete the alarm rule bound to the action rule.                                                   |
   +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for an alarm action rule | Enter a rule name in the search box in the upper right corner and click |image1|.                                                                         |
   +------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002289582401.png

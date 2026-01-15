:original_name: mon_01_0010.html

.. _mon_01_0010:

Creating an Event Alarm Rule
============================

You can set event conditions for services by setting event alarm rules. When the resource data meets an event condition, an event alarm is generated.

Precautions
-----------

If you want to receive email or SMS notifications when the resource data meets the event condition, set an alarm action rule by referring to :ref:`Creating an Alarm Action Rule <mon_01_0015>`.

Procedure
---------

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. On the **Alarm Rules** tab page, click **Create Alarm Rule**.

#. Set basic information about the alarm rule by referring to :ref:`Table 1 <mon_01_0010__en-us_topic_0000001213710704_en-us_topic_0000001258590587_table1249723616548>`.

   .. _mon_01_0010__en-us_topic_0000001213710704_en-us_topic_0000001258590587_table1249723616548:

   .. table:: **Table 1** Basic information

      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Description                                                                                                             |
      +=============+=========================================================================================================================+
      | Rule Name   | Name of a rule. Enter a maximum of 255 characters. The following special characters are not allowed: "$# ``%&'+;<=>?\`` |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Description | Description of the rule. Enter up to 1,000 characters.                                                                  |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+

#. Set the detailed information about the alarm rule.

   a. Set **Rule Type** to **Event alarm rule**.

   b. Set **Event Source**, **Monitored Object**, and **Alarm Condition**.


      .. figure:: /_static/images/en-us_image_0000002254869116.png
         :alt: **Figure 1** Setting an alarm rule

         **Figure 1** Setting an alarm rule

      .. table:: **Table 2** Alarm rule parameters

         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                                                                                  |
         +===================================+==============================================================================================================================================================================================================================================+
         | Event Source                      | Name of the service for which an event alarm is reported. You can select a service from the service list.                                                                                                                                    |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Monitored Object                  | Select criteria to filter service events. You can select **Notification Type**, **Event Name**, **Alarm Severity**, **Custom Attributes**, **Namespace**, or **Cluster Name** as the filter criterion. One or more criteria can be selected. |
         |                                   |                                                                                                                                                                                                                                              |
         |                                   | .. note::                                                                                                                                                                                                                                    |
         |                                   |                                                                                                                                                                                                                                              |
         |                                   |    Set **Event Name** as the filter criterion. If no event name is selected, all events are selected by default.                                                                                                                             |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Alarm Condition                   | Condition for triggering event alarms. In case of multiple events, click **Batch Set** to set alarm conditions for these events in batches.                                                                                                  |
         |                                   |                                                                                                                                                                                                                                              |
         |                                   | -  **Accumulated Trigger**: When the trigger condition is met for a specified number of times in a monitoring period, the alarm action rule is triggered and an event alarm of the corresponding severity is sent.                           |
         |                                   | -  **Immediate Trigger**: An alarm is generated immediately when the trigger condition is met.                                                                                                                                               |
         +-----------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Set an alarm notification policy.

   -  **Direct alarm reporting**: An alarm is directly sent when the alarm condition is met.

      If the existing alarm action rules cannot meet your requirements, click **Create Rule** to create one. For details about how to set an alarm action rule, see :ref:`Creating an Alarm Action Rule <mon_01_0015>`. Click **View Rule** to go to the **Alarm Action Rules** page and view the created alarm action rule.


      .. figure:: /_static/images/en-us_image_0000002289469369.png
         :alt: **Figure 2** Selecting the direct alarm reporting mode

         **Figure 2** Selecting the direct alarm reporting mode

#. Click **Confirm**. Then, click **Back to Alarm Rule List** to view the created alarm rule.

   Click |image1| in front of the rule name to check its details.

   When CCE resources meet the configured event alarm conditions, an event alarm will be generated on the alarm page. To view the alarm, choose **Alarm Management** > **Alarm List** in the navigation pane. The system also sends alarm notifications to specified personnel by email or SMS.

.. |image1| image:: /_static/images/en-us_image_0000002254812156.png

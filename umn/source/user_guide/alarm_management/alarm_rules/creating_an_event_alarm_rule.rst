:original_name: mon_01_0010.html

.. _mon_01_0010:

Creating an Event Alarm Rule
============================

You can set event conditions for services by setting event alarm rules. When the resource data meets an event condition, an event alarm is generated.

Precautions
-----------

-  If you want to receive email or SMS notifications when the resource data meets the event condition, set an alarm action rule by referring to :ref:`Creating an Alarm Action Rule <mon_01_0015>`.
-  When setting an alarm notification policy, you need to enable the **Action Rule** option and select an alarm action rule.

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.

#. Click **Create Alarm Rule**.

#. Set basic information about the alarm rule by referring to :ref:`Table 1 <mon_01_0010__en-us_topic_0000001213710704_en-us_topic_0000001582534348_table1730711167518>`.

   .. _mon_01_0010__en-us_topic_0000001213710704_en-us_topic_0000001582534348_table1730711167518:

   .. table:: **Table 1** Basic information

      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Parameter   | Description                                                                                                             |
      +=============+=========================================================================================================================+
      | Rule Name   | Name of a rule. Enter a maximum of 255 characters. The following special characters are not allowed: "$# ``%&'+;<=>?\`` |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+
      | Description | Description of the rule. Enter up to 1000 characters.                                                                   |
      +-------------+-------------------------------------------------------------------------------------------------------------------------+

#. Set the detailed information about the alarm rule.

   a. Set **Rule Type** to **Event alarm rule**.
   b. Specify an event type and source.

      -  If **Event Type** is set to **System**, **Event Source** can only be **CCE**.
      -  If **Event Type** to set to **Custom**, select an event source from the existing service list.

   c. Set alarm rule details.

      .. table:: **Table 2** Alarm rule parameters

         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                                                                                                                                                                                          |
         +===================================+======================================================================================================================================================================================================================================================================================================================================================+
         | Monitored Object                  | Select criteria to filter service events. You can select **Notification Type**, **Event Name**, **Alarm Severity**, **Custom Attributes**, **Namespace**, or **Cluster Name** as the filter criterion. One or more criteria can be selected.                                                                                                         |
         |                                   |                                                                                                                                                                                                                                                                                                                                                      |
         |                                   | .. note::                                                                                                                                                                                                                                                                                                                                            |
         |                                   |                                                                                                                                                                                                                                                                                                                                                      |
         |                                   |    Set **Event Name** as the filter criterion. If no event name is selected, all events are selected by default.                                                                                                                                                                                                                                     |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Alarm Condition                   | Condition for triggering event alarms. It contains:                                                                                                                                                                                                                                                                                                  |
         |                                   |                                                                                                                                                                                                                                                                                                                                                      |
         |                                   | -  **Event Name**: The value varies depending on **Monitored Object**. If you do not specify any event for **Monitored Object**, all events are displayed here and cannot be changed.                                                                                                                                                                |
         |                                   | -  **Trigger Mode**: trigger mode of an event alarm.                                                                                                                                                                                                                                                                                                 |
         |                                   |                                                                                                                                                                                                                                                                                                                                                      |
         |                                   |    -  **Accumulated Trigger**: When the trigger condition is met for a specified number of times in a monitoring period, alarm notifications are sent based on the preset interval.                                                                                                                                                                  |
         |                                   |                                                                                                                                                                                                                                                                                                                                                      |
         |                                   |       Assume that you set **Event Name** to **VolumeResizeFailed**, **Monitoring Period** to **20 minutes**, **Cumulative Times** to **>= 3**, and **Alarm Frequency** to **Every 5 minutes**. If data volume scale-out fails for 3 or more times within 20 minutes, an alarm notification will be sent every 5 minutes unless the alarm is cleared. |
         |                                   |                                                                                                                                                                                                                                                                                                                                                      |
         |                                   |    -  **Immediate Trigger**: An alarm is immediately generated when the trigger condition is met.                                                                                                                                                                                                                                                    |
         |                                   |                                                                                                                                                                                                                                                                                                                                                      |
         |                                   | -  **Alarm Severity**: includes **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                                                                                 |
         |                                   |                                                                                                                                                                                                                                                                                                                                                      |
         |                                   | In case of multiple events, click **Batch Set** to set alarm conditions for these events in batches.                                                                                                                                                                                                                                                 |
         +-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. .. _mon_01_0010__en-us_topic_0000001213710704_li15513123154817:

   Set an alarm notification policy.

   -  **Direct alarm reporting**: An alarm is directly sent when the alarm condition is met.

      For event alarm rules, the alarm action rule must be enabled. The system sends alarm notifications based on the associated SMN topic and message template. If the existing alarm action rules cannot meet your requirements, click **Create Rule** in the drop-down list to create one. For details about how to set an alarm action rule, see :ref:`Creating an Alarm Action Rule <mon_01_0015>`.

#. Click **Confirm**. Then click **Back to Alarm Rule List** to view the created alarm rule.

   When CCE resources meet the configured event alarm conditions, an event alarm will be generated on the alarm page. To view the alarm, choose **Alarm Management** > **Alarm List** in the navigation pane. The system also sends alarm notifications to specified personnel by email or SMS.

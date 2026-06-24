:original_name: mon_01_0075.html

.. _mon_01_0075:

Alarm Templates
===============

An alarm template is a group of alarm rules categorized based on cloud services. You can use an alarm template to create event alarm rules or PromQL alarm rules for CCE in batches.

Precautions
-----------

You can create up to 150 alarm templates. If the number of alarm templates reaches 150, delete unnecessary templates and create new ones.

Background
----------

AOM presets default alarm templates for key metrics (including CPU usage, physical memory usage, host status, and service status) of all hosts and services. They are displayed on the **Alarm Templates** > **Default** page. You can locate the desired default alarm template and click |image1| in the **Operation** column to quickly create a custom alarm template.

.. _mon_01_0075__en-us_topic_0000001632454281_en-us_topic_0169698339_section938319277517:

Creating an Alarm Template
--------------------------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane, choose **Alarm Management** > **Alarm Templates**.

#. Click **Create Alarm Template**.

#. Set the basic information about an alarm template. :ref:`Table 1 <mon_01_0075__en-us_topic_0000001632454281_table1730711167518>` describes the parameters.

   .. _mon_01_0075__en-us_topic_0000001632454281_table1730711167518:

   .. table:: **Table 1** Basic information

      +---------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter     | Description                                                                                                                                                                            |
      +===============+========================================================================================================================================================================================+
      | Template Name | Name of an alarm template. Enter a maximum of 100 characters and do not start or end with an underscore (_) or hyphen (-). Only letters, digits, underscores, and hyphens are allowed. |
      +---------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Description   | Description of the template. Enter up to 1,024 characters.                                                                                                                             |
      +---------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. Add a cloud service to be monitored and an alarm rule to the template.

   a. .. _mon_01_0075__en-us_topic_0000001632454281_li1919715411394:

      Select a desired cloud service from the drop-down list. Currently, alarm rules can only be added for CCE.

   b. Then add an alarm rule for the cloud service. For details, see :ref:`Table 2 <mon_01_0075__en-us_topic_0000001632454281_table24850919302>`.

      .. _mon_01_0075__en-us_topic_0000001632454281_table24850919302:

      .. table:: **Table 2** Parameters for adding an alarm rule for the cloud service

         +---------------+-------------------+--------------------------------------------------------------------------+
         | Cloud Service | Alarm Rule Type   | Method                                                                   |
         +===============+===================+==========================================================================+
         | CCEFromProm   | Event alarm rule  | See :ref:`6 <mon_01_0075__en-us_topic_0000001632454281_li181599587544>`. |
         +---------------+-------------------+--------------------------------------------------------------------------+
         |               | PromQL alarm rule | See :ref:`7 <mon_01_0075__en-us_topic_0000001632454281_li326644014814>`. |
         +---------------+-------------------+--------------------------------------------------------------------------+

#. .. _mon_01_0075__en-us_topic_0000001632454281_li181599587544:

   (Optional) Add an event alarm rule for the CCEFromProm service.

   a. Choose **Add Alarm Rule** > **Add Event Alarm Rule**.

   b. In the displayed dialog box, set the rule name and event rule details. For details, see :ref:`Table 3 <mon_01_0075__en-us_topic_0000001632454281_table2170155616162>`.

      -  You can click **Add Event** to add more events and set information such as the trigger mode and severity.
      -  In case of multiple events, click **Batch Set** to set alarm conditions for them in batches.
      -  Click |image2| next to the event details to copy them and then modify them as required.


      .. figure:: /_static/images/en-us_image_0000002514993011.png
         :alt: **Figure 1** Adding an event alarm rule

         **Figure 1** Adding an event alarm rule

      .. _mon_01_0075__en-us_topic_0000001632454281_table2170155616162:

      .. table:: **Table 3** Event rule parameters

         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter                         | Description                                                                                                                                                                                                                                                                                                                               |
         +===================================+===========================================================================================================================================================================================================================================================================================================================================+
         | Rule Name                         | Enter a maximum of 256 characters and do not start or end with an underscore (_) or hyphen (-). Only letters, digits, underscores, and hyphens are allowed.                                                                                                                                                                               |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Event Name                        | Select a value from the drop-down list. By default, all events are selected.                                                                                                                                                                                                                                                              |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Trigger Mode                      | Trigger mode of an event alarm.                                                                                                                                                                                                                                                                                                           |
         |                                   |                                                                                                                                                                                                                                                                                                                                           |
         |                                   | -  **Accumulated Trigger**: When the trigger condition is met for a specified number of times in a monitoring period, alarm notifications are sent based on the preset interval.                                                                                                                                                          |
         |                                   |                                                                                                                                                                                                                                                                                                                                           |
         |                                   |    Assume that you set **Event Name** to **VolumeResizeFailed**, **Monitoring Period** to **20 minutes**, **Cumulative Times** to **3**, and **Alarm Frequency** to **Every 5 minutes**. If data volume scale-out fails three times within 20 minutes, an alarm notification will be sent every five minutes unless the alarm is cleared. |
         |                                   |                                                                                                                                                                                                                                                                                                                                           |
         |                                   | -  **Immediate Trigger**: An alarm is immediately generated when the trigger condition is met.                                                                                                                                                                                                                                            |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Alarm Severity                    | Severity of an event alarm. Options: **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                                                                 |
         +-----------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   c. Click **OK**.

#. .. _mon_01_0075__en-us_topic_0000001632454281_li326644014814:

   (Optional) Add a PromQL alarm rule for the CCEFromProm service.

   a. Choose **Add Alarm Rule** > **Add PromQL Alarm Rule**.

   b. In the displayed dialog box, set the rule name, default rule, and alarm severity. For details, see :ref:`Table 4 <mon_01_0075__en-us_topic_0000001632454281_table74014583815>`.


      .. figure:: /_static/images/en-us_image_0000002482793040.png
         :alt: **Figure 2** Adding a PromQL alarm rule

         **Figure 2** Adding a PromQL alarm rule

      .. _mon_01_0075__en-us_topic_0000001632454281_table74014583815:

      .. table:: **Table 4** PromQL alarm rule parameters

         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Parameter             |                       | Description                                                                                                                                                                                                                                                                                                                  |
         +=======================+=======================+==============================================================================================================================================================================================================================================================================================================================+
         | Rule Name             |                       | Enter a maximum of 256 characters and do not start or end with an underscore (_) or hyphen (-). Only letters, digits, underscores, and hyphens are allowed.                                                                                                                                                                  |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Default Rule          |                       | Detection rule generated based on Prometheus statements. The system supports two input modes: **Custom** and **CCEFromProm**.                                                                                                                                                                                                |
         |                       |                       |                                                                                                                                                                                                                                                                                                                              |
         |                       |                       | -  **Custom**: If you have known the metric name and IP address and are familiar with Prometheus statements, select **Custom** from the drop-down list and manually enter a Prometheus statement.                                                                                                                            |
         |                       |                       | -  **CCEFromProm**: used when you do not know the metric information or are unfamiliar with Prometheus statements. Select **CCEFromProm** from the drop-down list and then select a desired template from the CCE templates. The system then automatically fills in the Prometheus statement based on the selected template. |
         |                       |                       |                                                                                                                                                                                                                                                                                                                              |
         |                       |                       | For details, see :ref:`Prometheus Statements <mon_01_0043>`.                                                                                                                                                                                                                                                                 |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Alarm Severity        |                       | Severity of a metric alarm. Options: **Critical**, **Major**, **Minor**, and **Warning**.                                                                                                                                                                                                                                    |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Dimensions            |                       | Metric monitoring dimension, which is automatically generated based on the Prometheus statement you set.                                                                                                                                                                                                                     |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Duration              |                       | A metric alarm will be triggered when the alarm condition is met for the specified duration. For example, if **Duration** is set to **2 minutes**, a metric alarm will be triggered when the alarm condition is met for two minutes.                                                                                         |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Advanced Settings     | Check Interval        | Interval at which metric query and analysis results are checked.                                                                                                                                                                                                                                                             |
         |                       |                       |                                                                                                                                                                                                                                                                                                                              |
         |                       |                       | -  *XX* **hours**: Check the query and analysis results every *XX* hours.                                                                                                                                                                                                                                                    |
         |                       |                       | -  *XX* **minutes**: Check the query and analysis results every *XX* minutes.                                                                                                                                                                                                                                                |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Alarm Tag             | Alarm identification attribute. It is in the format of "key:value".                                                                                                                                                                                                                                                          |
         |                       |                       |                                                                                                                                                                                                                                                                                                                              |
         |                       |                       | It is automatically generated based on the Prometheus statement you set. You can modify it as required. To add more alarm tags, click |image3|. For details, see :ref:`Alarm Tags and Annotations <mon_01_0044>`.                                                                                                            |
         |                       |                       |                                                                                                                                                                                                                                                                                                                              |
         |                       |                       | .. note::                                                                                                                                                                                                                                                                                                                    |
         |                       |                       |                                                                                                                                                                                                                                                                                                                              |
         |                       |                       |    If the tag policies related to AOM have already been set, add alarm tags based on these policies. If a tag does not comply with the policies, tag addition may fail. Contact your organization administrator to learn more about tag policies.                                                                            |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         |                       | Alarm Annotation      | Click |image4| to add an alarm annotation. Alarm non-identification attribute. It is used in alarm notification and message template scenarios. It is in the format of "key:value". For details, see :ref:`Alarm Tags and Annotations <mon_01_0044>`.                                                                        |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
         | Notification Content  |                       | Alarm notification content. It is automatically generated based on the Prometheus statement you set.                                                                                                                                                                                                                         |
         +-----------------------+-----------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

   c. Click **OK**.

#. Click **OK** to create the alarm template.

#. .. _mon_01_0075__en-us_topic_0000001632454281_li928520174411:

   (Optional) In the displayed **Bind Alarm Template with Prometheus Instance/Cluster** dialog box, set the cluster to be bound with the alarm template. For details about the parameters, see :ref:`Table 5 <mon_01_0075__en-us_topic_0000001632454281_table1587161191>`. After the setting is complete, click **OK**.

   .. _mon_01_0075__en-us_topic_0000001632454281_table1587161191:

   .. table:: **Table 5** Parameters for binding an alarm template

      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter                         | Description                                                                                                                                                                                                                                                                                                                     |
      +===================================+=================================================================================================================================================================================================================================================================================================================================+
      | Cluster                           | This parameter is optional. If the cloud services selected in :ref:`5.a <mon_01_0075__en-us_topic_0000001632454281_li1919715411394>` contain CCEFromProm, this parameter will be displayed.                                                                                                                                     |
      |                                   |                                                                                                                                                                                                                                                                                                                                 |
      |                                   | The drop-down list displays all CCE clusters of your account. Select your desired cluster.                                                                                                                                                                                                                                      |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Notify When                       | Set the scenario for sending alarm notifications.                                                                                                                                                                                                                                                                               |
      |                                   |                                                                                                                                                                                                                                                                                                                                 |
      |                                   | -  **Alarm triggered**: If the alarm trigger condition is met, the system sends an alarm notification to the specified personnel by email or SMS.                                                                                                                                                                               |
      |                                   | -  **Alarm cleared**: If the alarm clearance condition is met, the system sends an alarm notification to the specified personnel by email or SMS.                                                                                                                                                                               |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Alarm Mode                        | **Direct alarm reporting**: An alarm is directly sent when the alarm condition is met. If you select this mode, set an interval for notification and specify whether to enable an action rule.                                                                                                                                  |
      |                                   |                                                                                                                                                                                                                                                                                                                                 |
      |                                   | **Frequency**: interval for sending alarm notifications. Select a desired value from the drop-down list.                                                                                                                                                                                                                        |
      |                                   |                                                                                                                                                                                                                                                                                                                                 |
      |                                   | After an alarm action rule is enabled, the system sends notifications based on the associated SMN topic and message template. If the existing alarm action rules cannot meet your requirements, click **Create Rule** in the drop-down list to create one. For details, see :ref:`Creating an Alarm Action Rule <mon_01_0015>`. |
      +-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

#. View the created alarm template on the **Custom** tab page.

   If a resource or metric meets the alarm condition set in the alarm template, an alarm will be triggered. In the navigation pane, choose **Alarm Management** > **Alarm List** to view the alarm. The system also sends alarm notifications to specified personnel by email or SMS.

More Operations
---------------

After the alarm template is created, you can also perform the operations listed in :ref:`Table 6 <mon_01_0075__en-us_topic_0000001632454281_en-us_topic_0169698339_table15831736105910>`.

.. _mon_01_0075__en-us_topic_0000001632454281_en-us_topic_0169698339_table15831736105910:

.. table:: **Table 6** Related operations

   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Operation                                                       | Description                                                                                                                                                                                                                                                                                                                                           |
   +=================================================================+=======================================================================================================================================================================================================================================================================================================================================================+
   | Viewing an alarm template                                       | -  Viewing newly created alarm templates: On the **Custom** tab page, view the rule set name, number of rules, and associated cluster of the newly created templates in the template list.                                                                                                                                                            |
   |                                                                 | -  Viewing historical alarm templates: On the **Alarm Template (Retiring)** tab page, view the template name, and monitored object of historical alarm templates in the template list.                                                                                                                                                                |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Binding an alarm template with a Prometheus instance or cluster | Click |image5| in the **Operation** column. For details, see :ref:`9 <mon_01_0075__en-us_topic_0000001632454281_li928520174411>`.                                                                                                                                                                                                                     |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Modifying an alarm template                                     | Choose |image6| > **Edit** in the **Operation** column. For details, see :ref:`Creating an Alarm Template <mon_01_0075__en-us_topic_0000001632454281_en-us_topic_0169698339_section938319277517>`.                                                                                                                                                    |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Copying an alarm template                                       | Click |image7| in the **Operation** column.                                                                                                                                                                                                                                                                                                           |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Deleting an alarm template                                      | -  To delete an alarm template, choose |image8| > **Delete** in the **Operation** column.                                                                                                                                                                                                                                                             |
   |                                                                 | -  Deleting newly created alarm templates in batches: On the **Custom** tab page, select desired alarm templates and click **Delete** in the displayed dialog box.                                                                                                                                                                                    |
   |                                                                 | -  Deleting historical alarm templates in batches: On the **Alarm Template (Retiring)** tab page, select desired alarm templates and click **Delete** in the displayed dialog box.                                                                                                                                                                    |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Searching for an alarm template                                 | Enter a template name in the search box in the upper right corner and click |image9|.                                                                                                                                                                                                                                                                 |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Viewing alarm rules created using a template                    | In the navigation pane on the left, choose **Alarm Management** > **Alarm Rules**. Enter a template name keyword in the search box above the alarm rule list and click |image10|. If an alarm template has been bound with a Prometheus instance or cluster, you can also search for the alarm rule by the bound Prometheus instance or cluster name. |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Viewing alarms                                                  | If the metric value of a resource meets an alarm condition, an alarm will be generated.                                                                                                                                                                                                                                                               |
   |                                                                 |                                                                                                                                                                                                                                                                                                                                                       |
   |                                                                 | In the navigation pane, choose **Alarm Management** > **Alarm List**. On the **Alarms** tab page, view alarms. For details, see :ref:`Viewing Alarms <mon_01_0011>`.                                                                                                                                                                                  |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Viewing events                                                  | If no metric data is reported during the configured monitoring period, the system will report an insufficient data event.                                                                                                                                                                                                                             |
   |                                                                 |                                                                                                                                                                                                                                                                                                                                                       |
   |                                                                 | In the navigation pane, choose **Alarm Management** > **Alarm List**. On the **Events** tab page, view events. For details, see :ref:`Viewing Events <mon_01_0012>`.                                                                                                                                                                                  |
   +-----------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000002482913026.png
.. |image2| image:: /_static/images/en-us_image_0000002482913024.png
.. |image3| image:: /_static/images/en-us_image_0000002482793036.png
.. |image4| image:: /_static/images/en-us_image_0000002482793046.png
.. |image5| image:: /_static/images/en-us_image_0000002482793058.png
.. |image6| image:: /_static/images/en-us_image_0000002514993023.png
.. |image7| image:: /_static/images/en-us_image_0000002482913022.png
.. |image8| image:: /_static/images/en-us_image_0000002514993021.png
.. |image9| image:: /_static/images/en-us_image_0000002515113031.png
.. |image10| image:: /_static/images/en-us_image_0000002514993025.png

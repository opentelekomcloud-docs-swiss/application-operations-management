:original_name: mon_01_0044.html

.. _mon_01_0044:

Alarm Tags and Annotations
==========================

When creating alarm rules, you can set alarm tags and annotations. Tags are attributes that can be used to identify alarms. Annotations are attributes that cannot be used to identify alarms. They are applied to scenarios such as alarm notification and message templates.

Alarm Tag Description
---------------------

-  Each tag is in "key:value" format and can be customized. You can create up to 10 custom tags. The key and value can only contain letters, digits, and underscores (_).
-  If you set a tag when creating an alarm rule, the tag is automatically added as an alarm attribute when an alarm is triggered.
-  In a message template, the **$event.metadata.key1** variable specifies a tag. For details, see :ref:`Table 2 <mon_01_0016__en-us_topic_0000001258590589_table12639440194518>`.

.. note::

   If tag policies related to AOM have already been set, add alarm tags based on these policies. If a tag does not comply with the policies, tag addition may fail. Contact your organization administrator to learn more about tag policies.

Alarm Annotation Description
----------------------------

-  Annotations are attributes that cannot be used to identify alarms. They are applied to scenarios such as alarm notification and message templates.
-  Each annotation is in "key:value" format and can be customized. You can create up to 10 custom annotations. The key and value can only contain letters, digits, and underscores (_).
-  In a message template, the **$event.annotations.key2** variable specifies an annotation. For details, see :ref:`Table 2 <mon_01_0016__en-us_topic_0000001258590589_table12639440194518>`.

Managing Alarm Tags and Annotations
-----------------------------------

You can add, delete, modify, and query alarm tags or annotations on the alarm rule page.

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane, choose **Alarm Management** > **Alarm Rules**.
#. Click **Create Alarm Rule**, or locate a desired alarm rule and click |image1| in the **Operation** column.
#. On the displayed page, click **Advanced Settings**.
#. Under **Alarm Tag** or **Alarm Annotation**, click |image2| and enter a key and value.
#. Click **OK** to add an alarm tag or annotation.

   .. note::

      -  Adding multiple alarm tags or annotations: Click |image3| multiple times to add alarm tags or annotations (max.: 10).
      -  Modifying an alarm tag or annotation: Move the cursor to a desired alarm tag or annotation and click |image4| to modify them.
      -  Deleting an alarm tag or annotation: Move the cursor to a desired alarm tag or annotation and click |image5| to delete them.

.. |image1| image:: /_static/images/en-us_image_0000002514993093.png
.. |image2| image:: /_static/images/en-us_image_0000002482793124.png
.. |image3| image:: /_static/images/en-us_image_0000002482793126.png
.. |image4| image:: /_static/images/en-us_image_0000002482913096.png
.. |image5| image:: /_static/images/en-us_image_0000002515113099.png

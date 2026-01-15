:original_name: mon_01_0044.html

.. _mon_01_0044:

Alarm Tags and Annotations
==========================

When creating alarm rules, you can set alarm tags and annotations. Tags are attributes that can be used to identify alarms. Annotations are attributes that cannot be used to identify alarms. They are applied to scenarios such as alarm notification and message templates.

Alarm Tags
----------

-  Each tag is in "key:value" format and can be customized. You can create up to 10 custom tags. The key and value can contain only letters, digits, hyphens (-), underscores (_), and periods (.). They must start with a letter or digit.
-  If you set a tag when creating an alarm rule, the tag is automatically added as an alarm attribute when an alarm is triggered.
-  In the message template, the **$event.metadata.key1** variable specifies the tag. For details, see :ref:`Table 1 <mon_01_0016__en-us_topic_0000001258590589_table630854861713>`.

Alarm Annotations
-----------------

-  Annotations are attributes that cannot be used to identify alarms. They are applied to scenarios such as alarm notification and message templates.
-  Each annotation is in "key:value" format and can be customized. You can create up to 10 custom annotations. The key and value can contain only letters, digits, hyphens (-), underscores (_), and periods (.). They must start with a letter or digit.
-  In the message template, the **$event.annotations.key2** variable specifies the annotation. For details, see :ref:`Table 1 <mon_01_0016__en-us_topic_0000001258590589_table630854861713>`.

:original_name: mon_01_0007.html

.. _mon_01_0007:

Overview
========

AOM allows you to set alarm rules. With alarm rules, you can set event conditions for services, or set threshold conditions for resource metrics. An event alarm is generated when the resource data meets the event condition. If a metric value meets a threshold condition, a threshold alarm will be reported. If there is no metric data, an insufficient data event will be reported.

Alarm rules are classified into metric alarm rules and event alarm rules. Generally, metric alarm rules monitor the usage of resources (such as hosts and components) in the environment in real time. When there are too many resource usage alarms and alarm notifications are sent too frequently, you can use event alarm rules to simplify alarm notifications, quickly identify a type of resource usage problems of a service, and resolve the problems in a timely manner.

The total number of metric alarm rules and event alarm rules is 1000. If the number of alarm rules has reached the upper limit, delete unnecessary rules and create new ones.

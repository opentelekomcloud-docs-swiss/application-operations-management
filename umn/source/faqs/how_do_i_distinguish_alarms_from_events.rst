:original_name: aom_03_0005.html

.. _aom_03_0005:

How Do I Distinguish Alarms from Events?
========================================

Similarities Between Alarms and Events
--------------------------------------

Both alarms and events are the information reported to AOM when the status of AOM or an external service, such as Cloud Container Engine (CCE) changes.

Differences Between Alarms and Events
-------------------------------------

-  Alarms are reported when AOM or an external service, such as CCE is abnormal or may cause exceptions. Alarms must be handled. Otherwise, service exceptions may occur.
-  Events generally carry some important information. They are reported when AOM or an external service, such as CCE encounters some changes. Such changes do not necessarily cause service exceptions. Events do not need to be handled.

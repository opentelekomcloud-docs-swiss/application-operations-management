:original_name: aom_02_1010.html

.. _aom_02_1010:

Related Services
================

AOM supports services such as Simple Message Notification (SMN), Cloud Trace Service (CTS), and Cloud Container Engine (CCE). You can use them after subscription. For example, after you subscribe to SMN, threshold rule status changes of AOM can be sent to related personnel by email or Short Message Service (SMS) message.

SMN
---

SMN can push notifications based on your requirements, and end users can receive notifications by SMS message, email, or application. You can also integrate application functions through SMN to reduce system complexity.

AOM uses the message transmission mechanism provided by SMN. When it is inconvenient for you to query threshold rule status changes in time through AOM, SMN can send the changes to you by email or SMS message in a timely manner. In this way, you can obtain information such as resource running status in real time and take necessary measures to avoid service loss.

CTS
---

CTS records operations on cloud resources in your account. You can perform security analysis, track resource changes, conduct compliance audits, and locate faults based on operation records. To store operation records for a longer time, you can subscribe to Object Storage Service (OBS) and synchronize operation records to OBS in real time.

With CTS, you can record operations associated with AOM for later querying, auditing, and backtracking.

CCE
---

CCE provides high-performance and scalable container service, enabling you to build reliable container clusters based on cloud servers. It integrates network and storage capabilities, and is compatible with Kubernetes and Docker container ecosystems. CCE enables you to create and manage diverse container workloads easily. It also provides efficient O&M capabilities, such as self-healing of container faults, collection of monitoring logs, and auto scaling.

You can use AOM to monitor applications deployed on CCE.

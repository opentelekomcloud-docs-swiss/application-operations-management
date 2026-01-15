:original_name: aom_06_0013.html

.. _aom_06_0013:

Product Architecture
====================

AOM is a multi-dimensional O&M platform that focuses on resource data and associates log, metric, resource, alarm, and event data. It consists of the data collection and access layer, transmission and storage layer, and service computing layer.

Architecture Description
------------------------

-  **Data collection and access layer**

   -  Collecting data by using ICAgent

      You can install the ICAgent (a plug-in data collector) on a host and use it to report O&M data.

   -  Connecting data by using APIs

      You can connect service metrics to AOM as custom metrics through the open APIs or Exporter APIs provided by AOM.

-  **Transmission and storage layer**

   -  Data transmission: AOM Access is a proxy for receiving O&M data. After O&M data is received, such data will be placed in the Kafka queue. Kafka then transmits the data to the service computing layer in real time based on its high-throughput capability.
   -  Data storage: After being processed by the AOM backend, O&M data is written into a database. Cassandra stores sequential data, Redis is used for cache query, etcd stores AOM configuration data, and Elasticsearch stores resources, logs, alarms, and events.

-  **Service computing layer**

   AOM provides basic O&M services such as alarm management, log management, and resource monitoring (such as metric monitoring).

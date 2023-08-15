:original_name: AddMetricData.html

.. _AddMetricData:

Adding Monitoring Data
======================

Function
--------

This API is used to add one or more monitoring data records to a server.

URI
---

POST /v1/{project_id}/ams/report/metricdata

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+-------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                   |
   +============+===========+========+===============================================================================+
   | project_id | Yes       | String | Project ID obtained from IAM. Generally, a project ID contains 32 characters. |
   +------------+-----------+--------+-------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                              |
   +=================+=================+=================+==========================================+
   | X-Auth-Token    | Yes             | String          | User token obtained from IAM.            |
   +-----------------+-----------------+-----------------+------------------------------------------+
   | Content-Type    | Yes             | String          | Content type, which is application/json. |
   |                 |                 |                 |                                          |
   |                 |                 |                 | Enumeration values:                      |
   |                 |                 |                 |                                          |
   |                 |                 |                 | -  **application/json**                  |
   +-----------------+-----------------+-----------------+------------------------------------------+

.. table:: **Table 3** Request body parameters

   +-----------+-----------+--------------------------------------------------------------------------------+--------------------+
   | Parameter | Mandatory | Type                                                                           | Description        |
   +===========+===========+================================================================================+====================+
   | [items]   | Yes       | Array of :ref:`MetricDataItem <addmetricdata__request_metricdataitem>` objects | Metric parameters. |
   +-----------+-----------+--------------------------------------------------------------------------------+--------------------+

.. _addmetricdata__request_metricdataitem:

.. table:: **Table 4** MetricDataItem

   +-----------------+-----------------+------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                                                     | Description                                                                                                                                                                                                 |
   +=================+=================+==========================================================================================+=============================================================================================================================================================================================================+
   | collect_time    | Yes             | Long                                                                                     | Data collection time, which ranges from the last 24 hours to the next 0.5 hour. The following requirement must be met:                                                                                      |
   |                 |                 |                                                                                          |                                                                                                                                                                                                             |
   |                 |                 |                                                                                          | Current UTC time - Data collection time <= 24 hours, or Data collection time - Current UTC time <= 30 minutes                                                                                               |
   |                 |                 |                                                                                          |                                                                                                                                                                                                             |
   |                 |                 |                                                                                          | If the data reporting time is earlier than 08:00 of the current day, only the data generated after 08:00 of the current day is displayed on the metric monitoring page. Value range: UNIX timestamp, in ms. |
   +-----------------+-----------------+------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | metric          | Yes             | :ref:`RecieveMetricParam <addmetricdata__request_recievemetricparam>` object             | Metric details.                                                                                                                                                                                             |
   +-----------------+-----------------+------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | values          | Yes             | Array of :ref:`RecieveMetricValues <addmetricdata__request_recievemetricvalues>` objects | Metric value.                                                                                                                                                                                               |
   +-----------------+-----------------+------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _addmetricdata__request_recievemetricparam:

.. table:: **Table 5** RecieveMetricParam

   +------------+-----------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type                                                                 | Description                                                                                                                                                                                                                                                         |
   +============+===========+======================================================================+=====================================================================================================================================================================================================================================================================+
   | dimensions | Yes       | Array of :ref:`Dimension <addmetricdata__request_dimension>` objects | List of metric dimensions. A maximum of 50 dimensions are supported. Each dimension is in JSON format. The structure is as follows: dimension.name: 1-32 characters. dimension.value: 1-64 characters.                                                              |
   +------------+-----------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | namespace  | Yes       | String                                                               | Metric namespace.The namespace cannot contain any colon (:).It must be in the format of service.item. The value must contain 3 to 32 characters starting with a letter. Only letters, digits, and underscores (_) are allowed. In addition, service cannot be PAAS. |
   +------------+-----------+----------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _addmetricdata__request_dimension:

.. table:: **Table 6** Dimension

   ========= ========= ====== ================
   Parameter Mandatory Type   Description
   ========= ========= ====== ================
   name      Yes       String Dimension name.
   value     Yes       String Dimension value.
   ========= ========= ====== ================

.. _addmetricdata__request_recievemetricvalues:

.. table:: **Table 7** RecieveMetricValues

   +-----------------+-----------------+-----------------+------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                          |
   +=================+=================+=================+======================================================+
   | metric_name     | Yes             | String          | Metric name. Length: 1 to 255 characters.            |
   +-----------------+-----------------+-----------------+------------------------------------------------------+
   | type            | Yes             | String          | Data type. Value: int or float.                      |
   |                 |                 |                 |                                                      |
   |                 |                 |                 | Enumeration values:                                  |
   |                 |                 |                 |                                                      |
   |                 |                 |                 | -  **int**                                           |
   |                 |                 |                 |                                                      |
   |                 |                 |                 | -  **float**                                         |
   +-----------------+-----------------+-----------------+------------------------------------------------------+
   | unit            | No              | String          | Data unit. Length: up to 32 characters.              |
   +-----------------+-----------------+-----------------+------------------------------------------------------+
   | value           | Yes             | Double          | Metric value, which must be of a valid numeric type. |
   +-----------------+-----------------+-----------------+------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 8** Response body parameters

   ============ ====== =================
   Parameter    Type   Description
   ============ ====== =================
   errorCode    String Response code.
   errorMessage String Response message.
   ============ ====== =================

Example Requests
----------------

Add a monitoring data record to the server. (In the following example, set "collect_time" to the latest timestamp.)

.. code-block:: text

   POST https://{Endpoint}/v1/{project_id}/ams/report/metricdata

   [ {
     "metric" : {
       "namespace" : "NOPAAS.ESC",
       "dimensions" : [ {
         "name" : "instance_id",
         "value" : "instance-101"
       } ]
     },
     "values" : [ {
       "unit" : "percent",
       "metric_name" : "cpu_util",
       "type" : "int",
       "value" : 35
     } ],
     "collect_time" : 1467787152000
   } ]

Example Responses
-----------------

**Status code: 200**

The request is successful.

.. code-block::

   {
     "errorCode" : "SVCSTG_AMS_2000000",
     "errorMessage" : "success"
   }

Status Codes
------------

+-------------+-------------------------------------------------------------------------------------+
| Status Code | Description                                                                         |
+=============+=====================================================================================+
| 200         | The request is successful.                                                          |
+-------------+-------------------------------------------------------------------------------------+
| 400         | The request is invalid.                                                             |
+-------------+-------------------------------------------------------------------------------------+
| 401         | Invalid authentication information.                                                 |
+-------------+-------------------------------------------------------------------------------------+
| 403         | The server has received the request and understood it, but refuse to respond to it. |
+-------------+-------------------------------------------------------------------------------------+
| 500         | The server is able to receive the request, but the request is improper.             |
+-------------+-------------------------------------------------------------------------------------+
| 503         | The service is unavailable.                                                         |
+-------------+-------------------------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.

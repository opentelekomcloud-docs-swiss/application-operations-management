:original_name: DeleteAlarmThresholdRule.html

.. _DeleteAlarmThresholdRule:

Deleting a Threshold Rule
=========================

Function
--------

This API is used to delete a threshold rule.

URI
---

DELETE /v1/{project_id}/ams/alarms/{alarm_id}

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+-------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                   |
   +============+===========+========+===============================================================================+
   | project_id | Yes       | String | Project ID obtained from IAM. Generally, a project ID contains 32 characters. |
   +------------+-----------+--------+-------------------------------------------------------------------------------+
   | alarm_id   | Yes       | String | Threshold rule ID.                                                            |
   +------------+-----------+--------+-------------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 2** Request header parameters

   +-----------------+-----------------+-----------------+------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                              |
   +=================+=================+=================+==========================================+
   | X-Auth-Token    | Yes             | String          | Project-level token obtained from IAM.   |
   +-----------------+-----------------+-----------------+------------------------------------------+
   | Content-Type    | Yes             | String          | Content type, which is application/json. |
   |                 |                 |                 |                                          |
   |                 |                 |                 | Enumeration values:                      |
   |                 |                 |                 |                                          |
   |                 |                 |                 | -  **application/json**                  |
   +-----------------+-----------------+-----------------+------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 3** Response body parameters

   ============ ====== =================
   Parameter    Type   Description
   ============ ====== =================
   errorCode    String Response code.
   errorMessage String Response message.
   ============ ====== =================

Example Requests
----------------

Delete a threshold rule.

.. code-block:: text

   DELETE https://{Endpoint}/v1/{project_id}/ams/alarms/{alarm_id}

Example Responses
-----------------

**Status code: 200**

OK

The request is successful.

.. code-block::

   {
     "errorCode" : "SVCSTG_AMS_2000000",
     "errorMessage" : "Delete Threshold [aaaaaaaa] successfully"
   }

Status Codes
------------

+-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Status Code                       | Description                                                                                                                                                                                       |
+===================================+===================================================================================================================================================================================================+
| 200                               | OK                                                                                                                                                                                                |
|                                   |                                                                                                                                                                                                   |
|                                   | The request is successful.                                                                                                                                                                        |
+-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 400                               | Bad Request                                                                                                                                                                                       |
|                                   |                                                                                                                                                                                                   |
|                                   | Invalid request. The client should not repeat the request without modifications.                                                                                                                  |
+-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401                               | Unauthorized                                                                                                                                                                                      |
|                                   |                                                                                                                                                                                                   |
|                                   | The authorization information is incorrect or invalid.                                                                                                                                            |
+-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 403                               | ForbiddenThe request is rejected. The server has received the request and understood it, but the server refuses to respond to it. The client should not repeat the request without modifications. |
+-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 500                               | Internal Server Error                                                                                                                                                                             |
|                                   |                                                                                                                                                                                                   |
|                                   | The server is able to receive the request but unable to understand the request.                                                                                                                   |
+-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 503                               | Service Unavailable                                                                                                                                                                               |
|                                   |                                                                                                                                                                                                   |
|                                   | The requested service is invalid. The client should not repeat the request without modifications.                                                                                                 |
+-----------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.

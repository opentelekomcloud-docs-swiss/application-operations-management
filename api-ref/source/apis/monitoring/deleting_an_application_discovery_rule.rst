:original_name: DeleteServiceDiscoveryRules.html

.. _DeleteServiceDiscoveryRules:

Deleting an Application Discovery Rule
======================================

Function
--------

This API is used to delete an application discovery rule.

URI
---

DELETE /v1/{project_id}/inv/servicediscoveryrules

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+-------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                   |
   +============+===========+========+===============================================================================+
   | project_id | Yes       | String | Project ID obtained from IAM. Generally, a project ID contains 32 characters. |
   +------------+-----------+--------+-------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-------------+-----------+-------+------------------------------------------------------------+
   | Parameter   | Mandatory | Type  | Description                                                |
   +=============+===========+=======+============================================================+
   | appRulesIds | Yes       | Array | Discovery rule ID. IDs need to be separated by commas (,). |
   +-------------+-----------+-------+------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request header parameters

   ============ ========= ====== ========================================
   Parameter    Mandatory Type   Description
   ============ ========= ====== ========================================
   X-Auth-Token Yes       String User token obtained from IAM.
   Content-Type Yes       String Content type, which is application/json.
   ============ ========= ====== ========================================

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   ============== ======= =====================
   Parameter      Type    Description
   ============== ======= =====================
   errorCode      String  Response code.
   errorMessage   String  Response message.
   responseStatus Integer Response status code.
   ============== ======= =====================

Example Requests
----------------

Delete an application discovery rule with a specified ID.

.. code-block:: text

   DELETE https://{Endpoint}/v1/{project_id}/inv/servicediscoveryrules?appRulesIds=b788349e-62b2-3c7a-b597-02c611d59801

Example Responses
-----------------

**Status code: 200**

OK

The request is successful.

.. code-block::

   {
     "errorCode" : "SVCSTG.INV.2000000",
     "errorMessage" : null
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

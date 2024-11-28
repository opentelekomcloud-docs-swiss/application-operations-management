:original_name: ListAgentInfo.html

.. _ListAgentInfo:

Querying Agent Information
==========================

Function
--------

This API is used to query the Agent information about an account, a cluster, or a namespace.

URI
---

GET /v1/{project_id}/{cluster_id}/{namespace}/agents

.. table:: **Table 1** Path Parameters

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                          |
   +=================+=================+=================+======================================================================================+
   | project_id      | Yes             | String          | Project ID obtained from IAM. Generally, a project ID contains 32 characters.        |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------+
   | cluster_id      | Yes             | String          | Cluster ID.                                                                          |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------+
   | namespace       | Yes             | String          | Metric namespace.                                                                    |
   |                 |                 |                 |                                                                                      |
   |                 |                 |                 | Values:                                                                              |
   |                 |                 |                 |                                                                                      |
   |                 |                 |                 | -  PAAS.CONTAINER: namespace of component, instance, process, and container metrics. |
   |                 |                 |                 | -  PAAS.NODE: namespace of host, network, disk, and file system metrics.             |
   |                 |                 |                 | -  PAAS.AGGR: namespace of cluster metrics.                                          |
   |                 |                 |                 | -  Namespace of custom metrics.                                                      |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------+-----------+---------+--------------------------------------------------------------+
   | Parameter | Mandatory | Type    | Description                                                  |
   +===========+===========+=========+==============================================================+
   | offset    | No        | Integer | Pagination information.                                      |
   +-----------+-----------+---------+--------------------------------------------------------------+
   | limit     | No        | Integer | Default value: 1000. Number of records that can be returned. |
   +-----------+-----------+---------+--------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request header parameters

   ============ ========= ====== =============================
   Parameter    Mandatory Type   Description
   ============ ========= ====== =============================
   X-Auth-Token Yes       String User token obtained from IAM.
   ============ ========= ====== =============================

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 4** Response body parameters

   +------------+---------------------------------------------------------------------------+---------------------------------------------+
   | Parameter  | Type                                                                      | Description                                 |
   +============+===========================================================================+=============================================+
   | page_info  | :ref:`PageInfo <listagentinfo__response_pageinfo>` object                 | Metadata, including pagination information. |
   +------------+---------------------------------------------------------------------------+---------------------------------------------+
   | agent_list | Array of :ref:`AgentDetail <listagentinfo__response_agentdetail>` objects | Agent list.                                 |
   +------------+---------------------------------------------------------------------------+---------------------------------------------+

.. _listagentinfo__response_pageinfo:

.. table:: **Table 5** PageInfo

   +-----------+---------+---------------------------------------------------------------------------+
   | Parameter | Type    | Description                                                               |
   +===========+=========+===========================================================================+
   | count     | Integer | Number of records that can be returned.                                   |
   +-----------+---------+---------------------------------------------------------------------------+
   | offset    | Integer | Start of the next page, which is used for pagination. null: No more data. |
   +-----------+---------+---------------------------------------------------------------------------+
   | total     | Integer | Total number of records.                                                  |
   +-----------+---------+---------------------------------------------------------------------------+

.. _listagentinfo__response_agentdetail:

.. table:: **Table 6** AgentDetail

   +--------------+--------+-------------------------------------------------------------------------------------------+
   | Parameter    | Type   | Description                                                                               |
   +==============+========+===========================================================================================+
   | agentId      | String | Agent ID. This parameter is mandatory.                                                    |
   +--------------+--------+-------------------------------------------------------------------------------------------+
   | ip           | String | Private IP address of the node where the ICAgent is located. This parameter is mandatory. |
   +--------------+--------+-------------------------------------------------------------------------------------------+
   | nodeName     | String | Name of the node where the ICAgent is located. This parameter is mandatory.               |
   +--------------+--------+-------------------------------------------------------------------------------------------+
   | status       | String | ICAgent running status. This parameter is mandatory.                                      |
   +--------------+--------+-------------------------------------------------------------------------------------------+
   | lastModified | String | Time when the ICAgent was modified. This parameter is mandatory.                          |
   +--------------+--------+-------------------------------------------------------------------------------------------+
   | updateTime   | String | Time when the ICAgent was upgraded. This parameter is mandatory.                          |
   +--------------+--------+-------------------------------------------------------------------------------------------+
   | version      | String | ICAgent version number. This parameter is mandatory.                                      |
   +--------------+--------+-------------------------------------------------------------------------------------------+
   | osType       | String | OS of the node where the ICAgent is located. This parameter is mandatory.                 |
   +--------------+--------+-------------------------------------------------------------------------------------------+

**Status code: 400**

.. table:: **Table 7** Response body parameters

   ========== ====== ==============
   Parameter  Type   Description
   ========== ====== ==============
   error_code String Error code.
   error_msg  String Error message.
   ========== ====== ==============

**Status code: 401**

.. table:: **Table 8** Response body parameters

   ========== ====== ==============
   Parameter  Type   Description
   ========== ====== ==============
   error_code String Error code.
   error_msg  String Error message.
   ========== ====== ==============

**Status code: 403**

.. table:: **Table 9** Response body parameters

   ========== ====== ==============
   Parameter  Type   Description
   ========== ====== ==============
   error_code String Error code.
   error_msg  String Error message.
   ========== ====== ==============

**Status code: 500**

.. table:: **Table 10** Response body parameters

   ========== ====== ==============
   Parameter  Type   Description
   ========== ====== ==============
   error_code String Error code.
   error_msg  String Error message.
   ========== ====== ==============

**Status code: 503**

.. table:: **Table 11** Response body parameters

   ========== ====== ==============
   Parameter  Type   Description
   ========== ====== ==============
   error_code String Error code.
   error_msg  String Error message.
   ========== ====== ==============

Example Requests
----------------

Query information about the Agent whose cluster ID is 0f325*******00cb and namespace is default under the 75f54********0cbd0c4 account.

.. code-block:: text

   GET https://{endpoint}/v1/75f54********0cbd0c4/0f325*******00cb/default/agents?offset=50&limit=789

Example Responses
-----------------

**Status code: 200**

OK

The request is successful.

.. code-block::

   {
     "page_info" : {
       "count" : 2,
       "offset" : 0,
       "total" : 2
     },
     "agent_list" : [ {
       "agent_ip" : "192.***.***.102",
       "agent_id" : "8977a034********473f6ef642",
       "node_name" : "192.***.***.102",
       "status" : "uninstall",
       "last_modified" : "",
       "update_time" : "",
       "agent_version" : "",
       "os_type" : ""
     }, {
       "agent_ip" : "192.***.***.133",
       "agent_id" : "6211b62********a6d1389e233",
       "node_name" : "192.***.***.133",
       "status" : "uninstall",
       "last_modified" : "",
       "update_time" : "",
       "agent_version" : "",
       "os_type" : ""
     } ]
   }

Status Codes
------------

+-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Status Code                       | Description                                                                                                                                                                              |
+===================================+==========================================================================================================================================================================================+
| 200                               | OK                                                                                                                                                                                       |
|                                   |                                                                                                                                                                                          |
|                                   | The request is successful.                                                                                                                                                               |
+-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 400                               | Bad Request                                                                                                                                                                              |
|                                   |                                                                                                                                                                                          |
|                                   | Invalid request. The client should not repeat the request without modifications.                                                                                                         |
+-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401                               | Unauthorized                                                                                                                                                                             |
|                                   |                                                                                                                                                                                          |
|                                   | The authorization information is incorrect or invalid.                                                                                                                                   |
+-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 403                               | Forbidden                                                                                                                                                                                |
|                                   |                                                                                                                                                                                          |
|                                   | The request is rejected. The server has received the request and understood it, but the server refuses to respond to it. The client should not repeat the request without modifications. |
+-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 500                               | Internal Server Error                                                                                                                                                                    |
|                                   |                                                                                                                                                                                          |
|                                   | The server is able to receive the request but unable to understand the request.                                                                                                          |
+-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 503                               | Service Unavailable                                                                                                                                                                      |
|                                   |                                                                                                                                                                                          |
|                                   | The requested service is invalid. The client should not repeat the request without modifications.                                                                                        |
+-----------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Error Codes
-----------

See :ref:`Error Codes <errorcode>`.

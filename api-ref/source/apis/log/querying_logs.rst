:original_name: ListLogs.html

.. _ListLogs:

Querying Logs
=============

Function
--------

This API is used to query logs by different dimensions, such as by cluster, IP address, or application. Pagination queries are supported. For pagination queries, the lineNum (sequence number of the final log in the last query result), type (value: next), and size parameters need to be added. The values of category, searchKey, keyWord, startTime, and endTime must be the same as those in the first query. To implement another pagination query, change the value of lineNum to the sequence number of the final log in the last query result. The rest may be deduced by analogy.

URI
---

POST /v1/{project_id}/als/action

.. table:: **Table 1** Path Parameters

   +------------+-----------+--------+-------------------------------------------------------------------------------+
   | Parameter  | Mandatory | Type   | Description                                                                   |
   +============+===========+========+===============================================================================+
   | project_id | Yes       | String | Project ID obtained from IAM. Generally, a project ID contains 32 characters. |
   +------------+-----------+--------+-------------------------------------------------------------------------------+

.. table:: **Table 2** Query Parameters

   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type            | Description                                                                 |
   +=================+=================+=================+=============================================================================+
   | type            | Yes             | String          | API call mode. When the value is querylogs, this API is used to query logs. |
   |                 |                 |                 |                                                                             |
   |                 |                 |                 | Enumeration values:                                                         |
   |                 |                 |                 |                                                                             |
   |                 |                 |                 | -  **querylogs**                                                            |
   +-----------------+-----------------+-----------------+-----------------------------------------------------------------------------+

Request Parameters
------------------

.. table:: **Table 3** Request header parameters

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

.. table:: **Table 4** Request body parameters

   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Mandatory       | Type                                                  | Description                                                                                                                                                                                                                          |
   +=================+=================+=======================================================+======================================================================================================================================================================================================================================+
   | category        | Yes             | String                                                | Log type. Options: app_log: application log node_log: host log custom_log: log in a custom path                                                                                                                                      |
   |                 |                 |                                                       |                                                                                                                                                                                                                                      |
   |                 |                 |                                                       | Enumeration values:                                                                                                                                                                                                                  |
   |                 |                 |                                                       |                                                                                                                                                                                                                                      |
   |                 |                 |                                                       | -  **app_log**                                                                                                                                                                                                                       |
   |                 |                 |                                                       | -  **node_log**                                                                                                                                                                                                                      |
   |                 |                 |                                                       | -  **custom_log**                                                                                                                                                                                                                    |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | searchKey       | Yes             | :ref:`SearchKey <listlogs__request_searchkey>` object | Log filter criteria, which vary according to log sources.                                                                                                                                                                            |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | keyWord         | No              | String                                                | #. Exact search by keyword is supported. A keyword is a word between two adjacent delimiters.                                                                                                                                        |
   |                 |                 |                                                       | #. Fuzzy search by keyword is supported. Example: RROR, ERRO?, *ROR*, ERR*, or ER*OR.                                                                                                                                                |
   |                 |                 |                                                       | #. Exact search by phrase is supported. Example: Start to refresh alm Statistic.                                                                                                                                                     |
   |                 |                 |                                                       | #. Search using AND (&&) or OR (||) is supported. Example: query&&logs or query||logs. Note: Default delimiters include ``,'";=()[]{}@&<>/:\``\ n\\t\\r and spaces.                                                                  |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | startTime       | Yes             | Long                                                  | Start time of the query (UTC, in ms).                                                                                                                                                                                                |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | endTime         | Yes             | Long                                                  | End time of the query (UTC, in ms).                                                                                                                                                                                                  |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | lineNum         | No              | String                                                | Sequence number of the final log in the last query result. This parameter is not required for the first query, but is required for subsequent pagination queries.                                                                    |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | type            | No              | String                                                | Pagination query. This parameter is not required for the first query, but is required for subsequent pagination queries.                                                                                                             |
   |                 |                 |                                                       |                                                                                                                                                                                                                                      |
   |                 |                 |                                                       | Enumeration values:                                                                                                                                                                                                                  |
   |                 |                 |                                                       |                                                                                                                                                                                                                                      |
   |                 |                 |                                                       | -  **next**                                                                                                                                                                                                                          |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | pageSize/size   | No              | Integer                                               | Number of logs queried each time. Default value: 5000. Recommended value: 100. For the first query, pageSize is used. For subsequent pagination queries, size is used.                                                               |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | hideSyslog      | No              | Integer                                               | Whether to hide the system log (icagent\\kubectl) during the query. 0 (default): Hide. 1: Display.                                                                                                                                   |
   |                 |                 |                                                       |                                                                                                                                                                                                                                      |
   |                 |                 |                                                       | Enumeration values:                                                                                                                                                                                                                  |
   |                 |                 |                                                       |                                                                                                                                                                                                                                      |
   |                 |                 |                                                       | -  **0**                                                                                                                                                                                                                             |
   |                 |                 |                                                       | -  **1**                                                                                                                                                                                                                             |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | isDesc          | No              | Boolean                                               | Whether to query logs based on lineNum in ascending or descending order. true: lineNum in descending order (from the latest time to the earliest time) false: lineNum in ascending order (from the earliest time to the latest time) |
   |                 |                 |                                                       |                                                                                                                                                                                                                                      |
   |                 |                 |                                                       | Enumeration values:                                                                                                                                                                                                                  |
   |                 |                 |                                                       |                                                                                                                                                                                                                                      |
   |                 |                 |                                                       | -  **true**                                                                                                                                                                                                                          |
   |                 |                 |                                                       | -  **false**                                                                                                                                                                                                                         |
   +-----------------+-----------------+-------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. _listlogs__request_searchkey:

.. table:: **Table 5** SearchKey

   +-----------+-----------+--------+-----------------------------------------------------------------------+
   | Parameter | Mandatory | Type   | Description                                                           |
   +===========+===========+========+=======================================================================+
   | clusterId | Yes       | String | CCE cluster: CCE cluster ID Custom cluster: APM Host log: CONFIG_FILE |
   +-----------+-----------+--------+-----------------------------------------------------------------------+
   | nameSpace | No        | String | CCE cluster namespace.                                                |
   +-----------+-----------+--------+-----------------------------------------------------------------------+
   | appName   | No        | String | Service name.                                                         |
   +-----------+-----------+--------+-----------------------------------------------------------------------+
   | podName   | No        | String | Container instance name.                                              |
   +-----------+-----------+--------+-----------------------------------------------------------------------+
   | pathFile  | No        | String | Log file name.                                                        |
   +-----------+-----------+--------+-----------------------------------------------------------------------+
   | hostIP    | No        | String | IP address of the VM where logs are located.                          |
   +-----------+-----------+--------+-----------------------------------------------------------------------+

Response Parameters
-------------------

**Status code: 200**

.. table:: **Table 6** Response body parameters

   +--------------+------------------------------------------------------------+-----------------------------------------------------------------------+
   | Parameter    | Type                                                       | Description                                                           |
   +==============+============================================================+=======================================================================+
   | errorCode    | String                                                     | Response code. SVCSTG.ALS.200200: Success response.                   |
   +--------------+------------------------------------------------------------+-----------------------------------------------------------------------+
   | errorMessage | String                                                     | Response message.                                                     |
   +--------------+------------------------------------------------------------+-----------------------------------------------------------------------+
   | result       | :ref:`LogsResults <listlogs__response_logsresults>` object | Metadata, including results and the total number of returned records. |
   +--------------+------------------------------------------------------------+-----------------------------------------------------------------------+

.. _listlogs__response_logsresults:

.. table:: **Table 7** LogsResults

   +-----------+--------------------------------------------------------------+-----------------------------------------+
   | Parameter | Type                                                         | Description                             |
   +===========+==============================================================+=========================================+
   | total     | Integer                                                      | Number of records that can be returned. |
   +-----------+--------------------------------------------------------------+-----------------------------------------+
   | data      | Array of :ref:`LogItem <listlogs__response_logitem>` objects | Data array.                             |
   +-----------+--------------------------------------------------------------+-----------------------------------------+

.. _listlogs__response_logitem:

.. table:: **Table 8** LogItem

   ============== ====== =================================================
   Parameter      Type   Description
   ============== ====== =================================================
   category       String Log type.
   loghash        String Hash value of the log source.
   clusterId      String CCE cluster ID.
   clusterName    String CCE cluster name.
   nameSpace      String CCE cluster namespace.
   podName        String CCE container instance name.
   appName        String Service name.
   serviceID      String Service ID of an AOM resource.
   containerName  String CCE container name.
   logContent     String Raw log data.
   pathFile       String Absolute path of a log file.
   hostIP         String IP address of the VM where log files are located.
   hostId         String ID of a host in a cluster.
   hostName       String Name of the VM where log files are located.
   collectTime    String Log collection time (UTC time, in ms).
   lineNum        String Sequence number of a log line.
   logContentSize String Size of a single-line log.
   ============== ====== =================================================

Example Requests
----------------

-  Query application logs in a cluster.

   .. code-block:: text

      POST https://{Endpoint}/v1/{project_id}/als/action?type=querylogs

      {
        "category" : "app_log",
        "searchKey" : {
          "clusterId" : "874819a2-bd6f-11e9-80be-0255ac1001b3"
        },
        "keyWord" : "",
        "startTime" : 1569463658895,
        "endTime" : 1569463958895,
        "pageSize" : 100,
        "hideSyslog" : 0
      }

-  Query data by page.

   .. code-block::

      https://{Endpoint}/v1/{project_id}/als/action

      {
        "category" : "app_log",
        "searchKey" : {
          "clusterId" : "874819a2-bd6f-11e9-80be-0255ac1001b3"
        },
        "keyWord" : "",
        "startTime" : 1569463658895,
        "endTime" : 1569463958895,
        "lineNum" : "1569463911294010547",
        "type" : "next",
        "size" : 100,
        "hideSyslog" : 0
      }

Example Responses
-----------------

**Status code: 200**

OK

The request is successful.

.. code-block::

   {
     "errorCode" : "SVCSTG.ALS.200200",
     "errorMessage" : "Query data success",
     "result" : {
       "total" : 5000,
       "data" : [ {
         "category" : "app",
         "loghash" : "496b2070d40a83c17f2625401af8a50aadc316f216771fbe38b94d31feaa30eb",
         "clusterId" : "c693fa7c-54cd-11e8-8055-0255ac101e40",
         "clusterName" : "aomdemo",
         "nameSpace" : "default",
         "podName" : "als0712-7c4875f884-q5wwp",
         "appName" : "als0712",
         "serviceID" : "",
         "containerName" : "container-0",
         "logContent" : "warn:2018/10/09 06:57:01 helloworld.go:108: the main process is running now.n",
         "pathFile" : "/var/paas/sys/log/apm/debug_erro.trace",
         "hostIP" : "192.168.0.133",
         "hostId" : "c11c7211-5a0b-4925-bef4-d078661299b0",
         "hostName" : "192.168.0.133",
         "collectTime" : "1539068233983",
         "lineNum" : "15390682339830002",
         "logContentSize" : "77"
       } ]
     }
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

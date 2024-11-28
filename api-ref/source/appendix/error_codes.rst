:original_name: ErrorCode.html

.. _ErrorCode:

Error Codes
===========

If an error occurs in API calling, no result is returned. Identify the causes of errors based on the error codes of each API. If an error occurs in API calling, HTTP status code 4xx or 5xx is returned. The response body contains the specific error code and information. If you are unable to identify the cause of an error, contact technical support and provide the error code to solve the problem.

Format of an Error Response Body
--------------------------------

If an error occurs during API calling, an error code and a message will be displayed. The following shows an error response body.

.. code-block::

   {
       "errorCode": "SVCSTG_AMS_4000001",
       "errorMessage": "Request param invalid"
   }

In the response body, **errorCode** is an error code, and **errorMessage** provides information about the error.

Error Code Description
----------------------

+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| Error Code            | Message                                                 | Solution                                                            |
+=======================+=========================================================+=====================================================================+
| SVCSTG_AMS_2000000    | The request is successful.                              | No action is required after the request is executed.                |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000001    | Invalid request parameter.                              | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000002    | Invalid namespace.                                      | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000003    | Dimensions are left blank.                              | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000005    | Invalid metric data type.                               | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000006    | The metric data value is left blank.                    | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000007    | Invalid name or value length in the dimension.          | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000008    | The request exceeds 40 KB.                              | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000009    | A metric supports a maximum of 20 dimensions.           | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000010    | Invalid collection time.                                | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000101    | Invalid namespace.                                      | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000101    | Projectid is left blank.                                | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000101    | Invalid alarm name.                                     | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000102    | Invalid inventoryId.                                    | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000102    | The metric data parameter is null.                      | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000102    | The threshold rule name already exists.                 | Use another name.                                                   |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000103    | ProjectId is left blank.                                | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000103    | Invalid period.                                         | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000103    | Invalid alarm description.                              | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000104    | Invalid statistics.                                     | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000104    | Invalid alarm threshold.                                | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000105    | Invalid limit.                                          | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000105    | Invalid metrics.                                        | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000105    | Invalid alarm period.                                   | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000106    | Invalid start.                                          | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000106    | Invalid time range.                                     | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000106    | Invalid email list.                                     | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000107    | The number of data points in a time range exceeds 1440. | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000107    | The maximum number of threshold rules has been reached. | Contact technical support to expand the capacity.                   |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000108    | Invalid time range for alarm queries.                   | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000109    | Invalid metricName.                                     | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000109    | Invalid project ID.                                     | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000110    | Invalid fillValue.                                      | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000110    | Invalid limit.                                          | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000111    | Invalid start.                                          | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000115    | Invalid request parameter.                              | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000118    | Invalid number of consecutive periods.                  | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000119    | Invalid alarm statistic.                                | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000120    | Invalid alarm comparison operator.                      | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_4000121    | The alarm does not exist.                               | Check whether the threshold rule exists.                            |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_5000000    | Internal server error.                                  | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_5030001    | The Cassandra session is null.                          | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG_AMS_5030002    | The Cassandra execution is abnormal.                    | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| AOM.0400              | Invalid request parameter.                              | Check parameters.                                                   |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| AOM.0401              | Invalid authentication information.                     | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| AOM.0403              | Forbidden                                               | Use an authorized account.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| AOM.0500              | Internal server error.                                  | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| AOM.0503              | Failed to query event alarms.                           | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.INV.2000000    | The request is successful.                              | No action is required after the request is executed.                |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.INV.4000115    | Invalid request parameter.                              | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.INV.4030000    | Forbidden                                               | Use an authorized account.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.INV.5000001    | The Elasticsearch session is null.                      | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.INV.5000002    | The Elasticsearch execution is abnormal.                | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.INV.5000003    | The call ICMGR is abnormal.                             | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.INV.5000006    | The apprule name already exists.                        | Use another name.                                                   |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.INV.5000007    | The maximum number of rules has been reached.           | Delete unnecessary rules and add new rules.                         |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTR.ALS.200200     | Succeeded in querying logs.                             | No action is required after the request is executed.                |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.ALS.200.200    | Successful query.                                       | ``-``                                                               |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.ALS.200.201    | The maximum length of parameter %s exceeds %s.          | Check whether the parameter meets requirements.                     |
|                       |                                                         |                                                                     |
|                       | %s is empty.                                            |                                                                     |
|                       |                                                         |                                                                     |
|                       | %s is incorrect.                                        |                                                                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.ALS.200.203    | Failed to query logs.                                   | Check whether the parameter meets requirements.                     |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| SVCSTG.ALS.403.105    | Invalid project ID.                                     | Check whether the URL project_id and token project_id are the same. |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+
| APM.ICMGR.2001401     | Privilege Unavailable                                   | Contact technical support.                                          |
+-----------------------+---------------------------------------------------------+---------------------------------------------------------------------+

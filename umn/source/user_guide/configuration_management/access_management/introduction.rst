:original_name: aom_02_0921.html

.. _aom_02_0921:

Introduction
============

Access Management allows you to quickly connect monitoring data to AOM. This function determines whether to establish or delete network channels, and generate or revoke authentication credentials for reporting monitoring data.

By using the generated access code as an authentication credential, you can remotely report native Prometheus metrics to AOM according to :ref:`Reporting Prometheus Data to AOM <aom_02_0922>` and store time series data for a long time. You can also use the access code to query data in AOM according to :ref:`Viewing Metric Data in AOM Using Grafana <aom_02_0923>`. AOM supports the following native Prometheus APIs:

APIs for querying Prometheus data:

-  GET /v1/:project_id/aom/api/v1/query
-  GET /v1/:project_id/aom/api/v1/labels
-  GET /v1/:project_id/aom/api/v1/label/:label_name/values
-  POST /v1/:project_id/aom/api/v1/query
-  POST /v1/:project_id/aom/api/v1/query_range
-  POST /v1/:project_id/aom/api/v1/labels

When calling the preceding APIs, add **access_code** to the **Authorization** field in the request header.

Example: "Authorization: Bearer {access_code}" or "Authorization: Basic base64Encode("aom_access_code:{access_code}")"

API for reporting time series data: **POST /v1/:project_id/push**

.. note::

   **base64Encode** means that parameters are encoded using Base64.

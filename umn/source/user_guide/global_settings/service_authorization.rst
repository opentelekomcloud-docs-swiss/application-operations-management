:original_name: en-us_topic_0000002483218946.html

.. _en-us_topic_0000002483218946:

Service Authorization
=====================

Grant the permissions to access the data of Log Tank Service (LTS), Cloud Container Engine (CCE), and Elastic Cloud Server (ECS). The setting takes effect for the entire AOM service.

Prerequisites
-------------

You have been granted **AOMFullAccessPolicy**, **iam:agencies:createAgency**, and **iam:agencies:deleteAgency** permissions.

Procedure
---------

#. Log in to the AOM console.

#. In the navigation pane, choose **Global Configuration**.

#. In the upper right corner of the **Service Authorization** page, click **Authorize** to grant permissions to access the preceding cloud services with one click.

   Upon authorization, the **aom_admin_trust** agency will be created in IAM.

   If **Cancel Authorization** is displayed in the upper right corner of the page, you have the permissions to access the preceding cloud services.

:original_name: aom_06_0026.html

.. _aom_06_0026:

IAM-based Permissions Management
================================

If you need to assign different permissions to employees in your enterprise to access your created AOM resources on the cloud service platform, Identity and Access Management (IAM) is a good choice for fine-grained permissions management. IAM provides identity authentication, fine-grained permissions management, and access control. IAM helps you secure access to your cloud resources. If your account does not require IAM for permissions management, you can skip this section.

IAM is a free service. You only pay for the resources in your account.

With IAM, you can control access to specific cloud resources. For example, if you want some software developers in your enterprise to use AOM resources but do not want them to delete resources, you can grant permission to use AOM but not permission to delete its resources.

.. table:: **Table 1** Role/Policy-based authorization

   +---------------------------------+-------------------------------------+--------------------------+-----------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Name                            | Core Relationship                   | Permissions              | Authorization Method                    | Description                                                                                                                                                                                                                                                                                      |
   +=================================+=====================================+==========================+=========================================+==================================================================================================================================================================================================================================================================================================+
   | Role/Policy-based authorization | User-permission-authorization scope | -  System-defined roles  | Assign roles or policies to principals. | To authorize a user, you need to add it to a user group first and then specify the scope of authorization. It provides a limited number of condition keys and cannot meet the requirements of fine-grained permissions control. This method is suitable for small- and medium-sized enterprises. |
   |                                 |                                     | -  System-defined policy |                                         |                                                                                                                                                                                                                                                                                                  |
   |                                 |                                     | -  Custom policies       |                                         |                                                                                                                                                                                                                                                                                                  |
   +---------------------------------+-------------------------------------+--------------------------+-----------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

For more information, see *IAM Service Overview*.

Role/Policy-based Authorization
-------------------------------

AOM supports role/policy-based authorization. New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and then attach policies or roles to these groups. These users then inherit permissions from the groups and perform specified operations on cloud services.

AOM is a project-level service deployed and accessed in specific physical regions. When you set **Scope** to **Region-specific projects** and select the specified projects in the specified regions , the users only have permissions for resources in the selected projects. If you set **Scope** to **All resources**, the users have permissions for resources in all region-specific projects. When accessing AOM, the users need to switch to a region where they have been authorized to use this service.

:ref:`Table 2 <aom_06_0026__en-us_topic_0000001817202720_table145316572518>` lists all the system permissions supported by AOM.

.. _aom_06_0026__en-us_topic_0000001817202720_table145316572518:

.. table:: **Table 2** System permissions supported by AOM

   +-------------------+-------------+-------------------------------------------------------------------------------------------------------+-----------------------+-------------------------------------------+
   | Subservice Name   | Policy Name | Description                                                                                           | Type                  | Dependent System Permissions              |
   +===================+=============+=======================================================================================================+=======================+===========================================+
   | Monitoring center | AOM Admin   | Administrator permissions for AOM. Users granted these permissions can perform all operations on AOM. | System-defined policy | CCE ReadOnlyAccess and DMS ReadOnlyAccess |
   +-------------------+-------------+-------------------------------------------------------------------------------------------------------+-----------------------+-------------------------------------------+
   |                   | AOM Viewer  | Read-only permissions for AOM. Users granted these permissions can only view AOM data.                | System-defined policy |                                           |
   +-------------------+-------------+-------------------------------------------------------------------------------------------------------+-----------------------+-------------------------------------------+

:ref:`Table 3 <aom_06_0026__en-us_topic_0000001817202720_table126113571055>` lists the common operations supported by each system-defined policy of the monitoring center. Select policies as required.

.. _aom_06_0026__en-us_topic_0000001817202720_table126113571055:

.. table:: **Table 3** Common operations supported by each system-defined policy of the monitoring center

   ======================================= ========= ==========
   Operation                               AOM Admin AOM Viewer
   ======================================= ========= ==========
   Creating an alarm rule                  Y         x
   Modifying an alarm rule                 Y         x
   Deleting an alarm rule                  Y         x
   Creating an alarm template              Y         x
   Modifying an alarm template             Y         x
   Deleting an alarm template              Y         x
   Creating an alarm action rule           Y         x
   Modifying an alarm action rule          Y         x
   Deleting an alarm action rule           Y         x
   Creating a message template             Y         x
   Modifying a message template            Y         x
   Deleting a message template             Y         x
   Creating a dashboard                    Y         x
   Modifying a dashboard                   Y         x
   Deleting a dashboard                    Y         x
   Creating a Prometheus instance          Y         x
   Modifying a Prometheus instance         Y         x
   Deleting a Prometheus instance          Y         x
   Creating an application discovery rule  Y         x
   Modifying an application discovery rule Y         x
   Deleting an application discovery rule  Y         x
   Subscribing to threshold alarms         Y         x
   Configuring a VM log collection path    Y         x
   ======================================= ========= ==========

Roles/Policies Required by AOM Dependent Services
-------------------------------------------------

If an IAM user needs to view data or use functions on the AOM console, grant the **AOM FullAccess** or **AOM ReadOnlyAccess** policy to the user group to which the user belongs and then add the roles or policies required by AOM dependent services by referring to :ref:`Table 4 <aom_06_0026__en-us_topic_0000001817202720_table1774313531073>`.

.. note::

   When a user subscribes to AOM for the first time, AOM creates an agency for the user. In addition to **AOM FullAccess**, the user also needs to be granted the **Security Administrator** permission to create and delete agencies.

.. _aom_06_0026__en-us_topic_0000001817202720_table1774313531073:

.. table:: **Table 4** Roles/Policies required by AOM dependent services

   +------------------------+-----------------------+------------------------------------------------------------------------------------------------+
   | Console Function       | Dependent Service     | Policy/Role Required                                                                           |
   +========================+=======================+================================================================================================+
   | -  Workload monitoring | CCE                   | To use workload and cluster monitoring, you need to set the **CCE ReadOnlyAccess** permission. |
   | -  Cluster monitoring  |                       |                                                                                                |
   +------------------------+-----------------------+------------------------------------------------------------------------------------------------+

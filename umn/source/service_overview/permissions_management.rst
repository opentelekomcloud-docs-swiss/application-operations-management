:original_name: aom_06_0021.html

.. _aom_06_0021:

Permissions Management
======================

If you need to grant your enterprise personnel permission to access your AOM resources, use Identity and Access Management (IAM). IAM provides identity authentication, permissions management, and access control, helping you secure access to your AOM resources.

With IAM, you can use your account to create IAM users for your employees, and assign permissions to the users to control their access to specific types of resources. For example, some software developers in your enterprise need to use AOM resources but must not delete them or perform any high-risk operations such as deleting application discovery rules. To achieve this result, you can create IAM users for the software developers and grant them only the permissions required for using AOM resources.

If your account does not need individual IAM users for permissions management, you may skip over this chapter.

AOM Permissions
---------------

New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and then attach policies or roles to these groups. After authorization, the user can perform specified operations on AOM.

AOM is a project-level service deployed for specific regions. To assign AOM permissions to a user group, specify the scope as region-specific projects and select projects for the permissions to take effect. If **All projects** is selected, the permissions will take effect for the user group in all region-specific projects. When accessing AOM, the users need to switch to a region where they have been authorized to use this service.

You can grant permissions by using roles and policies.

-  Roles: A type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. This mechanism provides only a limited number of service-level roles for authorization. Cloud services depend on each other. When you grant permissions using roles, you may also need to attach dependent roles. However, roles are not ideal for fine-grained authorization and least privilege access.
-  Policies: A fine-grained authorization tool that defines permissions required to perform operations on specific cloud resources under certain conditions. This mechanism allows for more flexible policy-based authorization on a principle of least privilege (PoLP) basis. For example, you can grant users only permission to manage a certain type of ECSs.

:ref:`Table 1 <aom_06_0021__table145316572518>` lists all the system permissions supported by AOM.

.. _aom_06_0021__table145316572518:

.. table:: **Table 1** System permissions supported by AOM

   +--------------------+---------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------+
   | Policy             | Description                                                                                 | Type                  | Dependent System Permissions                             |
   +====================+=============================================================================================+=======================+==========================================================+
   | AOM FullAccess     | Administrator permissions for AOM. Users granted these permissions can operate and use AOM. | System-defined policy | CCE Administrator, OBS Administrator, and LTS FullAccess |
   +--------------------+---------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------+
   | AOM ReadOnlyAccess | Read-only permissions for AOM. Users granted these permissions can only check AOM data.     | System-defined policy |                                                          |
   +--------------------+---------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------+

:ref:`Table 2 <aom_06_0021__table126113571055>` lists the common operations supported by each system-defined policy of AOM. Please choose proper system-defined policies according to this table.

.. _aom_06_0021__table126113571055:

.. table:: **Table 2** Common operations supported by each system-defined policy of AOM

   +-----------------------------------------+----------------+--------------------+
   | Operation                               | AOM FullAccess | AOM ReadOnlyAccess |
   +=========================================+================+====================+
   | Creating an alarm rule                  | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Modifying an alarm rule                 | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Deleting an alarm rule                  | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Creating an alarm template              | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Creating an alarm template              | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Creating an alarm template              | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Creating a dashboard                    | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Modifying a dashboard                   | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Deleting a dashboard                    | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Creating an alarm action rule           | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Modifying an alarm action rule          | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Deleting an alarm action rule           | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Creating a message template             | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Modifying a message template            | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Deleting a message template             | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Creating an application discovery rule  | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Modifying an application discovery rule | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Deleting an application discovery rule  | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Exporting a monitoring report           | Y              | Y                  |
   +-----------------------------------------+----------------+--------------------+
   | Configuring a VM log collection path    | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Checking bucket logs                    | Y              | Y                  |
   +-----------------------------------------+----------------+--------------------+
   | Adding a log dump                       | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Modifying a log dump                    | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Deleting a log dump                     | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Starting periodical dump                | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Stopping periodical dump                | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Configuring delimiters                  | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Installing an ICAgent                   | Y              | Y                  |
   +-----------------------------------------+----------------+--------------------+
   | Upgrading an ICAgent                    | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+
   | Uninstalling an ICAgent                 | Y              | x                  |
   +-----------------------------------------+----------------+--------------------+

To use a custom fine-grained policy, log in to IAM as the administrator and select fine-grained permissions of AOM as required. For details about fine-grained permissions of AOM, see :ref:`Table 3 <aom_06_0021__table13611192118526>`.

.. _aom_06_0021__table13611192118526:

.. table:: **Table 3** Fine-grained permissions of AOM

   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | Permission Name          | Description                            | Dependency | Scenario                                                                  |
   +==========================+========================================+============+===========================================================================+
   | aom:alarmRule:create     | Creating a threshold rule              | N/A        | Creating a threshold rule                                                 |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:alarmRule:set        | Modifying a threshold rule             |            | Modifying a threshold rule                                                |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:alarmRule:get        | Querying threshold rules               |            | Querying all threshold rules or a single threshold rule by rule ID        |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:alarmRule:delete     | Deleting threshold rules               |            | Deleting threshold rules in batches or a single threshold rule by rule ID |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:discoveryRule:list   | Querying application discovery rules   |            | Querying existing application discovery rules                             |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:discoveryRule:delete | Deleting an application discovery rule |            | Deleting an application discovery rule                                    |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:discoveryRule:set    | Adding an application discovery rule   |            | Adding an application discovery rule                                      |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:metric:list          | Querying time series objects           |            | Querying time series objects                                              |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:metric:list          | Querying time series data              |            | Querying time series data                                                 |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:metric:get           | Querying metrics                       |            | Query metrics                                                             |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+
   | aom:metric:get           | Querying monitoring data               |            | Querying monitoring data                                                  |
   +--------------------------+----------------------------------------+------------+---------------------------------------------------------------------------+

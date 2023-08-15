:original_name: aom_04_0022.html

.. _aom_04_0022:

Introduction
============

This chapter describes fine-grained permissions management for your AOM. If your cloud account does not need individual Identity and Access Management (IAM) users, then you may skip over this chapter.

By default, new IAM users do not have any permissions assigned. You need to add a user to one or more groups, and assign permissions policies or roles to these groups. The user then inherits permissions from the groups it is a member of. This process is called authorization. After authorization, the user can perform specified operations on AOM.

You can grant users permissions by using roles and policies. Roles are a type of coarse-grained authorization mechanism that defines permissions related to user responsibilities. Policies define API-based permissions for operations on specific resources under certain conditions, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   Policy-based authorization is recommended if you want to allow or deny the access to an API.

A cloud account has all of the permissions required to call all APIs, but IAM users must have the required permissions specifically assigned. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions can call the API successfully. For example, if an IAM user queries metrics using an API, the user must have been granted permissions that allow the **aom:metric:get** action.

Supported Actions
-----------------

There are two kinds of policies: system-defined policies and custom policies. If the permissions preset in the system do not meet your requirements, you can create custom policies and apply these policies to user groups for refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: Defined by actions in a custom policy.
-  APIs: REST APIs that can be called in a custom policy.
-  Actions: Added to a custom policy to control permissions for specific operations.
-  Dependent actions: Actions on which a specific action depends to take effect. When assigning permissions for the action to a user, you also need to assign permissions for the dependent actions.
-  IAM projects: Authorization scope of a custom policy.

AOM supports the following actions that can be defined in custom policies:

-  :ref:`Monitoring Actions <aom_04_0062>`: include the actions supported by monitoring APIs, such as the APIs for querying metrics; querying and adding monitoring data; adding, modifying, querying, and deleting threshold rules; adding, modifying, querying, and deleting application discovery rules.

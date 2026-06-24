:original_name: aom_03_0007.html

.. _aom_03_0007:

Role/Policy-based Authorization
===============================

Role/Policy-based authorization provided by IAM let you control access to AOM. With IAM, you can:

-  Create IAM users for personnel based on your enterprise's organizational structure. Each IAM user has their own identity credentials for accessing AOM resources.
-  Grant users only the permissions required to perform a given task based on their job responsibilities.
-  Entrust an account or a cloud service to perform efficient O&M on your AOM resources.

If your account meets your permissions requirements, you can skip this section.

:ref:`Figure 1 <aom_03_0007__en-us_topic_0000001863957153_en-us_topic_0169701339_fig13279111625016>` shows the process flow of role/policy-based authorization.

Prerequisites
-------------

Before granting permissions to a user group, learn about the AOM system-defined permissions in section "IAM-based Permissions Management" in *AOM Service Overview*. To grant permissions for other services, learn about all permissions supported by IAM.

Process Flow
------------

.. _aom_03_0007__en-us_topic_0000001863957153_en-us_topic_0169701339_fig13279111625016:

.. figure:: /_static/images/en-us_image_0000002482792836.png
   :alt: **Figure 1** Process for granting AOM permissions using role/policy-based authorization

   **Figure 1** Process for granting AOM permissions using role/policy-based authorization

#. On the IAM console, create a user group and grant it permissions (**AOM ReadOnlyAccess** as an example).
#. Create an IAM user and add it to the created user group.
#. Log in as the IAM user and verify permissions.

Example Custom Policies
-----------------------

You can create custom policies to supplement the system-defined policies of AOM. For details about the actions supported in custom policies, see section "Actions Supported by Policy-based Authorization" in *AOM API Reference*.

To create a custom policy, choose either visual editor or JSON.

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Create a JSON policy or edit an existing one.

For details, see section "Creating a Custom Policy" in *IAM User Guide (Old Edition)*. The following lists examples of common AOM custom policies.

-  Example 1: Grant permission to create alarm rules.

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "aom:alarmRule:create"
                  ]
              }
          ]
      }

-  Example 2: Grant permission to deny deletion of application discovery rules.

   A policy with only "Deny" permissions must be used together with other policies. If the permissions granted to an IAM user contain both "Allow" and "Deny", the "Deny" permissions take precedence over the "Allow" permissions.

   Assume that you want to grant the permissions of the **AOM FullAccess** policy to a user but want to prevent them from deleting application discovery rules. You can create a custom policy for denying deletion of such rules, and attach this policy together with the **AOM FullAccess** policy to the user. As an explicit deny in any policy overrides any allows, the user can perform all operations on AOM excepting deleting application discovery rules. Example policy denying deletion of application discovery rules:

   .. code-block::

      {
            "Version": "1.1",
            "Statement": [
                  {
                "Effect": "Deny",
                        "Action": [
                              "aom:discoveryRule:delete"
                        ]
                  }
            ]
      }

-  Example 3: Create a custom policy containing multiple actions.

   A custom policy can contain the actions of one or multiple services that are of the same type (project-level). Example policy containing multiple actions:

   .. code-block::

      {
              "Version": "1.1",
              "Statement": [
                      {
                              "Effect": "Allow",
                              "Action": [
                                      "aom:*:list",
                                      "aom:*:get",
                                      "apm:*:list",
                                      "apm:*:get"
                              ]
                      },
                      {
                               "Effect": "Allow",
                               "Action": [
                                       "cce:cluster:get",
                                       "cce:cluster:list",
                                       "cce:node:get",
                                       "cce:node:list"
                              ]
                      }
              ]
      }

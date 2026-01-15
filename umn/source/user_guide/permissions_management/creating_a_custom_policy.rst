:original_name: aom_02_0091.html

.. _aom_02_0091:

Creating a Custom Policy
========================

Custom policies can be created as a supplement to the system policies of AOM.

You can create custom policies in either of the following two ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Edit JSON policies from scratch or based on an existing policy.

For example custom policies, see the following description.

Example Custom Policies
-----------------------

-  Example 1: Allowing a user to create threshold rules

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

-  Example 2: Forbidding a user to delete application discovery rules

   A deny policy must be used in conjunction with other policies to take effect. If the permissions assigned to a user contain both Allow and Deny actions, the Deny actions take precedence over the Allow actions.

   To grant a user the **AOM FullAccess** system policy but forbid the user to delete application discovery rules, create a custom policy that denies the deletion of application discovery rules, and grant both the **AOM FullAccess** and deny policies to the user. Because the Deny action takes precedence, the user can perform all operations except deleting application discovery rules. The following is an example deny policy:

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

-  Example 3: Defining permissions for multiple services in a policy

   A custom policy can contain actions of multiple services that are all of the project-level type. The following is an example policy containing actions of multiple services:

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

:original_name: aom_02_0090.html

.. _aom_02_0090:

Creating a User and Granting Permissions
========================================

This chapter describes how to use Identity and Access Management (IAM) for fine-grained permissions control for your Application Operations Management (AOM) resources. With IAM, you can:

-  Create IAM users for employees based on the organizational structure of your enterprise. Each IAM user has their own security credentials, providing access to AOM resources.
-  Grant only the permissions required for users to perform a task.
-  Entrust an account or a cloud service to perform professional and efficient O&M on your AOM resources.

If your account does not need individual IAM users, then you may skip over this chapter.

This section describes the procedure for granting permissions (see :ref:`Figure 1 <aom_02_0090__en-us_topic_0263893539_en-us_topic_0169701339_fig13279111625016>`).

Prerequisites
-------------

Learn about the permissions supported by AOM and choose policies or roles according to your requirements. See section "Permissions Management" in *AOM Service Overview*. For the permissions of other services, see section "Permission Description" in the help center.

Process
-------

.. _aom_02_0090__en-us_topic_0263893539_en-us_topic_0169701339_fig13279111625016:

.. figure:: /_static/images/en-us_image_0000002289582105.png
   :alt: **Figure 1** Process for granting AOM permissions

   **Figure 1** Process for granting AOM permissions

#. .. _aom_02_0090__en-us_topic_0263893539_en-us_topic_0169701339_li11838175082320:

   Create a user group and assign permissions.

   Create a user group on the IAM console, and assign the **AOM ReadOnlyAccess** policy to the group.

#. Create an IAM user.

   Create a user on the IAM console and add the user to the group created in :ref:`1 <aom_02_0090__en-us_topic_0263893539_en-us_topic_0169701339_li11838175082320>`.

#. Log in and verify permissions.

   Log in to the AOM console as the created user, and verify that it only has read permissions for AOM.

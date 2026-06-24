:original_name: aom_02_1202.html

.. _aom_02_1202:

Managing Access Rules
=====================

This section describes how to add, view, and delete access rules.

Prerequisites
-------------

-  A log group and log stream have been created. You can also create them on the **Add Access Rule** page.
-  A cluster, namespace, and workload are available.

Adding Access Rules
-------------------

To map the logs of CCE workloads from AOM to LTS, perform the following steps:

#. On the menu bar, choose **Monitoring Center**.
#. In the navigation pane, choose **Log Analysis** > **LTS Access**.
#. Click **Add Access Rule**.
#. Select an access type. **Access by Namespace**, **Access by Workload**, or **Automatic Mapping** are available.

   -  **Access by Namespace**: All logs of the selected namespace are connected to the specified log stream.

      a. **Rule Name**: Enter a rule name. Only letters, digits, hyphens (-), underscores (_), and periods (.) are allowed.
      b. **Cluster**: Select a cluster from the drop-down list.
      c. **Namespace**: Select a namespace from the drop-down list.
      d. **Workload**: Retain the default value **All**.
      e. **Container Name**: Select a container from the drop-down list.
      f. Set an access rule.

         -  **Access all logs**: If you select this option, select a log group and log stream.
         -  **Specify log paths**: If you select this option, specify a log path and then select a log group and log stream.

   -  **Access by Workload**: Logs of the selected workload are connected to the specified log stream.

      a. **Rule Name**: Enter a rule name. Only letters, digits, hyphens (-), underscores (_), and periods (.) are allowed.
      b. **Cluster**: Select a cluster from the drop-down list.
      c. **Namespace**: Select a namespace from the drop-down list.
      d. **Workload**: Select one or more workloads from the drop-down list.
      e. **Container Name**: Select a container from the drop-down list.
      f. Set an access rule.

         -  **Access all logs**: If you select this option, select a log group and log stream.
         -  **Specify log paths**: If you select this option, specify a log path and then select a log group and log stream.

   -  **Automatic Mapping**: Workload logs are automatically connected to the generated log streams with the same names as the workloads.

      a. **Rule Name**: Enter a rule name. Only letters, digits, hyphens (-), underscores (_), and periods (.) are allowed.

      b. **Cluster**: Select a cluster from the drop-down list.

      c. **Namespace**: Select a namespace from the drop-down list.

      d. **Workload**: Select one or more workloads from the drop-down list.

         If you select one workload, the rule name is changed to **Custom rule name_0** after the rule is created, for example, **test_0**. If you select multiple workloads, the rule names are changed to **Custom rule name_0**, **Custom rule name_1**, and so on, such as **test_0** and **test_1**.

      e. Set an access rule: Select a log group and specify a log stream prefix. A log stream will be generated based on the log stream prefix and workload name. By default, all logs of the selected workload are connected.


Managing Access Rules
---------------------

On the **LTS Access** page, you can search for, view, edit, and delete access rules.

-  Search

   Click the search box, select a filter criterion, for example, **Workload**, and then select options under it. You can also directly enter a keyword in the search box. In this case, the system searches for information based on access rule names by default.

-  View

   In the rule list, view the cluster name and namespace of the created rule. Click |image1| in the upper right corner of the search box to customize the display of columns. Click a log group name in the **Log Group** column to go to the log group details page on the LTS console.

-  Modify

   On the **LTS Access** page, click **Edit** in the **Operation** column to edit an access rule. For details about the impact of modifying an access rule, see :ref:`Modifying a Mapping <aom_02_1201__section42756211404>`.

-  Delete

   On the **LTS Access** page, click **Delete** in the **Operation** column to delete an access rule. Select one or more access rules and click **Delete** above the rule list.

   .. note::

      Deleted access rules or mapped log streams cannot be recovered. Exercise caution when performing this operation. For details about the impact of deleting an access rule, see :ref:`Deleting a Mapping <aom_02_1201__section2327059232>`.

Other Operations
----------------

On the **Access LTS** page, click **Go to LTS Console** to go to the LTS console and create a log group and log stream for mapping.

.. |image1| image:: /_static/images/en-us_image_0000002482792956.png

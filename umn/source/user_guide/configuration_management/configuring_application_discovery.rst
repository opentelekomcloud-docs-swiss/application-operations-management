:original_name: aom_02_0023.html

.. _aom_02_0023:

Configuring Application Discovery
=================================

AOM can discover applications and collect their metrics based on configured rules. Application discovery supports both automatic and manual configuration. This section focuses on manual configuration.

-  **Automatic configuration**

   After you install the ICAgent on a host according to :ref:`Installing the ICAgent <aom_02_0012>`, the ICAgent automatically discovers applications on the host based on :ref:`Built-in Service Discovery Rules <aom_02_0023__section938317591962>` and displays them on the **Application Monitoring** page.

-  **Manual configuration**

   After you add a custom application discovery rule on the application discovery page and apply it to the host where the ICAgent is installed (for details, see :ref:`Installing the ICAgent <aom_02_0012>`), the ICAgent discovers applications on the host based on the configured service discovery rule and displays them on the **Application Monitoring** page.

Filtering Rules
---------------

The ICAgent will periodically detect processes on the target host. The effect is similar to that of running the **ps -e -o pid,comm,lstart,cmd \| grep -v defunct** command. Then, the ICAgent checks whether processes match the filtering rules in :ref:`Table 1 <aom_02_0023__table11580171542711>`. If a process meets a filtering rule, the process is filtered out and is not discovered by AOM. If a process does not meet any filtering rules, the process is not filtered and is discovered by AOM.

ICAgent detection results may as follows:

.. code-block::

      PID COMMAND                          STARTED CMD
        1 systemd         Tue Oct  2 21:12:06 2018 /usr/lib/systemd/systemd --switched-root --system --deserialize 20
        2 kthreadd        Tue Oct  2 21:12:06 2018 [kthreadd]
        3 ksoftirqd/0     Tue Oct  2 21:12:06 2018 (ksoftirqd/0)
     1140 tuned           Tue Oct  2 21:12:27 2018 /usr/bin/python -Es /usr/sbin/tuned -l -P
     1144 sshd            Tue Oct  2 21:12:27 2018 /usr/sbin/sshd -D
     1148 agetty          Tue Oct  2 21:12:27 2018 /sbin/agetty --keep-baud 115200 38400 9600 hvc0 vt220
     1154 docker-containe Tue Oct  2 21:12:29 2018 docker-containerd -l unix:///var/run/docker/libcontainerd/docker-containerd.sock --shim docker-containerd-shim --start-timeout 2m --state-dir /var/run/docker/libcontainerd/containerd --runtime docker-runc --metrics-interval=0

.. _aom_02_0023__table11580171542711:

.. table:: **Table 1** Filtering rules

   +----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | Filtering Rule                                                                                                                                                                                                                                                                         | Example                                                                                                                                            |
   +========================================================================================================================================================================================================================================================================================+====================================================================================================================================================+
   | If the **COMMAND** value of a process is **docker-containe**, **vi**, **vim**, **pause**, **sshd**, **ps**, **sleep**, **grep**, **tailf**, **tail**, or **systemd-udevd**, and the process is not running in the container, the process is filtered out and is not discovered by AOM. | In the preceding information, the process whose **PID** is **1154** is not discovered by AOM because its **COMMAND** value is **docker-containe**. |
   +----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | If the **CMD** value of a process starts with **[** and ends with **]**, the process is filtered out and is not discovered by AOM.                                                                                                                                                     | In the preceding information, the process whose **PID** is **2** is not discovered by AOM because its **CMD** value is **[kthreadd]**.             |
   +----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | If the **CMD** value of a process starts with **(** and ends with **)**, the process is filtered out and is not discovered by AOM.                                                                                                                                                     | In the preceding information, the process whose **PID** is **3** is not discovered by AOM because its **CMD** value is **(ksoftirqd/0)**.          |
   +----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+
   | If the **CMD** value of a process starts with **/sbin/**, the process is filtered out and is not discovered by AOM.                                                                                                                                                                    | In the preceding information, the process whose **PID** is **1148** is not discovered by AOM because its **CMD** value starts with **/sbin/**.     |
   +----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------+

.. _aom_02_0023__section938317591962:

Built-in Service Discovery Rules
--------------------------------

AOM provides **Default_Rule**, ServiceStage provides **servicestage-default-rule**, and ICAgent has the built-in **Sys_Rule**. These rules are executed on all hosts, including those added later. The priorities of the three built-in discovery rules are as follows: **Sys_Rule** > **servicestage-default-rule** > **Default_Rule**. Rule details are as follows:

**Sys_Rule** (cannot be disabled)

-  For the component name, obtain the value of **-Dapm_tier** in the command, the value of the environment variable **PAAS_APP_NAME**, and the value of **-Dapm_tier** of the environment variable **JAVA_TOOL_OPTIONS** based on the priorities in descending order.
-  For the application name, obtain the value of **-Dapm_application** in the command, the value of environment variable **PAAS_MONITORING_GROUP**, and the value of **-Dapm_application** in the environment variable **JAVA_TOOL_OPTIONS** based on the priorities in descending order.

In the following example, the component name is **atps-demo** and the application name is **atpd-test**.

.. code-block:: text

   PAAS_MONITORING_GROUP=atpd-test
   PAAS_APP_NAME=atps-demo
   JAVA_TOOL_OPTIONS=-javaagent:/opt/oss/servicemgr/ICAgent/pinpoint/pinpoint-bootstrap.jar -Dapm_application=atpd-test -Dapm_tier=atps-demo

.. note::

   **sys_rule** (built-in application discovery rule) is used to discover CCE workloads in the CCE scenario (except the APM scenario).

**servicestage-default-rule** (can be disabled)

Detect the processes whose environment variables contain **CAS_APPLICATION_NAME**, **CAS_COMPONENT_NAME**, and **CAS_ENVIRONMENT_NAME**.

Obtain the value of the environment variable **CAS_COMPONENT_NAME** and combine it as the component name.

Obtain the value of the environment variable **CAS_APPLICATION_NAME** and combine it as the application name.

.. note::

   Nginx of a version earlier than 1.19 does not support manual configuration of environment variables. Therefore, the data source of the Nginx component configured on ServiceStage may be displayed as **CCE** on the **Component Monitoring** page of AOM. To solve this problem, use Nginx of 1.19 or a later version, manually configure environment variables such as **CAS_COMPONENT_NAME** and **CAS_COMPONENT_ID**.

**Default_Rule** (can be disabled)

-  If the **COMMAND** value of a process is **java**, obtain the name of the JAR package in the command, the main class name in the command, and the first keyword that does not start with a hyphen (-) in the command based on the priorities in descending order as the component name, and use the default value **unknownapplicationname** as the application name.
-  If the **COMMAND** value of a process is **python**, obtain the name of the first .py/.pyc script in the command as the component name, and use the default value **unknownapplicationname** as the application name.
-  If the **COMMAND** value of a process is **node**, obtain the name of the first .js script in the command as the component name, and use the default value **unknownapplicationname** as the application name.

Custom Discovery Rules
----------------------

The priorities of discovery rules are as follows: Sys_Rule > Custom discovery rules > Default_Rule. **servicestage-default-rule** is also a custom discovery rule.

#. In the navigation pane, choose **Configuration Management** > **Service Discovery**.

#. Click **Add Custom Application Discovery Rule** and configure an application discovery rule.

#. Select a host for pre-detection.

   a. Customize a rule name, for example, **ruletest**.
   b. Select a typical host, for example, **hhhhhh-27465**, to check whether the application discovery rule is valid. The hosts that execute the rule will be configured in :ref:`6 <aom_02_0023__li1434613512472>`. Then, click **Next**.

#. Set an application discovery rule.

   a. Click **Add Check Items**. AOM can discover processes that meet the conditions of check items.

      For example, AOM can detect the processes whose command parameters contain **ovs-vswitchd unix:** and environment variables contain **SUDO_USER=paas**.

      .. note::

         -  To precisely detect processes, you are advised to add check items about unique features of the processes.
         -  You need to add one check item at least and can add five check items at most. If there are multiple check items, AOM only discovers the processes that meet the conditions of all check items.

   b. After adding check items, click **Detect** to search for the processes that meet the conditions.

      If no process is detected within 20s, modify the application discovery rule and detect processes again. Go to the next step only when at least one process is detected.

#. Set a component name.

   a. Set an application name.

      In the **Application Name Settings** area, click **Add Naming Rule** to set an application name for the discovered process.

      .. note::

         -  If you do not set an application name, **unknownapplicationname** is used by default.
         -  When you add multiple naming rules, all the naming rules are combined as the application name of the process. Metrics with the same application name are aggregated.

   b. Set a component name.

      In the **Component Name Settings** area, click **Add Naming Rule** to set a component name for the discovered process.

      .. note::

         -  The component name cannot be left blank.
         -  When you add multiple naming rules, all the naming rules are combined as the component name of the process. Metrics with the same component name are aggregated.

   c. Preview the component name.

      If the application or component name does not meet your requirements, click |image1| in the **Preview Component Name** table for renaming.

#. .. _aom_02_0023__li1434613512472:

   Set a priority and detection range.

   a. Set a priority: When there are multiple rules, set priorities. Enter 1 to 9999. A smaller value indicates a higher priority. For example, **1** indicates the highest priority and **9999** indicates the lowest priority.

      .. note::

         Do not use multiple custom discovery rules with the same priority for the same process.

   b. Set a detection range: Select a host to be detected. That is, select the host to which the configured rule is applied. If no host is selected, this rule will be executed on all hosts, including those added later.

#. Click **Add** to complete the configuration. AOM collects metrics of the process.

#. Wait for about two minutes, choose **Monitoring** > **Component Monitoring** in the navigation pane, select the target host (for example, **hhhhhh-27465**) from the cluster drop-down list, and find the target component (for example, **/openvswitch/**) that has been monitored.

.. note::

   Custom discovery rules cannot be used to discover workload processes in the CCE scenario. You are advised to use custom discovery rules to discover non-workload processes in the CCE scenario or processes in the VM scenario.

More Operations
---------------

After creating an application discovery rule, you can also perform the operations described in :ref:`Table 2 <aom_02_0023__table62191141172620>`.

.. _aom_02_0023__table62191141172620:

.. table:: **Table 2** Related operations

   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Operation                         | Description                                                                                                       |
   +===================================+===================================================================================================================+
   | Viewing rule details              | In the **Name** column, click the name of an application discovery rule.                                          |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Enabling or disabling a rule      | -  Click **Enable** in the **Operation** column.                                                                  |
   |                                   | -  Click **Disable** in the **Operation** column. After a rule is disabled, AOM does not collect process metrics. |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Deleting a rule                   | -  To delete a discovery rule, click **Delete** in the **Operation** column.                                      |
   |                                   |                                                                                                                   |
   |                                   | .. note::                                                                                                         |
   |                                   |                                                                                                                   |
   |                                   |    Built-in application discovery rules cannot be deleted.                                                        |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+
   | Modifying a rule                  | Click **Modify** in the **Operation** column.                                                                     |
   |                                   |                                                                                                                   |
   |                                   | .. note::                                                                                                         |
   |                                   |                                                                                                                   |
   |                                   |    Built-in application discovery rules cannot be modified.                                                       |
   +-----------------------------------+-------------------------------------------------------------------------------------------------------------------+

.. |image1| image:: /_static/images/en-us_image_0000001448643217.png

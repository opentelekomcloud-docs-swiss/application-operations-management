:original_name: aom_05_0003.html

.. _aom_05_0003:

Discovering Applications
========================

Overview
--------

AOM can discover applications deployed on hosts and collects their metrics based on preset rules. The discovered applications and their metric data will be displayed on the **Application Monitoring** and **O&M** pages.

The relationship between applications and components is as follows:

-  Component refers to the smallest unit for completing a task. It can be a microservice, container process, or common process.
-  Application refers to a complete service module and consists of multiple components.

After application discovery is configured, you can use AOM to monitor application metrics and associate related alarms. Mainly, AOM can:

#. Provide association relationships between applications and components, between components and component instances, and between applications and hosts.
#. Enable you to search for associated components and logs.
#. Aggregate component metrics (so that you can obtain aggregated results of all component instances).

Procedure
---------

#. On the menu bar, choose **Monitoring Center**.

#. In the navigation pane, choose **Configuration Management** > **Application Discovery**.

#. Click **Add Custom Application Discovery Rule** and configure an application discovery rule.

#. Select a host for pre-detection.

   a. Customize a rule name, for example, **ruletest**.
   b. Select a typical host, for example, **host-test**, to check whether the application discovery rule is valid. The hosts that execute the rule will be configured in :ref:`7 <aom_05_0003__li1493910720017>`. Then, click **Next**.

#. Set an application discovery rule.

   a. Click **Add Check Items**. AOM can discover processes that meet the conditions of check items.

      For example, AOM can detect the processes whose command parameters contain **ovs-vswitchd unix:** and environment variables contain **SUDO_USER=paas**.

      .. note::

         -  To precisely detect processes, you are advised to add check items about unique features of the processes.
         -  You need to add one check item at least and can add five check items at most. If there are multiple check items, AOM only discovers the processes that meet the conditions of all check items.

   b. After adding check items, click **Detect** to search for the processes that meet the conditions.

      If no process is detected within 10s, modify the application discovery rule and detect processes again. Go to the next step only when at least one process is detected.

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

      If the application or component name does not meet your requirements, locate the name in the **Preview Component Name** table and rename it.

#. .. _aom_05_0003__li1493910720017:

   Set a priority and detection range.

   a. Set a priority: When there are multiple rules, set priorities. Enter 1 to 9999. The default value is **9999**. The smaller value, the higher priority. For example, **1** indicates the highest priority and **9999** indicates the lowest priority.

      .. note::

         Do not use multiple custom discovery rules with the same priority for the same process.

   b. Set a detection range: Select a host to be detected. That is, select the host to which the configured rule is applied. If no host is selected, this rule will be executed on all hosts, including those added later.

#. Click **Add** to complete the configuration. AOM collects metrics of the process.

#. Wait for about two minutes, choose **Infrastructure Monitoring** > **Component Monitoring** in the navigation pane, select the target host (for example, **host-test**) from the cluster drop-down list, and find the target component (for example, **/openvswitch/**) that has been monitored.

#. View the application status.

   a. In the navigation pane, choose **Infrastructure Monitoring** > **Application Monitoring**.

   b. Click an application to view its components and other resources.


      .. figure:: /_static/images/en-us_image_0000002482912898.png
         :alt: **Figure 1** Querying application details

         **Figure 1** Querying application details

   c. Click the **Component List** tab and view the component information.


      .. figure:: /_static/images/en-us_image_0000002515112901.png
         :alt: **Figure 2** Viewing a component

         **Figure 2** Viewing a component

   d. Click the **Host List** tab to view the host information.


      .. figure:: /_static/images/en-us_image_0000002482792922.png
         :alt: **Figure 3** Viewing a host

         **Figure 3** Viewing a host

   e. Click the **Alarms** tab to view alarms.

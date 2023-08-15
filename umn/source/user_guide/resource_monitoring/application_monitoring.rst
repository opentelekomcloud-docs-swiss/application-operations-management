:original_name: aom_02_0050.html

.. _aom_02_0050:

Application Monitoring
======================

An application is a group of identical or similar components divided based on business requirements. Applications are classified into system applications and custom applications. System applications are discovered based on built-in discovery rules, and custom applications are discovered based on custom rules.

After application discovery rules are set, Application Operations Management (AOM) automatically discovers applications that meet the rules and monitors related metrics. For details, see :ref:`Configuring Application Discovery <aom_02_0023>`.

.. note::

   The ICAgent reports resource information every ten minutes. The resource status changes are described as follows:

   -  If the ICAgent on a host does not report resource information **for three consecutive times**, the system determines that the resource has been deleted. Therefore, the host status is displayed as **Deleted** within 30 minutes after the ICAgent is uninstalled.
   -  When the ICAgent on a host reports resource information **for one time**, the system determines that the resource is restored. The host status is displayed as **Normal** ten minutes after the ICAgent is reinstalled.

Procedure
---------

#. In the navigation pane, choose **Monitoring** > **Application Monitoring**.

#. Click an application. On the details page that is displayed, manage and monitor components in batches by application.

   You can also view the component list, host list, and alarm analysis result of the current application.

#. On the application details page, click the **View Monitor Graphs** tab and monitor application metrics.

   You can also perform the following operations:

   -  **Adding an application**

      For the same or similar components that are discovered by default discovery rules or that are not installed with APM probes, you can group them logically, that is, add them to the same application for monitoring.

      In the upper right corner of the **Application Monitoring** page, click **Create Application** to add a custom application discovery rule. For details, see :ref:`Configuring Application Discovery <aom_02_0023>`. After the rule is added, you can monitor the application. AOM can display O&M information by component. For details, see :ref:`Component Monitoring <aom_02_0007>`.

   -  **Creating a view template**

      AOM provides the default view template (**Application Template**) that you can modify. You can also click the plus sign (+) in |image1| to add you own template.

   -  **Adding a metric graph**

      You can click |image2| to add a line graph or |image3| to add a digit graph to the view template. You can also delete, move, and copy metric graphs in the view template according to :ref:`Dashboard <aom_02_0003>`.

   -  **Adding a view template to a dashboard**

      On the application details page, choose **More** > **Add To Dashboard** in the upper right corner to add the view template to the dashboard for monitoring.

.. |image1| image:: /_static/images/en-us_image_0000001398562908.png
.. |image2| image:: /_static/images/en-us_image_0000001448483009.png
.. |image3| image:: /_static/images/en-us_image_0000001398083204.png

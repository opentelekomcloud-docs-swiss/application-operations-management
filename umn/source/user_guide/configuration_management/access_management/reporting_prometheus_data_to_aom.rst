:original_name: aom_02_0922.html

.. _aom_02_0922:

Reporting Prometheus Data to AOM
================================

If you have deployed the open-source Prometheus, go to :ref:`3 <aom_02_0922__li13345647121718>`.

This section describes how to configure the :ref:`access code <aom_02_0922__li622313202155>` in the Prometheus configuration file and make the configuration effective.

Prerequisites
-------------

You have created an ECS.

Procedure
---------

#. Install and start Prometheus. For details, see `Prometheus official documentation <https://prometheus.io/docs/prometheus/latest/getting_started/>`__.

#. .. _aom_02_0922__li622313202155:

   Add an access code.

   a. Log in to the AOM console. In the navigation pane, choose **Global Configuration**.
   b. In the right pane, click **Add Access Code**.
   c. In the dialog box that is displayed, click **OK**. The system automatically generates an access code.

      .. note::

         -  You can create up to two access codes for each project.
         -  An access code is an identity credential for calling APIs. Keep your access code secure.

   d. After the access code is added, click |image1| to view it. To delete the access code, click **Delete** in the **Operation** column. Deleted access codes cannot be recovered. Exercise caution when performing this operation.

#. .. _aom_02_0922__li13345647121718:

   Log in to the ECS and locate the Prometheus configuration file.

   Run the following command:

   .. code-block::

      ./prometheus --config.file=prometheus.yml

   Add the following configuration to the end of the **prometheus.yml** file:

   .. code-block::

      remote_write:
        - url: 'https://${POD_LB_IP}:8149/v1/{project_id}/push'
          tls_config:
            insecure_skip_verify: true
          bearer_token: '{access_code}'

   Parameter description:

   -  **POD_LB_IP**: IP address of the specified POD_LB. To obtain the IP address, choose **Configuration Management** > **Agent Management** and obtain it from the command for installing an ICAgent.
   -  **project_id**: project ID.

   The following shows an example. You need to configure the italic part.

   .. code-block::

      # my global config
      global:
      scrape_interval:     15s # Set the scrape interval to every 15 seconds. Default is every 1 minute.
      evaluation_interval: 15s # Evaluate rules every 15 seconds. The default is every 1 minute.
      # scrape_timeout is set to the global default (10s).

      # Alertmanager configuration
      alerting:
      alertmanagers:
        - static_configs:
        - targets:
      # - alertmanager:9093

      # Load rules once and periodically evaluate them according to the global 'evaluation_interval'.
      rule_files:
      # - "first_rules.yml"
      # - "second_rules.yml"

      # A scrape configuration containing exactly one endpoint to scrape:
      # Here it's Prometheus itself.
      scrape_configs:
      # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
        - job_name: 'prometheus'

      # metrics_path defaults to '/metrics'
      # scheme defaults to 'http'.

      static_configs:
        - targets: ['localhost:9090']
      remote_write:
        - url: 'https://${POD_LB_IP}:8149/v1/{project_id}/push'
          tls_config:
            insecure_skip_verify: true
          bearer_token: 'fVkvjOqghcIARvZZEEWhwSwxesmKz5Efsx9vxZSNGCXEffcjPxxxxxx'

#. Check the private domain name.

   In the preceding example, data is reported through the intranet. Ensure that the host where Prometheus is located can resolve private domain names.

#. Restart Prometheus.

#. You can :ref:`use Grafana to query metric data in AOM <aom_02_0923>` to check whether data is successfully reported after the preceding configuration is modified.

.. |image1| image:: /_static/images/en-us_image_0000002289582129.png

:original_name: mon_01_0076.html

.. _mon_01_0076:

Reporting Prometheus Data to AOM
================================

On the **Settings** tab page of the default Prometheus instance or of the Prometheus instance for CCE, or remote write, you can obtain the remote write address of the current Prometheus instance. Native Prometheus metrics can then be reported to AOM through remote write. In this way, time series data can be stored for long.

If the open-source Prometheus has been deployed and is being used, directly go to :ref:`4 <mon_01_0076__en-us_topic_0000001593789690_li13345647121718>`.

Prerequisites
-------------

-  You have created an ECS.
-  Your service has been connected for Prometheus monitoring. For more details, see:

   -  :ref:`Prometheus Instance for CCE <mon_01_0073>`
   -  :ref:`Prometheus Instance for Remote Write <mon_01_0070>`

Procedure
---------

#. Install and start Prometheus. For details, see `Prometheus official documentation <https://prometheus.io/docs/prometheus/latest/getting_started/>`__.

#. Add an access code.

   a. On the menu bar, choose **Monitoring Center**.
   b. In the navigation pane, choose **Global Configuration**.
   c. In the navigation pane on the left, choose **Authentication**. Click **Add Access Code**.
   d. In the dialog box that is displayed, click **OK**. The system then automatically generates an access code.

   .. note::

      -  You can create up to two access codes for each project.
      -  An access code is an identity credential for calling APIs. Keep your access code secure.

#. .. _mon_01_0076__en-us_topic_0000001593789690_li5262102016617:

   Obtain the configuration code for Prometheus remote write.

   a. On the menu bar, choose **Monitoring Center**.

   b. In the navigation pane on the left, choose **Prometheus Monitoring** > **Instances**. In the instance list, click the target Prometheus instance.

   c. On the displayed page, choose **Settings** in the navigation pane and obtain the configuration code for Prometheus remote write from the **Service Addresses** area.


      .. figure:: /_static/images/en-us_image_0000002482792888.png
         :alt: **Figure 1** Configuration code for Prometheus remote write

         **Figure 1** Configuration code for Prometheus remote write

#. .. _mon_01_0076__en-us_topic_0000001593789690_li13345647121718:

   Log in to the target ECS and configure the **prometheus.yml** file.

   Run the following command to find and start the **prometheus.yml** file:

   .. code-block::

      ./prometheus --config.file=prometheus.yml

   Add the configuration code for Prometheus remote write obtained in :ref:`3 <mon_01_0076__en-us_topic_0000001593789690_li5262102016617>` to the end of the **prometheus.yml** file.

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
      # Replace the italic content with the configuration code for Prometheus remote write obtained in 3 <mon_01_0076__en-us_topic_0000001593789690_li5262102016617>.
      remote_write:
        - url: 'https://aom-internal-access.eu-ch2.sc.otc.t-systems.com/v1/a43441***e5be/6fbed2***d972/push'
          tls_config:
            insecure_skip_verify: true
          bearer_token: 'SE**iH'

#. Check the private domain name.

   In the preceding example, data is reported through the intranet. Therefore, ensure that the host where Prometheus is located can resolve the private domain name.

#. Restart Prometheus.

#. :ref:`View metric data in AOM using Grafana <mon_01_0077>` to check whether data is successfully reported after the preceding configurations are modified.

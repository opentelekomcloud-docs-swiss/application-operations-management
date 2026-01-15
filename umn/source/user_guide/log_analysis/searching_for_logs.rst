:original_name: aom_02_0009.html

.. _aom_02_0009:

Searching for Logs
==================

AOM enables you to quickly query logs, and use log source information and context to locate faults.

#. In the navigation pane, choose **Log Analysis** > **Log Search**.

#. On the **Log Search** page, click the **Component**, **System**, or **Host** tab and set filter criteria as prompted.

   .. note::

      a. You can search for logs by component, system, or host.

         -  For component logs, you can set filter criteria such as **Cluster**, **Namespace**, and **Component**. You can also click **Advanced Search** and set filter criteria such as **Instance**, **Host**, and **File**, and choose whether to enable **Hide System Component**.
         -  For system logs, you can set filter criteria such as **Cluster** and **Host**.
         -  For host logs, you can set filter criteria such as **Cluster** and **Host**.

      b. Enter a keyword in the search box. Rules are as follows:

         -  Enter a case-sensitive keyword.
         -  Enter a keyword for exact search. A keyword refers to a word between two adjacent delimiters.
         -  Enter a keyword containing an asterisk (*) or a question mark (?) for fuzzy search. For example, enter **ER?OR**, **\*ROR**, or **ER*R**.
         -  Enter a phrase for exact search. For example, enter **Start to refresh** or **Start-to-refresh**. Note that hyphens (-) are :ref:`delimiters <aom_02_0082>`.
         -  Enter a keyword containing AND (&&) or OR (||) for search. For example, enter **query logs&&error\*** or **query logs||error**.
         -  If no log is found, you are advised to narrow down the search scope and add an asterisk (*) before and after the keyword for fuzzy match.

#. .. _aom_02_0009__li34212241:

   View the search results of logs.

   The search results are sorted based on the log collection time. The keywords in the search results are highlighted. You can click |image1| in the **Time** column to switch the sorting order. |image2| indicates the default order. |image3| indicates the ascending order by time (the latest log is displayed at the bottom). |image4| indicates the descending order by time (the latest log is displayed at the top).

   a. AOM allows you to view context. Click **Context** in the **Operation** column to view the previous or next logs of a log for fault locating.

      -  In the **Display Rows** drop-down list, set the number of rows that display raw context data of the log.

         .. note::

            For example, select **200** from the **Display Rows** drop-down list.

            -  If there are more than or equal to 100 logs printed prior to a log and more than or equal to 99 logs printed following the log, the preceding 100 logs and following 99 logs are displayed as the context.
            -  If there are fewer than 100 logs (for example, 90) printed prior to a log and fewer than 99 logs (for example, 80) printed following the log, the preceding 90 logs and following 80 logs are displayed as the context.

      -  Click **Export Current Page** to export displayed raw context data of the log to a local PC.

   .. note::

      To ensure that tenant hosts and services run properly, some components (for example, kube-dns) provided by the system will run on the tenant hosts. The logs of these components are also queried during tenant log query.

   b. Click **View Details** in the **Operation** column that contains the target log. Its details such as host IP address and source are displayed.

#. (Optional) Click |image5| on the right of the **Log Search** page, select an export format, and export the search result to a local PC.

   Logs are sorted according to the order set in :ref:`3 <aom_02_0009__li34212241>` and a maximum of 5000 logs can be exported. For example, when 6000 logs in the search result are sorted in the descending order, only the first 5000 logs can be exported.

   Logs can be exported in CSV or TXT format. You can select a format as required. If you select the CSV format, detailed information (such as the log content, host IP address, and source) can be exported. Only log content will be exported when you select the TXT format. Each line indicates a log.

#. (Optional) Click **Configure Dumps** to dump the searched logs to the same log file in the OBS bucket at a time. For details, see :ref:`Adding One-Off Dumps <aom_02_0080__en-us_topic_0169698290_section1130151415546>`.

.. |image1| image:: /_static/images/en-us_image_0000002289582605.png
.. |image2| image:: /_static/images/en-us_image_0000002289469537.png
.. |image3| image:: /_static/images/en-us_image_0000002289469529.png
.. |image4| image:: /_static/images/en-us_image_0000002254869276.png
.. |image5| image:: /_static/images/en-us_image_0000002254812312.png

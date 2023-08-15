:original_name: aom_02_0009.html

.. _aom_02_0009:

Searching for Logs
==================

AOM enables you to quickly query logs, and use log source information and context to locate faults.

#. In the navigation pane, choose **Log** > **Log Search**.

#. On the **Log Search** page, click the **Component**, **System**, or **Host** tab and set filter criteria as prompted.

   .. note::

      a. You can search for logs by component, system, or host.

         -  For component logs, you can set filter criteria such as **Cluster**, **Namespace**, and **Component**. You can also click **Advanced Search** and set filter criteria such as **Instance**, **Host**, and **File Name**, and choose whether to enable **Hide System Component**.
         -  For system logs, you can set filter criteria such as **Cluster** and **Host**.
         -  For host logs, you can set filter criteria such as **Cluster**, and **Host**.

      b. Enter a keyword in the search box. Rules are as follows:

         -  Enter a case-sensitive keyword.
         -  Enter a keyword for exact search. A keyword refers to a word between two adjacent delimiters.
         -  Enter a keyword containing an asterisk (*) or a question mark (?) for fuzzy search. For example, enter **ER?OR**, **\*ROR**, or **ER*R**.
         -  Enter a phrase for exact search. For example, enter **Start to refresh** or **Start-to-refresh**. Note that hyphens (-) are :ref:`delimiters <aom_02_0082>`.
         -  Enter a keyword containing AND (&&) or OR (||) for search. For example, enter **query logs&&error\*** or **query logs||error**.
         -  If no log is found, you are advised to narrow down the search scope and add an asterisk (*) before and after the keyword for fuzzy match.

#. .. _aom_02_0009__li34212241:

   View the search results of logs.

   The search results are sorted based on the log collection time. The keywords in the search results are highlighted.

   By default, the descending order is used. You can click |image1| in the **Time** column to change the order. |image2| indicates the ascending order by time (that is, the latest log is displayed at the end). |image3| indicates the descending order by time (that is, the latest log is displayed at the top).

   a. Click |image4| on the left of the log list to view details such as host IP address and source.
   b. AOM allows you to view the surrounding logs of a specified log by clicking **View Context** in the **Operation** column, facilitating fault locating. Therefore, you do not need to search for logs in raw files.

      -  In the **Display Rows** drop-down list, set the number of rows that display raw context data of the log.

         .. note::

            For example, select **200** from the **Display Rows** drop-down list.

            -  If there are more than or equal to 100 logs printed prior to a log and more than or equal to 99 logs printed following the log, the preceding 100 logs and following 99 logs are displayed as the context.
            -  If there are fewer than 100 logs (for example, 90) printed prior to a log and fewer than 99 logs (for example, 80) printed following the log, the preceding 90 logs and following 80 logs are displayed as the context.

      -  Click **Export Current Page** to export displayed raw context data of the log to a local PC.

   .. note::

      To ensure that tenant hosts and services run properly, some components (for example, kube-dns) provided by the system will run on the tenant hosts. The logs of these components are also queried during tenant log query.

#. (Optional) Click |image5| on the right of the **Log Search** page, select an export format, and export the search result to a local PC.

   Logs are sorted according to the order set in :ref:`3 <aom_02_0009__li34212241>` and a maximum of 5000 logs can be exported. For example, when 6000 logs in the search result are sorted in the descending order, only the first 5000 logs can be exported.

   Logs can be exported in CSV or TXT format. You can select a format as required. If you select the CSV format, detailed information (such as the log content, host IP address, and source) can be exported, as shown in :ref:`Figure 1 <aom_02_0009__fig1785710409496>`. Only log content will be exported when you select the TXT format (as shown in :ref:`Figure 2 <aom_02_0009__fig9558111333018>`). Each line indicates a log.

   .. _aom_02_0009__fig1785710409496:

   .. figure:: /_static/images/en-us_image_0000001398562760.png
      :alt: **Figure 1** Exporting logs in CSV format

      **Figure 1** Exporting logs in CSV format

   .. _aom_02_0009__fig9558111333018:

   .. figure:: /_static/images/en-us_image_0000001398242952.png
      :alt: **Figure 2** Exporting logs in TXT format

      **Figure 2** Exporting logs in TXT format

.. |image1| image:: /_static/images/en-us_image_0000001448562733.png
.. |image2| image:: /_static/images/en-us_image_0000001398562772.png
.. |image3| image:: /_static/images/en-us_image_0000001398402788.png
.. |image4| image:: /_static/images/en-us_image_0000001398242960.png
.. |image5| image:: /_static/images/en-us_image_0000001448643057.png

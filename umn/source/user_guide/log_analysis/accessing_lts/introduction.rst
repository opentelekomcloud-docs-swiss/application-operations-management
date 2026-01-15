:original_name: aom_02_1201.html

.. _aom_02_1201:

Introduction
============

Log Tank Service (LTS) allows you to search for and dump logs. By setting access rules, you can map the logs of CCE workloads from AOM to LTS for analysis.

What Is Mapping?
----------------

AOM logs exist in LTS in the form of a log stream, as shown in :ref:`Figure 1 <aom_02_1201__fig11995544194720>`. You can view raw logs in configured log collection paths on AOM, but cannot view the AOM log stream on LTS. You can create a mapping by adding an access rule on AOM. After the mapping is created, you can view and analyze AOM logs on LTS.

.. _aom_02_1201__fig11995544194720:

.. figure:: /_static/images/en-us_image_0000002289582293.png
   :alt: **Figure 1** Before mapping

   **Figure 1** Before mapping

After you create log stream A and an access rule, the mapping from AOM to LTS is created. New AOM logs will be reported to log stream A. You can view all logs on AOM before and after the mapping. Historical logs in the AOM log stream will not be copied or migrated to log stream A, as shown in :ref:`Figure 2 <aom_02_1201__fig36185512471>`.

.. _aom_02_1201__fig36185512471:

.. figure:: /_static/images/en-us_image_0000002254868956.png
   :alt: **Figure 2** After mapping

   **Figure 2** After mapping

.. _aom_02_1201__section42756211404:

Modifying a Mapping
-------------------

If you modify a mapping, for example, change log stream A to log stream B, new logs will be reported to log stream B. You can view the content of AOM log stream and log stream B on AOM, but cannot view the content of log stream A, as shown in :ref:`Figure 3 <aom_02_1201__fig1663425210110>`.

.. _aom_02_1201__fig1663425210110:

.. figure:: /_static/images/en-us_image_0000002289582285.png
   :alt: **Figure 3** Modifying a mapping

   **Figure 3** Modifying a mapping

.. _aom_02_1201__section2327059232:

Deleting a Mapping
------------------

When you delete an access rule or a mapped log stream, the corresponding mapping is deleted. New logs are reported only to the AOM log stream. In this case, you cannot view the content of log stream A, as shown in :ref:`Figure 4 <aom_02_1201__fig188294571843>`. If the access rule is deleted but log stream A is not, you can still view the logs that have already been mapped on LTS.

.. _aom_02_1201__fig188294571843:

.. figure:: /_static/images/en-us_image_0000002254812004.png
   :alt: **Figure 4** Deleting a mapping

   **Figure 4** Deleting a mapping

.. note::

   Deleted access rules or mapped log streams cannot be recovered. Exercise caution when performing this operation.

Duplicate Mapping
-----------------

If a workload or file is mapped to both log streams A and B, new logs will be reported to both of them. Duplicate logs exist on AOM. Therefore, duplicate mapping is not recommended.


.. figure:: /_static/images/en-us_image_0000002289469201.png
   :alt: **Figure 5** Duplicate mapping

   **Figure 5** Duplicate mapping

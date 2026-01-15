:original_name: aom_06_0019.html

.. _aom_06_0019:

VM Metrics and Dimensions
=========================

In AOM, VMs refer to processes, and VM metrics refer to process metrics.

.. table:: **Table 1** Process metrics

   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Metric                                                            | Description                                                                                           | Value Range     | Unit            |
   +===================================================================+=======================================================================================================+=================+=================+
   | Total CPU cores (aom_process_cpu_limit_core)                      | Total number of CPU cores that have been applied for a measured object                                | >= 1            | Cores           |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Used CPU cores (aom_process_cpu_used_core)                        | Number of CPU cores used by a measured object                                                         | >= 0            | Cores           |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | CPU usage (aom_process_cpu_usage)                                 | CPU usage of a measured object. That is, the percentage of the used CPU cores to the total CPU cores. | 0%-100%         | %               |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Handles (aom_process_handle_count)                                | Number of handles used by a measured object                                                           | >= 0            | N/A             |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Max. handles (aom_process_max_handle_count)                       | Maximum number of handles used by a measured object                                                   | >= 0            | N/A             |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Total physical memory (aom_process_memory_request_megabytes)      | Total physical memory that has been applied for a measured object                                     | >= 0            | MB              |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Physical memory usage (aom_process_memory_usage)                  | Percentage of the used physical memory to the total physical memory                                   | 0%-100%         | %               |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Used physical memory (aom_process_memory_used_megabytes)          | Used physical memory of a measured object                                                             | >= 0            | MB              |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Status (aom_process_status)                                       | Process status                                                                                        | 0 or 1          | N/A             |
   |                                                                   |                                                                                                       |                 |                 |
   |                                                                   |                                                                                                       | -  0: Normal    |                 |
   |                                                                   |                                                                                                       | -  1: Abnormal  |                 |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Threads (aom_process_thread_count)                                | Number of threads used by a measured object                                                           | >= 0            | N/A             |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Total virtual memory (aom_process_virtual_memory_total_megabytes) | Total virtual memory that has been applied for a measured object                                      | >= 0            | MB              |
   +-------------------------------------------------------------------+-------------------------------------------------------------------------------------------------------+-----------------+-----------------+

.. table:: **Table 2** Dimensions of process metrics

   ================== ==================
   Dimension          Description
   ================== ==================
   appName            Service name
   clusterId          Cluster ID
   clusterName        Cluster name
   nameSpace          Cluster namespace
   processID          Process ID
   processName        Process name
   serviceID          Inventory ID
   aomApplicationName Application name
   aomApplicationID   Application ID
   processCmd         Process command ID
   ================== ==================

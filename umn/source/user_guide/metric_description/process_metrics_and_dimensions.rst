:original_name: aom_02_1022.html

.. _aom_02_1022:

Process Metrics and Dimensions
==============================

.. table:: **Table 1** Process metrics

   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Metric                                | Description                                                            | Value Range     | Unit            |
   +=======================================+========================================================================+=================+=================+
   | Total CPU cores (cpuCoreLimit)        | Total number of CPU cores that have been applied for a measured object | >= 1            | Cores           |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Used CPU cores (cpuCoreUsed)          | Number of CPU cores used by a measured object                          | >= 0            | Cores           |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | CPU usage (cpuUsage)                  | Percentage of the used CPU cores to the total CPU cores                | 0%-100%         | %               |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Handles (handleCount)                 | Number of handles used by a measured object                            | >= 0            | None            |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Total physical memory (memCapacity)   | Total physical memory that has been applied for a measured object      | >= 0            | MB              |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Physical memory usage (memUsage)      | Percentage of the used physical memory to the total physical memory    | 0%-100%         | %               |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Used physical memory (memUsed)        | Used physical memory of a measured object                              | >= 0            | MB              |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Status (status)                       | Process status                                                         | 0 or 1          | None            |
   |                                       |                                                                        |                 |                 |
   |                                       |                                                                        | -  0: Normal    |                 |
   |                                       |                                                                        | -  1: Abnormal  |                 |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Threads (threadsCount)                | Number of threads used by a measured object                            | >= 0            | None            |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+
   | Total virtual memory (virMemCapacity) | Total virtual memory that has been applied for a measured object       | >= 0            | MB              |
   +---------------------------------------+------------------------------------------------------------------------+-----------------+-----------------+

.. table:: **Table 2** Dimensions of process metrics

   =========== =================
   Dimension   Description
   =========== =================
   appName     Service name
   clusterId   Cluster ID
   clusterName Cluster name
   nameSpace   Cluster namespace
   processID   Process ID
   processName Process name
   serviceID   Inventory ID
   =========== =================

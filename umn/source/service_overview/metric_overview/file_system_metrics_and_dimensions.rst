:original_name: aom_06_0017.html

.. _aom_06_0017:

File System Metrics and Dimensions
==================================

.. table:: **Table 1** File system metrics

   +-------------------------------------------------------------------+-----------------------------------------------------------+------------------+-----------------+
   | Metric                                                            | Description                                               | Value Range      | Unit            |
   +===================================================================+===========================================================+==================+=================+
   | Available disk space (aom_node_disk_available_capacity_megabytes) | Disk space that has not been used                         | >= 0             | MB              |
   +-------------------------------------------------------------------+-----------------------------------------------------------+------------------+-----------------+
   | Total disk space (aom_node_disk_capacity_megabytes)               | Total disk space                                          | >= 0             | MB              |
   +-------------------------------------------------------------------+-----------------------------------------------------------+------------------+-----------------+
   | Disk read/write status (aom_node_disk_rw_status)                  | Read or write status of a disk                            | 0 or 1           | N/A             |
   |                                                                   |                                                           |                  |                 |
   |                                                                   |                                                           | -  0: read/write |                 |
   |                                                                   |                                                           | -  1: read-only  |                 |
   +-------------------------------------------------------------------+-----------------------------------------------------------+------------------+-----------------+
   | Disk usage (aom_node_disk_usage)                                  | Percentage of the used disk space to the total disk space | 0%-100%          | %               |
   +-------------------------------------------------------------------+-----------------------------------------------------------+------------------+-----------------+

.. table:: **Table 2** Dimensions of file system metrics

   =========== =================
   Dimension   Description
   =========== =================
   clusterId   Cluster ID
   clusterName Cluster name
   fileSystem  File system
   hostID      Host ID
   mountPoint  Mount point
   nameSpace   Cluster namespace
   nodeIP      Host IP address
   nodeName    Host name
   =========== =================

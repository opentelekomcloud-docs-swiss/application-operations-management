:original_name: aom_02_1018.html

.. _aom_02_1018:

File System Metrics and Dimensions
==================================

.. table:: **Table 1** File system metrics

   +----------------------------------------------+-----------------------------------------------------------+------------------+-----------------+
   | Metric                                       | Description                                               | Value Range      | Unit            |
   +==============================================+===========================================================+==================+=================+
   | Available disk space (diskAvailableCapacity) | Disk space that has not been used                         | >= 0             | MB              |
   +----------------------------------------------+-----------------------------------------------------------+------------------+-----------------+
   | Total disk space (diskCapacity)              | Total disk space                                          | >= 0             | MB              |
   +----------------------------------------------+-----------------------------------------------------------+------------------+-----------------+
   | Disk read/write status (diskRWStatus)        | Read/write status of a disk                               | 0 or 1           | None            |
   |                                              |                                                           |                  |                 |
   |                                              |                                                           | -  0: read/write |                 |
   |                                              |                                                           | -  1: read-only  |                 |
   +----------------------------------------------+-----------------------------------------------------------+------------------+-----------------+
   | Disk usage (diskUsedRate)                    | Percentage of the used disk space to the total disk space | >= 0             | %               |
   +----------------------------------------------+-----------------------------------------------------------+------------------+-----------------+

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

:original_name: aom_06_0016.html

.. _aom_06_0016:

Disk Metrics and Dimensions
===========================

.. table:: **Table 1** Disk metrics

   +-------------------------------------------------+-----------------------------------------------+-------------+------+
   | Metric                                          | Description                                   | Value Range | Unit |
   +=================================================+===============================================+=============+======+
   | Disk read rate (aom_node_disk_read_kilobytes)   | Volume of data read from a disk per second    | >= 0        | KB/s |
   +-------------------------------------------------+-----------------------------------------------+-------------+------+
   | Disk write rate (aom_node_disk_write_kilobytes) | Volume of data written into a disk per second | >= 0        | KB/s |
   +-------------------------------------------------+-----------------------------------------------+-------------+------+

.. table:: **Table 2** Dimensions of disk metrics

   ========== =================
   Dimension  Description
   ========== =================
   clusterId  Cluster ID
   diskDevice Disk name
   hostID     Host ID
   nameSpace  Cluster namespace
   nodeIP     Host IP address
   nodeName   Host name
   ========== =================

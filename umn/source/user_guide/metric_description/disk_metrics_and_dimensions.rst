:original_name: aom_02_1017.html

.. _aom_02_1017:

Disk Metrics and Dimensions
===========================

.. table:: **Table 1** Disk metrics

   +---------------------------------+-----------------------------------------------+-------------+------+
   | Metric                          | Description                                   | Value Range | Unit |
   +=================================+===============================================+=============+======+
   | Disk read rate (diskReadRate)   | Volume of data read from a disk per second    | >= 0        | KB/s |
   +---------------------------------+-----------------------------------------------+-------------+------+
   | Disk write rate (diskWriteRate) | Volume of data written into a disk per second | >= 0        | KB/s |
   +---------------------------------+-----------------------------------------------+-------------+------+

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

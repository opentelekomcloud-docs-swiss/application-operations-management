:original_name: aom_06_0024.html

.. _aom_06_0024:

Disk Partition Metrics
======================

.. note::

   -  If the host type is **CCE**, you can view disk partition metrics. The supported OSs are CentOS 7.6 and EulerOS 2.5.
   -  Log in to the CCE node as the **root** user and run the **docker info \| grep 'Storage Driver'** command to check the Docker storage driver type. If the command output shows driver type **Device Mapper**, the thin pool metrics can be viewed. Otherwise, the thin pool metrics cannot be viewed.

.. table:: **Table 1** Disk partition metrics

   +----------------------------------------------------+---------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Metric                                             | Description                                                                                 | Value Range     | Unit            |
   +====================================================+=============================================================================================+=================+=================+
   | Thin pool's metadata space usage                   | Percentage of the thin pool's used metadata space to the total metadata space on a CCE node | 0%-100%         | %               |
   |                                                    |                                                                                             |                 |                 |
   | (aom_host_diskpartition_thinpool_metadata_percent) |                                                                                             |                 |                 |
   +----------------------------------------------------+---------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Thin pool's data space usage                       | Percentage of the thin pool's used data space to the total data space on a CCE node         | 0%-100%         | %               |
   |                                                    |                                                                                             |                 |                 |
   | (aom_host_diskpartition_thinpool_data_percent)     |                                                                                             |                 |                 |
   +----------------------------------------------------+---------------------------------------------------------------------------------------------+-----------------+-----------------+
   | Thin pool's disk partition space                   | Total thin pool's disk partition space on a CCE node                                        | >= 0            | MB              |
   |                                                    |                                                                                             |                 |                 |
   | (aom_host_diskpartition_total_capacity_megabytes)  |                                                                                             |                 |                 |
   +----------------------------------------------------+---------------------------------------------------------------------------------------------+-----------------+-----------------+

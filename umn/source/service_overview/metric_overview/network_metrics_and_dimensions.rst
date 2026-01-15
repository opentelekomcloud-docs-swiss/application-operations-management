:original_name: aom_06_0015.html

.. _aom_06_0015:

Network Metrics and Dimensions
==============================

.. table:: **Table 1** Network metrics

   +--------------------------------------------------------------+--------------------------------------------------------------+-------------+-----------+
   | Metrics                                                      | Description                                                  | Value Range | Unit      |
   +==============================================================+==============================================================+=============+===========+
   | Downlink rate (BPS) (aom_node_network_receive_bytes)         | Inbound traffic rate of a measured object                    | >= 0        | Byte/s    |
   +--------------------------------------------------------------+--------------------------------------------------------------+-------------+-----------+
   | Downlink rate (PPS) (aom_node_network_receive_packets)       | Number of data packets received by a NIC per second          | >= 0        | Packets/s |
   +--------------------------------------------------------------+--------------------------------------------------------------+-------------+-----------+
   | Downlink error rate (aom_node_network_receive_error_packets) | Number of error packets received by a NIC per second         | >= 0        | Count/s   |
   +--------------------------------------------------------------+--------------------------------------------------------------+-------------+-----------+
   | Uplink rate (BPS) (aom_node_network_transmit_bytes)          | Outbound traffic rate of a measured object                   | >= 0        | Byte/s    |
   +--------------------------------------------------------------+--------------------------------------------------------------+-------------+-----------+
   | Uplink error rate (aom_node_network_transmit_error_packets)  | Number of error packets sent by a NIC per second             | >= 0        | Count/s   |
   +--------------------------------------------------------------+--------------------------------------------------------------+-------------+-----------+
   | Uplink rate (PPS) (aom_node_network_transmit_packets)        | Number of data packets sent by a NIC per second              | >= 0        | Packets/s |
   +--------------------------------------------------------------+--------------------------------------------------------------+-------------+-----------+
   | Total rate (BPS) (aom_node_network_total_bytes)              | Total inbound and outbound traffic rate of a measured object | >= 0        | Byte/s    |
   +--------------------------------------------------------------+--------------------------------------------------------------+-------------+-----------+

.. table:: **Table 2** Dimensions of network metrics

   ========= =================
   Dimension Description
   ========= =================
   clusterId Cluster ID
   hostID    Host ID
   nameSpace Cluster namespace
   netDevice NIC name
   nodeIP    Host IP address
   nodeName  Host name
   ========= =================

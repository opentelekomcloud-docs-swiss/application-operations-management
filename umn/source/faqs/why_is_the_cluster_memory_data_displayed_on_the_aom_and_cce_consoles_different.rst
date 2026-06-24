:original_name: aom_03_0026.html

.. _aom_03_0026:

Why Is the Cluster Memory Data Displayed on the AOM and CCE Consoles Different?
===============================================================================

The memory usage and total memory of a CCE cluster displayed on the **Container Insights** > **Cluster Monitoring** page of the AOM console are inconsistent with those displayed on the **Clusters** page of the CCE console.

Possible Cause
--------------

When a system is running, its firmware and BIOS will occupy some cluster memory, and the kernel program will also occupy some memory. You can only use the remaining memory, which is called **Mem Total**. Therefore, the memory you can use is not equal to the total memory.

On the **Clusters** page of the CCE console, the displayed cluster memory is the total memory. The displayed memory usage is calculated according to the following formula: Memory usage = Used memory/Total memory.

However, on the **Container Insights** > **Cluster Monitoring** page of the AOM console, the displayed memory is the actual cluster memory you can use (that is, **Mem Total**). The displayed memory usage is calculated based on this actual available memory.

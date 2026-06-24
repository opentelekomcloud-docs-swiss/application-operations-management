:original_name: mon_01_0062.html

.. _mon_01_0062:

What Is the Relationship Between the Time Range and Statistical Period?
=======================================================================

In AOM, a maximum of 1440 data points can be returned for a single metric query. The relationship between the time range and statistical period is as follows:

Maximum time range = Statistical period x 1440

If you select a time range shorter than or equal to the maximum time range, all the statistical periods that meet the preceding formula can be selected. For example, if you want to query metrics in the last hour, the available statistical periods are 1 minute and 5 minutes.

For a :ref:`dashboard <mon_01_0003>`, the relationship between the time range and statistical period is shown in the following table.

.. table:: **Table 1** Relationship between the time range and statistical period

   =============== ==========================================
   Time Range      Statistical Period
   =============== ==========================================
   Last 30 minutes 1 minute or 5 minutes
   Last hour
   Latest 6 hours  1 minute, 5 minutes, 15 minutes, or 1 hour
   Last day
   Last week       1 hour
   Custom          1 minute, 5 minutes, 15 minutes, or 1 hour
   =============== ==========================================

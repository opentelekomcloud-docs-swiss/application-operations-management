:original_name: aom_02_1002.html

.. _aom_02_1002:

What Is the Relationship Between the Time Range and Statistical Cycle?
======================================================================

In AOM, a maximum of 1440 data points can be returned for a single metric query. The relationship between the time range and statistical cycle is as follows:

Maximum time range = Statistical cycle x 1440

If you select a time range shorter than or equal to the maximum time range, all the statistical cycles that meet the preceding formula can be selected. For example, if you want to query metrics in the last hour, the available statistical cycles are 1 minute and 5 minutes.

For a :ref:`dashboard <aom_02_0003>`, the relationship between the time range and statistical cycle is shown in the following table.

.. table:: **Table 1** Relationship between the time range and statistical cycle

   ============ ==============================
   Time Range   Statistical Cycle
   ============ ==============================
   Last 1 hour  1 minute or 5 minutes
   Last 6 hours 1 minute, 5 minutes, or 1 hour
   Last 1 day
   Last 1 week  1 hour
   Last 15 days 1 hour
   Last 30 days
   ============ ==============================

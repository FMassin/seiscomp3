scqc determines quality parameters of seismic data streams. The output parameters
are time averaged quality control (QC) parameters in terms of waveform quality messages.
In regular intervals report messages are sent containing the short term average
representation of the specific QC parameter for a given time span. Alarm messages
are generated if the short term average (e.g. 90s) of a QC parameter differs from
the long term average (e.g. 3600s) more than a defined threshold.
To avoid an excessive load, QC messages are sent distributed over time.

.. _scqc-fig-times:

.. figure:: media/times.png
   :align: center
   :width: 16cm

   Times describing the data records for calculating
   :ref:`delay<scqc-delay>` and :ref:`latency<scqc-latency>`.

The following parameters are determined:


.. _scqc-delay:

Delay [s]
 Time difference between arrival time of last record at the SeisComP3 system
 and end time of last record (see :ref:`Figure<scqc-fig-times>`):

 .. math::

   delay = t_{arr1} - t_{12}.

.. _scqc-latency:

Latency [s]
 Time difference between the end times of consecutive records (see :ref:`Figure<scqc-fig-times>`):

 .. math::

   latency = t_{arr2} - t_{arr1}.

 For constant and low delays, latency is approximately the mean record length.

Offset [counts]
 Average value of all samples of a record.

RMS [counts]
 Offset corrected root mean square (RMS) value of a record.

Spike (interval [s], amplitude [counts])
 In case of the occurrence of a spike in a record this parameter delivers the
 time interval between adjacent spikes and the mean amplitude of the spike;
 internally a list of spikes is stored (spike time, spike amplitude); the spike
 finder algorithm is still preliminary.

Gap (interval [s], length [s])
 In case of a data gap between two consecutive records this parameter delivers
 the gap interval time and the mean length of the gap.

Timing [%]
 miniSEED record timing quality (0 - 100 %).


.. map-header::


Time-based availability
=======================

*Content contributed by Sandia National Laboratories under IESO grant 52770* |pvmac|_

.. _pvmac: https://pvpmc.sandia.gov/pvmac/

.. |pvmac| replace:: *(PVMAC)*

Introduction
------------

Availability is an uptime metric calculated for inverters and other components
such as trackers and combiner boxes.  Availability is usually calculated on
the basis of time (time-based availability, TBA) but can also be calculated
weighted by energy (energy-based availability, EBA).  

TBA can be a useful business metric, for example as a reflection of O&M
response time.  However, the variable nature of PV output means that TBA is
only loosely correlated with energy generation and losses.  For example,
the same outage on a cloudy vs a sunny day will affect TBA the same but
EBA quite differently.  Nevertheless, TBA is often used for energy
accounting purposes, introducing error and frustrating decision making.

This chapter examines how the difference between EBA and TBA,
with the central question: **how suitable is TBA as an approximation for EBA?**


Methodology
-----------

We simulate a utility-scale system configuration typical for the U.S.:

- Single-axis tracking
- Bifacial TOPCon modules
- 1.3 DC:AC ratio

The simulation uses typical models for IAM, spectral effects, wiring losses,
inverter behavior, and other factors.  We simulate performance time series for
the period 1998–2023 to produce an outage-free dataset.  We then sweep artificial
outages across each month and calculate EBA and TBA for each scenario, mapping
the difference between EBA and TBA.  

For full details on the simulation and analysis methodology,
see :cite:`Anderson2026kpi`.


Results
-------

The following map shows the maximum difference between EBA and TBA.

.. map-widget:: 
   :colorscale_min: 10
   :colorscale_max: 40
   :colorscale_name: Reds
   :short_description: Max. value [%]
   :layers_title: Layer:

    availability/EBA_TBA_difference.tiff : EBA-TBA difference

A primary takeaway here is that the difference between EBA and TBA can be
large everywhere in the contiguous United States, with differences up to ~40%
in some areas.  Even in the best case, the difference can be up to ~10%.
The difference is driven by climate, being smaller in sunny locations like the
Desert Southwest and larger in cloudier locations like the Pacific Northwest.  

This is intuitive: in sunny locations, weather is more stable
day-to-day, so the timing of an outage matters less.  In more variable locations,
the outage timing involves more "luck" and matter more.


References
----------

.. bibliography::
   :list: enumerated
   :filter: False 

   Anderson2026kpi   


Data files
----------

The geographic datasets shown on this page are available in the GeoTIFF
files listed below:

.. geotiff-index::
    :pattern: geotiffs/availability/*.tiff


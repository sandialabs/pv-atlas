
.. map-header::


Capacity ratio
==============

*Content contributed by Sandia National Laboratories*

Introduction
------------

Capacity ratio is a metric typically calculated as part of an ASTM E2848
capacity test.  It is the ratio of actual capacity to expected capacity,
both calculated using the following equation (often called the PVUSA equation):

.. math::

    P = G \cdot (a_1+a_2 G+a_3 T_a+a_4 v),

- :math:`P`: system AC power
- :math:`G`: in-plane irradiance
- :math:`T_a`: ambient temperature
- :math:`v`: wind speed
- :math:`a_1`–:math:`a_4`: coefficients encoding the system's modeled or
  measured response to the environmental variables

The :math:`a` coefficients are determined by fitting to either modeled system
output (for calculating expected capacity) or measured system
output (for calculating actual capacity).

For the expected capacity, the PVUSA equation is effectively a surrogate for
a full PVsyst (or similar) model.  Obviously it cannot be a perfect replacement, so its
predictions will have some uncertainty relative to the original model.
That uncertainty will then propagate into the capacity ratio, potentially
affecting the result of the capacity test.

This chapter examines how this inherent uncertainty in capacity ratio
varies across climates, with the central question: **how much capacity
ratio variability is caused by using the PVUSA equation as a surrogate?**


Methodology
-----------

We simulate a utility-scale system configuration typical for the U.S.:

- Single-axis tracking
- Bifacial TOPCon modules
- 1.3 DC:AC ratio

The simulation uses typical models for IAM, spectral effects, wiring losses,
inverter behavior, and other factors.  We simulate first on the TMY dataset and
fit coefficient values for each month.  These coefficients are used to calculate
"expected" capacity for each month Jan–Dec.  

Then, we simulate performance time series again, but for the actual years 1998–2023.
New coefficient sets are fit for each month in this period, and corresponding
"actual" capacities are calculated.  Each "actual" capacity is then used with
the corresponding "expected" capacity from the TMY to calculate monthly capacity
ratio.

No degradation or atypical performance is included, meaning any variation
in the computed KPI values is due to the PVUSA equation's imperfect representation
of the complete system model.

For full details on the simulation and analysis methodology,
see :cite:`Anderson2026kpi`.


Results
-------

The following map shows how capacity ratio varies across the US.

.. map-widget:: 
   :colorscale_min: 1
   :colorscale_max: 5
   :colorscale_name: Reds
   :short_description: Max. deviation [%]
   :layers_title: Layer:

    capacity-ratio/capacity_ratio_deviation.tiff : Deviation


We see that maximum error is low but nonzero across much of the United States,
with most areas having maximum error of roughly 1%.  However, error can be much
larger in the higher latitudes, reaching 5% or more in some areas.


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
    :pattern: geotiffs/capacity-ratio/*.tiff

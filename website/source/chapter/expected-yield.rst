
.. map-header::


Expected yield
==============

*Content contributed by Sandia National Laboratories*

Introduction
------------

Expected yield is a key quantity for PV system performance assessment,
providing the foundation for KPIs like energy-based availability and energy
performance index (EPI).  It is also useful in monitoring, providing a basis
of comparison for detecting production shortfalls across all
timescales, from sub-hourly (e.g. shading loss) to daily (e.g. soiling loss)
to multi-annual (e.g. long-term accumulated performance loss).

Expected yield can be calculated in a variety of ways.  The typical method
is to use a sophisticated PV system performance model (e.g.  PVsyst,
PlantPredict, or SolarFarmer) and the observed weather conditions.  However,
in cases where  sophisticated models are deemed impractical, alternative
approaches are sometimes used, such as surrogate models or even simple
"weather adjustment" factors based on observed irradiance.  

This chapter examines the suitablility of these alternative approaches,
with the central question: **how well do simplified expected yield methods
reproduce a full model?**


Methodology
-----------

We compare "weather adjustment" factors of the following forms:

1. The "true" value: monthly energy calculated with a conventional energy model,
   divided by the output of the same model applied to the corresponding TMY month.
2. "GHI ratio": the ratio of observed to TMY global horizontal irradiation (GHI).
3. "POA ratio": the ratio of observed to TMY plane-of-array (POA) irradiation.
4. "PVUSA ratio": the ratio of monthly energy calculated using the PVUSA equation
   (with coefficients fitted to a TMY simulation) to the energy predicted by
   a conventional energy model for the corresponding TMY month.

The conventional energy model simulates a utility-scale system configuration
typical for the U.S.:

- Single-axis tracking
- Bifacial TOPCon modules
- 1.3 DC:AC ratio

The simulation uses typical models for IAM, spectral effects, wiring losses,
inverter behavior, and other factors.  We simulate performance time series for
the period 1998–2023 and compute weather adjustment factors for each month across
the period.

For full details on the simulation and analysis methodology,
see :cite:`Anderson2026kpi`.

Results
-------

The following map shows the accuracy variation for each simplified method, taken
relative to the "true" expected yield value calculated with a conventional energy
model.

.. map-widget:: 
   :colorscale_min: 1
   :colorscale_max: 15
   :colorscale_name: Reds
   :short_description: Max. deviation [%]
   :layers_title: Method:

    expected-yield/expected_yield_WA-GHI_deviation.tiff : GHI
    expected-yield/expected_yield_WA-POA_deviation.tiff : POA
    expected-yield/expected_yield_WA-PVUSA_deviation.tiff : PVUSA


We see that the two irradiance-based methods perform poorly,
with maximum errors in excess of 30% and 15% for the GHI and POA methods,
respectively.  The PVUSA method performed better, but worst-case error is
still significant at 4%. In all cases, the greatest
uncertainties are in the northern regions.


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
    :pattern: geotiffs/expected-yield/*.tiff


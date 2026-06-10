
.. map-header::


Performance ratio
=================

*Content contributed by Sandia National Laboratories*

Introduction
------------

Performance Ratio (PR) is a popular metric for PV system performance monitoring.
It is defined as the ratio of generated energy to received irradiance, scaled by
system size:

.. math::

    \text{PR} = \frac{\sum_i E_i}{\sum_i P_0\cdot (G_i/1000 \,\text{W m}^{-2})}

This has the advantages of requiring only basic inputs, accounting for variation
in the primary driver of system output (received irradiance), and being simple
to compute.  However, its omission of secondary PV performance effects makes
it difficult to interpret.  For example, a lower value in summer might not be
due to any issue with the system; it could just be because PV efficiency
decreases with increasing temperature, but PR doesn't account for that.

The "weather-corrected" PR (PRtc) was eventually introduced
to adjust for temperature and thereby reduce seasonal variation in PR.  More
recently, the "clipping-corrected" PR (PRcc) was proposed
to additionally account for inverter clipping.  One could imagine including
further adjustment factors for other effects (spectrum, IAM, wiring losses, ...).

This chapter examines how PR and its refined variants vary across climates,
with the central question: **how much PR variability is caused by these ignored effects?**


Methodology
-----------

We simulate a utility-scale system configuration typical for the U.S.:

- Single-axis tracking
- Bifacial TOPCon modules
- 1.3 DC:AC ratio

The simulation uses typical models for IAM, spectral effects, wiring losses,
inverter behavior, and other factors.  We simulate performance time series for
the period 1998–2023 and compute monthly KPI values.
No degradation or atypical performance is included, meaning any variation
in the computed KPI values is due to the KPI's imperfect understanding of
nominal PV performance.

For full details on the simulation and analysis methodology,
see :cite:`Anderson2026kpi`.


How does PR vary geographically?
--------------------------------

The following maps shows how these PR variants vary across the US.

.. map-widget:: 
   :colorscale_min: 75
   :colorscale_max: 90
   :colorscale_name: Spectral
   :short_description: Median value [%]
   :layers_title: PR variant:

    performance-ratio/PR_median.tiff : PR
    performance-ratio/PRtc_median.tiff : PRtc
    performance-ratio/PRcc_median.tiff : PRcc

Note a few takeaways:

1. PR is not "out of 100%".  A healthy system will have typical PRs in the range
   75–90%.
2. Typical values for PR and PRtc vary substantially across locations.  A
   "normal" value in one location may appear to indicate substantial under- or
   over-performance elsewhere.
3. Adjusting for additional effects (e.g. temperature and inverter clipping)
   improve the geographic stability, but some variation remains due to
   other performance factors not being accounted for.


How does PR vary seasonally?
----------------------------

Does monthly PR stay close to the median values shown in the previous map, or
does vary over time?  This map shows the range (maximum minus minimum)
for each PR across many years.

.. map-widget:: 
   :colorscale_min: 1
   :colorscale_max: 25
   :colorscale_name: Reds
   :short_description: Range (max - min) [%]
   :layers_title: PR variant:

    performance-ratio/PR_range.tiff : PR
    performance-ratio/PRtc_range.tiff : PRtc
    performance-ratio/PRcc_range.tiff : PRcc


What does this tell us?  Some climates are subtantially more variable than
others.  Even in the most stable climates, PR and PRtc span ranges of ~10 and
~5%, respectively.  


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
    :pattern: geotiffs/performance-ratio/*.tiff


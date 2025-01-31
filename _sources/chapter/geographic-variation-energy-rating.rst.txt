
.. map-header::


Geographic variation in energy rating
=====================================

*Content contributed by Sandia National Laboratories*

Introduction
------------

PV modules convert light to electricity with an efficiency of roughly 20%,
with the remainder being reflected from the module surface or converted to
thermal energy inside the module.  However, the exact efficiency varies,
both across modules (some module types are more efficient than others) and
according to the operating conditions of the module.  Modules ratings are
typically determined in the laboratory at standard test conditions (STC).
However, when deployed outdoors, the operating conditions (light intensity,
temperature, etc) often differ significantly from STC.  This means that efficiency
ratings at STC often don't represent module performance in real applications.

One way of determining more realistic efficiency ratings is with a
"climate-specific energy rating" (CSER) procedure.  As the name suggests,
CSER represents how a module would perform in a given climate.  CSER is
calculated as the ratio of overall outdoor efficiency to efficiency at STC:

.. math::

   \text{CSER} = \frac{\text{Efficiency at operating conditions}}{\text{Efficiency at STC}}

For example: a module with an STC efficiency of 20% and a CSER of 90% in a given
location, would have an overall efficiency of 18% in that location (0.9 times 20).
In another location with a CSER of 95%, it would have an overall efficiency
of 19%.

This chapter examines how CSER varies across climates, with the central
question: **how does module efficiency vary geographically, and what
factors drive the variation?**


Methodology
-----------

We consider modules corresponding to five PV technologies:

+--------------+--------------------------+-----------+--------------------+--------------------------------+
| Name         | Module                   | Cell type | STC efficiency [%] | Temperature coefficient [%/°C] |
+==============+==========================+===========+====================+================================+
| CSmono275    | Canadian Solar CS6K-275M | Al-BSF    | 16.9               | -0.415                         |
+--------------+--------------------------+-----------+--------------------+--------------------------------+
| Qmono300     | Q Cells Q.PEAK-G4.1 300  | PERC      | 17.4               | -0.403                         |
+--------------+--------------------------+-----------+--------------------+--------------------------------+
| LG320        | LG 320 N1K-A5            | N-PERT    | 18.7               | -0.400                         |
+--------------+--------------------------+-----------+--------------------+--------------------------------+
| Panasonic325 | Panasonic VBHN325SA 16   | HIT       | 19.3               | -0.297                         |
+--------------+--------------------------+-----------+--------------------+--------------------------------+
| FSLRs4       | First Solar FS-4112-3    | CdTe      | 16.4               | -0.297                         |
+--------------+--------------------------+-----------+--------------------+--------------------------------+

CSERs for each module are calculated according to the IEC 61853-3
standard.  The standard defines a modeling workflow that
accounts for the effects of spectral variation, operating temperature,
absolute irradiance level, and reflection loss (IAM).
To investigate the underlying sources of variation in CSER, we also
compute CSER values where each of those four performance effects are held at
their STC values instead of varying according to the climatic dataset.
For example, IAM is kept at STC by setting it to 1.0 for all angles of incidence.
Four aspects of performance are evaluated in this way: IAM, spectral mismatch (SMM),
low-light response, and temperature response.  By computing CSER values with each
of these effects "disabled" (i.e., held at the corresponding STC condition) and
comparing with the baseline CSER where all effects are active, we can quantify
each effect's contribution to the overall CSER.

We calculate CSER across the United States using solar resource and spectral
irradiance data from the NSRDB PSM3 datasets for calendar year 2022.

For full details on the simulation and analysis methodology,
see :cite:`Anderson2025cser`.

How does CSER vary geographically?
----------------------------------

The following map shows how CSER varies across the US.  Use the layer
widget to view maps for other modules. 

.. map-widget:: 
   :colorscale_min: 90
   :colorscale_max: 110
   :colorscale_name: RdBu
   :short_description: CSER [%]
   :layers_title: Module:

    cser/CSER_CSmono275_US_2022.tiff : CSmono275
    cser/CSER_Qmono300_US_2022.tiff : Qmono300
    cser/CSER_LG320_US_2022.tiff : LG320
    cser/CSER_Panasonic325_US_2022.tiff : Panasonic325
    cser/CSER_FSLRs4_US_2022.tiff : FSLRs4

The maps reveal several noteworthy facts:

1. CSER varies across CONUS from 86% to 103%.
2. CSER is almost always less than 100%, meaning modules perform worse outdoors
   than their STC rating suggests.  The exception is in the upper midwest,
   where some modules' CSER may exceed 100% by a small amount.
3. Geographic trends are qualtitatively similar across modules.
4. The FSLRs4 module has the highest CSER across all climates.
5. Among the four silicon modules, which one has the highest CSER depends on the location.


What factors drive the variation?
---------------------------------

We now examine how each of the four performance factors (temperature, spectrum,
reflection/IAM, and low light) contribute to the overall CSER.

First, temperature.  In this analysis, "temperature" includes the effects
of both the module's temperature coefficient (:math:`\gamma`) and Faiman
thermal coefficients (:math:`u_0`, :math:`u_1`).  We see that temperature
effects result in CSER deviations greater than 10%, and the deviations
are nearly always negative.  Modules with larger temperature coefficients
have larger deviations.  However, comparing Qmono300 with LG320 (which have
nearly identical temperature coefficients), we see that the two Faiman coefficients
also have meaningful effect on overall performance.

.. map-widget:: 
   :colorscale_min: -10
   :colorscale_max: 10
   :colorscale_name: RdBu
   :short_description: Effect of temperature on CSER [%]
   :layers_title: Module:

    cser/Temperature_CSmono275_US_2022.tiff : CSmono275
    cser/Temperature_Qmono300_US_2022.tiff : Qmono300
    cser/Temperature_LG320_US_2022.tiff : LG320
    cser/Temperature_Panasonic325_US_2022.tiff : Panasonic325
    cser/Temperature_FSLRs4_US_2022.tiff : FSLRs4


Next, spectrum.  The silicon modules see CSER differences from -2% in the arid
and mountainous regions in the southwest to to +2% in the pacific northwest.
In most of the country, the silicon modules see a small gain around 1%.  In
contrast, the CdTe module sees differences from -2.5% to +5%, with a geographic
pattern similar to that of the silicon modules.

.. map-widget:: 
   :colorscale_min: -5
   :colorscale_max: 5
   :colorscale_name: RdBu
   :short_description: Effect of spectrum on CSER [%]
   :layers_title: Module:

    cser/SMM_CSmono275_US_2022.tiff : CSmono275
    cser/SMM_Qmono300_US_2022.tiff : Qmono300
    cser/SMM_LG320_US_2022.tiff : LG320
    cser/SMM_Panasonic325_US_2022.tiff : Panasonic325
    cser/SMM_FSLRs4_US_2022.tiff : FSLRs4


Third, IAM.  IAM's influence on CSER varies with location/climate much less
than the previous effects.  The primary variation is with latitude, ranging
from -1.2% in the south to 2.2% in the far north.  Only minor variation
is visible according to terrain and other climatic effects.  Additionally,
the advantageous IAM curve assumed for the FSLRs4 module cuts the
reflection loss in half compared to the other modules.

.. map-widget:: 
   :colorscale_min: -3
   :colorscale_max: 3
   :colorscale_name: RdBu
   :short_description: Effect of IAM on CSER [%]
   :layers_title: Module:

    cser/IAM_CSmono275_US_2022.tiff : CSmono275
    cser/IAM_Qmono300_US_2022.tiff : Qmono300
    cser/IAM_LG320_US_2022.tiff : LG320
    cser/IAM_Panasonic325_US_2022.tiff : Panasonic325
    cser/IAM_FSLRs4_US_2022.tiff : FSLRs4


Finally, low-light conditions.  Here we see a large qualitative difference
between modules, where the nonlinear responses of the CSmono275 and Panasonic325
modules result in losses ranging from -0.3% to -1.5% depending on the location,
while the other modules (which have a more linear response to light) show
significantly smaller effects on CSER.  Sunny locations are less affected
by low-light loss than cloudier locations are.

.. map-widget:: 
   :colorscale_min: -2
   :colorscale_max: 2
   :colorscale_name: RdBu
   :short_description: Effect of low light on CSER [%]
   :layers_title: Module:

    cser/Low_light_CSmono275_US_2022.tiff : CSmono275
    cser/Low_light_Qmono300_US_2022.tiff : Qmono300
    cser/Low_light_LG320_US_2022.tiff : LG320
    cser/Low_light_Panasonic325_US_2022.tiff : Panasonic325
    cser/Low_light_FSLRs4_US_2022.tiff : FSLRs4



References
----------

.. bibliography::
   :list: enumerated
   :filter: False 

   Anderson2025cser   


Data files
----------

The geographic datasets shown on this page are available in the GeoTIFF
files listed below:

.. geotiff-index::
    :pattern: geotiffs/cser/*.tiff


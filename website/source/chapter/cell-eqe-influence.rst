
.. map-header::


Impact of cell-to-cell EQE variation on power output
====================================================

Introduction
------------
Cells in a PV module are typically connected in series, hence module
performance is limited by the cell generating the lowest current.  Reduced cell
performance can arise from manufacturing inconsistencies between cells, or
in-operando events such as localised temperature hotspots and non-uniform
module degradation.

Previous studies have investigated how external envrionmental factors
such as non-uniform shading can lead to reduced individual cell or module
performance resulting in mismatch losses.  While manufacturing inconsistencies
between cells are often cited as a cause of intramodule mismatch losses, they
are typically overlooked in the existing body of research.

One way to study the inherent differences between cells is through analyzing
their external quantum efficiency (EQE).  A cell's EQE curve represents the
efficiency with which incident photons of different wavelengths generate a
photocurrent.  Although this spectral effect on PV performance has been studied
at the module level, no studies have analysed the spectral effect at the cell
level and its potential role as a driver of mismatch losses at the module
level.  

To investigate the role of cell-to-cell variation on module performance, the
following questions are proposed:

#. How does the EQE vary between cells?
#. What is the impact on PV performance?
#. Does the performance impact vary seasonally or geographically?


Methodology
----------
EQE curves for each cell within each of 11 PV modules were measured by the Cell
Measurement and Performance group at the National Renewable Energy Laboratory.
These data are in conjunction with one year of simulated 30-minute
meteorological data, including spectral irradiance, spanning the contiguous
United States at a resolution of around 0.2° longitude/latitude (around 20km)
thus covering around 21,000 individual locations.

The PV devices studied cover a range of technologies, including
monocrystalline silicon (monoSi) and polycrystalline silicon
(polySi), and a range of cell architectures including Al-BSF (Aluminium Back
Surface Field), IBC (Interdigitated Back Contact), PERC (Passivated Emitter
and Rear Contact), PERT (Passivated Emitter Rear Totally Diffused), and SHJ
(Silicon heterojunction).

To quantify the impact of intradmodule EQE variation on PV device performance,
the output from the "worst cell" (lowest performance) is compared with that of
a hypothetical average cell, determined from the mean cell EQE.

The mean EQE curve is a useful approximation of the module EQE that a modeler
may use to estimate module performance without the need to process multiple EQE
curves and individual cell performances to determine which is driving the
module performance under any given spectral irradiance condition.  The power
loss calculation thus provides an indication of the error incurred through this
approximation.

Results
-------

How does the EQE vary between cells?
-----------------------------------
There are four forms of EQE variation among the devices, classified by this
study as follows:

#. Negligible
#. Amplitude
#. Wavelength
#. Mixed

The first type of variation is characterized by a tight distribution with a
mean absolute deviation of between 1% and 3% that is largely independent of
wavelength.  Examples include the CSPoly270 and Itek360 modules. The EQE
variation for the Panasonic325 module is also independent of wavelength, but a
significantly greater amplitude-dominant variation is present with a relatively
stable MAD of around 5%.  This relatively uniform variation in EQE can be
caused by a mixture of internal factors such as parasitic losses, and external
factors such as reflection leading to variable illumination from cell to cell
for each measurement.  The third category is characterized predominantly by
wavelength-dependent variation, such as in the case of the Qpoly280 device. 
Finally, devices such as the Mission300 module exhibit a mixture of
wavelength-dependent and amplitude variation, thus falling into the fourth
category.

What is the impact on PV performance?
-------------------------------------
Figure X shows the annual energy difference between the potential
non-mismatched output, as determined by the mean EQE, and the realistic module
output, as determined by the limiting cell. The overall energy difference, ΔE,
is relatively low for all modules, rarely exceeding ±0.20%.  Nonetheless, there
is a link between the scale of loss and the type of EQE variation.  Modules
with greatest ΔE are also those whose intramodule EQE variation is
characterized by a wavelength dependence (category 3) or mixed variation
(category 4). Variation in amplitude is likely to result primarily from
systematic measurement error, for example due to variable cell illumination,
and its effect is removed through an inherent normalization in the calculation
of M.


Does the performance impact vary seasonally or geographically?
--------------------------------------------------------------
Could the low annual ΔE be a result of month-to-month variations cancelling
each other out? Taking the Mission300 module as an example, Figure X shows the
monthly breakdown ΔE values.  The range in each month represents the range of
ΔE across the contiguous USA while the triangle and horizontal bar represent
the mean and median ΔE, respectively.  On a monthly scale, the energy
difference is more significant.  The range from month to month is almost double
the annual energy difference, with an approximately 50:50 split between
positive and negative ΔE months.

Since ΔE can be positive or negative, besides reducing the annualized ΔE, this
phenomenon also indicates that the driving cell under the prevailing spectrum
can yield both an energy gain or loss with respect to performance driven by the
mean EQE cell in the absence of intramodule EQE variation.

In terms of geography, ΔE has a range of 0.46% across all locations, which is
over four times the annualized ΔE.  Another phenomenon related to location is
the fact that the annual ΔE values are notably larger in the south/south east
USA than in the western states. This effect is particularly significant in
coastal states such as Florida, where the subtropical climate is driven by high
levels of humidity that are known to increase the spectral influence on PV
performance [X].


Discussion
----------



Conclusion
----------



References
----------



Data files
----------
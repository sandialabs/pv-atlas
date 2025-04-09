
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


Does the performance impact vary seasonally or geographically?
--------------------------------------------------------------


References
----------

Data files
----------
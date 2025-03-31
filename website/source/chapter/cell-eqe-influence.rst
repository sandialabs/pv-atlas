
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
These data are in conjunction with one year of simulated 30-minute meteorological data, including
spectral irradiance, spanning the contiguous United States at a resolution of
around 0.2° longitude/latitude (around 20km) thus covering around 21,000
individual locations.

The PV devices studied cover a range of technologies, including
monocrystalline silicon (monoSi) and polycrystalline silicon
(polySi), and a range of cell architectures including Al-BSF (Aluminium Back
Surface Field), IBC (Interdigitated Back Contact), PERC (Passivated Emitter
and Rear Contact), PERT (Passivated Emitter Rear Totally Diffused), and SHJ
(Silicon heterojunction). IEC 61853-1 characterisation data as well
as STC and field performance reports of the modules can be found in XXXX.
XX refer to data section or add references directly here? XX

The spectral mismatch factor, $M$ is used to quantify the change in PV
performance due to changes in the spectrum.  $M$ represents the ratio of the
usable fraction (UF) of measured irradiance to the usable fraction of the
reference irradiance XX IEC reference? XX, and is calculated using the spectral
response (SR) and spectral irradiance data as follows:

XX how much detail on the power model? XX

The power output of a module with series-connected cells is driven by the
cell with the lowest current, which can be determined by identifying the cell
with the lowest $M$.  Assuming as simple PVWatts-style power model, with linear
relationships between performance and temperature and irradiance, the module
power can be computed as follows:

XX just the final equation XX

A more detailed derivation and explanation can be found in [X cite the paper].

To quantify the impact of intradmodule EQE variation on PV device performance,
the real estimate of power (Equation X) is compared to an estimate of the ideal
power in the absence of intramodule EQE variaton, i.e. all cells have the same
spectral behaviour and thus the same spectral mismatch, $M_{mod}$. In this
study, $M_{mod}$ is calculated using the mean EQE.  The power output of this
idealistic PV module in which all cells operate at the same level, $P_2$, is
calculated as follows:

X

Therefore, the power loss as a result of the cell EQE mismatch within a PV
module is given by:

XX

where:

XX

The percentage power loss is given by:

XX

The mean EQE curve is a useful approximation of the module EQE that a modeller
may use to estimate module performance without the need to process multiple EQE
curves and individual cell performances to determine which is driving the
module performance under any given spectral irradiance condition. Using this
definition, $P_{loss}$ gives an indication of the error incurred through this
approximation. The definition of $M_{mod}$ in this model is flexible. In
another example use case, a device manufacturer may be interested in defining
$M_{mod}$ as the spectral mismatch of the cell that most frequently generates
the highest output, in order to determine the potential energy gain if all
cells were manufactured at that higher EQE level. 

Results
-------

How does the EQE vary between cells?
-----------------------------------

What is the impact on PV performance?
-------------------------------------

Does the performance impact vary seasonally or geographically?
--------------------------------------------------------------

References
----------

Data files
----------
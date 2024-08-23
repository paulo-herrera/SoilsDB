Unsaturated flow properties for different unconsolidated sediments
==================================================================

Introduction
------------

Unsaturated flow in porous media is usually approximated by solving the single phase (water) 
Richards equation, which requires a couple of constitutive functions that
relate pore pressure head (or suction) ($\psi$, [L]) with water content ($\theta$, [-]), 
and pore pressure head with relative permeability ($k_r$, [-]).

There have been proposed several expressions to approximate those constitutive functions,
which were derived from first principles and simplifying assumptions (e.g. Mualem, 1976). 
Those expressions include parameters cannot be directly linked to physical properties, so 
that they represent shape or fitting parameters. For example, two of the most used equations
are the water retention expression proposed by van Genuchten (1980): 

$se = [1 - (\alpha \cdot h)^n]^{-m}$, $m = 1 - 1 / n$

and the relative permeability formula proposed by Mualem (1976):

Relative permeability curve: Mualen  kr = se^n

Where saturation $se = (\theta - \theta_r) / (\theta_{sat} - \theta_r)$, where $\theta$ is the volumetic water content, $\theta_{sat}$ is the saturated water content, usually aproximated equal to porosity; and $\theta_r$ is the residual water content.


Contents
--------

There is data for 12 soils listed in Leij (1996) in the **data** directory. There are two
files for each soil: a *.csv* file with three columns 
(pressure, water content, relative permeability) and a *.png* that shows curves for all 12 soils.

The curves were generating using the following parameters:

Soil(id=sand, wr=0.045, ws=0.43, alpha=0.145, n=2.68, Ks=712.8)
Soil(id=loamy_sand, wr=0.057, ws=0.41, alpha=0.124, n=2.28, Ks=350.16)
Soil(id=sandy_loam, wr=0.065, ws=0.41, alpha=0.075, n=1.89, Ks=106.08)
Soil(id=loam, wr=0.078, ws=0.43, alpha=0.036, n=1.56, Ks=24.96)
Soil(id=silt, wr=0.034, ws=0.46, alpha=0.016, n=1.37, Ks=6.0)
Soil(id=silt_loam, wr=0.067, ws=0.45, alpha=0.02, n=1.41, Ks=10.8)
Soil(id=sandy_clay_loam, wr=0.1, ws=0.39, alpha=0.059, n=1.48, Ks=31.44)
Soil(id=clay_loam, wr=0.095, ws=0.41, alpha=0.019, n=1.31, Ks=6.24)
Soil(id=silty_clay_loam, wr=0.089, ws=0.43, alpha=0.01, n=1.23, Ks=1.68)
Soil(id=sandy_clay, wr=0.1, ws=0.38, alpha=0.027, n=1.23, Ks=2.88)
Soil(id=silty_clay, wr=0.07, ws=0.36, alpha=0.005, n=1.09, Ks=0.48)
Soil(id=clay, wr=0.068, ws=0.38, alpha=0.008, n=1.09, Ks=4.8)

Units for values are: [alpha] 1/cm, [Ks] cm/day, all others [-]


----------
REFERENCES
---------- 

Leij, F. J. (1996). The UNSODA unsaturated soil hydraulic database: user's manual (Vol. 96, No. 95). National Risk Management Research Laboratory, Office of Research and Development, US Environmental Protection Agency.

Nemes, A. D., Schaap, M. G., Leij, F. J., & Wösten, J. H. M. (2001). Description of the unsaturated soil hydraulic database UNSODA version 2.0. Journal of hydrology, 251(3-4), 151-162.

Mualem, Y. (1976). A new model for predicting the hydraulic conductivity of unsaturated porous media. Water resources research, 12(3), 513-522.

van Genuchten, M. T. (1980). A closed‐form equation for predicting the hydraulic conductivity of unsaturated soils. Soil science society of America journal, 44(5), 892-898.

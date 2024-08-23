==================================================================
Unsaturated flow properties for different unconsolidated sediments
==================================================================

------------
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

$se = [1 - (alpha h)^n]{-m}$, $m = 1 - 1 / n$

and the relative permeability formula proposed by Mualem (1976):

Relative permeability curve: Mualen  kr = se^n

Where saturation $se = (\theta - \theta_r) / (theta_{sat} - \theta_r)$, where $\theta$ is the volumetic water content, $\theta_{sat}$ is the saturated water content, usually aproximated equal to porosity; and $\theta_r$ is the residual water content.


--------
Contents
--------

There is data for 12 soils listed in Leij (1996) in the  

[alpha] 1/cm, [Ks] cm/day, all others [-]

----------
REFERENCES
---------- 

Leij, F. J. (1996). The UNSODA unsaturated soil hydraulic database: user's manual (Vol. 96, No. 95). National Risk Management Research Laboratory, Office of Research and Development, US Environmental Protection Agency.

Nemes, A. D., Schaap, M. G., Leij, F. J., & Wösten, J. H. M. (2001). Description of the unsaturated soil hydraulic database UNSODA version 2.0. Journal of hydrology, 251(3-4), 151-162.

Mualem, Y. (1976). A new model for predicting the hydraulic conductivity of unsaturated porous media. Water resources research, 12(3), 513-522.

van Genuchten, M. T. (1980). A closed‐form equation for predicting the hydraulic conductivity of unsaturated soils. Soil science society of America journal, 44(5), 892-898.

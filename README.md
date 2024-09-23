Unsaturated flow properties for different unconsolidated sediments
==================================================================

![Alt text](all_soils.png?raw=true "Unsaturate flow curves") 


Introduction
------------

Unsaturated flow in porous media is usually approximated by solving the single phase (water) 
Richards equation, which requires a couple of constitutive functions that
relate pore pressure head or suction ($\psi$, [L]) with water content ($\theta$, [-]), 
and $\psi$ with relative permeability ($k_r$, [-]).

There have been proposed several expressions to approximate those constitutive functions,
which were derived from first principles and simplifying assumptions (e.g. Mualem, 1976). 
Those expressions include parameters cannot be directly linked to physical properties, so 
that they represent shape or fitting parameters. For example, two of the most used equations
are the water retention expression proposed by van Genuchten (1980): 

$Se = [1 + (\alpha \cdot h)^n]^{-m}$, $m = 1 - 1 / n$

and the relative permeability formula proposed by Brooks-Corey (1963):

$k_r = Se^\beta$,

where saturation $Se = (\theta - \theta_r) / (\theta_{sat} - \theta_r)$ and, $\theta$ is the volumetic water content, $\theta_{sat}$ is the saturated water content, usually aproximated equal to porosity; and $\theta_r$ is the residual water content. Usually, the parameter $\beta$ is related to the pore size distribution index ($\lambda$) using $\beta = (2+3\lambda)/\lambda$. It is possible to relate the parameters of both models to obtain (Lenhard et al., 1989):

$\lambda = \frac{m}{1-m} [1 - S_e^{1/m}]$

Assuming a constant saturation $S_e = 0$ to evaluate the last expression, we obtain $\beta = 2 - 1/n$.

Contents
--------


The **data** directory contains data for 12 soils listed in Leij (1996). 
There are two files for each soil: 
a *.csv* file with three columns (pressure, water content, relative permeability) 
and a *.png* that shows $\theta$ vs $\psi$ and $k_r$ vs $\psi$ curves.

The curves were generating using the following parameters:


| Soil            | $\theta_r$  | $\theta_{sat}$  | $\alpha$  | $n$   |$K_s$
| :---            |  :---:      | :---:           | :---:     | :---: | ---:
| Sand            | 0.045       | 0.43            | 0.145     | 2.68  | 712.8
| Loamy-sand      | 0.057       | 0.41            | 0.124     | 2.28  | 350.2
| Sandy-loam      | 0.065       | 0.41            | 0.075     | 1.89  | 106.1
| Loam            | 0.078       | 0.43            | 0.036     | 1.56  | 25.0
| Silt            | 0.034       | 0.46            | 0.016     | 1.37  | 6.0
| Silt-loam       | 0.067       | 0.45            | 0.020     | 1.41  | 10.8
| Sandy-clay-loam | 0.100       | 0.39            | 0.059     | 1.48  | 31.4
| Clay-loam       | 0.095       | 0.41            | 0.019     | 1.31  | 6.2
| Silty-clay-loam | 0.089       | 0.43            | 0.010     | 1.23  | 1.7
| Sandy-clay      | 0.100       | 0.38            | 0.027     | 1.23  | 2.9
| Silty-clay      | 0.070       | 0.36            | 0.005     | 1.09  | 0.5
| Clay            | 0.068       | 0.38            | 0.008     | 1.09  | 4.8

Units for values are: [alpha] 1/cm, saturated hydraulic conductivity [Ks] cm/day, all others [-]


PFLOTRAN Users
--------------

Unsaturated flow properties can be set with the following statement:

```
    CHARACTERISTIC_CURVES sand_cc
        SATURATION_FUNCTION VAN_GENUCHTEN
            M 0.59142d0
            ALPHA  4.8955d-5
            LIQUID_RESIDUAL_SATURATION 0.1933d0
        /

        PERMEABILITY_FUNCTION MUALEM_VG_LIQ
            M 0.59142d0
            LIQUID_RESIDUAL_SATURATION 0.1933d0
            SMOOTH
        /
    /
```

In this case $M = 1-1/n$, *LIQUID_RESIDUAL_SATURATION* is $\theta_r$ and *ALPHA* must be in
[1/Pa].


Caveats
----------

The included curves **do not** consider hysteresis, which can be important in many situations
(Mualen, 1976b).


REFERENCES
---------- 

1. Brooks, R. H., & Corey, A. T. (1963). Hydraulic properties of porous media and their relationship to drainage design. Annual Meeting American Society of Agricultural Engineers, 63-214.

2. Leij, F. J. (1996). The UNSODA unsaturated soil hydraulic database: user's manual (Vol. 96, No. 95). National Risk Management Research Laboratory, Office of Research and Development, US Environmental Protection Agency.

3. Lenhard, R. J., Parker, J. C., & Mishra, S. (1989). On the correspondence between Brooks-Corey and van Genuchten models. Journal of Irrigation and Drainage Engineering, 115(4), 744-751.

4. Nemes, A. D., Schaap, M. G., Leij, F. J., & Wösten, J. H. M. (2001). Description of the unsaturated soil hydraulic database UNSODA version 2.0. Journal of Hydrology, 251(3-4), 151-162.

5. Mualem, Y. (1976). A new model for predicting the hydraulic conductivity of unsaturated porous media. Water Resources Research, 12(3), 513-522.

6. Mualem, Y. (1976b). Hysteretical models for prediction of the hydraulic conductivity of unsaturated porous media. Water Resources Research, 12(6), 1248-1254.

7. van Genuchten, M. T. (1980). A closed‐form equation for predicting the hydraulic conductivity of unsaturated soils. Soil Science Society of America Journal, 44(5), 892-898.

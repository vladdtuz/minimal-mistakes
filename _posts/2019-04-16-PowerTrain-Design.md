---
title: Mechanical Design - Powertrain design
tags:  Mechanical Engineering
layout: single
mathjax: true
---
Powertrain design is fundamentally an equilibrium between power required and power available. Traditionally, vehicles generate power through internal combustion. Power output from the engine is the power available. Power available is defined by the following formula:
$$F_{Z,A} = \frac{T(n_M)i_A}{r_{dyn}}\eta_{tot}$$

where $$T(n_M)$$ - motor torque at a given RPM, $$i_A $$ = powertrain ratio, $$r_{dyn}$$ = dynamic tire radius, $$\eta$$ = total powertrain efficiency

 Power required is a bit more involed complex. The amount of power required to move the vehicle is dependent on a number of resitances; these resistances arise from the following:
* Air resitance - dependent on aerodynamics of vehicle. Aerodynamic drag is defined as:
$$F_L = \frac{1}{2}\rho DAv^2 $$

where $$\rho$$ = density, D = drag coefficient, A = cross sectional area, v = velocity

* Acceleration resistance - inertial forces during acceleration and braking. Acceleration resitance is defined as:
$$F_a = \lambda m_F a $$

where $$\lambda$$ = rotational inertia coefficient, $$m_F$$ = mass, a = acceleration

* Wheel resistance - resistance due to friction between road and wheel rubber. Wheel resistance is defined as:
$$F_R = f_R m_F g cos(\alpha_{ST})$$

where $$f_R$$= rolling resistance coefficient, $$m_F$$ = mass, g = gravity, $$\alpha$$= angle of inclination

* Gradient resitance - resitance due to road inclination. Gradient resistance is defined as:
$$F_{ST} = m_F g sin(\alpha_{ST}) $$

where $$m_F$$ = mass, g = gravity, $$\alpha$$ = angle of inclination

Therefore with all that in mind, total power required is the summation of all the components. Total power required is defined as:

$$F_{Z,B} = F_R + F_{ST} + F_L + F_a$$

Powertrain design is all about increasing the power from engine to overcome total drag. One method in overcoming drag is increasing output engine power, the other method (the sole purpose of powertrain) is to step up the torque value, through a series of gear assemblies. Gears are used to step up or step down torque values; therefore designing a series of gear pairs will allow engine power to be stepped up in order to overcome total drag. There are three overall design conditions when designing a powertrain system.
* Largest powertrain ratio
* Smallest powertrain ratio
* Fuel efficiency on the engine performance map

Largest powertrain ratio is limited when tires reach adhesion limit with the road. Anymore power after this limit, will result in the tires spinning. Therefore largest ratio is chosen when $$F_{Z,A}= F_{Z,B}$$ and re-arranging for $$i_{A,Max}$$ yields the following formula:

$$i_{A,Max} = \frac{r_{dyn} m_F g (f_R cos(\alpha_{ST})+sin(\alpha_{ST}))}{T_{M,Max}\eta_{tot}}$$

Largest powertrain ratio is derived from the equation above (maximum power when tires still in contact with road), smallest powertrain ratio is also defined from the same equation. However, unllike for the maximum powertrain ratio, for the minimum powertrain ratio, engine characteristics are to be taken at minimum conditions (previously it was maximum engine characteristics)

Once the design engineer has determined maximum and minimum powertrain ratio ($$i_{A,Max}$$ & $$i_{A,Min}$$), three more ratios need to be defined. The overall powertrain is made up of three components:
* Moving off element ($$i_S$$)
* Gearbox ($$i_G$$)
* Final drive ($$i_E$$)

where $$i_A = i_S i_G i_E $$

Ratio for 'moving off element' is 1 for dry clutches and >1 for automatic clutches. This topic of discussion is for another post, another time. 

Final ratio ($$i_E$$) selected adapts handaling and fuel consumptions. Therefore, once again, this ratio is the topic for another post.

Lastly, choosing gearbox ratio ($$i_G$$) is deciding  gear ratios in the gearbox. Last gear ratio is designed to be 1 (unless underreving design is desired). Largest geabox ratio is determined by the design engineer based on fundamental gear analysis and gearbox sizing (gear teeth should not fail; gears cannot be too large)

Step size between gears is also an important factor. A small step size allows for smooth transition between gears, while also increasing efficiency (large number of gears allows gearbox to closely match engine power generation); however large number of gears leads to increased weight of the gearbox. Step size is a trade-off between efficiency and weight.  Gear step size is determined by the following formulas:

$$\phi_1 = (\frac{1}{\phi_2^{0.5(z-1)(z-n-1)}}i_{G,tot})^{\frac{1}{z-1}} $$

$$i_n = i_z \phi_1^{(z-n)} \phi_2^{0.5(z-n)(z-n-1)}$$

where n = gear, z = total number of gears (i.e. 5 speed gearbox; z = 5)

The post provides the general design overview of powertrain system. When choosing gear ratios, gear analysis must also be considered; such as Hertz stress. However this post provides the fundamentals and conditions of the powertrain.
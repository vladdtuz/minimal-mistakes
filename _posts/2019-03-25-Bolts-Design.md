---
title: Fastener design
tags: Design Engineering Beginner 
layout: single
mathjax: true
---
 
There is no way around it, working in design will mean implementation of fasterners; one way or another. Therefore, properly understanding and designing fasteners is important. The most important property of fasteners is their proof load (or proof stress). Proof load is 75% - 90% of yeild stress. Fasteners are recommended to be load to their proof load; this will ensure no yeilding will occur while also ensuring the clamping force is still maintained. 

Bolts are are usually specified in by their size (i.e. M5 ,M8 etc) but also by their grade (i.e. Grade 8.8, 10.9 etc) The grade of the bolt refers to the properties of the bolt. In the metric system, both numbers have a meaning:
* First number - fastener UTS = Number x 100. if first number is 8. UTS = 800
* Second number - fastener yield = UTS x Number/10 i.e if UTS is 800 and second number is 8. yield = 640

Therefore, with simply knowing the grade of the bolt; we can know the UTS and yield; both of which are very important in the design process. There is a second design aspect which is very important to fastener design; fastener tension and clamp force. 
* Clamp force - force exerted by the fastener on the components. Force which helps components press against each other. 
* Fastener tension - force exerted on the fastener by the components

In a static, ideal scenario both clamp force and bolt tension are equal to each other which both are equal to the initial applied torque. This means that a reduction in bolt tension, results a reduction in clamp force and vice versa; a reduction in initial torque also effects both. Fastener analysis becomes more complicated when an external load is exerted after initial torque. 

With the addition of an external load, clamping force should not change at all. If the clamp force reduces, this means the components aren't held together anymore, therefore will lead to failure. Therefore, going back to the analysis mentioned before. Since clamping force should not change, the extra load should be directed to the fastener i.e. bolt tension increasing. A simple relationship was developed between clamp force, initial load and component elastic properties (each material acts like a spring when under compression) The relationship is the following:

$$F_b = F_i + \frac{k_b}{k_b+k_c}F_e $$
$$F_c = F_i - \frac{k_c}{k_b+k_c}F_e $$

where : $F_C$ = clamp force; $F_b$ = bolt force;$F_e$= external force; $k_b$ = bolt spring constant; $k_c$ = clamp spring constant; 

Spring constant as calculated through the following relationship:
$$k = \frac{AE}{g}$$

where : A = area; E = elastic modulus; g = grip length

Wit this formula, we can determine if bolts will reduce their clamp force (and lead to failure) when external load is applied

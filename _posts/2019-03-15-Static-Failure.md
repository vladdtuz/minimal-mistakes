---
title: Design against static failure
tags: Design Engineering Beginner Fatigue
layout: single
mathjax: true
---

Engineering design narrows down to "*will the structure fail*". Failure occurs when the structure cannot support the applied loading conditions and it breaks down. Understanding types of loading, results in better understading of possible failure modes. Therefore, types of loading are narrowed down into two categories:
* Static - Static loading is the most common type of loading in engineering design. Static loads arise from gravity, self-weight and any other weight which the structure has to withstand.
* Cyclic - Cyclic loading is similar to static, however the weight is applied and removed on a regular pattern. This process of repetition needs to be considered separately, as cyclic loads can induce failures much sooner than its static counterpart. 

## Static loading
 
 Failure occurs in manifests itself differently in ductile materials when compared to brittle materials, therefore failure criteria needs to independetly be defined. As is the general rule:
> **Brittle materials tend to fail on the plane of maximum normal stress**

> **Ductile materials tend to fail on the plane of maximum shear stress**

Over the years, many failure theories have been proposed as "*the most adequate*", the general consensus for failure theories are:

Material | Failure criteria|
-----    | --------|
Brittle  | "Maximum normal stress" theory (Rankine) |
Ductile  |"Maximum shear stress" theory (Tresca) <br/> "Maximum distortion energy" theory (von Mises) |

### "Maximum normal stress" theory (Rankine)
$$ \sigma_{fail}< MAX(|\sigma_1|,|\sigma_2|,|\sigma_3|) $$

where: $$\sigma_{fail}$$= material strength. i.e. material's ultimate strength (tensile or compressive).  
$$\sigma$$ = principle stress in the respective direction. 

Therefore according to this theory, if principle stress (in any direction) is greater than material stress level, structure will fail.

### "Maximum shear" theory (Tresca)
$$ S< MAX(|\sigma_1-\sigma_2|,|\sigma_2 - \sigma_3|,|\sigma_3- \sigma_1|) $$

where: $$S_y$$= material yield stress 
$$\sigma$$ = principle stress in the respective direction. 

Unlike the Rankine's theory, maximum shear may occur outside the plane. 

### "Maximum distortion energy" theory (von Mises)
This theory proposes that, every material has the capability to absorb elastic deflection. When the "distortion work" done on the material exceeds the limit, the material yields.  Therefore according to  von Mises' theory, yield occurs when:

$$ \sigma_e  > S_y $$

where $$S_y$$ = material yield stress. $$\sigma_e$$ = equivalent stress (i.e. von Mises stress)

von Mises is determined using the following:

$$ \sigma_e = \frac{\sqrt 2}{2}[(\sigma_2-\sigma_1)^2+(\sigma_3-\sigma_1)^2+(\sigma_2-\sigma_3)^2]^{\frac{1}{2}}$$

### Mohr's circle
In both modes of failure, failure is compared against principle stress of the element. This stress is determined from Mohr's circle equations can be seen in [wikipedia](https://en.wikipedia.org/wiki/Mohr%27s_circle#Finding_principal_normal_stresses) .
Functions to determine princple stress, as well as plot Mohr's circle can be found at [this](https://github.com/vladdtuz/PersonalProjects/blob/master/mohr_circle.py) Github repository. This script contains three functions. 
1. Principle stress - detemines princple stresses, maximum shear and angle to principle plane
2. Orientation - detemines the new orientation stress levels
3. Circle - plots Mohr's circle for stresses

Therfore, desiging for failure under static conditions is done using the following steps:
1. Understanding type of failure. Ductile or Brittle?
2. Using Github script, detemine principle stresses
3. Apply failure criteria. Rankine for brittle failure; von Mises or Tesca for ductile

Cyclic loading failure will be discussed in a different post, at a later date
---
layout: post
title: "Understanding polarization of waves"
comments: true
description: "physics"
keywords: "physics, electromagnetism, waves"
---

Polarization refers to the direction that electric field points, given particular space and time. Typically, we think of the electric field as pointing in a linear direction. For instance, let $$H$$ and $$V$$ be the horizontal and vertical vectors respectively. This linear polarization is illustrated in figure below. When looking at the incoming waves along the z axis, the polarization ellipse shows a movement of up and down along the v axis.

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/linear-v.gif" width="400"/>


However, the fact is that the electric field vector direction can change in space and time. We know that it is orthogonal to the $$\mathbf{u_z}$$, unit vector of z axis. That means the electric field can be pointing to any direction in the plane $$\mathbf{H-V}$$. It does not necessarily have to point exactly in the $$\mathbf{u_h}$$ or $$\mathbf{u_v}$$, it can also point somewhere between them. On the surface, this makes polarization harder to capture mathematically. However, from the principles of superposition of plane waves, we know that the total wave is the sum of all components. Moreover, any plane wave can be subdivided into two or more components. This allows us to generalize the field in terms of h and v axes.

The corresponding equation of the plane wave is given by

$$\begin{align} 
E = \bf{u}_h E_h {\rm cos}(\omega t-kz+\phi_h) + 
\bf{u}_v E_v {\rm cos}(\omega t-kz+\phi_v) 

\end{align}$$ 

where $$\bf{u}_h$$ and $$\bf{u}_v$$ are the unit vector of h and v axes, respectively. As a brief refresher, $$\omega$$ (*angular frequency*) is a term that dictates at what time the amplitude resets, $$k$$ is a term that dictates at which distance along z-axis the amplitude resets.[^1]. Meanwhile, $$\phi_h$$ and $$\phi_v$$ are the terms that will shift the waves along the h and v axes respectively. 

## Case 1: Linear polarization - one component.

The simplest case is when the electrical field is just moving in one axis. We have shown one such case in figure above, where $$\mathbf{E}$$ is pointing only in $$ \pm \mathbf{u_v}$$. Mathematically, this can be written as 

$$\begin{align*}
E &= \bf{u}_h.0.{\rm cos}(\omega t-kz+\phi_h) + 
\bf{u}_v E_v {\rm cos}(\omega t-kz+\phi_v) \\
&= \bf{u}_h|E_v{\rm cos}(\omega t-kz+\phi_v) 
\end{align*}$$

In this case, $$\phi_z$$ can be set to zero, as it is not relevant in one component case.

## Case 2: Linear polarization - two components.

Another linear case is when when the electrical field is not pointing in the h or v directions. In this case, we rely on the equation above to make inference about the direction and amplitude of the polarization. Moreover, the phase terms $$ \phi_v,\phi_h$$ become very critical.

Consider the case when $$ \phi_v - \phi_h=0$$. In this case, the polarization will be a straight line along 45 $$^{\circ}$$. As $$E_h$$ moves to the right, $$E_v$$ moves up by the same magnitude, at the same time. These result in a 45 $$^{\circ}$$ line towards the top right. Conversely, when $$E_h$$ moves to the left, $$E_v$$ also moves down by the same magnitude, at the same time. These creates a line towards the bottom left. 


<img src="https://github.com/zulfadz/zulfadz.github.io/blob/master/pictures/%20idk0..gif?raw=true" width="400"/>

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/linear-45.gif" width="400"/>

Mirroring this observation is when $$\phi_v - \phi_h=\pi$$. In this case,  the polarization is a straight line along -45 $$^{\circ}$$.


<img src="https://github.com/zulfadz/zulfadz.github.io/blob/master/pictures/%20idk..gif?raw=true" width="400"/>

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/linear-negative45.gif" width="400"/>

Therefore, polarization remains linear (i.e. a straightline) in both cases. More generally, this happens when the phase terms are "in-sync". This occurs when $$ \phi_v - \phi_h=0, \pi, \pi,$$ or $$2\pi $$. 

## Case 3: Circular polarization.

Circular polarization occurs when the polarization is making a circular movement around the z axis. It may be difficult to imagine that a vector in space can have a circular component, but this is definitely possible from equation above. For circular polarization to occur, the phase terms should be out of sync by 

$$\begin{align*} 
\phi_v - \phi_h =\pi/2 \text{ or} -\pi/2
\end{align*}$$ 

and the amplitude remains the same, $$|E_h|=|E_v|$$. 



Figures below illustrates the case when $$\phi_h=0, \phi_v=\pi/2$$.

<img src="https://github.com/zulfadz/zulfadz.github.io/blob/master/pictures/%20idk0.5..gif?raw=true" width="400"/>

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/circular-rhs.gif" width="400"/>

## Case 4: Elliptical polarization.

The circular polarization is a specific case of elliptical polarization. In general, the amplitudes do not have to be the same. When the phase terms are out of sync by other values, the resulting polarization will resemble an ellipse. For instance, when $$\phi_v - \phi_h =\pi/4$$, we get the following polarization:

<img src="https://github.com/zulfadz/zulfadz.github.io/blob/master/pictures/%20idk0.25..gif?raw=true" width="400"/>


References:
1. [kridnix youtube channel](https://www.youtube.com/watch?v=84AcKIcF7VY&t=705s)
2. [Matlab simulation tool](https://www.mathworks.com/help/phased/ug/modeling-and-analyzing-polarization.html)


Footnote:

[^1]: [Khan Academy](https://www.youtube.com/watch?v=9WZM68aVnGk&t=618s)

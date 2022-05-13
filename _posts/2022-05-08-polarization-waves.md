---
layout: post
title: "Understanding polarization of waves"
comments: true
description: "physics"
keywords: "physics, electromagnetism, waves"
---


Polarization refers to the direction that electric field points, given particular space and time. Typically, we think of the electric field as pointing in a linear direction. For instance, let $$H$$ and $$V$$ be the horizontal and vertical vectors respectively. This linear polarization is illustrated in figure below. When looking at the incoming waves along the z axis, the polarization ellipse shows a movement of up and down along the v axis.

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/linear-v.gif" width="400"/>


However, the fact is that the electric field vector direction can change in space and time. We know that it is orthogonal to z axis. That means the electric field can be pointing to any direction in the plane $$H-V$$. In fact, there are many possible polarization patterns, and these are not just a linear straightline such as the above, but also circular and elliptical. A simulation can better help to visualise these.

Recall the equation of the plane wave:

$$\begin{align*} 
\mathbf{E} = u_h E_h  cos(\omega t-kz+\phi_h) + 
u_v E_v cos(\omega t-kz+\phi_v) 
\end{align*}$$[^1]

The simulation can be done in matlab using the following code[^2]:

```Matlab
Ah = 1;  % h amplitude
Av = 1;  % v amplitude
lamda = 2;  % wavelength
k = 2*pi/lamda;  % wave vector
dphi = input('Phase Difference in pi? ')*pi; % phase difference phiy - phix
z = linspace(0,4,160); % spatial variation
t = linspace(0,1,50); % time 
vp = 2;  % phase velocity 
f = vp/lamda;  % frequency
w = 2*pi*f; % omega

% Capture animation
% Prepare the new file.
filename = input('File Name?','s');
vid = VideoWriter(filename);
open(vid);

% Plot the wave
for m = 1:length(t)
    v = real(Av*exp(i*(w*t(m)- k*z+ dphi)));
    h = real(Ah*exp(i*(w*t(m) - k*z)));

    a = plot3(z,h,v,'b');
    set(a,'MarkerSize',10)
    for mm=2:length(h)
        %line([z(mm) z(mm)],[0 h(mm)],[0,v(mm)])  % use this for lines
        a=patch([z(mm) z(mm-1) z(mm-1) z(mm)],[0 0 h(mm-1) h(mm)],[0 0 v(mm-1) v(mm)],[.8 .8 .8]);
        set(a,'FaceAlpha',.7);
        set(a,'EdgeAlpha',.3);
        set(a,'EdgeColor',[0 .7 0]);
    end
    % set up graph
    a = line([0 max(z)],[0 0],[0 0]);
    set(a,'Color','k')
    box on
    grid on
    axis('equal')
    axis([0 4 -1 1 -1 1])
    xlabel('Z')
    ylabel('H')
    zlabel('V')

    % Plot dashline of the overall line on hv plane
    trailx(m) = h(1);
    traily(m) = v(1);
    trailz(m) = 0;
    hold on
    plot3(trailz,trailx,traily,'k.');
    hold off
    view(-45,20)
    
    % Customize the lines
    a = line([0 0],[0 h(1)],[0 0]);
    set(a,'LineWidth',3)
    set(a,'Color',[0 0 0]);
    % now the y source field...
    a = line([0 0],[0 0],[0 v(1)]);
    set(a,'LineWidth',3)
    set(a,'Color',[1 0 0]);
    % and the overall source field as a blue line
    a = line([0 0],[0 h(1)],[0 v(1)]);
    set(a,'LineWidth',3);
    set(a,'Color',[0 0 1]);
    % plot two narrow black lines to clarify it is vector addition
    a = line([0 0],[h(1) h(1)],[0 v(1)]);
    set(a,'LineWidth',1);
    set(a,'Color',[0 0 0]);
    a = line([0 0],[0 h(1)],[v(1) v(1)]);
    set(a,'LineWidth',1);
    set(a,'Color',[0 0 0]);

    % Capture a frame for the video, and put in a pause
    pause(.05)
    currFrame = getframe(gcf);
    writeVideo(vid,currFrame);
end
trailx = 0;
traily = 0
trailz = 0;

% Close the video file.
close(vid);

```
## Findings

### Case 1: Linear polarization - one component.

The simplest case is when the electrical field is just pointing in one axis, in which case either $$E_h$$ or $$E_v$$ to zero. One such case is shown in figure above, where $$\mathbf{E}$$ is pointing only in $$ \pm u_v$$.

### Case 2: Linear polarization - two components.

Consider the case when $$|E_h| = |E_v| =1$$ and $$ \phi_v - \phi_h=0$$. In this case, the polarization will be a straight line along 45 $$^{\circ}$$.  

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/linear-45.gif" width="400"/>

<img src="https://github.com/zulfadz/zulfadz.github.io/blob/master/pictures/%20idk0..gif?raw=true" width="400"/>


Mirroring this observation is when $$\phi_v - \phi_h=\pi$$. In this case,  the polarization is a straight line along -45 $$^{\circ}$$.

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/linear-negative45.gif" width="400"/>

<img src="https://github.com/zulfadz/zulfadz.github.io/blob/master/pictures/%20idk..gif?raw=true" width="400"/>


Therefore, polarization remains linear (i.e. a straightline) in both cases. More generally, this happens when the phase terms are "in-sync". This occurs when $$ \phi_v - \phi_h=0, \pi, \pi,$$ or $$2\pi $$. 

## Case 3: Circular polarization.

Circular polarization occurs when the polarization is making a circular movement around the z axis. It may be difficult to imagine that a vector in space can have a circular component. For circular polarization to occur, the phase terms should be out of sync by $$\phi_v - \phi_h =\pi/2$$ or $$ -\pi/2$$ and the amplitude remains the same. Figures below illustrates the case when $$\phi_h=0, \phi_v=\pi/2$$ and $$|E_h| = |E_v| =1$$.

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/circular-rhs.gif" width="400"/>

<img src="https://github.com/zulfadz/zulfadz.github.io/blob/master/pictures/%20idk0.5..gif?raw=true" width="400"/>


## Case 4: Elliptical polarization.

The circular polarization is a specific case of elliptical polarization. In general, the amplitudes do not have to be the same. When the phase terms are out of sync by other values, the resulting polarization will resemble an ellipse. For instance, when $$\phi_v - \phi_h =\pi/4$$, we get the following polarization:

<img src="https://github.com/zulfadz/zulfadz.github.io/blob/master/pictures/%20idk0.25..gif?raw=true" width="400"/>



Footnote:

[^1]: $$u_h$$ and $$u_v$$ are the unit vectors of h and v axes, respectively. As a brief refresher, $$\omega$$ (*angular frequency*) is a term that dictates at what time the amplitude resets, and $$k$$ is a term that dictates at which distance along z-axis the amplitude resets. Meanwhile, $$\phi_h$$ and $$\phi_v$$ are the phase terms. [Khan Academy](https://www.youtube.com/watch?v=9WZM68aVnGk&t=618s).
[^2]: Built based on a comment from youtube user [Alan Cheville](https://www.youtube.com/channel/UCLZHlgLIALvNRzVEDuvgoyQ)




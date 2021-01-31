# Adaptive Control Systems Design - MRAC

As part of the third assignment in the course of Neuro-fuzzy Control in Electrical and Computer Engineering in NTUA we were asked to design and simulate an adaptive control system for a 2-phase motor model including uncertainty and an unknown torque load on motor shaft.

The motor model is:

<img src="https://render.githubusercontent.com/render/math?math=\dot{\theta} = \omega">

<img src="https://render.githubusercontent.com/render/math?math=J\dot{\omega}=K_{m} i_{b} cos(N\theta) - K_{m} i_{a} sin(N \theta) - B\omega - T_L(\theta)">

where <img src="https://render.githubusercontent.com/render/math?math=\theta(rad)"> is the angular position, <img src="https://render.githubusercontent.com/render/math?math=\omega(\frac{rad}{sec})"> is and angular velocity, <img src="https://render.githubusercontent.com/render/math?math=i_a(A), i_b(A)"> are the phase currents (control inputs), <img src="https://render.githubusercontent.com/render/math?math=J=4.5 \times 10^{-5} kgr \cdot m^2"> is the moment of inertia of the motor, <img src="https://render.githubusercontent.com/render/math?math=K_m=0.19 N\cdot \frac{m}{A}"> is the motor torque constant, <img src="https://render.githubusercontent.com/render/math?math=B=8.0 \times 10^{-4} N \cdot m \cdot \frac{sec}{rad}"> is the friction coefficient, <img src="https://render.githubusercontent.com/render/math?math=N=50"> is the number of notches of the motor and <img src="https://render.githubusercontent.com/render/math?math=T_L(\theta)"> is the external load torque on the motor shaft which is a function of the angular position.

Finally, the reference model is:

<img src="https://quicklatex.com/cache3/47/ql_e9f70c0c7501c4342f6d008a9ae86347_l3.png">

<!-- \left[\begin{tabular}{c} $\dot{\theta_r}$ \\ $\dot{\omega_r}$ \end{tabular}\right]= \left[\begin{tabular}{c c} 0 & 1 \\ -24 & -10 \end{tabular}\right]\left[\begin{tabular}{c} $\theta_r$ \\ $\omega_r$ \end{tabular}\right] + \left[\begin{tabular}{c} 0 \\ 24 \end{tabular}\right]$\theta_c$
<img src="https://render.githubusercontent.com/render/math?math=\dot{\theta_r} = \omega_r">
<img src="https://render.githubusercontent.com/render/math?math=J\dot{\omega_r}=24 \theta_c-24 \theta_r -10 \omega_r"> -->

where <img src="https://render.githubusercontent.com/render/math?math=\theta_r(rad)"> and <img src="https://render.githubusercontent.com/render/math?math=\omega_r(\frac{rad}{sec})"> are the states of the reference model and <img src="https://render.githubusercontent.com/render/math?math=\theta_c"> is the reference command.

We will increase the reference command by 5 degrees every 3 seconds and we will set the unknown torque load as <img src="https://render.githubusercontent.com/render/math?math=T_L(\theta)=10^{-3} \cos^2(2\theta)\sin(3\theta) N\cdot m">

## Prerequisites

* scipy (to solve differential equations)
* matplotlib (for plotting)
* numpy

# Foucault Pendulum Simulation with RK4

This project numerically models the motion of a Foucault pendulum in a rotating reference frame. The goal was to study how the Coriolis and centrifugal terms affect the pendulum trajectory for different Rossby numbers.

## Overview

The motion of the pendulum is modeled using coupled differential equations for the horizontal displacements \(x(t)\) and \(y(t)\). After non-dimensionalizing the equations using the natural pendulum timescale, the system is solved numerically using the fourth-order Runge-Kutta method.

The project compares the motion for:

- \(R_0 = 10\)
- \(R_0 = 2\)
- \(R_0 = 1\)

where \(R_0\) measures the relative importance of the pendulum swing timescale compared to the rotation timescale.

## Methods

The second-order system was rewritten as a first-order system using the state vector:

\[
[x, y, v_x, v_y]
\]

The numerical solver uses RK4 with a step size of \(h = 0.01\) for the main trajectory simulations. A convergence test was also performed for \(R_0 = 2\) using step sizes:

\[
h = 0.1,\ 0.05,\ 0.025,\ 0.0125
\]

Richardson extrapolation was used to estimate the numerical error.

## Results

For larger \(R_0\), the pendulum behaves closer to a normal oscillating pendulum, with the plane of oscillation slowly changing direction. For \(R_0 = 10\), the trajectory forms a star-like pattern.

For \(R_0 = 2\), the rotational effects become stronger, producing a more distinct two-dimensional diamond-shaped trajectory.

For \(R_0 = 1\), the restoring and centrifugal terms cancel for the chosen initial conditions, causing the pendulum to remain at an equilibrium point.

## Skills Demonstrated

- Numerical integration of coupled differential equations
- Fourth-order Runge-Kutta method
- Non-dimensionalization
- Error analysis and convergence testing
- Richardson extrapolation
- Scientific computing with Python
- Data visualization with Matplotlib

## Files

- `FoucaultCode.ipynb` — Python notebook containing the RK4 solver, simulations, convergence test, and plots.
- `report/Connor_Beatty_Foucault_Discussion.pdf` — Full written project report.
- `figures/` — Output plots generated from the simulation.

## Requirements

```bash
numpy
matplotlib

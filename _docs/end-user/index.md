---
title: "End-User Tutorials"
nav_order: 1
permalink: /docs/end-user/
---

# End-User Tutorials

## Which Tutorial should you Read?
This guide helps you quickly identify where to start and which tutorials are relevant to your goals when working with BoSSS as an end-user.
#### Note:
This guide applies only to end-user tutorials. Developer tutorials are not required for running, validating, or scaling simulations.

### If you are completely new to BoSSS
Start here:
1.	Introduction to C# and Jupyter Notebooks / BoSSSpad
2.	Simple channel flow using the Incompressible Solver
After these two tutorials, you will be able to:
•	run BoSSS interactively
•	execute a complete CFD simulation
•	inspect basic results

### If you want to understand or modify a simulation setup
Read these next:
3.	Grid Generation
4.	Initial Values
5.	Further Topics on Initial and Boundary Values
These tutorials teach you how to:
•	create and modify computational grids,
•	define initial conditions,
•	specify boundary conditions correctly.
You should read them before attempting to change physics or geometry.

### If you want to run a compressible flow simulation
Read this tutorial:
6.	An Isentropic Vortex with the Compressible Navier–Stokes Solver
This tutorial assumes:
•	familiarity with grids,
•	initial and boundary values,
•	basic solver usage.
It introduces the compressible solver family and more advanced setups.

### If you can run simulations, but unsure whether the results are correct or not
Read this tutorial:
7.	Post-Processing, Errors, and Convergence (End-User View)
This tutorial explains:
•	how to interpret simulation results,
•	how to evaluate errors,
•	how to recognize convergence and failure modes.
You should read this before running large or expensive simulations.

### If you want to run many simulations or use a cluster
Read this tutorial:
8.	Workflow management and the Meta Job Scheduler
This tutorial shows how to:
•	run simulations non-interactively,
•	manage jobs on clusters,
•	automate execution.
You should already understand:
•	how to set up a simulation,
•	how to judge its correctness.

### If you want to perform convergence studies or parameter sweeps
Read this tutorial:
9.	Convergence and Parameter Studies using the Meta Job Scheduler
This is the final end-user tutorial.
It teaches you how to:
•	perform systematic refinement
•	vary parameters
•	design reproducible numerical studies

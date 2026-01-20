---
title: "Developer Tutorials"
nav_order: 2
permalink: /docs/developer/
---

# Developer Tutorials
Developer tutorials are intended for users who want to modify the source in
order to create their own solvers, they are not required for running simulations as an end user.


## Which Developer Tutorial Should you Read?
This guide helps you choose the appropriate developer tutorial depending on your goal when working with the BoSSS framework.


### If you want to understand the numerical foundations of BoSSS
Start here:
1.	DG Basics: Projection and Approximation Properties
2.	Numerical Fluxes

These tutorials explain:
*	how DG approximates functions
*	how inter-element coupling works
*	why numerical fluxes are essential for stability

You should read these before attempting to implement any operator.


### If you want to understand how elliptic operators are implemented and stabilized
Read these next:
3.	Symmetric Interior Penalty for the Poisson Equation
4.	Poisson Equation as a System

These tutorials explain:
*	stabilization of elliptic operators
*	mixed formulations
*	how Poisson-type operators are constructed in BoSSS

They form the foundation for:
*	Stokes solvers
*	Navier–Stokes solvers
*	diffusion operators

### If you want to understand BoSSS operator abstractions
Read this tutorial:
5.	Definition of Spatial Operators

This tutorial explains:
*	equation components
*	differential operators
*	how BoSSS maps weak forms to code

This is the core abstraction layer of the framework.

### If you want to understand time integration and stability
Read this tutorial:
6.	Numerical Stability of Time Integration

This tutorial explains:
*	timestep restrictions,
*	stability regions,
*	why certain time-stepping schemes are used.

It assumes familiarity with:
*	DG discretization
*	operator assembly

### If you want to study complete PDE implementations
Read these tutorials:
7.	Steady Stokes Equation
8.	Time-dependent Heat Equation Solver

These tutorials show:
*	how full PDE systems are assembled
*	how multiple operators interact
*	how time integration is applied in practice

They serve as reference implementations for developers.


### If you want to work with advanced or specialized framework internals
Read these tutorials (optional):
9.	Note on agglomeration in XDG
10.	Global versus Local Indices

These tutorials cover:
*	advanced grid and algebra concepts
*	performance-critical internal details

They are not required for most solver development tasks.


### If you want to analyze performance or interface with external tools
Read these tutorials:
11.	Memory Profiling of an Application
12.	Interacting with Matlab

These tutorials explain:
*	memory usage and profiling techniques
*	coupling BoSSS with external analysis tools

They are independent of numerical foundations.

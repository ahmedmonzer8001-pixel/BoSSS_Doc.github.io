---
title: "ALTSTests"
parent: "API Reference"
nav_order: 1
permalink: /docs/api/ALTSTests/
---
# Namespace: ALTSTests

## Class: ALTSTests.NUnitTests <a id="altstests.nunittests"></a>

**Summary:** NUnit test class for ALTS

## Class: ALTSTests.Program <a id="altstests.program"></a>

**Summary:** Test program for the implementation of A-LTS.
A scalar transport equation is being used for testing.
In total 1 test run is carried out:
- 1 run with A-LTS featuring a change in the cell metric
to trigger the dynamic (re-)clustering.

## Class: ALTSTests.ScalarTransportFlux2D <a id="altstests.scalartransportflux2d"></a>

**Summary:** Flux to a 2D scalar transport equation


## Method: ALTSTests.ScalarTransportFlux2D.FlowField(System.Double[],System.Double[],System.Double[]) <a id="altstests.scalartransportflux2d.flowfield(system.double[],system.double[],system.double[])"></a>
**Summary:** the predefined, div-free flow field


## Method: ALTSTests.ScalarTransportFlux2D.InnerEdgeFlux(System.Double,System.Double[],System.Double[],System.Double[],System.Double[],System.Int32) <a id="altstests.scalartransportflux2d.inneredgeflux(system.double,system.double[],system.double[],system.double[],system.double[],system.int32)"></a>
**Summary:** calculating the inner edge fluxes by using a first oder upwind scheme


### Property: ALTSTests.ScalarTransportFlux2D.ArgumentOrdering <a id="altstests.scalartransportflux2d.argumentordering"></a>


### Property: ALTSTests.ScalarTransportFlux2D.ParameterOrdering <a id="altstests.scalartransportflux2d.parameterordering"></a>
**Summary:** the transport velocity





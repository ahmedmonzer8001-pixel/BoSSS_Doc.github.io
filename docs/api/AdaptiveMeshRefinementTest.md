---
title: "AdaptiveMeshRefinementTest"
---
# Namespace: AdaptiveMeshRefinementTest

## Class: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain"></a>

**Summary:** App which performs basic tests on adaptive mesh refinement and dynamic load balancing.


### Field: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.DEGREE <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.degree"></a>
**Summary:** DG polynomial degree


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.SetInitial(System.Double) <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.setinitial(system.double)"></a>
**Summary:** Setting initial value.


### Field: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.alpha_A <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.alpha_a"></a>
**Summary:** Equation coefficient, species A.


### Field: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.alpha_B <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.alpha_b"></a>
**Summary:** Equation coefficient, species B.


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.DelUpdateLevelset(BoSSS.Foundation.DGField[],System.Double,System.Double,System.Double,System.Boolean) <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.delupdatelevelset(bosss.foundation.dgfield[],system.double,system.double,system.double,system.boolean)"></a>
**Summary:** Sets level-set and solution at time ('time' + 'dt').


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.TestDataFunc(System.Double,System.Double) <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.testdatafunc(system.double,system.double)"></a>
**Summary:** A polynomial expression which is projected onto **BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.TestData**; since it is polynomial,
the data should remain constant under refinement and coarsening.


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.uEx(System.Double[],System.Double) <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.uex(system.double[],system.double)"></a>
**Summary:** Function which is projected onto **BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.u**;


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.LevelIndicator(System.Int32,System.Int32) <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.levelindicator(system.int32,system.int32)"></a>
**Summary:** Very primitive refinement indicator, works on a gradient criterion.


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.AdaptiveMeshRefinementTestMain.GetCellsToRefine <a id="bosss.application.adaptivemeshrefinementtest.adaptivemeshrefinementtestmain.getcellstorefine"></a>
**Summary:** Creates the cellmask which should be refined.

## Class: BoSSS.Application.AdaptiveMeshRefinementTest.AllUpTest <a id="bosss.application.adaptivemeshrefinementtest.alluptest"></a>

**Summary:** Complete Test for the load balancing.


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.AllUpTest.RuntimeCostDynamicBalanceTest(System.Int32,System.Int32) <a id="bosss.application.adaptivemeshrefinementtest.alluptest.runtimecostdynamicbalancetest(system.int32,system.int32)"></a>
**Summary:** Da Test!

## Class: BoSSS.Application.AdaptiveMeshRefinementTest.ScalarTransportFlux <a id="bosss.application.adaptivemeshrefinementtest.scalartransportflux"></a>

**Summary:** Flux for an 2D scalar transport equation


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.ScalarTransportFlux.FlowField(System.Double[]) <a id="bosss.application.adaptivemeshrefinementtest.scalartransportflux.flowfield(system.double[])"></a>
**Summary:** The predefined, div-free flow field


## Method: BoSSS.Application.AdaptiveMeshRefinementTest.ScalarTransportFlux.InnerEdgeFlux(System.Double,System.Double[],System.Double[],System.Double[],System.Double[],System.Int32) <a id="bosss.application.adaptivemeshrefinementtest.scalartransportflux.inneredgeflux(system.double,system.double[],system.double[],system.double[],system.double[],system.int32)"></a>
**Summary:** a new comment
**Parameter:** `time` - 
**Parameter:** `X` - 
**Parameter:** `normal` - 
**Parameter:** `Uin` - 
**Parameter:** `Uout` - 
**Returns:**



### Property: BoSSS.Application.AdaptiveMeshRefinementTest.ScalarTransportFlux.ArgumentOrdering <a id="bosss.application.adaptivemeshrefinementtest.scalartransportflux.argumentordering"></a>


### Property: BoSSS.Application.AdaptiveMeshRefinementTest.ScalarTransportFlux.ParameterOrdering <a id="bosss.application.adaptivemeshrefinementtest.scalartransportflux.parameterordering"></a>
**Summary:** the transport velocity



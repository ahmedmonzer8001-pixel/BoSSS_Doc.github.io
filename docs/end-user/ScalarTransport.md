---
title: "ScalarTransport"
---
# Namespace: ScalarTransport

## Class: BoSSS.Application.ScalarTransport.ScalarTransportMain <a id="bosss.application.scalartransport.scalartransportmain"></a>

**Summary:** Application class of my own BoSSS Application


## Method: BoSSS.Application.ScalarTransport.ScalarTransportMain.Main(System.String[]) <a id="bosss.application.scalartransport.scalartransportmain.main(system.string[])"></a>
**Summary:** Entry point of my program
**Parameter:** `args` - 


## Method: BoSSS.Application.ScalarTransport.ScalarTransportMain.CreateOrLoadGrid <a id="bosss.application.scalartransport.scalartransportmain.createorloadgrid"></a>
**Summary:** creates a simple 2d/3d Cartesian grid within the domain $(-7,7)^D$


### Field: BoSSS.Application.ScalarTransport.ScalarTransportMain.u <a id="bosss.application.scalartransport.scalartransportmain.u"></a>
**Summary:** the scalar property that is convected


### Field: BoSSS.Application.ScalarTransport.ScalarTransportMain.OpValue <a id="bosss.application.scalartransport.scalartransportmain.opvalue"></a>
**Summary:** the result of operator evaluation


### Field: BoSSS.Application.ScalarTransport.ScalarTransportMain.Velocity <a id="bosss.application.scalartransport.scalartransportmain.velocity"></a>
**Summary:** transport velocity


### Field: BoSSS.Application.ScalarTransport.ScalarTransportMain.mpi_rank <a id="bosss.application.scalartransport.scalartransportmain.mpi_rank"></a>
**Summary:** stores the mpi processor rank - just for illustration


## Method: BoSSS.Application.ScalarTransport.ScalarTransportMain.CreateFields <a id="bosss.application.scalartransport.scalartransportmain.createfields"></a>
**Summary:** creates the field [BoSSS.Application.ScalarTransport.ScalarTransportMain.u](#bosss.application.scalartransport.scalartransportmain.u);


## Method: BoSSS.Application.ScalarTransport.ScalarTransportMain.CreateEquationsAndSolvers(BoSSS.Solution.LoadBalancing.GridUpdateDataVaultBase) <a id="bosss.application.scalartransport.scalartransportmain.createequationsandsolvers(bosss.solution.loadbalancing.gridupdatedatavaultbase)"></a>


## Method: BoSSS.Application.ScalarTransport.ScalarTransportMain.PerformanceVsCachesize <a id="bosss.application.scalartransport.scalartransportmain.performancevscachesize"></a>
**Summary:** Auto-tuning


## Method: BoSSS.Application.ScalarTransport.ScalarTransportMain.RunSolverOneStep(System.Int32,System.Double,System.Double) <a id="bosss.application.scalartransport.scalartransportmain.runsolveronestep(system.int32,system.double,system.double)"></a>
**Summary:** performs some timesteps


## Method: BoSSS.Application.ScalarTransport.ScalarTransportMain.PlotCurrentState(System.Double,BoSSS.Foundation.IO.TimestepNumber,System.Int32) <a id="bosss.application.scalartransport.scalartransportmain.plotcurrentstate(system.double,bosss.foundation.io.timestepnumber,system.int32)"></a>
**Summary:** performs Tecplot output of field [BoSSS.Application.ScalarTransport.ScalarTransportMain.u](#bosss.application.scalartransport.scalartransportmain.u)


## Method: BoSSS.Application.ScalarTransport.ScalarTransportMain.SetInitial(System.Double) <a id="bosss.application.scalartransport.scalartransportmain.setinitial(system.double)"></a>
**Summary:** sets some initial value for field [BoSSS.Application.ScalarTransport.ScalarTransportMain.u](#bosss.application.scalartransport.scalartransportmain.u);

## Class: BoSSS.Application.ScalarTransport.ScalarTransportFlux <a id="bosss.application.scalartransport.scalartransportflux"></a>

**Summary:** Flux for an 2D scalar transport equation


## Method: BoSSS.Application.ScalarTransport.ScalarTransportFlux.FlowField(System.Double[],System.Double[],System.Double[]) <a id="bosss.application.scalartransport.scalartransportflux.flowfield(system.double[],system.double[],system.double[])"></a>
**Summary:** the predefined, div-free flow field


## Method: BoSSS.Application.ScalarTransport.ScalarTransportFlux.InnerEdgeFlux(System.Double,System.Double[],System.Double[],System.Double[],System.Double[],System.Int32) <a id="bosss.application.scalartransport.scalartransportflux.inneredgeflux(system.double,system.double[],system.double[],system.double[],system.double[],system.int32)"></a>
**Summary:** a new comment
**Parameter:** `time` - 
**Parameter:** `x` - 
**Parameter:** `normal` - 
**Parameter:** `Uin` - 
**Parameter:** `Uout` - 
**Returns:**



### Property: BoSSS.Application.ScalarTransport.ScalarTransportFlux.ArgumentOrdering <a id="bosss.application.scalartransport.scalartransportflux.argumentordering"></a>


### Property: BoSSS.Application.ScalarTransport.ScalarTransportFlux.ParameterOrdering <a id="bosss.application.scalartransport.scalartransportflux.parameterordering"></a>
**Summary:** the transport velocity

## Class: BoSSS.Application.ScalarTransport.ScalarTransportFlux3D <a id="bosss.application.scalartransport.scalartransportflux3d"></a>

**Summary:** flux fo an 3D scalar transport equation


## Method: BoSSS.Application.ScalarTransport.ScalarTransportFlux3D.FlowField(System.Double[],System.Double[],System.Double[]) <a id="bosss.application.scalartransport.scalartransportflux3d.flowfield(system.double[],system.double[],system.double[])"></a>
**Summary:** predefined, div-free flow field


## Method: BoSSS.Application.ScalarTransport.ScalarTransportFlux3D.InnerEdgeFlux(System.Double,System.Double[],System.Double[],System.Double[],System.Double[],System.Int32) <a id="bosss.application.scalartransport.scalartransportflux3d.inneredgeflux(system.double,system.double[],system.double[],system.double[],system.double[],system.int32)"></a>
**Summary:** a new comment


### Property: BoSSS.Application.ScalarTransport.ScalarTransportFlux3D.ArgumentOrdering <a id="bosss.application.scalartransport.scalartransportflux3d.argumentordering"></a>


### Property: BoSSS.Application.ScalarTransport.ScalarTransportFlux3D.ParameterOrdering <a id="bosss.application.scalartransport.scalartransportflux3d.parameterordering"></a>
**Summary:** the transport velocity


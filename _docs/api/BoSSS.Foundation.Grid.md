---
title: "BoSSS.Foundation.Grid"
parent: "API Reference"
nav_order: 3
permalink: /docs/api/BoSSS.Foundation.Grid/
---
# Namespace: BoSSS.Foundation.Grid

## Class: BoSSS.Foundation.Grid.Classic.Grid1D <a id="bosss.foundation.grid.classic.grid1d"></a>

**Summary:** onedimensional grid


## Method: BoSSS.Foundation.Grid.Classic.Grid1D.#ctor <a id="bosss.foundation.grid.classic.grid1d.#ctor"></a>
**Summary:** constructs an empty 1D grid.


## Method: BoSSS.Foundation.Grid.Classic.Grid1D.ExponentialSpaceing(System.Double,System.Double,System.Int32,System.Double) <a id="bosss.foundation.grid.classic.grid1d.exponentialspaceing(system.double,system.double,system.int32,system.double)"></a>
**Summary:** creates exponentially distributed nodes between two points
**Parameter:** `loBound` - minimum;
**Parameter:** `hiBound` - maximum;
**Parameter:** `N` - number of nodes, i.e. length of the returend array
**Parameter:** `alpha` - stretching; must be grater than 0; if grater than one distribution of points gets finer
around 'loBound' and if smaller it becomes coarser.
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid1D.TanhSpacing(System.Double,System.Double,System.Int32,System.Double,System.Boolean) <a id="bosss.foundation.grid.classic.grid1d.tanhspacing(system.double,system.double,system.int32,system.double,system.boolean)"></a>
**Summary:** creates points with hyperbolic tangent distribution.
**Parameter:** `loBound` - minimum value of interval
**Parameter:** `hiBound` - maximum value of interval
**Parameter:** `N` - number of nodes, i.e. length of the returend array
**Parameter:** `alpha` - stretching; must be grater than zero
**Parameter:** `loBoundStP` - true, if finer distribution towards 'loBound' is desired
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid1D.TanhSpacing_DoubleSided(System.Double,System.Double,System.Int32,System.Double) <a id="bosss.foundation.grid.classic.grid1d.tanhspacing_doublesided(system.double,system.double,system.int32,system.double)"></a>
**Summary:** creates points with double sided symmetric hyperbolic tangent distribution.
**Parameter:** `loBound` - minimum value of interval
**Parameter:** `hiBound` - maximum value of interval
**Parameter:** `N` - number of nodes, i.e. length of the returend array
**Parameter:** `alpha` - stretching; must be grater than zero
**Returns:**

**Remark:**
finer distribution near the two ends


## Method: BoSSS.Foundation.Grid.Classic.Grid1D.LineGrid(System.Double[],System.Boolean) <a id="bosss.foundation.grid.classic.grid1d.linegrid(system.double[],system.boolean)"></a>
**Summary:** constructs a 1D-grid.
**Parameter:** `Nodes` - nodes of the grid.
**Parameter:** `periodic` - 


## Method: BoSSS.Foundation.Grid.Classic.Grid1D.LineGrid(System.Collections.Generic.ICollection{System.Double[]},System.Boolean) <a id="bosss.foundation.grid.classic.grid1d.linegrid(system.collections.generic.icollection{system.double[]},system.boolean)"></a>
**Summary:** constructs a 1D-grid consisting of multiple (not connected) segments
**Parameter:** `nodeSets` - a collection of node segments;
if running with more than one MPI process, only the input on rank 0 is considered
**Parameter:** `periodic` - 

## Class: BoSSS.Foundation.Grid.Classic.Grid2D <a id="bosss.foundation.grid.classic.grid2d"></a>

**Summary:** a two-dimensional grid.


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.#ctor(BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.grid.classic.grid2d.#ctor(bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Constructs an empty 2D grid.
**Parameter:** `_RefElement` - The [BoSSS.Foundation.Grid.RefElements.RefElement](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement) for this grid. Currently only grids with _one_ RefElement are supported!!!


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.#ctor <a id="bosss.foundation.grid.classic.grid2d.#ctor"></a>
**Summary:** empty ctor. to support cloning.


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.Cartesian2DGrid(System.Double[],System.Double[],BoSSS.Foundation.Grid.RefElements.CellType,System.Boolean,System.Boolean,System.Func{ilPSP.Vector,ilPSP.Vector},BoSSS.Platform.Utils.Geom.BoundingBox[]) <a id="bosss.foundation.grid.classic.grid2d.cartesian2dgrid(system.double[],system.double[],bosss.foundation.grid.refelements.celltype,system.boolean,system.boolean,system.func{ilpsp.vector,ilpsp.vector},bosss.platform.utils.geom.boundingbox[])"></a>
**Summary:** constructs a new 2D Grid
**Parameter:** `xNodes` - 
**Parameter:** `yNodes` - 
**Parameter:** `periodicX` - turn on periodic boundary conditions in x direction
**Parameter:** `periodicY` - turn on periodic boundary conditions in y direction
**Parameter:** `CutOuts` - Optional regions that are not meshed
**Parameter:** `type` - The type of the cells to be used
**Parameter:** `NonlinearGridTrafo` - Arbitrary transformation (i.e. a diffeomorphism, i.e. bijective and differentiable) applied to 'xNodes' and 'yNodes', optioanl


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.Trapezoidal2dGrid(System.Double,System.Double,System.Int32,System.Double[],BoSSS.Foundation.Grid.RefElements.CellType) <a id="bosss.foundation.grid.classic.grid2d.trapezoidal2dgrid(system.double,system.double,system.int32,system.double[],bosss.foundation.grid.refelements.celltype)"></a>
**Summary:** Constructs a new 2D Grid.

## Class: BoSSS.Foundation.Grid.Classic.Grid2D.PointsFunc <a id="bosss.foundation.grid.classic.grid2d.pointsfunc"></a>


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.BilinearSquareGrid(System.Double[],System.Double[],System.Double,System.Double,System.Double,BoSSS.Foundation.Grid.Classic.Grid2D.PointsFunc) <a id="bosss.foundation.grid.classic.grid2d.bilinearsquaregrid(system.double[],system.double[],system.double,system.double,system.double,bosss.foundation.grid.classic.grid2d.pointsfunc)"></a>
**Summary:** standard constructor;
performs basic checks on array dimensions;
**Remark:**
Grid creation is MPI-serial, i.e. on exit, all cells are located at MPI process rank 0.
During setup, the grid must be redistributed, e.g. by ParMETIS, see [BoSSS.Foundation.Grid.Classic.GridCommons.Redistribute(BoSSS.Foundation.IO.IDatabaseInfo,BoSSS.Foundation.Grid.GridPartType,System.String)](BoSSS.Foundation.md#bosss.foundation.grid.classic.gridcommons.redistribute(bosss.foundation.io.idatabaseinfo,bosss.foundation.grid.gridparttype,system.string)).
This will be usually done automatically.


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.Param2XY(System.Double,System.Double) <a id="bosss.foundation.grid.classic.grid2d.param2xy(system.double,system.double)"></a>
**Summary:** This Method convert Points in the Parametric r-s-Space into Points in the x-y-Space
**Parameter:** `rPoint` - 
**Parameter:** `sPoint` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid2D.CurvedSquareGrid(System.Double[],System.Double[],BoSSS.Foundation.Grid.RefElements.CellType,System.Boolean) <a id="bosss.foundation.grid.classic.grid2d.curvedsquaregrid(system.double[],system.double[],bosss.foundation.grid.refelements.celltype,system.boolean)"></a>
**Summary:** Generates a Grid Consisting of a Ring. from Coordinates in
Parametric Description[BoSSS.Foundation.Grid.Classic.Grid2D.Param2XY(System.Double,System.Double)](#bosss.foundation.grid.classic.grid2d.param2xy(system.double,system.double)). Later
Arbitrary Transformation Functions might be introduced.
**Parameter:** `rNodes` - Vector consisting of Points in radial direction, must be greater than 0.
**Parameter:** `sNodes` - Vector consisting of Points in rotational direction (1.0 represents 2Pi)
**Parameter:** `CellType` - Type of Elements. Currently only Quads supported.
**Parameter:** `PeriodicS` - Toggle for periodicity in s-direction
**Returns:**
A grid consisting of curved elements forming a (section of) a ring


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.CurvedSquareGridChannel(System.Double[],System.Double[],BoSSS.Foundation.Grid.RefElements.CellType,System.Boolean,System.Func{System.Double,System.Double,ilPSP.Vector}) <a id="bosss.foundation.grid.classic.grid2d.curvedsquaregridchannel(system.double[],system.double[],bosss.foundation.grid.refelements.celltype,system.boolean,system.func{system.double,system.double,ilpsp.vector})"></a>
**Summary:** Generates a Grid Consisting of a curved Surface from Coordinates in
Parametric Description[BoSSS.Foundation.Grid.Classic.Grid2D.Param2XY(System.Double,System.Double)](#bosss.foundation.grid.classic.grid2d.param2xy(system.double,system.double)). Later
Arbitrary Transformation Functions might be introduced.
**Parameter:** `rNodes` - Vector consisting of Points in r-Direction
**Parameter:** `sNodes` - Vector consisting of Points in s-Direction
**Parameter:** `CellType` - Type of Elements. Currently only Quads supported.
**Parameter:** `PeriodicR` - Toggle for periodicity in r-direction
**Parameter:** `Topology` - Convert Points in the Parametric r-s-Space (arguments) into Points in the x-y-Space (return value)
**Returns:**
A grid consisting of curved elements forming a curved Surface


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.UnstructuredTriangleGrid(System.Double[],System.Double[],System.Double) <a id="bosss.foundation.grid.classic.grid2d.unstructuredtrianglegrid(system.double[],system.double[],system.double)"></a>
**Summary:** creates an unstructured triangle grid on a Cartesian mesh.


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.HangingNodes2D(System.Boolean,System.Boolean,BoSSS.Foundation.Grid.Classic.GridCommons.GridBox[]) <a id="bosss.foundation.grid.classic.grid2d.hangingnodes2d(system.boolean,system.boolean,bosss.foundation.grid.classic.gridcommons.gridbox[])"></a>
**Summary:** Creates a grid in 2D with hanging nodes. 
Idea: gridBoxes defines the individual region and its resolution. All boxes are put together
and if one gridBox overlaps a previous one, it is cut out of the previous box. Thus, the boxes 
should be ordered from large to small in terms of physical dimension
**Parameter:** `periodicX` - 
**Parameter:** `periodicY` - 
**Parameter:** `gridBoxes` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid2D.HangingNodes2D(BoSSS.Foundation.Grid.Classic.GridCommons.GridBox[]) <a id="bosss.foundation.grid.classic.grid2d.hangingnodes2d(bosss.foundation.grid.classic.gridcommons.gridbox[])"></a>
**Summary:** Overload, if no periodic boundaries is needed
**Parameter:** `gridBoxes` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid2D.CheckConnectivity2D(BoSSS.Foundation.Grid.Classic.GridCommons.GridBox,BoSSS.Foundation.Grid.Classic.GridCommons.GridBox) <a id="bosss.foundation.grid.classic.grid2d.checkconnectivity2d(bosss.foundation.grid.classic.gridcommons.gridbox,bosss.foundation.grid.classic.gridcommons.gridbox)"></a>
**Parameter:** `coarse` - 
**Parameter:** `fine` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid2D.Ogrid(System.Double,System.Double,System.Int32,System.Int32,BoSSS.Foundation.Grid.RefElements.CellType) <a id="bosss.foundation.grid.classic.grid2d.ogrid(system.double,system.double,system.int32,system.int32,bosss.foundation.grid.refelements.celltype)"></a>
**Summary:** Generates a so-called O-grid of a circular domain.
**Parameter:** `Radius` - Radius of the circular domain.
**Parameter:** `CenterSectionWidth` - With of center section which is meshed Cartesian.
**Parameter:** `NoOfCenterNodes` - Number of nodes in the center section, in each direction. this also determines the 
Number of nodes in rotational direction for each of the four ring segments.
**Parameter:** `NoOfRadialNodes` - Number of nodes in the radial section.
**Parameter:** `type` - Cell type.
**Returns:**
A block-structured O-grid.


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.HalfOgrid(System.Double,System.Double,System.Int32,System.Int32,BoSSS.Foundation.Grid.RefElements.CellType) <a id="bosss.foundation.grid.classic.grid2d.halfogrid(system.double,system.double,system.int32,system.int32,bosss.foundation.grid.refelements.celltype)"></a>
**Summary:** Generates a so-called O-grid of a half circular domain
**Parameter:** `Radius` - Radius of the circular domain.
**Parameter:** `CenterSectionWidth` - With of center section which is meshed Cartesian.
**Parameter:** `NoOfCenterNodes` - Number of nodes in the center section, in height direction. this also determines the 
Number of nodes in rotational direction for each of the four ring segments.
**Parameter:** `NoOfRadialNodes` - Number of nodes in the radial section.
**Parameter:** `type` - Cell type.
**Returns:**
A block-structured O-grid.


## Method: BoSSS.Foundation.Grid.Classic.Grid2D.HelicalHangingNodes(System.Double,System.Double,System.Double,System.Double,System.Int32,System.Int32,System.Int32,System.Int32) <a id="bosss.foundation.grid.classic.grid2d.helicalhangingnodes(system.double,system.double,system.double,system.double,system.int32,system.int32,system.int32,system.int32)"></a>
**Summary:** Special-Purpose grid generator for helical solver project

## Class: BoSSS.Foundation.Grid.Classic.Grid3D <a id="bosss.foundation.grid.classic.grid3d"></a>

**Summary:** three-dimensional grids


## Method: BoSSS.Foundation.Grid.Classic.Grid3D.#ctor(BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.grid.classic.grid3d.#ctor(bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Constructs an empty 3D grid.
**Parameter:** `_RefElement` - 


## Method: BoSSS.Foundation.Grid.Classic.Grid3D.#ctor <a id="bosss.foundation.grid.classic.grid3d.#ctor"></a>
**Summary:** Private constructor to support de-serialization


## Method: BoSSS.Foundation.Grid.Classic.Grid3D.Cartesian3DGrid(System.Double[],System.Double[],System.Double[],BoSSS.Foundation.Grid.RefElements.CellType,System.Boolean,System.Boolean,System.Boolean,BoSSS.Platform.Utils.Geom.BoundingBox[]) <a id="bosss.foundation.grid.classic.grid3d.cartesian3dgrid(system.double[],system.double[],system.double[],bosss.foundation.grid.refelements.celltype,system.boolean,system.boolean,system.boolean,bosss.platform.utils.geom.boundingbox[])"></a>
**Summary:** Constructs a Cartesian 3D Grid
**Parameter:** `xNodes` - Array containing the nodes in x-Direction
**Parameter:** `yNodes` - Array containing the nodes in y-Direction
**Parameter:** `zNodes` - Array containing the nodes in z-Direction
**Parameter:** `periodicX` - Toggle for periodic boundary condition in x-direction
**Parameter:** `periodicY` - Toggle for periodic boundary condition in y-direction
**Parameter:** `periodicZ` - Toggle for periodic boundary condition in z-direction
**Parameter:** `_CellType` - The specific type of hexahedral elements to be used.
**Parameter:** `CutOuts` - Optional regions that are not meshed
**Returns:**
A Cartesian 3D grid with the given nodes.


## Method: BoSSS.Foundation.Grid.Classic.Grid3D.CylinderGrid(System.Double[],System.Double[],System.Double[],BoSSS.Foundation.Grid.RefElements.CellType,System.Boolean,System.Boolean) <a id="bosss.foundation.grid.classic.grid3d.cylindergrid(system.double[],system.double[],system.double[],bosss.foundation.grid.refelements.celltype,system.boolean,system.boolean)"></a>
**Parameter:** `rNodes` - nodes in radial direction: first node must be greater than 0.0.
**Parameter:** `sNodes` - 
**Parameter:** `zNodes` - 
**Parameter:** `type` - 
**Parameter:** `PeriodicZ` - 
**Parameter:** `PeriodicS` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid3D.HangingNodes3D(System.Boolean,System.Boolean,System.Boolean,BoSSS.Foundation.Grid.Classic.GridCommons.GridBox[]) <a id="bosss.foundation.grid.classic.grid3d.hangingnodes3d(system.boolean,system.boolean,system.boolean,bosss.foundation.grid.classic.gridcommons.gridbox[])"></a>
**Summary:** Creates a grid in 3D with hanging nodes. 
Idea: gridBoxes defines the individual region and its resolution. All boxes are put together
and if one gridBox overlaps a previous one, it is cut out of the previous box. Thus, the boxes 
should be ordered from large to small in terms of physical dimension
**Parameter:** `periodicX` - 
**Parameter:** `periodicY` - 
**Parameter:** `periodicZ` - 
**Parameter:** `gridBoxes` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid3D.CheckConnectivity3D(BoSSS.Foundation.Grid.Classic.GridCommons.GridBox,BoSSS.Foundation.Grid.Classic.GridCommons.GridBox) <a id="bosss.foundation.grid.classic.grid3d.checkconnectivity3d(bosss.foundation.grid.classic.gridcommons.gridbox,bosss.foundation.grid.classic.gridcommons.gridbox)"></a>
**Parameter:** `coarse` - 
**Parameter:** `fine` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid3D.SphereCutout(System.Double[],System.Double[],System.Double[],BoSSS.Foundation.Grid.RefElements.CellType) <a id="bosss.foundation.grid.classic.grid3d.spherecutout(system.double[],system.double[],system.double[],bosss.foundation.grid.refelements.celltype)"></a>
**Summary:** Cutout of a sphere
**Parameter:** `rNodes` - Radial nodes, currently r=0 is not supported
**Parameter:** `phiNodes` - Azimutal nodes, decoding multiples of 2 Pi
**Parameter:** `thetaNodes` - Polar nodes, decoding multiples of Pi,
supported range is (-0.5, 0.5) excluding the polar points///
**Parameter:** `type` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Classic.Grid3D.Ogrid(System.Double,System.Double,System.Int32,System.Int32,System.Double[],BoSSS.Foundation.Grid.RefElements.CellType) <a id="bosss.foundation.grid.classic.grid3d.ogrid(system.double,system.double,system.int32,system.int32,system.double[],bosss.foundation.grid.refelements.celltype)"></a>
**Summary:** Generates a so-called O-grid of a cylindrical domain.
**Parameter:** `Radius` - Radius of the circular domain.
**Parameter:** `CenterSectionWidth` - With of center section which is meshed Cartesian.
**Parameter:** `NoOfCenterNodes` - Number of nodes in the center section, in each direction. this also determines the 
Number of nodes in rotational direction for each of the four ring segments.
**Parameter:** `NoOfRadialNodes` - Number of nodes in the radial section.
**Parameter:** `type` - Cell type.
**Parameter:** `zNodes` - Nodes along the cylinder heigh.
**Returns:**
A block-structured O-grid.

## Class: BoSSS.Foundation.Grid.GridRefinementController <a id="bosss.foundation.grid.gridrefinementcontroller"></a>

**Summary:** Basic algorithms for refinement and coarsening.


## Method: BoSSS.Foundation.Grid.GridRefinementController.#ctor(BoSSS.Foundation.Grid.Classic.GridData,BoSSS.Foundation.Grid.CellMask,BoSSS.Foundation.Grid.CellMask,System.Boolean) <a id="bosss.foundation.grid.gridrefinementcontroller.#ctor(bosss.foundation.grid.classic.griddata,bosss.foundation.grid.cellmask,bosss.foundation.grid.cellmask,system.boolean)"></a>
**Summary:** Constructor for the grid refinement controller, defines input cells
**Parameter:** `CurrentGrid` - Current grid.
**Parameter:** `CutCells` - Cut cells will have always the max refinement level. Null is a valid input if no level-set is used.
**Parameter:** `cellsNotOK2Coarsen` - Cells which are not allowed to be coarsend. It is not necessary to include cut cells here, as they are handled by the cutCells CellMask.
**Parameter:** `EnsureHighestLevelAtPeriodicBoundary` - 


## Method: BoSSS.Foundation.Grid.GridRefinementController.ComputeGridChange(System.Int32[],System.Collections.Generic.List{System.Int32}@,System.Collections.Generic.List{System.Int32[]}@) <a id="bosss.foundation.grid.gridrefinementcontroller.computegridchange(system.int32[],system.collections.generic.list{system.int32}@,system.collections.generic.list{system.int32[]}@)"></a>
**Summary:** Computes refinement and coarsening lists 
(inputs for [BoSSS.Foundation.Grid.Classic.GridData.Adapt(System.Collections.Generic.IEnumerable{System.Int32},System.Collections.Generic.IEnumerable{System.Int32[]},BoSSS.Foundation.Grid.Classic.GridCorrelation@)](BoSSS.Foundation.md#bosss.foundation.grid.classic.griddata.adapt(system.collections.generic.ienumerable{system.int32},system.collections.generic.ienumerable{system.int32[]},bosss.foundation.grid.classic.gridcorrelation@))),
based on the max refinement level provided by the calling solver. This method is fully parallized.
**Parameter:** `localCellsToRefine` - Output, local indices of cells which should be refined.
**Parameter:** `localCellsToCoarsen` - Output, clusters of cells (identified by local cell indices) which can be combined into coarser cells.
**Parameter:** `LocalDesiredLevel` - The refinement level of each local cell.
**Returns:**
True if any refinement or coarsening of the current grid should be performed; otherwise false.


## Method: BoSSS.Foundation.Grid.GridRefinementController.ComputeGridChange(System.Func{System.Int32,System.Int32,System.Int32},System.Collections.Generic.List{System.Int32}@,System.Collections.Generic.List{System.Int32[]}@) <a id="bosss.foundation.grid.gridrefinementcontroller.computegridchange(system.func{system.int32,system.int32,system.int32},system.collections.generic.list{system.int32}@,system.collections.generic.list{system.int32[]}@)"></a>
**Summary:** Computes refinement and coarsening lists 
(inputs for [BoSSS.Foundation.Grid.Classic.GridData.Adapt(System.Collections.Generic.IEnumerable{System.Int32},System.Collections.Generic.IEnumerable{System.Int32[]},BoSSS.Foundation.Grid.Classic.GridCorrelation@)](BoSSS.Foundation.md#bosss.foundation.grid.classic.griddata.adapt(system.collections.generic.ienumerable{system.int32},system.collections.generic.ienumerable{system.int32[]},bosss.foundation.grid.classic.gridcorrelation@))),
based on a refinement indicator. If the calculation should work parallel 
it is recommend to use [BoSSS.Foundation.Grid.GridRefinementController.ComputeGridChange(System.Int32[],System.Collections.Generic.List{System.Int32}@,System.Collections.Generic.List{System.Int32[]}@)](#bosss.foundation.grid.gridrefinementcontroller.computegridchange(system.int32[],system.collections.generic.list{system.int32}@,system.collections.generic.list{system.int32[]}@)).
**Parameter:** `levelIndicator` - Mapping from (local cell index, current refinement level) to desired refinement level for the respective cell,
see [BoSSS.Foundation.Grid.Classic.Cell.RefinementLevel](BoSSS.Foundation.md#bosss.foundation.grid.classic.cell.refinementlevel).
**Parameter:** `localCellsToRefine` - Output, local indices of cells which should be refined.
**Parameter:** `localCellsToCoarsen` - Output, clusters of cells (identified by local cell indices) which can be combined into coarser cells.
**Returns:**
True if any refinement or coarsening of the current grid should be performed; otherwise false.


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetGlobalCellNeigbourship <a id="bosss.foundation.grid.gridrefinementcontroller.getglobalcellneigbourship"></a>
**Summary:** Computes the global cell neighbourship of all cells. 
Returns an jagged array where the 
- first index: global index of the current cell 
- second index: enumeration over neighbors.
- content: global index of neighbor cells.


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetGlobalNearBand(System.Int64[][]) <a id="bosss.foundation.grid.gridrefinementcontroller.getglobalnearband(system.int64[][])"></a>
**Summary:** Returns the cutcells + neighbours on a global level.
**Parameter:** `globalCellNeighbourship` - 


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetGlobalRefinementLevel(System.Int64[][],System.Collections.BitArray,System.Int32[]) <a id="bosss.foundation.grid.gridrefinementcontroller.getglobalrefinementlevel(system.int64[][],system.collections.bitarray,system.int32[])"></a>
**Summary:** Computes the level indicator for each cell (mpi global).
**Parameter:** `globalNeighbourship` - 
**Parameter:** `cutCellsWithNeighbours` - 
**Parameter:** `LocalDesiredLevel` - 


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetGlobalDesiredLevel(System.Collections.BitArray,System.Int32[]) <a id="bosss.foundation.grid.gridrefinementcontroller.getglobaldesiredlevel(system.collections.bitarray,system.int32[])"></a>
**Summary:** Writes the max desired level of the specified cells into an int-array (mpi global).
**Parameter:** `cutCellsWithNeighbours` - 
**Parameter:** `CellRefinementLevel` - 


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetGlobalCurrentLevel <a id="bosss.foundation.grid.gridrefinementcontroller.getglobalcurrentlevel"></a>
**Summary:** Gets the current refinement level for each global cell.


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetRefinementLevelRecursive(System.Int64,System.Int32,System.Int64[][],System.Int32[]) <a id="bosss.foundation.grid.gridrefinementcontroller.getrefinementlevelrecursive(system.int64,system.int32,system.int64[][],system.int32[])"></a>
**Summary:** Recursive computation for the desired level of each global cell.
**Parameter:** `globalCellIndex` - The global index of the current cell.
**Parameter:** `desiredLevel` - 
**Parameter:** `globalNeighbourship` - Jagged int-array where the first index refers to the current cell and the second one to the neighbour cells.
**Parameter:** `globalRefinementLevel` - 


## Method: BoSSS.Foundation.Grid.GridRefinementController.RefineNeighboursRecursive(System.Int32,System.Int32[],System.Int64,System.Int32,System.Int64[][],System.Int32[]) <a id="bosss.foundation.grid.gridrefinementcontroller.refineneighboursrecursive(system.int32,system.int32[],system.int64,system.int32,system.int64[][],system.int32[])"></a>
**Summary:** Recursive computation for the desired level of each global cell.
**Parameter:** `currentLevel` - The current level of the cell with the index globalCellIndex.
**Parameter:** `DesiredLevel` - Int-array of the desired level of each global cell.
**Parameter:** `globalCellIndex` - The global index of the current cell.
**Parameter:** `DesiredLevelNeigh` - The desired level of the neighbours of the current cell.
**Parameter:** `globalNeighbourship` - Jaggerd int-array where the first index refers to the current cell and the second one to the neighbour cells.
**Parameter:** `globalCurrentLevel` - 


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetCellsToRefine(System.Int32[]) <a id="bosss.foundation.grid.gridrefinementcontroller.getcellstorefine(system.int32[])"></a>
**Summary:** Gets all cells to refine and writes them to a local int-list.
**Parameter:** `globalDesiredLevel` - The desired level of all global cells.


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetCellsToCoarsen(System.Int32[],System.Int64[][],System.Collections.BitArray) <a id="bosss.foundation.grid.gridrefinementcontroller.getcellstocoarsen(system.int32[],system.int64[][],system.collections.bitarray)"></a>
**Summary:** Returns local cells to coarsen
**Parameter:** `globalRefinementLevel` - 
**Parameter:** `globalCellNeigbourship` - 
**Parameter:** `cutCellsWithNeighbours` - 


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetCellsOk2Coarsen(System.Int32[],System.Int64[][],System.Collections.BitArray) <a id="bosss.foundation.grid.gridrefinementcontroller.getcellsok2coarsen(system.int32[],system.int64[][],system.collections.bitarray)"></a>
**Summary:** Gets all cells to refine and writes them to a int-list.
**Parameter:** `globalDesiredLevel` - The desired level of all global cells.
**Parameter:** `globalCellNeigbourship` - Jaggerd int-array where the first index refers to the current cell and the second one to the neighbour cells.
**Parameter:** `cutCellsWithNeighbours` - 


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetGlobalCellsNotOK2Coarsen <a id="bosss.foundation.grid.gridrefinementcontroller.getglobalcellsnotok2coarsen"></a>
**Summary:** Globalize cellsNotOk2Coarsen


## Method: BoSSS.Foundation.Grid.GridRefinementController.FindCoarseningClusters(System.Collections.BitArray) <a id="bosss.foundation.grid.gridrefinementcontroller.findcoarseningclusters(system.collections.bitarray)"></a>
**Summary:** Gets all cells to be coarsened. This operates process local, no coarsening allowed over process boundaries.
**Parameter:** `oK2CoarsenGlobal` - A BitArray of all cells which should be coarsened.


## Method: BoSSS.Foundation.Grid.GridRefinementController.FindCoarseiningClusterRecursive(System.Int32,System.Int32,System.Int32[],System.Collections.BitArray,System.Func{System.Int32,BoSSS.Foundation.Grid.Classic.Cell},System.Int32,System.Int32,System.Int32,System.Collections.Generic.List{System.Int32},System.Boolean@) <a id="bosss.foundation.grid.gridrefinementcontroller.findcoarseiningclusterrecursive(system.int32,system.int32,system.int32[],system.collections.bitarray,system.func{system.int32,bosss.foundation.grid.classic.cell},system.int32,system.int32,system.int32,system.collections.generic.list{system.int32},system.boolean@)"></a>
**Summary:** Recursive computing of all coarsening clusters.
**Parameter:** `j` - The local index of the current cell.
**Parameter:** `MaxRecursionDeph` - The max recursion depht, depending on the spatial dimension of the grid.
**Parameter:** `CellNeighbours` - 
**Parameter:** `marker` - Returns true for all cells not ok to coarsen.
**Parameter:** `GetCell` - A func to find the current cell in the current grid.
**Parameter:** `currentRefinementLevel` - The refinement level of the current cell.
**Parameter:** `searchClusterID` - The ID of the current cluster.
**Parameter:** `clusterSize` - The size of the current cluster.
**Parameter:** `coarseningCluster` - The current coarsening cluster
**Parameter:** `complete` - Bool is true if recursion has found all cells of the current cluster.


## Method: BoSSS.Foundation.Grid.GridRefinementController.GetGlobalDesiredLevel(System.Func{System.Int32,System.Int32,System.Int32},System.Int64[][]) <a id="bosss.foundation.grid.gridrefinementcontroller.getglobaldesiredlevel(system.func{system.int32,system.int32,system.int32},system.int64[][])"></a>
**Summary:** Calculates the desired level for each global cell. Note that the desired level can only increase by 1 compared to the current level of the cell.
**Parameter:** `levelIndicator` - The level indicator func provided by the calling solver.
**Parameter:** `globalNeighbourship` - Jaggerd int-array where the first index refers to the current cell and the second one to the neighbour cells.

## Class: BoSSS.Foundation.Grid.OpenFOAMGrid <a id="bosss.foundation.grid.openfoamgrid"></a>

**Summary:** Instantiation of BoSSS grids from an OpenFOAM polymesh structure


## Method: BoSSS.Foundation.Grid.OpenFOAMGrid._SetForeignPointer(System.IntPtr) <a id="bosss.foundation.grid.openfoamgrid._setforeignpointer(system.intptr)"></a>
**Summary:** %


## Method: BoSSS.Foundation.Grid.OpenFOAMGrid._GetForeignPointer <a id="bosss.foundation.grid.openfoamgrid._getforeignpointer"></a>
**Summary:** %


## Method: BoSSS.Foundation.Grid.OpenFOAMGrid.#ctor(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32,System.Int32*,System.Int32,System.Int32**,System.Int32*,System.Int32*,System.Int32*,System.Double*,System.Int32**,System.Int32*) <a id="bosss.foundation.grid.openfoamgrid.#ctor(system.int32,system.int32,system.int32,system.int32,system.int32,system.int32*,system.int32,system.int32**,system.int32*,system.int32*,system.int32*,system.double*,system.int32**,system.int32*)"></a>
**Summary:** Create a BoSSS grid from an OpenFOAM mesh (polymesh)
**Parameter:** `faces` - point labels (indices) of faces, according to OpenFOAM polymesh description (array of arrays)
**Parameter:** `vertices_per_face` - number of vertices for each face
**Parameter:** `nCells` - number of cells in OpenFOAM polymesh
**Parameter:** `neighbour` - Neighbor cell labels for internal faces (length is 'nInternalFaces')
**Parameter:** `owner` - for each face, the owner cell label
**Parameter:** `nPoints` - number of points/vertices
**Parameter:** `nFaces` - number of faces
**Parameter:** `nInternalFaces` - number of internal faces
**Parameter:** `points` - point coordinates, array of 'nPoints'*3
**Parameter:** `names` - 
**Parameter:** `nameLenghts` - 
**Parameter:** `emptyTag` - 
**Parameter:** `nNames` - 
**Parameter:** `patchIDs` - 


## Method: BoSSS.Foundation.Grid.OpenFOAMGrid.#ctor(System.Int32,System.Int32[][],System.Int32[],System.Int32[],System.Double[0:,0:],System.String[],System.Int32[],System.Int32) <a id="bosss.foundation.grid.openfoamgrid.#ctor(system.int32,system.int32[][],system.int32[],system.int32[],system.double[0:,0:],system.string[],system.int32[],system.int32)"></a>
**Summary:** Create a BoSSS grid from an OpenFOAM mesh
**Parameter:** `faces` - point labels (indices) of faces, according to OpenFOAM polymesh description (array of arrays)
**Parameter:** `nCells` - number of cells in OpenFOAM polymesh
**Parameter:** `neighbour` - Neighbor cell labels for internal faces
**Parameter:** `owner` - for each face, the owner cell label
**Parameter:** `points` -
point coordinates
- 1st index: point index
- 2nd index: spatial direction
**Parameter:** `patchIDs` - 
**Parameter:** `emptyTag` - 
**Parameter:** `names` - 


## Method: BoSSS.Foundation.Grid.OpenFOAMGrid.TestMethod(System.Int32) <a id="bosss.foundation.grid.openfoamgrid.testmethod(system.int32)"></a>
**Summary:** Only for testing purposes
**Parameter:** `a` - 
**Returns:**



### Property: BoSSS.Foundation.Grid.OpenFOAMGrid.GridDataObject <a id="bosss.foundation.grid.openfoamgrid.griddataobject"></a>
**Summary:** The grid metrics


## Method: BoSSS.Foundation.Grid.OpenFOAMGrid.GetGridData <a id="bosss.foundation.grid.openfoamgrid.getgriddata"></a>
**Summary:** [BoSSS.Foundation.Grid.OpenFOAMGrid.GridDataObject](#bosss.foundation.grid.openfoamgrid.griddataobject)

## Class: BoSSS.Foundation.Grid.Voronoi.VoronoiGrid2D <a id="bosss.foundation.grid.voronoi.voronoigrid2d"></a>

**Summary:** Static methods to create Voronoi Meshes


## Method: BoSSS.Foundation.Grid.Voronoi.VoronoiGrid2D.Rectangle(System.Double,System.Double,System.Int32) <a id="bosss.foundation.grid.voronoi.voronoigrid2d.rectangle(system.double,system.double,system.int32)"></a>
**Summary:** Create a random voronoi mesh inside a rectangle
**Parameter:** `width` - 
**Parameter:** `height` - 
**Parameter:** `numberOfNodes` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Voronoi.VoronoiGrid2D.Rectangle(System.Double[],System.Double[]) <a id="bosss.foundation.grid.voronoi.voronoigrid2d.rectangle(system.double[],system.double[])"></a>
**Summary:** Create a regular checkerboard mesh
**Parameter:** `xTics` - Ascending tics of grid in x direction.
**Parameter:** `yTics` - Ascending tics of grid in y direction.
**Returns:**



## Method: BoSSS.Foundation.Grid.Voronoi.VoronoiGrid2D.Polygonal(ilPSP.Vector[],System.Int32,System.Int32) <a id="bosss.foundation.grid.voronoi.voronoigrid2d.polygonal(ilpsp.vector[],system.int32,system.int32)"></a>
**Summary:** Creates a random voronoi mesh inside a polygon.
**Parameter:** `polygonBoundary` - Outer boundary of mesh. Is expected to be closed and must be non-overlapping.
**Parameter:** `noOfLyyodsIter` - Number of smoothing iterations.
**Parameter:** `noOfNodeSeed` - Number of random nodes that are placed in the bounding box of the PolygonBoundary.
**Returns:**



## Method: BoSSS.Foundation.Grid.Voronoi.VoronoiGrid2D.Polygonal(BoSSS.Foundation.Grid.Voronoi.VoronoiBoundary,System.Int32,System.Int32) <a id="bosss.foundation.grid.voronoi.voronoigrid2d.polygonal(bosss.foundation.grid.voronoi.voronoiboundary,system.int32,system.int32)"></a>
**Summary:** Creates a voronoi mesh inside a polygon.
**Parameter:** `boundary` - Specifies polygonal boundary, edgetags, bounding box, ...
**Parameter:** `noOfLyyodsIter` - Number of smoothing iterations.
**Parameter:** `noOfNodeSeed` - Number of random nodes that are placed in the bounding box of the PolygonBoundary.
**Returns:**



## Method: BoSSS.Foundation.Grid.Voronoi.VoronoiGrid2D.Polygonal(ilPSP.MultidimensionalArray,ilPSP.Vector[],System.Int32,System.Int32) <a id="bosss.foundation.grid.voronoi.voronoigrid2d.polygonal(ilpsp.multidimensionalarray,ilpsp.vector[],system.int32,system.int32)"></a>
**Summary:** Creates a voronoi mesh inside a polygon.
**Parameter:** `nodePositions` - Voronoi nodes: Center of each agglomerated cell. Will not be considered if outside of PolygonBoundary.
**Parameter:** `polygonBoundary` - Outer boundary of mesh. Is expected to be closed and must be non-overlapping.
**Parameter:** `noOfLyyodsIter` - Number of smoothing iterations.
**Parameter:** `firstCellNodeIndice` - Indices of node where the algorithm will start looking for the first Vector of PolygonBoundary.
**Returns:**


## Class: BoSSS.Foundation.Grid.Voronoi.Meshing.DataStructures.CountingEnumerator`1 <a id="bosss.foundation.grid.voronoi.meshing.datastructures.countingenumerator`1"></a>

**Summary:** Wrapper arround IEnumerator object that counts the enumerated objects

## Class: BoSSS.Foundation.Grid.Voronoi.Meshing.DataStructures.LinkedListDictionary`2 <a id="bosss.foundation.grid.voronoi.meshing.datastructures.linkedlistdictionary`2"></a>

**Summary:** LinkedList implementation of Dictionary. Needs minimal ammount of memory, 
but has O(n) complexity for Contains Key/Value and TryGetValue.
Should be used for very small (less than 10) dictionary.Count.

## Class: BoSSS.Foundation.Grid.Voronoi.Meshing.InsideCellEnumerator`1 <a id="bosss.foundation.grid.voronoi.meshing.insidecellenumerator`1"></a>


## Method: BoSSS.Foundation.Grid.Voronoi.Meshing.InsideCellEnumerator`1.RecursiveYieldConnectedCells(BoSSS.Foundation.Grid.Voronoi.Meshing.MeshCell{`0},System.Collections.Generic.HashSet{System.Int32}) <a id="bosss.foundation.grid.voronoi.meshing.insidecellenumerator`1.recursiveyieldconnectedcells(bosss.foundation.grid.voronoi.meshing.meshcell{`0},system.collections.generic.hashset{system.int32})"></a>
**Summary:** Enumerates the cells inside the boundary of this mesh.
Recursion produces Stack overflow, when to many cells in mesh.
**Parameter:** `cell` - Enumeration starts with this cell and then return its neighbors and so on.
**Parameter:** `visited` - 
**Returns:**



## Method: BoSSS.Foundation.Grid.Voronoi.Meshing.InsideCellEnumerator`1.IterativeYieldConnectedCells(BoSSS.Foundation.Grid.Voronoi.Meshing.MeshCell{`0},System.Collections.Generic.HashSet{System.Int32}) <a id="bosss.foundation.grid.voronoi.meshing.insidecellenumerator`1.iterativeyieldconnectedcells(bosss.foundation.grid.voronoi.meshing.meshcell{`0},system.collections.generic.hashset{system.int32})"></a>
**Summary:** Enumerates the cells inside the boundary of this mesh.
**Parameter:** `cell` - Enumeration starts with this cell and then return its neighbors and so on.
**Parameter:** `visited` - 
**Returns:**


## Class: BoSSS.Foundation.Grid.Voronoi.Meshing.MatlabPlotter <a id="bosss.foundation.grid.voronoi.meshing.matlabplotter"></a>


### Field: BoSSS.Foundation.Grid.Voronoi.Meshing.MatlabPlotter.CellColor <a id="bosss.foundation.grid.voronoi.meshing.matlabplotter.cellcolor"></a>
**Summary:** MatlabColor


### Field: BoSSS.Foundation.Grid.Voronoi.Meshing.MatlabPlotter.NodePlotSettings <a id="bosss.foundation.grid.voronoi.meshing.matlabplotter.nodeplotsettings"></a>
**Summary:** https://de.mathworks.com/help/matlab/ref/scatter.html

## Class: BoSSS.Foundation.Grid.Voronoi.Meshing.Transformation <a id="bosss.foundation.grid.voronoi.meshing.transformation"></a>


## Method: BoSSS.Foundation.Grid.Voronoi.Meshing.Transformation.Combine(BoSSS.Foundation.Grid.Voronoi.Meshing.Transformation,BoSSS.Foundation.Grid.Voronoi.Meshing.Transformation) <a id="bosss.foundation.grid.voronoi.meshing.transformation.combine(bosss.foundation.grid.voronoi.meshing.transformation,bosss.foundation.grid.voronoi.meshing.transformation)"></a>
**Summary:** Combine a(x) and b(x) to c(x) = a(b(x))
**Parameter:** `a` - 
**Parameter:** `b` - 
**Returns:**





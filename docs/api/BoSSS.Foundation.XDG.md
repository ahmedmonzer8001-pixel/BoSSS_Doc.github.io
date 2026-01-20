---
title: "BoSSSFoundationXDG"
parent: "API Reference"
nav_order: 5
---
# Namespace: BoSSS.Foundation.XDG

## Class: BoSSS.Foundation.XDG.AgglomerationAlgorithm <a id="bosss.foundation.xdg.agglomerationalgorithm"></a>

**Summary:** Sometimes, this provides indeed a correct agglomeration graph ;), 
the result is stored in [BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationPairs](#bosss.foundation.xdg.agglomerationalgorithm.agglomerationpairs).
If agglomeration fails -- which it does quite regularly -- unleash the [BoSSS.Foundation.XDG.AgglomerationAlgorithm.Katastrophenplot](#bosss.foundation.xdg.agglomerationalgorithm.katastrophenplot) to see the mess!

**Remark:**
Cell agglomeration is used to handle two problems:
first, for the treatment of very small cut cells and, for temporally evolving interfaces, to 
ensure an equal topology of the (agglomerated) XDG cut-cell mesh for all involved temporal levels.
- the issue of small cut cells is described in the paper:
_Extended discontinuous Galerkin methods for two-phase flows: the spatial discretization; Kummer; IJNMF 109 (2), 2017_. 
- the agglomeration of _newborn_ and _decased_ cells is described in 
the paper: _Time integration for extended discontinuous Galerkin methods with moving domains; Kummer, Müller, Utz; IJNMF 113 (5), 2018_.
- cell agglomeration is performed per species, this implementation looks only at one species at time;

## Class: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup"></a>

**Summary:** defines a group of agglomeration sources to create appropriate agglomeration pairs (source and target)


### Field: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup.jCellGroupTarget <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup.jcellgrouptarget"></a>
**Summary:** local cell index of agglomeration target cell (the cell where volume is added)


### Field: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup.OwnerRank4GroupTarget <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup.ownerrank4grouptarget"></a>
**Summary:** MPI rank of the process which owns cell [BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup.OwnerRank4GroupTarget](#bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup.ownerrank4grouptarget)


### Field: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup.Sources <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup.sources"></a>
**Summary:** list of agglomeration source cells


### Field: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup.NeighborCells <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup.neighborcells"></a>
**Summary:** list of neighbor edges via connected edges


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup.GetHashCode <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup.gethashcode"></a>
**Summary:** GetHashCode
**Returns:**



## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup.Equals(BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup) <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup.equals(bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup)"></a>
**Parameter:** `other` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationGroup.ToString <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationgroup.tostring"></a>
**Summary:** Returns a string listing the chain target cell and the agglomeration pairs in the chain


### Field: BoSSS.Foundation.XDG.AgglomerationAlgorithm.Katastrophenplot <a id="bosss.foundation.xdg.agglomerationalgorithm.katastrophenplot"></a>
**Summary:** Temporary feature; will be removed in future;
Plotting if agglomeration fails.


### Field: BoSSS.Foundation.XDG.AgglomerationAlgorithm.debugging_PlotAgglomeration <a id="bosss.foundation.xdg.agglomerationalgorithm.debugging_plotagglomeration"></a>
**Summary:** If agglomeration plots are demanded. A flag for debugging purposes in the agglomeration algorithm.


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.XDG.SpeciesId,System.Int32,System.Double,System.Double[],System.Double,System.Boolean,System.Boolean,System.Boolean,System.String) <a id="bosss.foundation.xdg.agglomerationalgorithm.#ctor(bosss.foundation.xdg.levelsettracker,bosss.foundation.xdg.speciesid,system.int32,system.double,system.double[],system.double,system.boolean,system.boolean,system.boolean,system.string)"></a>


### Field: BoSSS.Foundation.XDG.AgglomerationAlgorithm.EmptyEdgeTreshold <a id="bosss.foundation.xdg.agglomerationalgorithm.emptyedgetreshold"></a>
**Summary:** edges with a measure below or equal to this threshold are
considered to be 'empty', therefore they should not be used for agglomeration;
there is, as always, an exception: if all inner edges which belong to a
cell that should be agglomerated, the criterion mentioned above must be ignored.


### Property: BoSSS.Foundation.XDG.AgglomerationAlgorithm.Tracker <a id="bosss.foundation.xdg.agglomerationalgorithm.tracker"></a>
**Summary:** reference level set tracker


### Property: BoSSS.Foundation.XDG.AgglomerationAlgorithm.spId <a id="bosss.foundation.xdg.agglomerationalgorithm.spid"></a>
**Summary:** species, for which the agglomeration graph is determined


### Property: BoSSS.Foundation.XDG.AgglomerationAlgorithm.grdDat <a id="bosss.foundation.xdg.agglomerationalgorithm.grddat"></a>
**Summary:** reference grid data


### Property: BoSSS.Foundation.XDG.AgglomerationAlgorithm.m_AggPairsWithExtNeighborPairs <a id="bosss.foundation.xdg.agglomerationalgorithm.m_aggpairswithextneighborpairs"></a>
**Summary:** returns the unique pairs on this this processor and neighbors pairs (not all pairs of the neighbor procs)


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.FindAgglomerationSources <a id="bosss.foundation.xdg.agglomerationalgorithm.findagglomerationsources"></a>
**Summary:** 1st pass: of agglomeration algorithm, Identification of agglomeration sources
**Returns:**
- `AgglomCellsList`: all agglomeration sources
- `AgglomCellsBitmask`: the same as `AgglomCellsList`, just in bit-mask form
- `AggCandidates`: all cells which are allowed as **potential** agglomeration **targets*


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.FindAgglomerationTargets(System.Collections.Generic.List{System.Int32},System.Collections.BitArray,System.Collections.BitArray) <a id="bosss.foundation.xdg.agglomerationalgorithm.findagglomerationtargets(system.collections.generic.list{system.int32},system.collections.bitarray,system.collections.bitarray)"></a>
**Summary:** 2nd pass of agglomeration algorithm, Identification of agglomeration targets
**Remark:**
Old version, used until Dec. 2021


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.DoAggPairsMPIexchangeForGhostCells(System.Collections.Generic.List{BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair},System.Collections.Generic.List{BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair}@) <a id="bosss.foundation.xdg.agglomerationalgorithm.doaggpairsmpiexchangeforghostcells(system.collections.generic.list{bosss.foundation.xdg.cellagglomerator.agglomerationpair},system.collections.generic.list{bosss.foundation.xdg.cellagglomerator.agglomerationpair}@)"></a>
**Summary:** Exchange the local agglomeration pairs with their neighbors (only the ranks that is adjacent to the cells in a pair)
**Parameter:** `AggPairs` - Local pairs [BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair](#bosss.foundation.xdg.cellagglomerator.agglomerationpair)See agglomeration pairs
**Parameter:** `AggPairsOnExtNeighborPairs` - Incoming pairs
**Returns:**



## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.FindAgglomerationTargets_Mk2(System.Collections.Generic.List{System.Int32},System.Collections.BitArray,System.Collections.BitArray) <a id="bosss.foundation.xdg.agglomerationalgorithm.findagglomerationtargets_mk2(system.collections.generic.list{system.int32},system.collections.bitarray,system.collections.bitarray)"></a>
**Summary:** 2nd pass of agglomeration algorithm, Identification of agglomeration targets
**Remark:**
Revised algorithm, in use since Dec. 2021


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.FindAgglomerationTargets_Mk3(System.Collections.Generic.List{System.Int32},System.Collections.BitArray,System.Collections.BitArray,System.Collections.Generic.List{System.Int32},System.Collections.Generic.List{System.Int32}) <a id="bosss.foundation.xdg.agglomerationalgorithm.findagglomerationtargets_mk3(system.collections.generic.list{system.int32},system.collections.bitarray,system.collections.bitarray,system.collections.generic.list{system.int32},system.collections.generic.list{system.int32})"></a>
**Summary:** 3rd pass of agglomeration algorithm, Identification of agglomeration targets
**Remark:**
Revised algorithm for chains, in use since Sept. 2023


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.SearchChainAgglomeration_Mk3(System.Collections.Generic.List{System.Int32},System.Collections.BitArray,System.Collections.BitArray) <a id="bosss.foundation.xdg.agglomerationalgorithm.searchchainagglomeration_mk3(system.collections.generic.list{system.int32},system.collections.bitarray,system.collections.bitarray)"></a>
**Summary:** searches chaing agglomeration targets
**Parameter:** `CellsNeedChainAgglomeration` - 
**Parameter:** `AggCandidates` - 
**Parameter:** `AggSourcesWithExternalCell` - 


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.SearchDirectAgglomeration_Mk3(System.Collections.Generic.List{System.Int32},System.Collections.BitArray,System.Collections.BitArray) <a id="bosss.foundation.xdg.agglomerationalgorithm.searchdirectagglomeration_mk3(system.collections.generic.list{system.int32},system.collections.bitarray,system.collections.bitarray)"></a>
**Summary:** searches direct agglomeration targets
**Parameter:** `AgglomSourceCellsList` - 
**Parameter:** `AggCandidates` - 
**Parameter:** `AggSourcesWithExternalCell` - 


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.SearchGroupAgglomeration_Mk3(System.Collections.Generic.List{System.Int32},System.Collections.BitArray,System.Collections.BitArray,System.Collections.Generic.List{System.Int32}) <a id="bosss.foundation.xdg.agglomerationalgorithm.searchgroupagglomeration_mk3(system.collections.generic.list{system.int32},system.collections.bitarray,system.collections.bitarray,system.collections.generic.list{system.int32})"></a>
**Summary:** creates agglomeration groups from cut cells isolated from uncut cells, with the biggests being targets
**Parameter:** `CellsNeedChainAgglomeration` - 
**Parameter:** `AggCandidates` - 
**Parameter:** `AggSourcesWithExternalCell` - 
**Parameter:** `CellsRequireTopologyChanges` - 


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.PlotFail(System.Boolean,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray[],System.Collections.Generic.List{System.Int32},System.Collections.Generic.List{System.Int32},System.Collections.BitArray,System.Int32[],System.Int32[],System.Int32[],ilPSP.Vector[],System.Double[],System.String) <a id="bosss.foundation.xdg.agglomerationalgorithm.plotfail(system.boolean,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray[],system.collections.generic.list{system.int32},system.collections.generic.list{system.int32},system.collections.bitarray,system.int32[],system.int32[],system.int32[],ilpsp.vector[],system.double[],system.string)"></a>
**Summary:** plot failure as tecplot
**Parameter:** `ExceptionOnFailedAgglomeration` - 
**Parameter:** `CellVolumes` - 
**Parameter:** `oldCellVolumes` - 
**Parameter:** `AgglomCellsList` - 
**Parameter:** `failCells` - 
**Parameter:** `aggCandidates` - 
**Parameter:** `aggTargets` - 
**Parameter:** `pairIdentification` - 
**Parameter:** `pairColor` - 
**Parameter:** `aggDirection` - 
**Parameter:** `volFrac` - 
**Parameter:** `Tag` - 


## Method: BoSSS.Foundation.XDG.AgglomerationAlgorithm.GetEdgeInfo(System.Int32) <a id="bosss.foundation.xdg.agglomerationalgorithm.getedgeinfo(system.int32)"></a>
**Summary:** returns the cell indices for an edge
**Parameter:** `iEdge` - local edge index
**Returns:**



### Property: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationPairs <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationpairs"></a>
**Summary:** Result of the algorithm


### Property: BoSSS.Foundation.XDG.AgglomerationAlgorithm.AgglomerationPairsWithRanks <a id="bosss.foundation.xdg.agglomerationalgorithm.agglomerationpairswithranks"></a>
**Summary:** Result of the algorithm

## Class: BoSSS.Foundation.XDG.CellAgglomerator <a id="bosss.foundation.xdg.cellagglomerator"></a>

**Summary:** Cell agglomeration for a single species;
This class is responsible for applying a given agglomeration graph onto operator matrices and residual vectors,
see [BoSSS.Foundation.XDG.CellAgglomerator.ManipulateMatrixAndRHS``2(``0,``1,BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.UnsetteledCoordinateMapping)](#bosss.foundation.xdg.cellagglomerator.manipulatematrixandrhs``2(``0,``1,bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.unsetteledcoordinatemapping)) and [BoSSS.Foundation.XDG.CellAgglomerator.ManipulateRHS``1(``0,BoSSS.Foundation.UnsetteledCoordinateMapping)](#bosss.foundation.xdg.cellagglomerator.manipulaterhs``1(``0,bosss.foundation.unsetteledcoordinatemapping)).
The agglomeration graph itself is computed by [BoSSS.Foundation.XDG.AgglomerationAlgorithm](#bosss.foundation.xdg.agglomerationalgorithm).

## Class: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair"></a>

**Summary:** defines a pair (source and target) of cells affected by agglomeration

**Remark:**
A pair is local when the source cell is local (OwnerRank4Source) but still needs to be present on target ranks (OwnerRank4Target)


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.jCellTarget <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.jcelltarget"></a>
**Summary:** local cell index of agglomeration target cell (the cell where volume is added)


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.OwnerRank4Target <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.ownerrank4target"></a>
**Summary:** MPI rank of the process which owns cell [BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.jCellTarget](#bosss.foundation.xdg.cellagglomerator.agglomerationpair.jcelltarget)


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.posTarget <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.postarget"></a>
**Summary:** position of the target cell


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.fracTarget <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.fractarget"></a>
**Summary:** position of the target cell


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.jCellSource <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.jcellsource"></a>
**Summary:** local cell index of agglomeration source cell (the cell which is eliminated)


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.OwnerRank4Source <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.ownerrank4source"></a>
**Summary:** MPI rank of the process which owns cell [BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.jCellSource](#bosss.foundation.xdg.cellagglomerator.agglomerationpair.jcellsource)


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.AgglomerationLevel <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.agglomerationlevel"></a>
**Summary:** level-0 agglomerations have to be done first, level=1 agglomerations second, ...


## Method: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.GetHashCode <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.gethashcode"></a>
**Returns:**



## Method: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.Equals(BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair) <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.equals(bosss.foundation.xdg.cellagglomerator.agglomerationpair)"></a>
**Parameter:** `other` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.ToString <a id="bosss.foundation.xdg.cellagglomerator.agglomerationpair.tostring"></a>

## Class: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo"></a>

**Summary:** General information about the structure of the agglomeration, see [BoSSS.Foundation.XDG.CellAgglomerator.AggInfo](#bosss.foundation.xdg.cellagglomerator.agginfo)


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.MaxLevel <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.maxlevel"></a>
**Summary:** The MPI-global maximum over all [BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.AgglomerationLevel](#bosss.foundation.xdg.cellagglomerator.agglomerationpair.agglomerationlevel) 
for all [BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.AgglomerationPairs](#bosss.foundation.xdg.cellagglomerator.agglomerationinfo.agglomerationpairs).


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.InterProcessAgglomeration <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.interprocessagglomeration"></a>
**Summary:** true if any agglomeration occurs across MPI boundaries


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.AgglomerationEdges <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.agglomerationedges"></a>
**Summary:** Edges between agglomerated cells, i.e. pair-wise edges between agglomeration source- and target-cells


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.SourceCells <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.sourcecells"></a>
**Summary:** all cells that are eliminated (aka. 'agglomeration sources', see
[BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.jCellSource](#bosss.foundation.xdg.cellagglomerator.agglomerationpair.jcellsource)) by agglomeration
(does NOT include agglomeration target cells);


### Property: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.TargetCells <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.targetcells"></a>
**Summary:** all cells that are receivers (aka. 'agglomeration targets', see
[BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair.jCellTarget](#bosss.foundation.xdg.cellagglomerator.agglomerationpair.jcelltarget)) by agglomeration
(does NOT include agglomeration source cells);


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.AgglomerationPairs <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.agglomerationpairs"></a>
**Summary:** Cell pairs for agglomeration


### Property: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.AllAffectedCells <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.allaffectedcells"></a>
**Summary:** all cells affected by agglomeration (source and target cells)


### Field: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.SourceCellsEdges <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.sourcecellsedges"></a>
**Summary:** all edges which are connected to at least one cell in
[BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.SourceCells](#bosss.foundation.xdg.cellagglomerator.agglomerationinfo.sourcecells)


## Method: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.GetHashCode <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.gethashcode"></a>
**Returns:**



## Method: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.Equals(BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo) <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.equals(bosss.foundation.xdg.cellagglomerator.agglomerationinfo)"></a>


## Method: BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.ToString <a id="bosss.foundation.xdg.cellagglomerator.agglomerationinfo.tostring"></a>


### Property: BoSSS.Foundation.XDG.CellAgglomerator.GridDat <a id="bosss.foundation.xdg.cellagglomerator.griddat"></a>
**Summary:** Grid data.


### Property: BoSSS.Foundation.XDG.CellAgglomerator.AggInfo <a id="bosss.foundation.xdg.cellagglomerator.agginfo"></a>
**Summary:** Agglomeration info.


### Property: BoSSS.Foundation.XDG.CellAgglomerator.TotalNumberOfAgglomerations <a id="bosss.foundation.xdg.cellagglomerator.totalnumberofagglomerations"></a>
**Summary:** Number of agglomerations on all MPI processors.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.#ctor(BoSSS.Foundation.Grid.Classic.GridData,System.Collections.Generic.IEnumerable{BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair}) <a id="bosss.foundation.xdg.cellagglomerator.#ctor(bosss.foundation.grid.classic.griddata,system.collections.generic.ienumerable{bosss.foundation.xdg.cellagglomerator.agglomerationpair})"></a>
**Summary:** The cell agglomerator v2 (without explicit cycle detection)
**Parameter:** `g` - grid
**Parameter:** `AgglomerationPairs` - Local pairs
[BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair](#bosss.foundation.xdg.cellagglomerator.agglomerationpair))
**Remark:**
The cell agglomerator checks possible problems in the agglomeration pairs coming from [BoSSS.Foundation.XDG.AgglomerationAlgorithm](#bosss.foundation.xdg.agglomerationalgorithm) (Mk3) and then exchange local pairs with targetRanks.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.#ctor(BoSSS.Foundation.Grid.Classic.GridData,System.Collections.Generic.IEnumerable{System.ValueTuple{System.Int32,System.Int32}}) <a id="bosss.foundation.xdg.cellagglomerator.#ctor(bosss.foundation.grid.classic.griddata,system.collections.generic.ienumerable{system.valuetuple{system.int32,system.int32}})"></a>
**Summary:** ctor.
**Parameter:** `g` - 
**Parameter:** `AgglomerationPairs` -
Each tuple represents one agglomeration operation:
- 1st entry: source cell index, i.e. cell which will be removed due to agglomeration; must be in the range of locally updated cells.
- 2nd entry: target cell index, i.e. cell which will be enlarged due to agglomeration
**Remark:**
The cell agglomerator eliminates (resp. tries to eliminate ;) cycles in the agglomeration graph, since 
it cannot be guaranteed that the [BoSSS.Foundation.XDG.AgglomerationAlgorithm](#bosss.foundation.xdg.agglomerationalgorithm) provides cycle-free agglomeration graphs.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.DoAggPairsMPIexchangeForOwners(BoSSS.Foundation.Grid.Classic.GridData,System.Collections.Generic.List{BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair},System.Collections.Generic.List{BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair}@) <a id="bosss.foundation.xdg.cellagglomerator.doaggpairsmpiexchangeforowners(bosss.foundation.grid.classic.griddata,system.collections.generic.list{bosss.foundation.xdg.cellagglomerator.agglomerationpair},system.collections.generic.list{bosss.foundation.xdg.cellagglomerator.agglomerationpair}@)"></a>
**Summary:** Exchange the agglomeration pairs with their owners (for target cells), a restricted variant of [BoSSS.Foundation.XDG.AgglomerationAlgorithm.DoAggPairsMPIexchangeForGhostCells(System.Collections.Generic.List{BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair},System.Collections.Generic.List{BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationPair}@)](#bosss.foundation.xdg.agglomerationalgorithm.doaggpairsmpiexchangeforghostcells(system.collections.generic.list{bosss.foundation.xdg.cellagglomerator.agglomerationpair},system.collections.generic.list{bosss.foundation.xdg.cellagglomerator.agglomerationpair}@))
**Parameter:** `grdDat` - 
**Parameter:** `LocalAggPairs` - 
**Parameter:** `AggPairsDirectedToThisRank` - 
**Returns:**



### Field: BoSSS.Foundation.XDG.CellAgglomerator.CouplingMtx <a id="bosss.foundation.xdg.cellagglomerator.couplingmtx"></a>
**Summary:** coupling matrix.
- 1st index: agglomeration edge index, i.e. index into the items of [BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.AgglomerationEdges](#bosss.foundation.xdg.cellagglomerator.agglomerationinfo.agglomerationedges); 
- 2nd index: row index. 
- 3rd index: column index.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.GetRowManipulationMatrix(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32,System.Int32,System.Func{System.Int32,System.Int32,System.Int64},System.Func{System.Int32,System.Int32,System.Int32},BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.cellagglomerator.getrowmanipulationmatrix(bosss.foundation.unsetteledcoordinatemapping,system.int32,system.int32,system.func{system.int32,system.int32,system.int64},system.func{system.int32,system.int32,system.int32},bosss.foundation.grid.cellmask)"></a>
**Parameter:** `map` - 
**Parameter:** `MaxDegree` - 
**Parameter:** `NoOfVars` - 
**Parameter:** `i0Func` -
Start indices for blocks
- 1st argument: local cell index
- 2nd argument: variable index
- return: global index of first DOF
**Parameter:** `NjFunc` -
Length of blocks
- 1st argument: local cell index
- 2nd argument: variable index
- return: number of DOFs in cell for respective variable
**Parameter:** `cm` - 


## Method: BoSSS.Foundation.XDG.CellAgglomerator.GetRowManipulationMatrix_Internal(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32,System.Int32,System.Func{System.Int32,System.Int32,System.Int64},System.Func{System.Int32,System.Int32,System.Int32},System.Boolean,BoSSS.Foundation.Grid.CellMask[],System.Boolean[]) <a id="bosss.foundation.xdg.cellagglomerator.getrowmanipulationmatrix_internal(bosss.foundation.unsetteledcoordinatemapping,system.int32,system.int32,system.func{system.int32,system.int32,system.int64},system.func{system.int32,system.int32,system.int32},system.boolean,bosss.foundation.grid.cellmask[],system.boolean[])"></a>
**Parameter:** `map` - 
**Parameter:** `MaxDegree` - 
**Parameter:** `NoOfVars` - 
**Parameter:** `i0Func` -
Start indices for blocks
- 1st argument: local cell index
- 2nd argument: variable index
- return: global index of first DOF
**Parameter:** `NjFunc` -
Length of blocks
- 1st argument: local cell index
- 2nd argument: variable index
- return: number of DOFs in cell for respective variable
**Parameter:** `MakeInPlace` -
- `true`: the returned matrix $M$ performs an in-place transformation, i.e., for a vector $v$, the agglomeration is given by $v + M v$.
The in-place version requires less memory, 
since it does not need to store diagonal 1.0 elements in cells not touched by the agglomeration
and also requires less multiplications to execute.
- `false`: the returned matrix $M$ performs the entire agglomeration, i.e., for a vector $v$, the agglomeration is given by $M v$.
**Parameter:** `masksPerVariable` -
for each variable in 'map', a mask which cells should be considered at all, 
i.e., if the mask does not contain a cell, the corresponding row/column in the matrix will be zero.
- index: variable index, correlates with DG basis's in 'map'
**Parameter:** `doVar` - turn agglomeration for each variable on/off


## Method: BoSSS.Foundation.XDG.CellAgglomerator.ClearAgglomerated``1(``0,BoSSS.Foundation.UnsetteledCoordinateMapping,System.Boolean[]) <a id="bosss.foundation.xdg.cellagglomerator.clearagglomerated``1(``0,bosss.foundation.unsetteledcoordinatemapping,system.boolean[])"></a>
**Summary:** In a vector 'V', this clears all entries which correspond to agglomerated cells.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.NormInAgglomerated``1(``0,BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.cellagglomerator.norminagglomerated``1(``0,bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** computes the l2-Norm of the DG coordinates
in the agglomerated cells
**Remark:**
The l2-Norm of the DG coordinates
is NOT equal to the L2-Norm of the DG-field in the XDG-case,
since the basis is no longer orthonormal and therefore Parcival's equation does not hold.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.Extrapolate(BoSSS.Foundation.CoordinateMapping) <a id="bosss.foundation.xdg.cellagglomerator.extrapolate(bosss.foundation.coordinatemapping)"></a>
**Summary:** For a list of DG fields, this method performs a
polynomial extrapolation from agglomeration target cells to agglomeration source cells.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.Extrapolate(BoSSS.Foundation.CoordinateMapping,System.Boolean[]) <a id="bosss.foundation.xdg.cellagglomerator.extrapolate(bosss.foundation.coordinatemapping,system.boolean[])"></a>
**Summary:** For a list of DG fields, this method performs a
polynomial extrapolation from agglomeration target cells to agglomeration source cells.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.PlotAgglomerationPairs(System.IO.StreamWriter,ilPSP.MultidimensionalArray,System.Boolean) <a id="bosss.foundation.xdg.cellagglomerator.plotagglomerationpairs(system.io.streamwriter,ilpsp.multidimensionalarray,system.boolean)"></a>
**Summary:** plots "stays" between agglomerated cells;


## Method: BoSSS.Foundation.XDG.CellAgglomerator.PlotAgglomerationPairs(System.String,ilPSP.MultidimensionalArray,System.Boolean) <a id="bosss.foundation.xdg.cellagglomerator.plotagglomerationpairs(system.string,ilpsp.multidimensionalarray,system.boolean)"></a>
**Summary:** plots "stays" between agglomerated cells;


## Method: BoSSS.Foundation.XDG.CellAgglomerator.ManipulateRHS``1(``0,BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.cellagglomerator.manipulaterhs``1(``0,bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** Apply the basis agglomeration to a right-hand-side vector.


## Method: BoSSS.Foundation.XDG.CellAgglomerator.ManipulateMassMatrixBlocks(ilPSP.MultidimensionalArray,BoSSS.Foundation.Basis,System.Int32[],System.Collections.Generic.Dictionary{System.Int32,System.Int32}) <a id="bosss.foundation.xdg.cellagglomerator.manipulatemassmatrixblocks(ilpsp.multidimensionalarray,bosss.foundation.basis,system.int32[],system.collections.generic.dictionary{system.int32,system.int32})"></a>
**Summary:** designed to work together with [BoSSS.Foundation.XDG.MassMatrixFactory](#bosss.foundation.xdg.massmatrixfactory)


## Method: BoSSS.Foundation.XDG.CellAgglomerator.ManipulateMatrixAndRHS``2(``0,``1,BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.cellagglomerator.manipulatematrixandrhs``2(``0,``1,bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** applies the agglomeration on a general matrix
**Parameter:** `Matrix` - the matrix that should be manipulated.
**Parameter:** `Rhs` - the right-hand-side that should be manipulated
**Parameter:** `ColMap` - 
**Parameter:** `RowMap` - 

## Class: BoSSS.Foundation.XDG.OperatorFactory.DelCoefficientFactory <a id="bosss.foundation.xdg.operatorfactory.delcoefficientfactory"></a>

**Summary:** Factory for the allocation of storage for storing the coefficients for this component

## Class: BoSSS.Foundation.XDG.OperatorFactory.Coefficient <a id="bosss.foundation.xdg.operatorfactory.coefficient"></a>

**Summary:** For now [BoSSS.Foundation.XDG.OperatorFactory.DelCoefficientFactory](#bosss.foundation.xdg.operatorfactory.delcoefficientfactory) is called repeatedly,
maybe this will be changed in the future to align coefficient handling to Parameterhandling

## Class: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory <a id="bosss.foundation.xdg.operatorfactory.operatorfactory"></a>

**Summary:** Factory to create a spatial operator.
Usage:
1. Create System by:
- Adding Equations: [BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.AddEquation(BoSSS.Foundation.XDG.OperatorFactory.BulkEquation)](#bosss.foundation.xdg.operatorfactory.operatorfactory.addequation(bosss.foundation.xdg.operatorfactory.bulkequation)) (and variants)
- Adding Parameters (Parameters are fields, e.g. spatially dependent viscosity): [BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.AddParameter(BoSSS.Foundation.XDG.OperatorFactory.ParameterS)](#bosss.foundation.xdg.operatorfactory.operatorfactory.addparameter(bosss.foundation.xdg.operatorfactory.parameters))
- Adding Coefficients (Coefficients are single numbers, e.g. the Reynolds number): [BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.AddCoefficient(BoSSS.Foundation.XDG.OperatorFactory.Coefficient)](#bosss.foundation.xdg.operatorfactory.operatorfactory.addcoefficient(bosss.foundation.xdg.operatorfactory.coefficient))
2. Create spatial operator by calling GetSpatialOperator


## Method: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.#ctor <a id="bosss.foundation.xdg.operatorfactory.operatorfactory.#ctor"></a>
**Summary:** Default constructor


## Method: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.AddEquation(BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation) <a id="bosss.foundation.xdg.operatorfactory.operatorfactory.addequation(bosss.foundation.xdg.operatorfactory.spatialequation)"></a>
**Summary:** Add an spatial equation to this factory.
**Parameter:** `equation` - 


## Method: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.AddEquation(BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation) <a id="bosss.foundation.xdg.operatorfactory.operatorfactory.addequation(bosss.foundation.xdg.operatorfactory.surfaceequation)"></a>
**Summary:** Adds a surface equation to the factory.
**Parameter:** `equation` - 


## Method: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.AddEquation(BoSSS.Foundation.XDG.OperatorFactory.BulkEquation) <a id="bosss.foundation.xdg.operatorfactory.operatorfactory.addequation(bosss.foundation.xdg.operatorfactory.bulkequation)"></a>
**Summary:** Adds a bulk equation to the factory.
**Parameter:** `equation` - 


## Method: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.AddParameter(BoSSS.Foundation.XDG.OperatorFactory.ParameterS) <a id="bosss.foundation.xdg.operatorfactory.operatorfactory.addparameter(bosss.foundation.xdg.operatorfactory.parameters)"></a>
**Summary:** Add parameter to factory. Only parameters, that are present in at least one equation will be used.
**Parameter:** `parameter` - 


## Method: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.AddCoefficient(BoSSS.Foundation.XDG.OperatorFactory.Coefficient) <a id="bosss.foundation.xdg.operatorfactory.operatorfactory.addcoefficient(bosss.foundation.xdg.operatorfactory.coefficient)"></a>
**Summary:** Add coefficient to factory. Only coefficients, that are present in at least one equation will be used.
**Parameter:** `coefficient` - 


## Method: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.GetSpatialOperator(System.Int32) <a id="bosss.foundation.xdg.operatorfactory.operatorfactory.getspatialoperator(system.int32)"></a>
**Summary:** Creates Spatial operator
**Parameter:** `quadOrder` - Quadrature Order of regular cells
**Returns:**
Configured spatial operator. Not committed.


## Method: BoSSS.Foundation.XDG.OperatorFactory.OperatorFactory.GetSpatialOperator(System.Func{System.Int32[],System.Int32[],System.Int32[],System.Int32}) <a id="bosss.foundation.xdg.operatorfactory.operatorfactory.getspatialoperator(system.func{system.int32[],system.int32[],system.int32[],system.int32})"></a>
**Summary:** Creates Spatial operator
**Parameter:** `QuadOrderFunc` - Function Mapping from Domain Variable Degrees, 
Parameter Degrees and CoDomain Variable Degrees to the Quadrature Order
**Returns:**
Configured spatial operator. Not committed.

## Class: BoSSS.Foundation.XDG.OperatorFactory.ParameterS <a id="bosss.foundation.xdg.operatorfactory.parameters"></a>

**Summary:** A parameter (for a spatial operator) is some field data ([BoSSS.Foundation.IDifferentialOperator.ParameterVar](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.parametervar)),
upon which the PDE depends on; It is neither a residual nor some field to solve for.
A typical example would be a non-constant diffusion coefficient.

This class (or factory) provides means for updating and generating parameter fields

**Remark:**
This class is a member of the operator factory framework, 
which provides a driver framework (to specify entire equations at once)
upon the fine-grained specification for the spatial operator (where equations are build up from individual components).


### Property: BoSSS.Foundation.XDG.OperatorFactory.ParameterS.ParameterNames <a id="bosss.foundation.xdg.operatorfactory.parameters.parameternames"></a>
**Summary:** To correlate the parameters handled by this class
with the entire parameter list of the spatial operator ([BoSSS.Foundation.IDifferentialOperator.ParameterVar](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.parametervar))


### Property: BoSSS.Foundation.XDG.OperatorFactory.ParameterS.Factory <a id="bosss.foundation.xdg.operatorfactory.parameters.factory"></a>
**Summary:** Allocation of DG fields;


### Property: BoSSS.Foundation.XDG.OperatorFactory.ParameterS.Update <a id="bosss.foundation.xdg.operatorfactory.parameters.update"></a>
**Summary:** Update of DG fields;

## Class: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation <a id="bosss.foundation.xdg.operatorfactory.spatialequation"></a>

**Summary:** Base class for all equations of the operator factory.
A spatial equation is an equation for one codomain. 
Implement this class, if you have a single phase equation.


## Method: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.#ctor <a id="bosss.foundation.xdg.operatorfactory.spatialequation.#ctor"></a>
**Summary:** Empty spatial equation.


### Property: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.Components <a id="bosss.foundation.xdg.operatorfactory.spatialequation.components"></a>
**Summary:** Equation components of this equation. All components belong to a single codomain.


### Property: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.CodomainName <a id="bosss.foundation.xdg.operatorfactory.spatialequation.codomainname"></a>
**Summary:** Single codomain name of this equation. A codomain a name for the row in a system of equations.


### Property: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.VariableNames <a id="bosss.foundation.xdg.operatorfactory.spatialequation.variablenames"></a>
**Summary:** All names of variables in equation. Must match variables of components.


### Property: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.Parameters <a id="bosss.foundation.xdg.operatorfactory.spatialequation.parameters"></a>
**Summary:** All names of parameters in equation. Must match parameters of components.


### Property: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.Coefficients <a id="bosss.foundation.xdg.operatorfactory.spatialequation.coefficients"></a>
**Summary:** All names of coefficients. Must match coefficients of components.


## Method: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.AddVariableNames(System.String[]) <a id="bosss.foundation.xdg.operatorfactory.spatialequation.addvariablenames(system.string[])"></a>
**Summary:** Add name of variable. Will only add, if name was not already added.
**Parameter:** `names` - 


## Method: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.AddParameter(System.String[]) <a id="bosss.foundation.xdg.operatorfactory.spatialequation.addparameter(system.string[])"></a>
**Summary:** Add name of parameter. Will only add, if name was not already added.
**Parameter:** `names` - 


## Method: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.AddCoefficient(System.String[]) <a id="bosss.foundation.xdg.operatorfactory.spatialequation.addcoefficient(system.string[])"></a>
**Summary:** Add name of coefficient. Will only add, if name was not already added.
**Parameter:** `names` - 


## Method: BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.AddComponent(BoSSS.Foundation.IEquationComponent) <a id="bosss.foundation.xdg.operatorfactory.spatialequation.addcomponent(bosss.foundation.iequationcomponent)"></a>
**Summary:** Add component to this equation. The variable/parameter/coefficient names must be added separately.
**Parameter:** `component` - Equation component for this equation's codomain

## Class: BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation <a id="bosss.foundation.xdg.operatorfactory.surfaceequation"></a>

**Summary:** XDG Equations on a surface. 
Surface is between to species.


## Method: BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation.#ctor <a id="bosss.foundation.xdg.operatorfactory.surfaceequation.#ctor"></a>
**Summary:** Empty surface equation.


### Property: BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation.FirstSpeciesName <a id="bosss.foundation.xdg.operatorfactory.surfaceequation.firstspeciesname"></a>
**Summary:** First/Negative species (with respect to level-set)
Order not important.


### Property: BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation.SecondSpeciesName <a id="bosss.foundation.xdg.operatorfactory.surfaceequation.secondspeciesname"></a>
**Summary:** Second/Positive species (with respect to level-set)
Order not important.


### Property: BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation.SurfaceComponents <a id="bosss.foundation.xdg.operatorfactory.surfaceequation.surfacecomponents"></a>
**Summary:** Specialized surface components that are part of a special spatial operator in the general spatial operator.
Generally, surface equations are also collected in [BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.Components](#bosss.foundation.xdg.operatorfactory.spatialequation.components).


### Property: BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation.ContactLineComponents <a id="bosss.foundation.xdg.operatorfactory.surfaceequation.contactlinecomponents"></a>
**Summary:** Specialized contact line components that are part of a special spatial operator in the general spatial operator.


## Method: BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation.AddSurfaceComponent(BoSSS.Foundation.IEquationComponent) <a id="bosss.foundation.xdg.operatorfactory.surfaceequation.addsurfacecomponent(bosss.foundation.iequationcomponent)"></a>
**Summary:** Add Specialized surface components that will be part of a special spatial operator.
Generally, surface equations are also added via [BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.AddComponent(BoSSS.Foundation.IEquationComponent)](#bosss.foundation.xdg.operatorfactory.spatialequation.addcomponent(bosss.foundation.iequationcomponent)).
**Parameter:** `surfaceComponent` - Specialized surface component


## Method: BoSSS.Foundation.XDG.OperatorFactory.SurfaceEquation.AddContactLineComponent(BoSSS.Foundation.IEquationComponent) <a id="bosss.foundation.xdg.operatorfactory.surfaceequation.addcontactlinecomponent(bosss.foundation.iequationcomponent)"></a>
**Summary:** Add Specialized surface components that will be part of a special spatial operator.
Generally, surface equations are also added via [BoSSS.Foundation.XDG.OperatorFactory.SpatialEquation.AddComponent(BoSSS.Foundation.IEquationComponent)](#bosss.foundation.xdg.operatorfactory.spatialequation.addcomponent(bosss.foundation.iequationcomponent)).
**Parameter:** `surfaceComponent` - Specialized surface component

## Class: BoSSS.Foundation.XDG.OperatorFactory.BulkEquation <a id="bosss.foundation.xdg.operatorfactory.bulkequation"></a>

**Summary:** XDG Equations for bulk phase.


### Property: BoSSS.Foundation.XDG.OperatorFactory.BulkEquation.SpeciesName <a id="bosss.foundation.xdg.operatorfactory.bulkequation.speciesname"></a>
**Summary:** Name of species for which equation is valid.


### Property: BoSSS.Foundation.XDG.OperatorFactory.BulkEquation.MassScale <a id="bosss.foundation.xdg.operatorfactory.bulkequation.massscale"></a>
**Summary:** This is required, when the whole equation is scaled, e.g. by density. 
In time stepping, the respective entries of the mass matrix will be scaled by this factor.


### Property: BoSSS.Foundation.XDG.OperatorFactory.BulkEquation.GhostComponents <a id="bosss.foundation.xdg.operatorfactory.bulkequation.ghostcomponents"></a>
**Summary:** Special component of an extra ghost spatial operator.


## Method: BoSSS.Foundation.XDG.OperatorFactory.BulkEquation.#ctor <a id="bosss.foundation.xdg.operatorfactory.bulkequation.#ctor"></a>
**Summary:** Empty bulk equation.


## Method: BoSSS.Foundation.XDG.OperatorFactory.BulkEquation.AddGhostComponent(BoSSS.Foundation.IEquationComponent) <a id="bosss.foundation.xdg.operatorfactory.bulkequation.addghostcomponent(bosss.foundation.iequationcomponent)"></a>
**Summary:** Add a specialized ghost component.
**Parameter:** `ghostComponent` - 

## Class: BoSSS.Foundation.XDG.OperatorFactory.EquationList`1 <a id="bosss.foundation.xdg.operatorfactory.equationlist`1"></a>

**Summary:** List of Equations. There is only one equation for each codomain species pair.


## Method: BoSSS.Foundation.XDG.OperatorFactory.EquationList`1.Add(`0) <a id="bosss.foundation.xdg.operatorfactory.equationlist`1.add(`0)"></a>
**Parameter:** `equation` - If the codomain of equation is already present, equation will be combined with the present entry.

## Class: BoSSS.Foundation.XDG.OperatorFactory.SystemOfEquations <a id="bosss.foundation.xdg.operatorfactory.systemofequations"></a>

**Summary:** Accumulation of equations
Finds the names of all required parameters and coefficients


## Method: BoSSS.Foundation.XDG.OperatorFactory.SystemOfEquations.#ctor <a id="bosss.foundation.xdg.operatorfactory.systemofequations.#ctor"></a>
**Summary:** Create empty System

## Class: BoSSS.Foundation.XDG.ICutCellMetrics <a id="bosss.foundation.xdg.icutcellmetrics"></a>


### Property: BoSSS.Foundation.XDG.ICutCellMetrics.CutCellQuadratureOrder <a id="bosss.foundation.xdg.icutcellmetrics.cutcellquadratureorder"></a>
**Summary:** Quadrature order used to obtain the metrics


### Property: BoSSS.Foundation.XDG.ICutCellMetrics.SpeciesList <a id="bosss.foundation.xdg.icutcellmetrics.specieslist"></a>
**Summary:** available species


### Property: BoSSS.Foundation.XDG.ICutCellMetrics.CutCellVolumes <a id="bosss.foundation.xdg.icutcellmetrics.cutcellvolumes"></a>
**Summary:** Volume of non-agglomerated cut cells.
- key: species
- index: cell index


### Property: BoSSS.Foundation.XDG.ICutCellMetrics.CellSurface <a id="bosss.foundation.xdg.icutcellmetrics.cellsurface"></a>
**Summary:** Surface (Level-Set plus cut edges) of non-agglomerated cut cells.
- key: species
- index: cell index

## Class: BoSSS.Foundation.XDG.CutCellMetrics <a id="bosss.foundation.xdg.cutcellmetrics"></a>

**Summary:** HMF-based computation of cut-cell volumes and cut-edge areas.


### Property: BoSSS.Foundation.XDG.CutCellMetrics.XDGSpaceMetrics <a id="bosss.foundation.xdg.cutcellmetrics.xdgspacemetrics"></a>
**Summary:** owner object.


## Method: BoSSS.Foundation.XDG.CutCellMetrics.#ctor(BoSSS.Foundation.XDG.XDGSpaceMetrics) <a id="bosss.foundation.xdg.cutcellmetrics.#ctor(bosss.foundation.xdg.xdgspacemetrics)"></a>
**Summary:** ctor.


### Property: BoSSS.Foundation.XDG.CutCellMetrics.CutCellQuadratureOrder <a id="bosss.foundation.xdg.cutcellmetrics.cutcellquadratureorder"></a>
**Summary:** The quadrature order used for computing cell volumes and edge areas.


### Property: BoSSS.Foundation.XDG.CutCellMetrics.HMFvariant <a id="bosss.foundation.xdg.cutcellmetrics.hmfvariant"></a>
**Summary:** The kind of HMF which is be used for computing cell volumes.


### Property: BoSSS.Foundation.XDG.CutCellMetrics.SpeciesList <a id="bosss.foundation.xdg.cutcellmetrics.specieslist"></a>
**Summary:** All species for which agglomeration is available.


### Property: BoSSS.Foundation.XDG.CutCellMetrics.CutCellVolumes <a id="bosss.foundation.xdg.cutcellmetrics.cutcellvolumes"></a>
**Summary:** Volume of non-agglomerated cut cells.
- key: species
- index: cell index


### Property: BoSSS.Foundation.XDG.CutCellMetrics.InterfaceArea <a id="bosss.foundation.xdg.cutcellmetrics.interfacearea"></a>
**Summary:** Area of the interface, resp. level-set-surface of non-agglomerated cut cells.
- key: species
- index: cell index


### Property: BoSSS.Foundation.XDG.CutCellMetrics.CutEdgeAreas <a id="bosss.foundation.xdg.cutcellmetrics.cutedgeareas"></a>
**Summary:** Area of non-agglomerated cut edges.
- key: species
- index: edge index


### Property: BoSSS.Foundation.XDG.CutCellMetrics.CellSurface <a id="bosss.foundation.xdg.cutcellmetrics.cellsurface"></a>
**Summary:** Surface (Level-Set plus cut edges) of non-agglomerated cut cells.
- key: species
- index: cell index


## Method: BoSSS.Foundation.XDG.CutCellMetrics.WriteEdgeRulesToVtp <a id="bosss.foundation.xdg.cutcellmetrics.writeedgerulestovtp"></a>
**Summary:** Writes all the edge rules as vtp files


## Method: BoSSS.Foundation.XDG.CutCellMetrics.WriteVolumeRulesToVtp <a id="bosss.foundation.xdg.cutcellmetrics.writevolumerulestovtp"></a>
**Summary:** Writes all the volume rules as vtp files


## Method: BoSSS.Foundation.XDG.CutCellMetrics.WriteSurfaceRulesToVtp <a id="bosss.foundation.xdg.cutcellmetrics.writesurfacerulestovtp"></a>
**Summary:** Writes all the surface rules (level set=0) as vtp files


## Method: BoSSS.Foundation.XDG.CutCellMetrics.ComputeNonAgglomeratedMetrics <a id="bosss.foundation.xdg.cutcellmetrics.computenonagglomeratedmetrics"></a>
**Summary:** Computes Cell-volumes and edge areas before agglomeration.


### Property: BoSSS.Foundation.XDG.CutCellMetrics.CutLineLength <a id="bosss.foundation.xdg.cutcellmetrics.cutlinelength"></a>
**Summary:** Total length (i.e., D-2 dimensional measure) of cut line (i.e., intersection of D-1 dimensional level-set surface with D-1 dimensional cell boundary) for each non-agglomerated cut cell.
- key: species
- index: cell index


### Property: BoSSS.Foundation.XDG.CutCellMetrics.IntersectionLength <a id="bosss.foundation.xdg.cutcellmetrics.intersectionlength"></a>
**Summary:** Total length (i.e., D-2 dimensional measure) of 
level-set intersection (i.e., intersection of the D-1 dimensional level-set 0 with the d-1 dimensional level-set 1) 
for each non-agglomerated cut cell.
- key: species
- index: cell index
See also: [BoSSS.Foundation.XDG.XQuadSchemeHelper.GetContactLineQuadScheme(BoSSS.Foundation.XDG.SpeciesId,System.Int32,System.Int32)](#bosss.foundation.xdg.xquadschemehelper.getcontactlinequadscheme(bosss.foundation.xdg.speciesid,system.int32,system.int32))


### Property: BoSSS.Foundation.XDG.CutCellMetrics.CutLineLengthEdge <a id="bosss.foundation.xdg.cutcellmetrics.cutlinelengthedge"></a>
**Summary:** Total length (i.e., D-2 dimensional measure) of cut line (i.e., intersection of D-1 dimensional level-set surface with D-1 dimensional cell boundary) for each edge.
for each edge.
- key: species
- index: edge index

## Class: BoSSS.Foundation.XDG.FieldExtensions <a id="bosss.foundation.xdg.fieldextensions"></a>

**Summary:** Extension methods for [BoSSS.Foundation.DGField](BoSSS.Foundation.md#bosss.foundation.dgfield)


## Method: BoSSS.Foundation.XDG.FieldExtensions.AccLevelSetDist(BoSSS.Foundation.DGField,System.Double,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32) <a id="bosss.foundation.xdg.fieldextensions.acclevelsetdist(bosss.foundation.dgfield,system.double,bosss.foundation.xdg.levelsettracker,system.int32)"></a>
**Summary:** accumulates (to field 'f'), in every cell the
distance form the cut cells times 'alpha';
Note: this is NOT the geometric distance, but the distance index
that identifies the 'Near+1' , 'Near-1', 'Near+2',  ..., - layers.


## Method: BoSSS.Foundation.XDG.FieldExtensions.AccNoOfSpecies(BoSSS.Foundation.DGField,System.Double,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32) <a id="bosss.foundation.xdg.fieldextensions.accnoofspecies(bosss.foundation.dgfield,system.double,bosss.foundation.xdg.levelsettracker,system.int32)"></a>
**Summary:** accumulates (to field 'f'), in every cell the
number of species times 'alpha'

## Class: BoSSS.Foundation.XDG.FieldStorage <a id="bosss.foundation.xdg.fieldstorage"></a>

**Summary:** a sparse data structure, used by e.g. [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)


## Method: BoSSS.Foundation.XDG.FieldStorage.#ctor(System.Int32,System.Int32,System.Int32) <a id="bosss.foundation.xdg.fieldstorage.#ctor(system.int32,system.int32,system.int32)"></a>
**Parameter:** `_NoOfCells` - 
**Parameter:** `_Nmin` - 
**Parameter:** `_Nmax` - 


### Property: BoSSS.Foundation.XDG.FieldStorage.NMin <a id="bosss.foundation.xdg.fieldstorage.nmin"></a>


### Property: BoSSS.Foundation.XDG.FieldStorage.NMax <a id="bosss.foundation.xdg.fieldstorage.nmax"></a>
**Summary:** maximum number of supported DG coordinates


## Method: BoSSS.Foundation.XDG.FieldStorage.BeginResize(System.Int32) <a id="bosss.foundation.xdg.fieldstorage.beginresize(system.int32)"></a>
**Summary:** initiation of resize operation ([BoSSS.Foundation.XDG.FieldStorage.Resize(System.Int32,System.Int32)](#bosss.foundation.xdg.fieldstorage.resize(system.int32,system.int32)) and [BoSSS.Foundation.XDG.FieldStorage.FinishResize](#bosss.foundation.xdg.fieldstorage.finishresize));
**Parameter:** `NMax_New` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.FieldStorage.Resize(System.Int32,System.Int32) <a id="bosss.foundation.xdg.fieldstorage.resize(system.int32,system.int32)"></a>
**Summary:** resizes the total number of XDG coordinates for cell 'j';
Must be called in between of [BoSSS.Foundation.XDG.FieldStorage.BeginResize(System.Int32)](#bosss.foundation.xdg.fieldstorage.beginresize(system.int32)) and [BoSSS.Foundation.XDG.FieldStorage.FinishResize](#bosss.foundation.xdg.fieldstorage.finishresize);
**Parameter:** `j` - 
**Parameter:** `NewN` - 


## Method: BoSSS.Foundation.XDG.FieldStorage.FinishResize <a id="bosss.foundation.xdg.fieldstorage.finishresize"></a>
**Summary:** finalization of resize operation ([BoSSS.Foundation.XDG.FieldStorage.Resize(System.Int32,System.Int32)](#bosss.foundation.xdg.fieldstorage.resize(system.int32,system.int32)) and [BoSSS.Foundation.XDG.FieldStorage.BeginResize(System.Int32)](#bosss.foundation.xdg.fieldstorage.beginresize(system.int32)));


## Method: BoSSS.Foundation.XDG.FieldStorage.CopyFrom(BoSSS.Foundation.XDG.FieldStorage) <a id="bosss.foundation.xdg.fieldstorage.copyfrom(bosss.foundation.xdg.fieldstorage)"></a>
**Summary:** initializes this to be a non-shallow copy of 'other';


### Property: BoSSS.Foundation.XDG.FieldStorage.NoOfCells <a id="bosss.foundation.xdg.fieldstorage.noofcells"></a>


### Property: BoSSS.Foundation.XDG.FieldStorage.BaseStorageMda <a id="bosss.foundation.xdg.fieldstorage.basestoragemda"></a>
**Summary:** shallow copy of **BoSSS.Foundation.XDG.FieldStorage.m_BaseStorage**.


## Method: BoSSS.Foundation.XDG.FieldStorage.GetNoOfCoordinates(System.Int32) <a id="bosss.foundation.xdg.fieldstorage.getnoofcoordinates(system.int32)"></a>
**Summary:** returns the number of DG coordinates in cell 'j'
**Parameter:** `j` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.FieldStorage.Clear <a id="bosss.foundation.xdg.fieldstorage.clear"></a>
**Summary:** sets all entries to 0.0;


### Property: BoSSS.Foundation.XDG.FieldStorage.NoOfCols <a id="bosss.foundation.xdg.fieldstorage.noofcols"></a>
**Summary:** equal to [BoSSS.Foundation.XDG.FieldStorage.NMax](#bosss.foundation.xdg.fieldstorage.nmax)


### Property: BoSSS.Foundation.XDG.FieldStorage.NoOfRows <a id="bosss.foundation.xdg.fieldstorage.noofrows"></a>
**Summary:** equal to [BoSSS.Foundation.XDG.FieldStorage.NoOfCells](#bosss.foundation.xdg.fieldstorage.noofcells)


## Method: BoSSS.Foundation.XDG.FieldStorage.IndBase(System.Int32,System.Int32) <a id="bosss.foundation.xdg.fieldstorage.indbase(system.int32,system.int32)"></a>
**Summary:** computes the index into the **BoSSS.Foundation.XDG.FieldStorage.m_BaseStorage**-array,
for some ('j','n')-pair;
**Parameter:** `j` - 
**Parameter:** `n` - 
**Returns:**



### Property: BoSSS.Foundation.XDG.FieldStorage.Item(System.Int32,System.Int32) <a id="bosss.foundation.xdg.fieldstorage.item(system.int32,system.int32)"></a>
**Summary:** sets/get an entry;
"Getting" is supported for all entries (in the matrix) (non-allocated entries are returned as 0.0),
"Setting" is only supported for allocated entries;
**Remark:**
setting an entry for which no memory is allocated
will throw an exception;


## Method: BoSSS.Foundation.XDG.FieldStorage.Acc(System.Double,ilPSP.Utils.IMatrix) <a id="bosss.foundation.xdg.fieldstorage.acc(system.double,ilpsp.utils.imatrix)"></a>
**Summary:** accumulates 'a'*'M' to this matrix


## Method: BoSSS.Foundation.XDG.FieldStorage.Scale(System.Double) <a id="bosss.foundation.xdg.fieldstorage.scale(system.double)"></a>
**Summary:** multiplies all entries by number 'a'
**Parameter:** `a` - 


## Method: BoSSS.Foundation.XDG.FieldStorage.Clone <a id="bosss.foundation.xdg.fieldstorage.clone"></a>
**Summary:** creates a non-shallow copy of this object;
**Returns:**



## Method: BoSSS.Foundation.XDG.FieldStorage.CopyTo(System.Double[0:,0:],System.Int32,System.Int32) <a id="bosss.foundation.xdg.fieldstorage.copyto(system.double[0:,0:],system.int32,system.int32)"></a>
**Summary:** Copies values from this array into a 2-dimensional .NET-array;
**Parameter:** `dest` - target for the copy operation;
the [0,0]-entry of this matrix will end up in the ['i0','i1']-entry
of 'dest';
**Parameter:** `i0` - offset into this array, 1st index;
**Parameter:** `i1` - offset into this array, 2nd index;


## Method: BoSSS.Foundation.XDG.FieldStorage.CopyTo``1(``0,System.Boolean,System.Int32) <a id="bosss.foundation.xdg.fieldstorage.copyto``1(``0,system.boolean,system.int32)"></a>
**Summary:** Copies to a one-dimensional array/list
**Parameter:** `array` - 
**Parameter:** `RowWise` - if true, elements are taken row-by-row (column index rotating fastest) and copied to 'array';
if false, elements are taken column-by-column;
**Parameter:** `arrayoffset` - 

## Class: BoSSS.Foundation.XDG.FormDifferentiatorCommon <a id="bosss.foundation.xdg.formdifferentiatorcommon"></a>

**Summary:** Base-Functionality for utilities for computation of Spatial Operator Jacobians, ([BoSSS.Foundation.DifferentialOperator.GetJacobiOperator(System.Int32)](BoSSS.Foundation.md#bosss.foundation.differentialoperator.getjacobioperator(system.int32)),
i.e. approximate differentiation of equation components.


## Method: BoSSS.Foundation.XDG.FormDifferentiatorCommon.#ctor(BoSSS.Foundation.IEquationComponent,BoSSS.Foundation.TermActivationFlags,System.Int32) <a id="bosss.foundation.xdg.formdifferentiatorcommon.#ctor(bosss.foundation.iequationcomponent,bosss.foundation.termactivationflags,system.int32)"></a>
**Summary:** %


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.Terms <a id="bosss.foundation.xdg.formdifferentiatorcommon.terms"></a>
**Summary:** required terms for the linearization


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.m_SpatialDimension <a id="bosss.foundation.xdg.formdifferentiatorcommon.m_spatialdimension"></a>


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.ParamUreq <a id="bosss.foundation.xdg.formdifferentiatorcommon.paramureq"></a>
**Summary:** Differentiation w.r.t. Trial Variable required.


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.ParamGradUreq <a id="bosss.foundation.xdg.formdifferentiatorcommon.paramgradureq"></a>
**Summary:** Differentiation w.r.t. Trial Variable Gradient required.


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.OffsetUparams <a id="bosss.foundation.xdg.formdifferentiatorcommon.offsetuparams"></a>
**Summary:** Offset into parameters to access Trial variable (called 'U') value at linearization point


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.OffsetGradUparams <a id="bosss.foundation.xdg.formdifferentiatorcommon.offsetgraduparams"></a>
**Summary:** Offset into parameters to access Trial variable gradient (called 'U') value at linearization point


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.OffsetOrgParams <a id="bosss.foundation.xdg.formdifferentiatorcommon.offsetorgparams"></a>
**Summary:** Offset into parameters to access parameters of original form


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.NoOfOrgParams <a id="bosss.foundation.xdg.formdifferentiatorcommon.nooforgparams"></a>
**Summary:** number of parameters in original component


### Field: BoSSS.Foundation.XDG.FormDifferentiatorCommon.m_eps <a id="bosss.foundation.xdg.formdifferentiatorcommon.m_eps"></a>
**Summary:** Relative finite difference length


### Property: BoSSS.Foundation.XDG.FormDifferentiatorCommon.ArgumentOrdering <a id="bosss.foundation.xdg.formdifferentiatorcommon.argumentordering"></a>
**Summary:** %


### Property: BoSSS.Foundation.XDG.FormDifferentiatorCommon.ParameterOrdering <a id="bosss.foundation.xdg.formdifferentiatorcommon.parameterordering"></a>
**Summary:** %


### Property: BoSSS.Foundation.XDG.FormDifferentiatorCommon.IgnoreVectorizedImplementation <a id="bosss.foundation.xdg.formdifferentiatorcommon.ignorevectorizedimplementation"></a>
**Summary:** %


## Method: BoSSS.Foundation.XDG.FormDifferentiatorCommon.GetOrgParams(System.Double[],System.Double[]@) <a id="bosss.foundation.xdg.formdifferentiatorcommon.getorgparams(system.double[],system.double[]@)"></a>
**Summary:** Extract parameters for original form.


## Method: BoSSS.Foundation.XDG.FormDifferentiatorCommon.GetTmpTrialVals(System.Double[],System.Double[]@,System.Double[0:,0:]@) <a id="bosss.foundation.xdg.formdifferentiatorcommon.gettmptrialvals(system.double[],system.double[]@,system.double[0:,0:]@)"></a>


## Method: BoSSS.Foundation.XDG.FormDifferentiatorCommon.CoefficientUpdate(BoSSS.Foundation.CoefficientSet,System.Int32[],System.Int32) <a id="bosss.foundation.xdg.formdifferentiatorcommon.coefficientupdate(bosss.foundation.coefficientset,system.int32[],system.int32)"></a>
**Summary:** passes the coefficients to original form


## Method: BoSSS.Foundation.XDG.FormDifferentiatorCommon.MyParameterUpdate(BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.formdifferentiatorcommon.myparameterupdate(bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** redirects to parameter update of original form; Jacobi parameter are updated in [BoSSS.Foundation.JacobianParamUpdate](BoSSS.Foundation.md#bosss.foundation.jacobianparamupdate)


## Method: BoSSS.Foundation.XDG.FormDifferentiatorCommon.MyParameterAlloc(BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.formdifferentiatorcommon.myparameteralloc(bosss.foundation.dgfield[])"></a>
**Summary:** redirects to parameter update of original form; Jacobi parameter are updated in [BoSSS.Foundation.JacobianParamUpdate](BoSSS.Foundation.md#bosss.foundation.jacobianparamupdate)


## Method: BoSSS.Foundation.XDG.FormDifferentiatorCommon.SetParameter(System.String) <a id="bosss.foundation.xdg.formdifferentiatorcommon.setparameter(system.string)"></a>
**Summary:** [BoSSS.Foundation.XDG.IEquationComponentSpeciesNotification.SetParameter(System.String)](#bosss.foundation.xdg.iequationcomponentspeciesnotification.setparameter(system.string))


### Property: BoSSS.Foundation.XDG.FormDifferentiatorCommon.ValidSpecies <a id="bosss.foundation.xdg.formdifferentiatorcommon.validspecies"></a>
**Summary:** [BoSSS.Foundation.XDG.ISpeciesFilter.ValidSpecies](#bosss.foundation.xdg.ispeciesfilter.validspecies)

## Class: BoSSS.Foundation.XDG.VolumeFormDifferentiator <a id="bosss.foundation.xdg.volumeformdifferentiator"></a>

**Summary:** Differentiation of a volume form, used to obtain a Jacobian of an operator, see [BoSSS.Foundation.DifferentialOperator.GetJacobiOperator(System.Int32)](BoSSS.Foundation.md#bosss.foundation.differentialoperator.getjacobioperator(system.int32)).


## Method: BoSSS.Foundation.XDG.VolumeFormDifferentiator.#ctor(BoSSS.Foundation.IVolumeForm,System.Int32) <a id="bosss.foundation.xdg.volumeformdifferentiator.#ctor(bosss.foundation.ivolumeform,system.int32)"></a>
**Summary:** %


### Property: BoSSS.Foundation.XDG.VolumeFormDifferentiator.VolTerms <a id="bosss.foundation.xdg.volumeformdifferentiator.volterms"></a>
**Summary:** %


## Method: BoSSS.Foundation.XDG.VolumeFormDifferentiator.VolumeForm(BoSSS.Foundation.CommonParamsVol@,System.Double[],System.Double[0:,0:],System.Double,System.Double[]) <a id="bosss.foundation.xdg.volumeformdifferentiator.volumeform(bosss.foundation.commonparamsvol@,system.double[],system.double[0:,0:],system.double,system.double[])"></a>
**Summary:** %

## Class: BoSSS.Foundation.XDG.EdgeFormDifferentiator <a id="bosss.foundation.xdg.edgeformdifferentiator"></a>

**Summary:** Differentiation of a edge form, used e.g.to obtain a Jacobian of an operator, see [BoSSS.Foundation.DifferentialOperator.GetJacobiOperator(System.Int32)](BoSSS.Foundation.md#bosss.foundation.differentialoperator.getjacobioperator(system.int32)).


## Method: BoSSS.Foundation.XDG.EdgeFormDifferentiator.#ctor(BoSSS.Foundation.IEdgeForm,System.Int32) <a id="bosss.foundation.xdg.edgeformdifferentiator.#ctor(bosss.foundation.iedgeform,system.int32)"></a>
**Summary:** ctor


### Property: BoSSS.Foundation.XDG.EdgeFormDifferentiator.InnerEdgeTerms <a id="bosss.foundation.xdg.edgeformdifferentiator.inneredgeterms"></a>
**Summary:** %


### Property: BoSSS.Foundation.XDG.EdgeFormDifferentiator.BoundaryEdgeTerms <a id="bosss.foundation.xdg.edgeformdifferentiator.boundaryedgeterms"></a>
**Summary:** %

## Class: BoSSS.Foundation.XDG.LevelSetFormDifferentiator <a id="bosss.foundation.xdg.levelsetformdifferentiator"></a>

**Summary:** Differentiation of an edge form, used e.g.to obtain a Jacobian of an operator, see [BoSSS.Foundation.DifferentialOperator.GetJacobiOperator(System.Int32)](BoSSS.Foundation.md#bosss.foundation.differentialoperator.getjacobioperator(system.int32)).
In principal the same as [BoSSS.Foundation.XDG.EdgeFormDifferentiator](#bosss.foundation.xdg.edgeformdifferentiator), but using [BoSSS.Foundation.XDG.ILevelSetForm](#bosss.foundation.xdg.ilevelsetform)


## Method: BoSSS.Foundation.XDG.LevelSetFormDifferentiator.#ctor(BoSSS.Foundation.XDG.ILevelSetForm,System.Int32) <a id="bosss.foundation.xdg.levelsetformdifferentiator.#ctor(bosss.foundation.xdg.ilevelsetform,system.int32)"></a>
**Summary:** ctor


### Property: BoSSS.Foundation.XDG.LevelSetFormDifferentiator.LevelSetTerms <a id="bosss.foundation.xdg.levelsetformdifferentiator.levelsetterms"></a>
**Summary:** %


### Property: BoSSS.Foundation.XDG.LevelSetFormDifferentiator.LevelSetIndex <a id="bosss.foundation.xdg.levelsetformdifferentiator.levelsetindex"></a>
**Summary:** %


### Property: BoSSS.Foundation.XDG.LevelSetFormDifferentiator.PositiveSpecies <a id="bosss.foundation.xdg.levelsetformdifferentiator.positivespecies"></a>
**Summary:** %


### Property: BoSSS.Foundation.XDG.LevelSetFormDifferentiator.NegativeSpecies <a id="bosss.foundation.xdg.levelsetformdifferentiator.negativespecies"></a>
**Summary:** %


## Method: BoSSS.Foundation.XDG.LevelSetFormDifferentiator.CoefficientUpdate(BoSSS.Foundation.CoefficientSet,BoSSS.Foundation.CoefficientSet,System.Int32[],System.Int32) <a id="bosss.foundation.xdg.levelsetformdifferentiator.coefficientupdate(bosss.foundation.coefficientset,bosss.foundation.coefficientset,system.int32[],system.int32)"></a>
**Summary:** passes the coefficients to original form

## Class: BoSSS.Foundation.XDG.IEquationComponentSpeciesNotification <a id="bosss.foundation.xdg.iequationcomponentspeciesnotification"></a>

**Summary:** this interface should be implemented by bulk equation components which require to switch coefficients based on species.


## Method: BoSSS.Foundation.XDG.IEquationComponentSpeciesNotification.SetParameter(System.String) <a id="bosss.foundation.xdg.iequationcomponentspeciesnotification.setparameter(system.string)"></a>
**Summary:** called before the integration on respective species

## Class: BoSSS.Foundation.XDG.ISpeciesFilter <a id="bosss.foundation.xdg.ispeciesfilter"></a>

**Summary:** this interface should be implemented by bulk equation components which are only valid in one species


### Property: BoSSS.Foundation.XDG.ISpeciesFilter.ValidSpecies <a id="bosss.foundation.xdg.ispeciesfilter.validspecies"></a>
**Summary:** the species in which the bulk equation component is valid;
Null deactivates the Filter, i.e. the component is integrated for all species.

## Class: BoSSS.Foundation.XDG.ILevelSetEquationComponentCoefficient <a id="bosss.foundation.xdg.ilevelsetequationcomponentcoefficient"></a>

**Summary:** Interface for equation components which require e.g. grid and/or problem-dependent coefficients,
e.g. cell length scales


## Method: BoSSS.Foundation.XDG.ILevelSetEquationComponentCoefficient.CoefficientUpdate(BoSSS.Foundation.CoefficientSet,BoSSS.Foundation.CoefficientSet,System.Int32[],System.Int32) <a id="bosss.foundation.xdg.ilevelsetequationcomponentcoefficient.coefficientupdate(bosss.foundation.coefficientset,bosss.foundation.coefficientset,system.int32[],system.int32)"></a>
**Summary:** Passes various coefficients to the equation component.
**Parameter:** `csA` - Coefficient set related to negative species ([BoSSS.Foundation.XDG.ILevelSetForm.NegativeSpecies](#bosss.foundation.xdg.ilevelsetform.negativespecies))
**Parameter:** `csB` - Coefficient set related to positive species ([BoSSS.Foundation.XDG.ILevelSetForm.PositiveSpecies](#bosss.foundation.xdg.ilevelsetform.positivespecies))
**Parameter:** `DomainDGdeg` - actual polynomial degree of domain variables
**Parameter:** `TestDGdeg` - actual polynomial degree of codomain variables

## Class: BoSSS.Foundation.XDG.ILevelSetForm <a id="bosss.foundation.xdg.ilevelsetform"></a>

**Summary:** An integrand on the level set; per definition a level-set is always an interior edge


### Property: BoSSS.Foundation.XDG.ILevelSetForm.LevelSetIndex <a id="bosss.foundation.xdg.ilevelsetform.levelsetindex"></a>
**Summary:** index of the species-separating level set.


### Property: BoSSS.Foundation.XDG.ILevelSetForm.PositiveSpecies <a id="bosss.foundation.xdg.ilevelsetform.positivespecies"></a>
**Summary:** regarding this integrand, the species on the positive side of level set number [BoSSS.Foundation.XDG.ILevelSetForm.LevelSetIndex](#bosss.foundation.xdg.ilevelsetform.levelsetindex)


### Property: BoSSS.Foundation.XDG.ILevelSetForm.NegativeSpecies <a id="bosss.foundation.xdg.ilevelsetform.negativespecies"></a>
**Summary:** guess what?


### Property: BoSSS.Foundation.XDG.ILevelSetForm.LevelSetTerms <a id="bosss.foundation.xdg.ilevelsetform.levelsetterms"></a>
**Summary:** Controls integration at the level-set.

## Class: BoSSS.Foundation.XDG.ILevelSetFormSetup <a id="bosss.foundation.xdg.ilevelsetformsetup"></a>

**Summary:** provides access to the level set tracker


## Method: BoSSS.Foundation.XDG.ILevelSetFormSetup.Setup(BoSSS.Foundation.XDG.LevelSetTracker) <a id="bosss.foundation.xdg.ilevelsetformsetup.setup(bosss.foundation.xdg.levelsettracker)"></a>
**Summary:** Called before Integration

## Class: BoSSS.Foundation.XDG.ILevelSetForm_UxV <a id="bosss.foundation.xdg.ilevelsetform_uxv"></a>

**Summary:** The XDG-counterpart of [BoSSS.Foundation.IEdgeForm_UxV](BoSSS.Foundation.md#bosss.foundation.iedgeform_uxv)

## Class: BoSSS.Foundation.XDG.ILevelSetForm_GradUxV <a id="bosss.foundation.xdg.ilevelsetform_graduxv"></a>

**Summary:** The XDG-counterpart of [BoSSS.Foundation.IEdgeForm_UxV](BoSSS.Foundation.md#bosss.foundation.iedgeform_uxv)

## Class: BoSSS.Foundation.XDG.IEquationComponentExtension <a id="bosss.foundation.xdg.iequationcomponentextension"></a>

**Summary:** extension methods for the [BoSSS.Foundation.IEquationComponent](BoSSS.Foundation.md#bosss.foundation.iequationcomponent)-interface


## Method: BoSSS.Foundation.XDG.IEquationComponentExtension.XOperator(BoSSS.Foundation.IEquationComponent,System.Collections.Generic.IEnumerable{System.String},System.Int32) <a id="bosss.foundation.xdg.iequationcomponentextension.xoperator(bosss.foundation.iequationcomponent,system.collections.generic.ienumerable{system.string},system.int32)"></a>
**Summary:** creates the spatial operator that consists only of component 'c'


## Method: BoSSS.Foundation.XDG.IEquationComponentExtension.XOperator(BoSSS.Foundation.IEquationComponent,System.Collections.Generic.IEnumerable{System.String},System.Func{System.Int32[],System.Int32[],System.Int32[],System.Int32}) <a id="bosss.foundation.xdg.iequationcomponentextension.xoperator(bosss.foundation.iequationcomponent,system.collections.generic.ienumerable{system.string},system.func{system.int32[],system.int32[],system.int32[],system.int32})"></a>
**Summary:** creates the spatial operator that consists only of component 'c'

## Class: BoSSS.Foundation.XDG.IReinitialisationAlgorithm <a id="bosss.foundation.xdg.ireinitialisationalgorithm"></a>

**Summary:** common template of all Level-Set reinitialization algorithms


## Method: BoSSS.Foundation.XDG.IReinitialisationAlgorithm.ReInitialize(BoSSS.Foundation.XDG.LevelSet,BoSSS.Foundation.Grid.SubGrid) <a id="bosss.foundation.xdg.ireinitialisationalgorithm.reinitialize(bosss.foundation.xdg.levelset,bosss.foundation.grid.subgrid)"></a>
**Summary:** performs a reinitialization of the Level Set function 'LS'
**Parameter:** `LS` - on entry, an arbitrary Level Set function; on exit, a signed-distance Level Set function 
with equal zero-set.
**Parameter:** `Restriction` - optional restriction to the computational domain

## Class: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2 <a id="bosss.foundation.xdg.lecquadraturelevelset`2"></a>

**Summary:** integrator for coupling components, linear components;


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.time <a id="bosss.foundation.xdg.lecquadraturelevelset`2.time"></a>
**Summary:** Physical time.


### Property: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.m_LevSetIdx <a id="bosss.foundation.xdg.lecquadraturelevelset`2.m_levsetidx"></a>
**Summary:** index of the level set to evaluate


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.m_lsTrk <a id="bosss.foundation.xdg.lecquadraturelevelset`2.m_lstrk"></a>
**Summary:** les tracker


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.m_LsTrkHistoryIndex <a id="bosss.foundation.xdg.lecquadraturelevelset`2.m_lstrkhistoryindex"></a>
**Summary:** index into [BoSSS.Foundation.XDG.LevelSetTracker.RegionsHistory](#bosss.foundation.xdg.levelsettracker.regionshistory), etc.


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.m_SpeciesPair <a id="bosss.foundation.xdg.lecquadraturelevelset`2.m_speciespair"></a>
**Summary:** Negative and positive (with respect to level-set) species.


### Property: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.SpeciesA <a id="bosss.foundation.xdg.lecquadraturelevelset`2.speciesa"></a>
**Summary:** Negative species/Species A


### Property: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.SpeciesB <a id="bosss.foundation.xdg.lecquadraturelevelset`2.speciesb"></a>
**Summary:** Positive species/Species B


## Method: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.#ctor(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.XDG.XDifferentialOperatorMk2,`0,`1,BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,System.Int32,System.Tuple{BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId},BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.lecquadraturelevelset`2.#ctor(bosss.foundation.grid.igriddata,bosss.foundation.xdg.xdifferentialoperatormk2,`0,`1,bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.levelsettracker,system.int32,system.int32,system.tuple{bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid},bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** ctor.


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.m_ParamFieldValuesPos <a id="bosss.foundation.xdg.lecquadraturelevelset`2.m_paramfieldvaluespos"></a>
**Summary:** values of parameter fields, positive side of level Set

1st index: parameter index
2nd index: cell index, plus some offset
3rd index: node index


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.m_ParamFieldValuesNeg <a id="bosss.foundation.xdg.lecquadraturelevelset`2.m_paramfieldvaluesneg"></a>
**Summary:** values of parameter fields, positive side of level Set

1st index: parameter index
2nd index: cell index, plus some offset
3rd index: node index


## Method: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.AllocateBuffers(System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.lecquadraturelevelset`2.allocatebuffers(system.int32,bosss.foundation.nodeset)"></a>
**Summary:** memory allocation.


## Method: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.TestNegativeAndPositiveSpecies(BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId,System.Int32) <a id="bosss.foundation.xdg.lecquadraturelevelset`2.testnegativeandpositivespecies(bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule},bosss.foundation.xdg.levelsettracker,system.int32,bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid,system.int32)"></a>
**Summary:** Test for the correct configuration of positive and negative species.
Should be pretty quick, so we can do this also in Release.


## Method: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.TestNegativeAndPositiveSpecies(System.Int32,System.Int32,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId,System.Int32) <a id="bosss.foundation.xdg.lecquadraturelevelset`2.testnegativeandpositivespecies(system.int32,system.int32,bosss.foundation.xdg.levelsettracker,system.int32,bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid,system.int32)"></a>
**Summary:** Test for the correct configuration of positive and negative species.
Should be pretty quick, so we can do this also in Release.


## Method: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.EvalBasis(System.Int32,System.Int32,System.Collections.Generic.IList{BoSSS.Foundation.Basis},System.Boolean[],System.Boolean[],ilPSP.MultidimensionalArray[]@,ilPSP.MultidimensionalArray[]@,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.lecquadraturelevelset`2.evalbasis(system.int32,system.int32,system.collections.generic.ilist{bosss.foundation.basis},system.boolean[],system.boolean[],ilpsp.multidimensionalarray[]@,ilpsp.multidimensionalarray[]@,bosss.foundation.nodeset)"></a>
**Summary:** Evaluation of DG basis and DG basis gradients
**Parameter:** `i0` - 1st cell to evaluate
**Parameter:** `Len` - number of cells to evaluate
**Parameter:** `basisEnum` - set of basis objects
**Parameter:** `ReqB` - true, if the gradient of the basis is required
**Parameter:** `ReqGrad` - true, if the gradient of the basis is required
**Parameter:** `TestValues` - 
**Parameter:** `TestGradientValues` - 
**Parameter:** `Nodes` - input, nodes where the basis should be evaluated


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.OperatorMatrix <a id="bosss.foundation.xdg.lecquadraturelevelset`2.operatormatrix"></a>
**Summary:** result of the integration


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.OperatorAffine <a id="bosss.foundation.xdg.lecquadraturelevelset`2.operatoraffine"></a>
**Summary:** affine part of da operator.


### Field: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.m_alpha <a id="bosss.foundation.xdg.lecquadraturelevelset`2.m_alpha"></a>
**Summary:** scaling factor for accumulation


## Method: BoSSS.Foundation.XDG.LECQuadratureLevelSet`2.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.lecquadraturelevelset`2.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** writes the dammed result of the integration to the sparse matrix

## Class: BoSSS.Foundation.XDG.LevelSet <a id="bosss.foundation.xdg.levelset"></a>

**Summary:** a level set that is implemented as a DG field, i.e. a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)


## Method: BoSSS.Foundation.XDG.LevelSet.#ctor(BoSSS.Foundation.Basis,System.String) <a id="bosss.foundation.xdg.levelset.#ctor(bosss.foundation.basis,system.string)"></a>
**Summary:** Constructor


## Method: BoSSS.Foundation.XDG.LevelSet.EvaluateGradient(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelset.evaluategradient(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray)"></a>
**Summary:** as defined by [BoSSS.Foundation.XDG.ILevelSet.EvaluateGradient(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray)](BoSSS.Foundation.md#bosss.foundation.xdg.ilevelset.evaluategradient(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray))


## Method: BoSSS.Foundation.XDG.LevelSet.EvaluateLaplacian(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelset.evaluatelaplacian(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray)"></a>
**Summary:** Evaluates the broken Laplacian (by cell-local analytic derivation of
the basis polynomials) of this field; this method my move to the
[BoSSS.Foundation.DGField](BoSSS.Foundation.md#bosss.foundation.dgfield)-class in future;
**Parameter:** `j0` - 
**Parameter:** `Len` - 
**Parameter:** `NodeSet` - 
**Parameter:** `result` -
- 1st index: cell index j
- 2nd index: node index m into nodeset 'NodeSet'

So, the entry [j,m] = $\sum_{d=1}^{D} \frac{\partial}{\partial x_d} \varphi (\vec{\xi}_m)$ 
where $\vec{xi}_m$  is the m-th vector in the 'NodeSet',
in the j-th cell.
**Remark:**
Because of 2 derivatives taken, this field needs to be at least of DG degree 2 to get a non-zero result
from this method.


## Method: BoSSS.Foundation.XDG.LevelSet.ComputeNormalByFlux(BoSSS.Foundation.VectorField{BoSSS.Foundation.SinglePhaseField},BoSSS.Foundation.Grid.SubGrid,BoSSS.Foundation.SubGridBoundaryModes) <a id="bosss.foundation.xdg.levelset.computenormalbyflux(bosss.foundation.vectorfield{bosss.foundation.singlephasefield},bosss.foundation.grid.subgrid,bosss.foundation.subgridboundarymodes)"></a>
**Summary:** Assigns the normalized gradient of the level set to the Output
vector
**Parameter:** `Output` - Normal vector
**Parameter:** `optionalSubGrid` - Restriction of the computations to a an optional subgrid
**Parameter:** `bndMode` - 


## Method: BoSSS.Foundation.XDG.LevelSet.ComputeTotalCurvatureByFlux(BoSSS.Foundation.SinglePhaseField,BoSSS.Foundation.Grid.SubGrid,BoSSS.Foundation.SubGridBoundaryModes) <a id="bosss.foundation.xdg.levelset.computetotalcurvaturebyflux(bosss.foundation.singlephasefield,bosss.foundation.grid.subgrid,bosss.foundation.subgridboundarymodes)"></a>
**Summary:** Determines the total curvature which is twice the mean curvature
Please pay attention to the sign of this expression!
**Parameter:** `Output` - The total curvature
**Parameter:** `optionalSubGrid` - Subgrid which can be defined, for example for carrying out
computations on a narrow band
**Parameter:** `bndMode` - Definition of the behavior at subgrid boundaries


## Method: BoSSS.Foundation.XDG.LevelSet.ComputeDerivativesOfTheNormalByFlux(BoSSS.Foundation.VectorField{BoSSS.Foundation.SinglePhaseField},System.Int32,BoSSS.Foundation.Grid.SubGrid,BoSSS.Foundation.SubGridBoundaryModes) <a id="bosss.foundation.xdg.levelset.computederivativesofthenormalbyflux(bosss.foundation.vectorfield{bosss.foundation.singlephasefield},system.int32,bosss.foundation.grid.subgrid,bosss.foundation.subgridboundarymodes)"></a>
**Summary:** Vector of the d partial derivatives of the i-th component of the
normal vector
**Parameter:** `Output` - Vector of the partial derivatives
**Parameter:** `componentOfNormalVec` - specifies the component i of the normal vector
**Parameter:** `optionalSubGrid` - 
**Parameter:** `bndMode` - 


## Method: BoSSS.Foundation.XDG.LevelSet.ComputeNormal(BoSSS.Foundation.VectorField{BoSSS.Foundation.SinglePhaseField},BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.levelset.computenormal(bosss.foundation.vectorfield{bosss.foundation.singlephasefield},bosss.foundation.grid.cellmask)"></a>
**Summary:** Assigns the normalized gradient of the level set to the Output
vector
**Parameter:** `Output` - Normal Vector
**Parameter:** `optionalCellMask` - Cell mask used when computing the derivatives


## Method: BoSSS.Foundation.XDG.LevelSet.ProjectTotalcurvature2(System.Double,BoSSS.Foundation.SinglePhaseField,System.Int32,System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme) <a id="bosss.foundation.xdg.levelset.projecttotalcurvature2(system.double,bosss.foundation.singlephasefield,system.int32,system.int32,system.int32,bosss.foundation.quadrature.cellquadraturescheme)"></a>
**Summary:** Computation of mean curvature according to Bonnet's formula.
**Parameter:** `scale` - 
**Parameter:** `Output` - output.
**Parameter:** `quadScheme` - 
**Parameter:** `UseCenDiffUpTo` - Either 0, 1, or 2:
If 0, all derivatives are computed locally (broken derivative); 
if 1, the first order derivatives are computed by central
differences, while the second order ones are computed locally,
based on the first order ones;
if 2, all derivatives are computed by central differences.
**Parameter:** `_1stDerivDegree` - Relative DG polynomial degree for the 1st order derivatives, i.e.
degree is '_1stDerivDegree'+p, where
p is the degree of this field.
Only active if 'UseCenDiffUpTo' is greater than 0.
**Parameter:** `_2ndDerivDegree` - Relative DG polynomial degree for the 2nd order derivatives, i.e.
degree is '_2ndDerivDegree'+p, where
p is the degree of this field. Only active if
'UseCenDiffUpTo' is greater than 1.
**Remark:**
using central differences causes memory allocation: D
fields for 'UseCenDiffUpTo'=1, and
D*(D+1) for 'UseCenDiffUpTo'=2,
where D notates the spatial dimension.


## Method: BoSSS.Foundation.XDG.LevelSet.EvaluateTotalCurvature(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelset.evaluatetotalcurvature(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray)"></a>
**Summary:** curvature computation according to Bonnet's formula


## Method: BoSSS.Foundation.XDG.LevelSet.ComputeTotalCurvature(BoSSS.Foundation.SinglePhaseField,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.levelset.computetotalcurvature(bosss.foundation.singlephasefield,bosss.foundation.grid.cellmask)"></a>
**Summary:** Determines the total curvature which is twice the mean curvature
Please pay attention to the sign of this expression!
**Parameter:** `Output` - Field representing the total curvature
**Parameter:** `optionalCellMask` - Cell Mask for the derivatives and their accumulation regarding the
curvature


## Method: BoSSS.Foundation.XDG.LevelSet.ComputeDerivativesOfTheNormal(BoSSS.Foundation.VectorField{BoSSS.Foundation.SinglePhaseField},System.Int32,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.levelset.computederivativesofthenormal(bosss.foundation.vectorfield{bosss.foundation.singlephasefield},system.int32,bosss.foundation.grid.cellmask)"></a>
**Summary:** Vector of the d partial derivatives of the i-th component of the
normal vector
**Parameter:** `Output` - Vector of the partial derivatives
**Parameter:** `componentOfNormalVec` - specifies the component i of the normal vector
**Parameter:** `optionalCellMask` - Cell Mask for the computation


## Method: BoSSS.Foundation.XDG.LevelSet.ApproximateSignFunction(BoSSS.Foundation.SinglePhaseField,System.Double,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.levelset.approximatesignfunction(bosss.foundation.singlephasefield,system.double,bosss.foundation.grid.cellmask)"></a>
**Summary:** Approximation of the signum function of the level set field
**Parameter:** `Output` - 
**Parameter:** `gridParameter` - 
**Parameter:** `optionalCellMask` - 


## Method: BoSSS.Foundation.XDG.LevelSet.SignedDistanceError(BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.levelset.signeddistanceerror(bosss.foundation.grid.cellmask)"></a>
**Summary:** computes the L2 norm of the Residual of the Eikonal equation in the
domain 'K', i.e. 
\f[ 
\left\|
\textrm{\textbf{1}}_K
\cdot
\left(  | \nabla \phi | - 1 \right)
\right\|_2
\f]
**Parameter:** `K` - optional restriction to a subdomain

## Class: BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad <a id="bosss.foundation.xdg.levelset.signeddistanceerrorquad"></a>

**Summary:** Quadrature for the computation of the deviance of the level set
function from a signed distance function.


## Method: BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.#ctor(BoSSS.Foundation.XDG.LevelSet,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.levelset.signeddistanceerrorquad.#ctor(bosss.foundation.xdg.levelset,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** ctor


### Field: BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.m_phi <a id="bosss.foundation.xdg.levelset.signeddistanceerrorquad.m_phi"></a>
**Summary:** owner


### Field: BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.m_gradPhi <a id="bosss.foundation.xdg.levelset.signeddistanceerrorquad.m_gradphi"></a>
**Summary:** Values of the gradient of [BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.m_phi](#bosss.foundation.xdg.levelset.signeddistanceerrorquad.m_phi)


### Field: BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.LocalErrorL2Accumulated <a id="bosss.foundation.xdg.levelset.signeddistanceerrorquad.localerrorl2accumulated"></a>
**Summary:** Sum of L2 errors in the current process


## Method: BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.AllocateBuffers(System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.levelset.signeddistanceerrorquad.allocatebuffers(system.int32,bosss.foundation.nodeset)"></a>
**Summary:** [BoSSS.Foundation.Quadrature.Quadrature`2.AllocateBuffers(System.Int32,BoSSS.Foundation.NodeSet)](BoSSS.Foundation.md#bosss.foundation.quadrature.quadrature`2.allocatebuffers(system.int32,bosss.foundation.nodeset))


## Method: BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.Quadrature.QuadRule,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelset.signeddistanceerrorquad.evaluate(system.int32,system.int32,bosss.foundation.quadrature.quadrule,ilpsp.multidimensionalarray)"></a>
**Summary:** Computes the residual of the Eikonal equation.


## Method: BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelset.signeddistanceerrorquad.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Accumulates the result to [BoSSS.Foundation.XDG.LevelSet.SignedDistanceErrorQuad.LocalErrorL2Accumulated](#bosss.foundation.xdg.levelset.signeddistanceerrorquad.localerrorl2accumulated)
**Parameter:** `i0` - 
**Parameter:** `Length` - 
**Parameter:** `ResultsOfIntegration` - 


## Method: BoSSS.Foundation.XDG.LevelSet.CloneAs <a id="bosss.foundation.xdg.levelset.cloneas"></a>
**Summary:** Clones this object


## Method: BoSSS.Foundation.XDG.LevelSet.Clone <a id="bosss.foundation.xdg.levelset.clone"></a>
**Summary:** Clones this object


## Method: BoSSS.Foundation.XDG.LevelSet.CopyFrom(BoSSS.Foundation.XDG.ILevelSet) <a id="bosss.foundation.xdg.levelset.copyfrom(bosss.foundation.xdg.ilevelset)"></a>


### Field: BoSSS.Foundation.XDG.LevelSet.m_Initializer <a id="bosss.foundation.xdg.levelset.m_initializer"></a>
**Summary:** See [BoSSS.Foundation.XDG.LevelSet.Initializer](#bosss.foundation.xdg.levelset.initializer)


### Property: BoSSS.Foundation.XDG.LevelSet.Initializer <a id="bosss.foundation.xdg.levelset.initializer"></a>
**Summary:** To support IO-architecture, NOT for direct user interaction. Note
that it is essential that this member always returns the SAME
object (reference-equals)!

## Class: BoSSS.Foundation.XDG.LevelSet.LevelSetInitializer <a id="bosss.foundation.xdg.levelset.levelsetinitializer"></a>

**Summary:** Specialized initializer for level set fields.


## Method: BoSSS.Foundation.XDG.LevelSet.LevelSetInitializer.Initialize(BoSSS.Foundation.IO.IInitializationContext) <a id="bosss.foundation.xdg.levelset.levelsetinitializer.initialize(bosss.foundation.io.iinitializationcontext)"></a>
**Summary:** [BoSSS.Foundation.IO.IInitializer`1.Initialize(BoSSS.Foundation.IO.IInitializationContext)](BoSSS.Foundation.md#bosss.foundation.io.iinitializer`1.initialize(bosss.foundation.io.iinitializationcontext))
**Parameter:** `c` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSet.LevelSetInitializer.Equals(BoSSS.Foundation.IO.Initializer{BoSSS.Foundation.DGField}) <a id="bosss.foundation.xdg.levelset.levelsetinitializer.equals(bosss.foundation.io.initializer{bosss.foundation.dgfield})"></a>
**Summary:** Compares the given object 'other' with respect
to the 
[BoSSS.Foundation.DGField.FieldInitializer.Identification](BoSSS.Foundation.md#bosss.foundation.dgfield.fieldinitializer.identification) and the 
[BoSSS.Foundation.DGField.FieldInitializer.BasisInfo](BoSSS.Foundation.md#bosss.foundation.dgfield.fieldinitializer.basisinfo).
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSet.LevelSetInitializer.GetHashCode <a id="bosss.foundation.xdg.levelset.levelsetinitializer.gethashcode"></a>
**Summary:** Computes a hash code based on 
[BoSSS.Foundation.DGField.FieldInitializer.Identification](BoSSS.Foundation.md#bosss.foundation.dgfield.fieldinitializer.identification) and 
[BoSSS.Foundation.DGField.FieldInitializer.BasisInfo](BoSSS.Foundation.md#bosss.foundation.dgfield.fieldinitializer.basisinfo).

## Class: BoSSS.Foundation.XDG.LevelsetCellSignCode <a id="bosss.foundation.xdg.levelsetcellsigncode"></a>

**Summary:** Encodes, for one cell, the sign of all four level sets;


### Field: BoSSS.Foundation.XDG.LevelsetCellSignCode.lsSig <a id="bosss.foundation.xdg.levelsetcellsigncode.lssig"></a>
**Summary:** 3adic representation of the [BoSSS.Foundation.XDG.LevelsetSign](#bosss.foundation.xdg.levelsetsign) for all four level sets;
Therefore, this should be in the range of 0 to $3^4 - 1 = 80$.


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.GetSign(System.Int32) <a id="bosss.foundation.xdg.levelsetcellsigncode.getsign(system.int32)"></a>
**Summary:** extracts the level set sign for level set no. 'LevSetIdx'


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.SetSign(System.Int32,BoSSS.Foundation.XDG.LevelsetSign) <a id="bosss.foundation.xdg.levelsetcellsigncode.setsign(system.int32,bosss.foundation.xdg.levelsetsign)"></a>
**Summary:** manipulates the level set sign for level set no. 'LevSetIdx'


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.GetAllSignCodes(System.Int32) <a id="bosss.foundation.xdg.levelsetcellsigncode.getallsigncodes(system.int32)"></a>
**Summary:** Returns all combinations of level set signs which are possible under this cell sign.
**Parameter:** `NoOfLS` - Total number of level-sets, [BoSSS.Foundation.XDG.LevelSetTracker.NoOfLevelSets](#bosss.foundation.xdg.levelsettracker.nooflevelsets)


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.Equals(System.Object) <a id="bosss.foundation.xdg.levelsetcellsigncode.equals(system.object)"></a>
**Summary:** equality


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.GetHashCode <a id="bosss.foundation.xdg.levelsetcellsigncode.gethashcode"></a>
**Summary:** hasch code


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.op_Equality(BoSSS.Foundation.XDG.LevelsetCellSignCode,BoSSS.Foundation.XDG.LevelsetCellSignCode) <a id="bosss.foundation.xdg.levelsetcellsigncode.op_equality(bosss.foundation.xdg.levelsetcellsigncode,bosss.foundation.xdg.levelsetcellsigncode)"></a>
**Summary:** equality


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.op_Inequality(BoSSS.Foundation.XDG.LevelsetCellSignCode,BoSSS.Foundation.XDG.LevelsetCellSignCode) <a id="bosss.foundation.xdg.levelsetcellsigncode.op_inequality(bosss.foundation.xdg.levelsetcellsigncode,bosss.foundation.xdg.levelsetcellsigncode)"></a>
**Summary:** inequality


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.IsContained(BoSSS.Foundation.XDG.LevelSetSignCode,System.Int32) <a id="bosss.foundation.xdg.levelsetcellsigncode.iscontained(bosss.foundation.xdg.levelsetsigncode,system.int32)"></a>
**Summary:** true, if 'cd' is contained in this


## Method: BoSSS.Foundation.XDG.LevelsetCellSignCode.Extract(System.UInt16) <a id="bosss.foundation.xdg.levelsetcellsigncode.extract(system.uint16)"></a>
**Summary:** Extracts the level set cell sign code
**Parameter:** `RegionCode` - 
**Returns:**
the reduced region code for the "full" region code 'RegionCode';
this is a number between 0 (including) and 81 (excluding).

## Class: BoSSS.Foundation.XDG.LevelSetCFLException <a id="bosss.foundation.xdg.levelsetcflexception"></a>

**Summary:** thrown by [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[])), if the level-set has moved by **more** than one cell in a single timestep/update


## Method: BoSSS.Foundation.XDG.LevelSetCFLException.#ctor(System.Int32[]) <a id="bosss.foundation.xdg.levelsetcflexception.#ctor(system.int32[])"></a>
**Summary:** ctor


### Property: BoSSS.Foundation.XDG.LevelSetCFLException.NoOfViolatedCellsPerLevSet <a id="bosss.foundation.xdg.levelsetcflexception.noofviolatedcellsperlevset"></a>
**Summary:** index: Level Set index 
content: Number of cells in which the CFL condition is violated.

## Class: BoSSS.Foundation.XDG.LevelSetTracker <a id="bosss.foundation.xdg.levelsettracker"></a>

**Summary:** The level set - tracker manages the tracking of narrow - bands of up to 4 level set.
It is a perquisite for
the memory management of cut-cell fields, i.e. [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield) and [BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis)

**Remark:**
After changing one ore more level sets, the [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[]))-method must be
called.

## Class: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions <a id="bosss.foundation.xdg.levelsettracker.levelsetregions"></a>

**Summary:** A summary of information about a level set


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.#ctor(BoSSS.Foundation.XDG.LevelSetTracker) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.#ctor(bosss.foundation.xdg.levelsettracker)"></a>
**Summary:** Constructor


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.Version <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.version"></a>
**Summary:** The 'version' of the data, i.e. a number that is always increased
when the data changes (see [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[]))).


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.Time <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.time"></a>
**Summary:** physical/simulation time associated with this Level-Set state


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.RegionsCode <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.regionscode"></a>
**Summary:** Level set region codes for locally updated and external cells


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetLevelSetDistance(System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getlevelsetdistance(system.int32,system.int32)"></a>
**Summary:** returns the distance layer index for level-set 'levSetIdx',
see also [BoSSS.Foundation.XDG.LevelSetTracker.DecodeLevelSetDist(System.UInt16,System.Int32)](#bosss.foundation.xdg.levelsettracker.decodelevelsetdist(system.uint16,system.int32)), [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.RegionsCode](#bosss.foundation.xdg.levelsettracker.levelsetregions.regionscode).


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.ColorMap4Spc <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.colormap4spc"></a>
**Summary:** A color map for each species; a color is a positive integer. Each topologically, simply connected part
of a species is painted in a unique color. 
- key: species ID
- index into value: local cell index
- each entry value: the unique color of the respective cell; 0 if the species is not present in the respective cell


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetPreviousRegion <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getpreviousregion"></a>
**Summary:** walk back in region stack


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.VerifyColoring(BoSSS.Foundation.Grid.IGridData,System.Int32[]) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.verifycoloring(bosss.foundation.grid.igriddata,system.int32[])"></a>
**Summary:** - verifies the consistency of a color map among MPI processors
- in future versions, it may be DEBUG-only


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.FindColorsRecursive2(System.Collections.Generic.HashSet{System.Int32},System.Collections.BitArray,System.Int32,System.Int32,System.Int32[],System.Int32[],BoSSS.Foundation.Grid.IGridData) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.findcolorsrecursive2(system.collections.generic.hashset{system.int32},system.collections.bitarray,system.int32,system.int32,system.int32[],system.int32[],bosss.foundation.grid.igriddata)"></a>
**Summary:** 'Non-Recursive' implementation of the recursive algorithm, should be less prone to stack overflow.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.RecursiveColoring2(BoSSS.Foundation.Grid.IGridData,System.Collections.BitArray,System.Int32,System.Int32,System.Int32[],System.Boolean@) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.recursivecoloring2(bosss.foundation.grid.igriddata,system.collections.bitarray,system.int32,system.int32,system.int32[],system.boolean@)"></a>
**Summary:** 'Non-Recursive' implementation of the recursive algorithm, should be less prone to stack overflow.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_SpeciesSubGrids <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_speciessubgrids"></a>
**Summary:** For each species: The sub-grid of cells populated with this species


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetRegions <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetregions"></a>
**Summary:** Level set region code,
for locally updated and external cells


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetRegions_b4Update <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetregions_b4update"></a>
**Summary:** Level set region code, before the most recent call to [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[]))
for locally updated and external cells


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetCoincidingFaces <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetcoincidingfaces"></a>
**Summary:** [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingfaces)


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingFaces <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingfaces"></a>
**Summary:** Handling of special cases, when the level-set coincides with a cell face;
It can be null, if there is no such face in the entire mesh;
- 1st index: local geometric cell index
- 2nd index: enumeration (most of the time, only one level-set will have a coinciding face, so there can be 
- entry: if null, there is no face on the cell which coincides with any level-set 
- contains tuples, which level-set coincides with which face (if any)
**Remark:**
This member enables stable treatment of the special case when 
the level set is on some cell boundary.
There, the normal rules behave unstably, e.g.
- the Level set is recognized in both cells
- the Level set is not recognized in any cell.
Therefore, this case is already intercepted in the tracker beforehand, see [BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule](#bosss.foundation.xdg.quadrature.levelsetonedgerule)


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetCoincidingCoFaces <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetcoincidingcofaces"></a>
**Summary:** [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingCoFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingcofaces)>


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingCoFaces <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingcofaces"></a>
**Summary:** Handling of special cases, when the level-set coincides with a cell co-face (e.g., in 2D it passes through a corner, in 3D through a co-face);
It can be null, if there is no such co-face in the entire mesh;
- 1st index: local geometric cell index
- 2nd index: enumeration (most of the time, only one level-set will have a coinciding co-face, so there can be 
- entry: if null, there is no face on the cell which coincides with any level-set 
- contains tuples, which level-set coincides with which co-face (if any)
**Remark:**
This member enables stable treatment of the special case when 
the level set is on some cell boundary.
There, the normal rules behave unstably, e.g.
- the Level set is recognized in both cells
- the Level set is not recognized in any cell.
Therefore, this case is already intercepted in the tracker beforehand, see [BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule](#bosss.foundation.xdg.quadrature.levelsetonedgerule)


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetCellSignCode(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getcellsigncode(system.int32)"></a>
**Summary:** Returns the sign (pos, neg, both) for all level-sets in cell 'jCell'


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LenToNextChange <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_lentonextchange"></a>
**Summary:** For each cell j, the number of cells that follow with the same region code as cell j.
- index: cell index j;


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.Recalc_LenToNextchange <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.recalc_lentonextchange"></a>
**Summary:** Update of [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LenToNextChange](#bosss.foundation.xdg.levelsettracker.levelsetregions.m_lentonextchange).


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.InvalidateCaches <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.invalidatecaches"></a>


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetCutCellSubgrid4LevSet(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getcutcellsubgrid4levset(system.int32)"></a>
**Summary:** Returns the subgrid of those cells which are cut by level set No. 'LevSetIdx'.
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetCutCellSubGrid <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getcutcellsubgrid"></a>
**Summary:** Returns the subgrid that contains all cells that are cut by any of the zero -- level sets
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetCutCellMask4LevSet(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getcutcellmask4levset(system.int32)"></a>
**Summary:** returns the subgrid of those cells which are cut by level set No. 'LevSetIdx'.
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetCutCellMask <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getcutcellmask"></a>
**Summary:** gets the subgrid that contains all cells that are cut by any of the zero -- level sets
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetZeroSetEdges(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getzerosetedges(system.int32)"></a>
**Summary:** For each level-set, a mask containing all edges that coincide with the level-set itself.
Return value can be null, if there are no such edges.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_NearMask <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_nearmask"></a>
**Summary:** Caches the values returned by [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNearFieldSubgrid4LevSet(System.Int32,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getnearfieldsubgrid4levset(system.int32,system.int32));
index: width of subgrid around the cut cells


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNearFieldMask(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getnearfieldmask(system.int32)"></a>
**Summary:** gets a mask of width 'FieldWidth', around any level set
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_NearField <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_nearfield"></a>
**Summary:** caches the values returned by [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNearFieldSubgrid4LevSet(System.Int32,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getnearfieldsubgrid4levset(system.int32,system.int32));

index: width of subgrid around the cut cells


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNearFieldSubgrid(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getnearfieldsubgrid(system.int32)"></a>
**Summary:** gets a subgrid of width 'FieldWidth', around any level set
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_NearField4LevelSet <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_nearfield4levelset"></a>
**Summary:** caches the values returned by [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNearFieldSubgrid4LevSet(System.Int32,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getnearfieldsubgrid4levset(system.int32,system.int32));

1st index: Level Set - index 
2nd index: width of subgrid around the cut cells


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNearFieldSubgrid4LevSet(System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getnearfieldsubgrid4levset(system.int32,system.int32)"></a>
**Summary:** gets a subgrid of width 'FieldWidth', around level set No. 'levSetIdx';
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_NearMask4LevelSet <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_nearmask4levelset"></a>
**Summary:** caches the values returned by [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNearFieldSubgrid4LevSet(System.Int32,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getnearfieldsubgrid4levset(system.int32,system.int32));

1st index: Level Set - index 
2nd index: width of subgrid around the cut cells


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNearMask4LevSet(System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getnearmask4levset(system.int32,system.int32)"></a>
**Summary:** gets a cell-mask of width 'FieldWidth', around level set No. 'levSetIdx';
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_PresenceMask4LevelSet <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.m_presencemask4levelset"></a>
**Summary:** caches the values returned by [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesRestrictedNearMask4LevSet(System.Int32,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesrestrictednearmask4levset(system.int32,system.int32));

1st index: Level Set - index 
2nd index: width of subgrid around the cut cells


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesRestrictedNearMask4LevSet(System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesrestrictednearmask4levset(system.int32,system.int32)"></a>
**Summary:** gets a cell-mask of width 'FieldWidth', around level set No. 'levSetIdx';
The mask only contains the entries, where the phases that the level set separates are present, as defined in [BoSSS.Foundation.XDG.LevelSetTracker.m_SpeciesTable](#bosss.foundation.xdg.levelsettracker.m_speciestable).
**Remark:**
In contrast to [BoSSS.Foundation.Grid.SubGrid](BoSSS.Foundation.md#bosss.foundation.grid.subgrid)'s, [BoSSS.Foundation.Grid.CellMask](BoSSS.Foundation.md#bosss.foundation.grid.cellmask)'s are not MPI-collective, and should therefore be preferred.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesSubGrid(BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciessubgrid(bosss.foundation.xdg.speciesid)"></a>
**Summary:** Equivalent to [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesSubGrid(System.String)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciessubgrid(system.string))


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetLevelSetWing(System.Int32,System.Double) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getlevelsetwing(system.int32,system.double)"></a>
**Summary:** returns the subgrid containing all cells in which the sign of the level set function #'LevelSetIndex'
is at least in one point equal to 'sign'.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesSubGrid(System.String) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciessubgrid(system.string)"></a>
**Summary:** Creates an subgrid which only contains cells
that are at least partly occupied by species
'speciesName';
**Parameter:** `speciesName` - The name of the species
**Returns:**
A subgrid containing only cells with at least a portion of
species 'speciesName'


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesMask(System.String) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesmask(system.string)"></a>
**Summary:** see [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesMask(BoSSS.Foundation.XDG.SpeciesId)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesmask(bosss.foundation.xdg.speciesid))
**Parameter:** `speciesName` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesMask(BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesmask(bosss.foundation.xdg.speciesid)"></a>
**Summary:** Creates an execution mask (volume mask) which only contains cells
that are at least partly occupied by species
'speciesId';
**Parameter:** `speciesId` - The name of the species
**Returns:**
A volume mask containing only cells with at least a portion of
species 'speciesId'
**Remark:**
Note: The method is so complex because we do not want to
consider the whole narrow-band because it may contain additional
cells on the "other" side of the level set!


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.IsSpeciesPresentInCell(BoSSS.Foundation.XDG.SpeciesId,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.isspeciespresentincell(bosss.foundation.xdg.speciesid,system.int32)"></a>
**Summary:** Tests if a species $\mathfrak{s}$ is actually $\emph{present}$ in some cell $K_{\text{\tt jCell}}$,
i.e. if 
the measure of the species in the cell is positive, i.e. 
\[
\int_{K_{\text{\tt jCell}} \cap \mathfrak{s} } 1 \dV > 0 
\]
**Parameter:** `speciesId` - The id of species \mathfrak{s}.
**Parameter:** `jCell` - a cell index
**Returns:**

**Remark:**
Note that 
a species may not be 'present' in some cell 
although 
the index of a species (e.g. obtained by [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesIndex(BoSSS.Foundation.XDG.SpeciesId,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesindex(bosss.foundation.xdg.speciesid,system.int32)))
may be positive.
In the near-field, some species index may be allocated (on the 'other' side of the level-set),
but the species may not be present.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.ToDGField <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.todgfield"></a>
**Summary:** Outputs a piecewise constant field which is 0 outside the narrow band
1+width on cut cells and decreasing on the near-cells


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNoOfSpecies(System.Int32,BoSSS.Foundation.XDG.ReducedRegionCode@) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getnoofspecies(system.int32,bosss.foundation.xdg.reducedregioncode@)"></a>
**Summary:** returns the (possible) number of species in cell 'j';
**Parameter:** `j` - local cell index;
**Parameter:** `ReducedRegionCode` - on exit, the reduced region code for cell 'j'
in an 3-adic representation; This number 
is later on required as an input for [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesIndex(BoSSS.Foundation.XDG.SpeciesId,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesindex(bosss.foundation.xdg.speciesid,system.int32));
**Returns:**

**Remark:**
Here, three states for each of the for level sets are considered:

positive far (FAR+)
negative far (FAR-)
positive near, negative near or cut

This implies, that also for cells in the near region, memory is allocated for more than one
species.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesIdFromIndex(System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesidfromindex(system.int32,system.int32)"></a>
**Summary:** this function is the inverse to [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesIndex(BoSSS.Foundation.XDG.SpeciesId,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesindex(bosss.foundation.xdg.speciesid,system.int32));
**Parameter:** `SpeciesIndex` - 
**Parameter:** `jCell` - local cell index.
**Returns:**

**Remark:**
this function is the inverse to [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesIndex(BoSSS.Foundation.XDG.SpeciesId,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesindex(bosss.foundation.xdg.speciesid,system.int32))


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesIndex(BoSSS.Foundation.XDG.SpeciesId,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesindex(bosss.foundation.xdg.speciesid,system.int32)"></a>
**Summary:** Returns the index of species ''_SpeciesId'' in the cell ''jCell''.
**Parameter:** `jCell` - a local cell index
**Parameter:** `_SpeciesId` - species identification


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetNoOfSpecies(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getnoofspecies(system.int32)"></a>
**Summary:** returns the (possible) number of species in cell 'j';
**Parameter:** `j` - local cell index;
**Returns:**



### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.SpeciesIdS <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.speciesids"></a>
**Summary:** Equal to [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesIdS](#bosss.foundation.xdg.levelsettracker.speciesids).


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.SpeciesTable <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.speciestable"></a>
**Summary:** See [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable).


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesName(BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesname(bosss.foundation.xdg.speciesid)"></a>
**Summary:** Equal to [BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesName(BoSSS.Foundation.XDG.SpeciesId)](#bosss.foundation.xdg.levelsettracker.getspeciesname(bosss.foundation.xdg.speciesid)).


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GetSpeciesId(System.String) <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.getspeciesid(system.string)"></a>
**Summary:** Equal to [BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesName(BoSSS.Foundation.XDG.SpeciesId)](#bosss.foundation.xdg.levelsettracker.getspeciesname(bosss.foundation.xdg.speciesid)).


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.Clone <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.clone"></a>
**Summary:** Non-Shallow copy
**Returns:**



### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.GridDat <a id="bosss.foundation.xdg.levelsettracker.levelsetregions.griddat"></a>
**Summary:** Link to the underlying background grid of the XDG discretization.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.AllFARplus <a id="bosss.foundation.xdg.levelsettracker.allfarplus"></a>
**Summary:** Region code (see [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetRegions](#bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetregions)) indicating that all level set values in a cell are in
the positive far region


### Field: BoSSS.Foundation.XDG.LevelSetTracker.AllFARminus <a id="bosss.foundation.xdg.levelsettracker.allfarminus"></a>
**Summary:** Region code (see [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetRegions](#bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetregions)) indicating that all level set values in a cell are in
the negative far region


### Field: BoSSS.Foundation.XDG.LevelSetTracker.AllCut <a id="bosss.foundation.xdg.levelsettracker.allcut"></a>
**Summary:** Region code (see [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetRegions](#bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetregions)) indicating that all level sets cut the actual cell


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesTable(System.String,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getspeciestable(system.string,system.int32)"></a>
**Summary:** computes the species table array from a code string;
- E.g., for a single level-set, the code `-:A +:B` means: species A in negative domain, species B in positive domain
- for


## Method: BoSSS.Foundation.XDG.LevelSetTracker.#ctor(BoSSS.Foundation.XDG.LevelSet,System.String,BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.#ctor(bosss.foundation.xdg.levelset,system.string,bosss.foundation.xdg.cutcellquadraturemethod,system.int32)"></a>
**Summary:** Creates a level set tracker for just one level set.
**Parameter:** `SpeciesTableCode` - The species table, see [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable);
**Parameter:** `levSet1` - 
**Parameter:** `__NearRegionWidth` - width of near region, in number of cells
**Parameter:** `cutCellquadType` - the type of integration in cut-cells; if more than one type is required within a single application, two [BoSSS.Foundation.XDG.LevelSetTracker](#bosss.foundation.xdg.levelsettracker)'s should be used.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.#ctor(BoSSS.Foundation.Grid.Classic.GridData,BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32,System.String[],BoSSS.Foundation.XDG.ILevelSet) <a id="bosss.foundation.xdg.levelsettracker.#ctor(bosss.foundation.grid.classic.griddata,bosss.foundation.xdg.cutcellquadraturemethod,system.int32,system.string[],bosss.foundation.xdg.ilevelset)"></a>
**Summary:** Creates a level set tracker for just one level set.
**Parameter:** `BackgroundGrid` - 
**Parameter:** `_SpeciesTable` - The species table, see [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable);
**Parameter:** `levSet1` - 
**Parameter:** `__NearRegionWidth` - width of near region, in number of cells
**Parameter:** `cutCellquadType` - the type of integration in cut-cells; if more than one type is required within a single application, two [BoSSS.Foundation.XDG.LevelSetTracker](#bosss.foundation.xdg.levelsettracker)'s should be used.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.#ctor(BoSSS.Foundation.Grid.Classic.GridData,BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32,System.String[0:,0:],BoSSS.Foundation.XDG.ILevelSet,BoSSS.Foundation.XDG.ILevelSet) <a id="bosss.foundation.xdg.levelsettracker.#ctor(bosss.foundation.grid.classic.griddata,bosss.foundation.xdg.cutcellquadraturemethod,system.int32,system.string[0:,0:],bosss.foundation.xdg.ilevelset,bosss.foundation.xdg.ilevelset)"></a>
**Summary:** Creates a level set tracker for two level sets.
**Parameter:** `BackgroundGrid` - 
**Parameter:** `_SpeciesTable` - The species table, see [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable);
**Parameter:** `levSet1` - 
**Parameter:** `levSet2` - 
**Parameter:** `__NearRegionWidth` - width of near region, in number of cells
**Parameter:** `cutCellquadType` - the type of integration in cut-cells; if more than one type is required within a single application, two [BoSSS.Foundation.XDG.LevelSetTracker](#bosss.foundation.xdg.levelsettracker)'s should be used.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.#ctor(BoSSS.Foundation.Grid.Classic.GridData,BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32,System.String[0:,0:,0:],BoSSS.Foundation.XDG.ILevelSet,BoSSS.Foundation.XDG.ILevelSet,BoSSS.Foundation.XDG.ILevelSet) <a id="bosss.foundation.xdg.levelsettracker.#ctor(bosss.foundation.grid.classic.griddata,bosss.foundation.xdg.cutcellquadraturemethod,system.int32,system.string[0:,0:,0:],bosss.foundation.xdg.ilevelset,bosss.foundation.xdg.ilevelset,bosss.foundation.xdg.ilevelset)"></a>
**Summary:** Creates a level set tracker for three level sets.
**Parameter:** `BackgroundGrid` - 
**Parameter:** `_SpeciesTable` - The species table, see [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable);
**Parameter:** `levSet1` - 
**Parameter:** `levSet2` - 
**Parameter:** `levSet3` - 
**Parameter:** `__NearRegionWidth` - width of near region, in number of cells
**Parameter:** `cutCellquadType` - the type of integration in cut-cells; if more than one type is required within a single application, two [BoSSS.Foundation.XDG.LevelSetTracker](#bosss.foundation.xdg.levelsettracker)'s should be used.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.#ctor(BoSSS.Foundation.Grid.Classic.GridData,BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32,System.String[0:,0:,0:,0:],BoSSS.Foundation.XDG.ILevelSet,BoSSS.Foundation.XDG.ILevelSet,BoSSS.Foundation.XDG.ILevelSet,BoSSS.Foundation.XDG.ILevelSet) <a id="bosss.foundation.xdg.levelsettracker.#ctor(bosss.foundation.grid.classic.griddata,bosss.foundation.xdg.cutcellquadraturemethod,system.int32,system.string[0:,0:,0:,0:],bosss.foundation.xdg.ilevelset,bosss.foundation.xdg.ilevelset,bosss.foundation.xdg.ilevelset,bosss.foundation.xdg.ilevelset)"></a>
**Summary:** Creates a level set tracker for four level sets.
**Parameter:** `BackgroundGrid` - 
**Parameter:** `_SpeciesTable` - The species table, see [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable);
**Parameter:** `levSet1` - 
**Parameter:** `levSet2` - 
**Parameter:** `levSet3` - 
**Parameter:** `levSet4` - 
**Parameter:** `__NearRegionWidth` - width of near region, in number of cells
**Parameter:** `cutCellquadType` - the type of integration in cut-cells; if more than one type is required within a single application, two [BoSSS.Foundation.XDG.LevelSetTracker](#bosss.foundation.xdg.levelsettracker)'s should be used.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.#ctor(BoSSS.Foundation.Grid.Classic.GridData,BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32,System.Array,BoSSS.Foundation.XDG.ILevelSet[]) <a id="bosss.foundation.xdg.levelsettracker.#ctor(bosss.foundation.grid.classic.griddata,bosss.foundation.xdg.cutcellquadraturemethod,system.int32,system.array,bosss.foundation.xdg.ilevelset[])"></a>
**Parameter:** `BackgroundGrid` - 
**Parameter:** `__NearRegionWidth` - 
**Parameter:** `SpeciesTable` - 
**Parameter:** `levSets` - 
**Parameter:** `cutCellquadType` - the type of integration in cut-cells; if more than one type is required within a single application, two [BoSSS.Foundation.XDG.LevelSetTracker](#bosss.foundation.xdg.levelsettracker)'s should be used.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.IncreaseHistoryLength(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.increasehistorylength(system.int32)"></a>
**Summary:** Increases [BoSSS.Foundation.XDG.LevelSetTracker.HistoryLength](#bosss.foundation.xdg.levelsettracker.historylength) to 'ReqLeng', if the latter is smaller.
**Parameter:** `ReqLeng` - The requested length
**Returns:**
the actual value of [BoSSS.Foundation.XDG.LevelSetTracker.HistoryLength](#bosss.foundation.xdg.levelsettracker.historylength)


### Property: BoSSS.Foundation.XDG.LevelSetTracker.HistoryLength <a id="bosss.foundation.xdg.levelsettracker.historylength"></a>
**Summary:** Number of previous states in the various history stacks ([BoSSS.Foundation.XDG.LevelSetTracker.DataHistories](#bosss.foundation.xdg.levelsettracker.datahistories), [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetHistories](#bosss.foundation.xdg.levelsettracker.levelsethistories), [BoSSS.Foundation.XDG.LevelSetTracker.RegionsHistory](#bosss.foundation.xdg.levelsettracker.regionshistory), etc.).


### Property: BoSSS.Foundation.XDG.LevelSetTracker.PopulatedHistoryIndices <a id="bosss.foundation.xdg.levelsettracker.populatedhistoryindices"></a>
**Summary:** indexes of all available times, i.e. all valid indexes to access any [BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1](#bosss.foundation.xdg.levelsettracker.historystack`1)


### Property: BoSSS.Foundation.XDG.LevelSetTracker.PushCount <a id="bosss.foundation.xdg.levelsettracker.pushcount"></a>
**Summary:** Number of times [BoSSS.Foundation.XDG.LevelSetTracker.PushStacks](#bosss.foundation.xdg.levelsettracker.pushstacks) was called;


### Property: BoSSS.Foundation.XDG.LevelSetTracker.PopulatedHistoryLength <a id="bosss.foundation.xdg.levelsettracker.populatedhistorylength"></a>
**Summary:** The number of previous time-steps available in the various stacks, see also [BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.GetPopulatedLength](#bosss.foundation.xdg.levelsettracker.historystack`1.getpopulatedlength).


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ConstructorCommon(BoSSS.Foundation.Grid.Classic.GridData,System.Int32,System.Array,BoSSS.Foundation.XDG.CutCellQuadratureMethod,BoSSS.Foundation.XDG.ILevelSet[]) <a id="bosss.foundation.xdg.levelsettracker.constructorcommon(bosss.foundation.grid.classic.griddata,system.int32,system.array,bosss.foundation.xdg.cutcellquadraturemethod,bosss.foundation.xdg.ilevelset[])"></a>
**Summary:** Implementation of the constructor;


### Property: BoSSS.Foundation.XDG.LevelSetTracker.CutCellQuadratureType <a id="bosss.foundation.xdg.levelsettracker.cutcellquadraturetype"></a>
**Summary:** The type of integration used in cut cells.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.m_GhostTable <a id="bosss.foundation.xdg.levelsettracker.m_ghosttable"></a>
**Summary:** used by [BoSSS.Foundation.XDG.LevelSetTracker.ContainesSpecies(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.LevelsetCellSignCode)](#bosss.foundation.xdg.levelsettracker.containesspecies(bosss.foundation.xdg.speciesid,bosss.foundation.xdg.levelsetcellsigncode));
- 1st index: ID: Species Id minus **BoSSS.Foundation.XDG.LevelSetTracker.___SpeciesIDOffest**;
- 2nd index: SIGN: [BoSSS.Foundation.XDG.LevelsetCellSignCode.lsSig](#bosss.foundation.xdg.levelsetcellsigncode.lssig);
Content: true, if species with given ID is contained in a cell with level set sign code SIGN;


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ComputeGhostTable <a id="bosss.foundation.xdg.levelsettracker.computeghosttable"></a>
**Summary:** initializes [BoSSS.Foundation.XDG.LevelSetTracker.m_GhostTable](#bosss.foundation.xdg.levelsettracker.m_ghosttable)


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ContainesSpecies(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.LevelsetCellSignCode) <a id="bosss.foundation.xdg.levelsettracker.containesspecies(bosss.foundation.xdg.speciesid,bosss.foundation.xdg.levelsetcellsigncode)"></a>
**Summary:** Detects whether a species is present in some cell
**Parameter:** `id` - species id;
**Parameter:** `cd` - acquire by [BoSSS.Foundation.XDG.LevelsetCellSignCode.Extract(System.UInt16)](#bosss.foundation.xdg.levelsetcellsigncode.extract(system.uint16));
**Returns:**
true, if species with given 'id' is contained in a cell with level set sign code 
'cd'; Not that, if the return value is false, the cell still may have DOF allocated
for the species;


## Method: BoSSS.Foundation.XDG.LevelSetTracker.CollectSpeciesNamesRecursive(System.Int32,System.Int32[]) <a id="bosss.foundation.xdg.levelsettracker.collectspeciesnamesrecursive(system.int32,system.int32[])"></a>
**Summary:** initializes **BoSSS.Foundation.XDG.LevelSetTracker.m_SpeciesNames**
**Parameter:** `recdeph` - 
**Parameter:** `indices` - 


## Method: BoSSS.Foundation.XDG.LevelSetTracker.CollectPossibleSpecies(BoSSS.Foundation.XDG.ReducedRegionCode) <a id="bosss.foundation.xdg.levelsettracker.collectpossiblespecies(bosss.foundation.xdg.reducedregioncode)"></a>
**Summary:** returns a collection of all species (identified by their names) which can 
possibly occur in a cell with 'ReducedRegionCode'
**Parameter:** `ReducedRegionCode` - the reduced region code ([BoSSS.Foundation.XDG.ReducedRegionCode.Extract(System.UInt16)](#bosss.foundation.xdg.reducedregioncode.extract(system.uint16)));
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.CollectPossibleSpecies(BoSSS.Foundation.XDG.LevelsetSign[]) <a id="bosss.foundation.xdg.levelsettracker.collectpossiblespecies(bosss.foundation.xdg.levelsetsign[])"></a>
**Summary:** collects the names of species that can occur in a cell
**Parameter:** `LevSetSigns` - 
**Returns:**
a collection containing the names of all species that can occur in a cell
with level sets with signs 'LevSetSigns';


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ComputeNoOfSpeciesRecursive(System.Int32,System.Int32[]) <a id="bosss.foundation.xdg.levelsettracker.computenoofspeciesrecursive(system.int32,system.int32[])"></a>
**Summary:** for each (reduced) region code, this method
computes the possible number of species in that cell ([BoSSS.Foundation.XDG.LevelSetTracker.m_NoOfSpecies](#bosss.foundation.xdg.levelsettracker.m_noofspecies))
and assigned
**Parameter:** `recdeph` - 
**Parameter:** `ReducedRegionSign` - 


### Property: BoSSS.Foundation.XDG.LevelSetTracker.SpeciesNames <a id="bosss.foundation.xdg.levelsettracker.speciesnames"></a>
**Summary:** The set of all species names tracked by this object.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.SpeciesIdS <a id="bosss.foundation.xdg.levelsettracker.speciesids"></a>
**Summary:** The set of all species id's tracked by this object.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.TotalNoOfSpecies <a id="bosss.foundation.xdg.levelsettracker.totalnoofspecies"></a>
**Summary:** the number of all different species;


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesName(BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.levelsettracker.getspeciesname(bosss.foundation.xdg.speciesid)"></a>
**Summary:** returns the name of the species with ID-number 'SpeciesId';
**Parameter:** `SpeciesId` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesId(System.String) <a id="bosss.foundation.xdg.levelsettracker.getspeciesid(system.string)"></a>
**Summary:** returns the ID-number which the level set tracker (this object) 
has assigned to the species with name 'species'.
**Parameter:** `species` - 
**Returns:**
species ID-number


### Field: BoSSS.Foundation.XDG.LevelSetTracker.m_SpeciesTable <a id="bosss.foundation.xdg.levelsettracker.m_speciestable"></a>
**Summary:** see [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable)


### Property: BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable <a id="bosss.foundation.xdg.levelsettracker.speciestable"></a>
**Summary:** Gets a copy of the species table, a multidimensional string-array.

The species table defines, which species corresponds with 
which combination of level set - signs.
**Remark:**
The rank (number of dimensions) of this array is equal to the number of level-sets ([BoSSS.Foundation.XDG.LevelSetTracker.LevelSets](#bosss.foundation.xdg.levelsettracker.levelsets)).
Valid indices are only 0 and 1, 0 corresponds to a negative sign an 1 to the positive sign.
E.g. if there are two level sets G1 and G1
and for some point in space, their sign is -1 and 1, than the species 
at this point is identified by entry [0,1].


### Property: BoSSS.Foundation.XDG.LevelSetTracker.RegionsHistory <a id="bosss.foundation.xdg.levelsettracker.regionshistory"></a>
**Summary:** Information about the level set sign for current and previous states (see [BoSSS.Foundation.XDG.LevelSetTracker.PushStacks](#bosss.foundation.xdg.levelsettracker.pushstacks)).


### Property: BoSSS.Foundation.XDG.LevelSetTracker.TimeLevelsInStack <a id="bosss.foundation.xdg.levelsettracker.timelevelsinstack"></a>
**Summary:** Returns all [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.Time](#bosss.foundation.xdg.levelsettracker.levelsetregions.time) entries in the [BoSSS.Foundation.XDG.LevelSetTracker.RegionsHistory](#bosss.foundation.xdg.levelsettracker.regionshistory) stack.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.Regions <a id="bosss.foundation.xdg.levelsettracker.regions"></a>
**Summary:** Information about the current level set sign in each cell.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpecies(BoSSS.Foundation.XDG.LevelSetSignCode) <a id="bosss.foundation.xdg.levelsettracker.getspecies(bosss.foundation.xdg.levelsetsigncode)"></a>
**Parameter:** `LevSetSignCode` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesSeparatedByLevSet(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getspeciesseparatedbylevset(system.int32)"></a>
**Summary:** Returns the species that are speratated by Level Set 'levSetIdx', as defined in [BoSSS.Foundation.XDG.LevelSetTracker.m_SpeciesTable](#bosss.foundation.xdg.levelsettracker.m_speciestable).
**Parameter:** `levSetIdx` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesPairsSeparatedByLevSet(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getspeciespairsseparatedbylevset(system.int32)"></a>
**Summary:** Returns the species that are speratated by Level Set 'levSetIdx', as defined in [BoSSS.Foundation.XDG.LevelSetTracker.m_SpeciesTable](#bosss.foundation.xdg.levelsettracker.m_speciestable).
**Parameter:** `levSetIdx` - 
**Returns:**
Species Pair. First species is negative species, second species is positive species.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.FindSeparatedSpeciesPairs(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.findseparatedspeciespairs(system.int32)"></a>
**Summary:** Returns species that are separated by levelSet with No. 'levSetIdx'


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesIdFromSign(System.Double[]) <a id="bosss.foundation.xdg.levelsettracker.getspeciesidfromsign(system.double[])"></a>
**Summary:** computes the id of the species that is set for a specific sign
**Parameter:** `levelSetValues` - signs of all level set functions
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetLevelSetSignCodes(System.String) <a id="bosss.foundation.xdg.levelsettracker.getlevelsetsigncodes(system.string)"></a>
**Summary:** Determines all sign codes (i.e. level set sign combinations, see
[BoSSS.Foundation.XDG.LevelSetTracker.GetSpecies(BoSSS.Foundation.XDG.LevelSetSignCode)](#bosss.foundation.xdg.levelsettracker.getspecies(bosss.foundation.xdg.levelsetsigncode))) in [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable) that
identify a given species with name 'species'

Consider two level sets "Phi_0" and "Phi_1" (with level set indices 0 and
1, respectively) and three species "a", "b" and "c". Consider the
following [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable):
[0, 0] = "a"
[0, 1] = "b"
[1, 0] = "c"
[1, 1] = "c"
That is, if "Phi_0" and "Phi_1" are both negative, we have species "a". If
"Phi_0" is negative and "Phi_1" is positive, we have "b". If "Phi_0" is
positive, we have "c", irrespective of the value of "Phi_1". Thus,
there are two sign combinations for "c" (namely [+,-] and [+,+]).
This translates to the sign codes 1 and 3 and the return value
would be [1, 3] in such a case.
**Parameter:** `species` - The considered species
**Returns:**
A list of sign codes identifying 'species'


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetLevelSetSignCodes(BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.levelsettracker.getlevelsetsigncodes(bosss.foundation.xdg.speciesid)"></a>
**Summary:** see [BoSSS.Foundation.XDG.LevelSetTracker.GetLevelSetSignCodes(System.String)](#bosss.foundation.xdg.levelsettracker.getlevelsetsigncodes(system.string))


### Property: BoSSS.Foundation.XDG.LevelSetTracker.NearRegionWidth <a id="bosss.foundation.xdg.levelsettracker.nearregionwidth"></a>
**Summary:** Width, in Number of cells, of the near field (set as an argument of [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[])));


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetHistories <a id="bosss.foundation.xdg.levelsettracker.levelsethistories"></a>
**Summary:** The level sets stack;
- 1st index: index of level-set
- 2nd index: index into stack


## Method: BoSSS.Foundation.XDG.LevelSetTracker.PushStacks <a id="bosss.foundation.xdg.levelsettracker.pushstacks"></a>
**Summary:** Advances the history stacks which store previous states of the level-set tracker
(see [BoSSS.Foundation.XDG.LevelSetTracker.DataHistories](#bosss.foundation.xdg.levelsettracker.datahistories), [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetHistories](#bosss.foundation.xdg.levelsettracker.levelsethistories), [BoSSS.Foundation.XDG.LevelSetTracker.RegionsHistory](#bosss.foundation.xdg.levelsettracker.regionshistory), etc.).


## Method: BoSSS.Foundation.XDG.LevelSetTracker.PopStacks <a id="bosss.foundation.xdg.levelsettracker.popstacks"></a>
**Summary:** throws away the top of the history, reverts to the latest pushed state ([BoSSS.Foundation.XDG.LevelSetTracker.PushStacks](#bosss.foundation.xdg.levelsettracker.pushstacks),
see also [BoSSS.Foundation.XDG.LevelSetTracker.DataHistories](#bosss.foundation.xdg.levelsettracker.datahistories), [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetHistories](#bosss.foundation.xdg.levelsettracker.levelsethistories), [BoSSS.Foundation.XDG.LevelSetTracker.RegionsHistory](#bosss.foundation.xdg.levelsettracker.regionshistory), etc.).

The top state of the stack can also be back-upped/resored by
- [BoSSS.Foundation.XDG.LevelSetTracker.BackupTimeLevel(System.Int32)](#bosss.foundation.xdg.levelsettracker.backuptimelevel(system.int32))
- [BoSSS.Foundation.XDG.LevelSetTracker.ReplaceCurrentTimeLevel(BoSSS.Foundation.XDG.LevelSetTracker.TrackerBackup)](#bosss.foundation.xdg.levelsettracker.replacecurrenttimelevel(bosss.foundation.xdg.levelsettracker.trackerbackup))


### Property: BoSSS.Foundation.XDG.LevelSetTracker.NoOfLevelSets <a id="bosss.foundation.xdg.levelsettracker.nooflevelsets"></a>
**Summary:** Number of used level-sets fields, between 1 and 4.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSets <a id="bosss.foundation.xdg.levelsettracker.levelsets"></a>
**Summary:** The level sets, identical to the top of the level-set stack ([BoSSS.Foundation.XDG.LevelSetTracker.LevelSetHistories](#bosss.foundation.xdg.levelsettracker.levelsethistories))
- 1st index: index of level-set


### Property: BoSSS.Foundation.XDG.LevelSetTracker.GridDat <a id="bosss.foundation.xdg.levelsettracker.griddat"></a>
**Summary:** Reference to the background grid of the XDG space.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetNoOfSpeciesByRegionCode(System.UInt16,BoSSS.Foundation.XDG.ReducedRegionCode@) <a id="bosss.foundation.xdg.levelsettracker.getnoofspeciesbyregioncode(system.uint16,bosss.foundation.xdg.reducedregioncode@)"></a>
**Summary:** returns the (possible) number of species in 
a cell with region code 'RegionCode'.
**Parameter:** `RegionCode` - region code for the cell;
**Parameter:** `_ReducedRegionCode` - on exit, the reduced region code for 'RegionCode'
in an 3-adic representation; This number 
is later on required as an input for
[BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesIndex(BoSSS.Foundation.XDG.ReducedRegionCode,BoSSS.Foundation.XDG.SpeciesId)](#bosss.foundation.xdg.levelsettracker.getspeciesindex(bosss.foundation.xdg.reducedregioncode,bosss.foundation.xdg.speciesid));
The reduced region code in 3-adic representation;
**Returns:**

**Remark:**
Here, three states (the reduced region) for each of the for level sets are considered:
- positive far (FAR+)
- negative far (FAR-)
- positive near, negative near or cut
This implies, that also for cells in the near region, memory is allocated for more than one
species.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.m_NoOfSpecies <a id="bosss.foundation.xdg.levelsettracker.m_noofspecies"></a>
**Summary:** Number of species, for each reduced region code;
**Remark:**
This array, which contains exactly 34 = 81 entries, stores the number of
species for each possible combination of level sets; 
For each level set, in each cell, we distinct between three different states:
- the cell if in the positive FAR region: distance == 7, i.e. the code is 0xf
- the cell if in the negative FAR region: distance == -1, i.e the code is 0x1
- the cell is cut or in the near region: -6 < distance < 6
So, there are in total 3*4 states for some cell (for 4 level sets);


### Field: BoSSS.Foundation.XDG.LevelSetTracker.m_SpeciesIndex <a id="bosss.foundation.xdg.levelsettracker.m_speciesindex"></a>
**Summary:** - There are 3 states for each level-set in each cell: completely positive, completely negative or cut;
- Considering at max. 4 level-sets, this leads to 34 = 81 different states.
- For the sign of all 4 level-sets, there are 24 = 16 different states.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.SetNumSpecies(System.Int32,System.Int32[],BoSSS.Foundation.XDG.ReducedRegionCode@) <a id="bosss.foundation.xdg.levelsettracker.setnumspecies(system.int32,system.int32[],bosss.foundation.xdg.reducedregioncode@)"></a>
**Parameter:** `NumSpecies` - 
**Parameter:** `ReducedRegionSign` - Signs of the of reduced region, for each level set, i.e.

positive: the cell is in the positive FAR region
negative: the cell is in the negative FAR region
0: the cell is cut or in the positive or negative near region;
**Parameter:** `_ReducedRegionCode` - on exit, the reduced region code for 'ReducedRegionSign'


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesIndex(BoSSS.Foundation.XDG.ReducedRegionCode,BoSSS.Foundation.XDG.LevelSetSignCode) <a id="bosss.foundation.xdg.levelsettracker.getspeciesindex(bosss.foundation.xdg.reducedregioncode,bosss.foundation.xdg.levelsetsigncode)"></a>
**Summary:** the index of some species, with level set signs 'LevelSetSignBytecode'
and the region 'rrc'.
**Parameter:** `rrc` - the value returned by the 2nd parameter of [BoSSS.Foundation.XDG.LevelSetTracker.GetNoOfSpeciesByRegionCode(System.UInt16,BoSSS.Foundation.XDG.ReducedRegionCode@)](#bosss.foundation.xdg.levelsettracker.getnoofspeciesbyregioncode(system.uint16,bosss.foundation.xdg.reducedregioncode@));
**Parameter:** `LevelSetSignBytecode` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesIdFromIndex(BoSSS.Foundation.XDG.ReducedRegionCode,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getspeciesidfromindex(bosss.foundation.xdg.reducedregioncode,system.int32)"></a>
**Summary:** this function is the inverse to [BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesIndex(BoSSS.Foundation.XDG.ReducedRegionCode,BoSSS.Foundation.XDG.LevelSetSignCode)](#bosss.foundation.xdg.levelsettracker.getspeciesindex(bosss.foundation.xdg.reducedregioncode,bosss.foundation.xdg.levelsetsigncode));
**Parameter:** `_ReducedRegionCode` - the value returned by the 2nd parameter of [BoSSS.Foundation.XDG.LevelSetTracker.GetNoOfSpeciesByRegionCode(System.UInt16,BoSSS.Foundation.XDG.ReducedRegionCode@)](#bosss.foundation.xdg.levelsettracker.getnoofspeciesbyregioncode(system.uint16,bosss.foundation.xdg.reducedregioncode@));
**Parameter:** `SpeciesIndex` - 
**Returns:**

**Remark:**
this function is the inverse to [BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesIdFromIndex(BoSSS.Foundation.XDG.ReducedRegionCode,System.Int32)](#bosss.foundation.xdg.levelsettracker.getspeciesidfromindex(bosss.foundation.xdg.reducedregioncode,system.int32))


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesIndex(BoSSS.Foundation.XDG.ReducedRegionCode,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.levelsettracker.getspeciesindex(bosss.foundation.xdg.reducedregioncode,bosss.foundation.xdg.speciesid)"></a>
**Summary:** converts a species id ('_SpeciesId') into a species index;
Note that the sorting of species is not constant (over the grid), so the return value
depends on the reduced region code '_ReducedRegionCode';
**Parameter:** `_ReducedRegionCode` - the value returned by the 2nd parameter of [BoSSS.Foundation.XDG.LevelSetTracker.GetNoOfSpeciesByRegionCode(System.UInt16,BoSSS.Foundation.XDG.ReducedRegionCode@)](#bosss.foundation.xdg.levelsettracker.getnoofspeciesbyregioncode(system.uint16,bosss.foundation.xdg.reducedregioncode@));
**Parameter:** `_SpeciesId` - 
**Returns:**
a negative value indicates that the species is not present within the given '_ReducedRegionCode';
**Remark:**
this function is the inverse to [BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesIdFromIndex(BoSSS.Foundation.XDG.ReducedRegionCode,System.Int32)](#bosss.foundation.xdg.levelsettracker.getspeciesidfromindex(bosss.foundation.xdg.reducedregioncode,system.int32))


## Method: BoSSS.Foundation.XDG.LevelSetTracker.DecodeLevelSetDist(System.UInt16,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.decodelevelsetdist(system.uint16,system.int32)"></a>
**Summary:** Extracts the distance layer index for level-set 'levSetInd'
from the code 'code' (see [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetRegions](#bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetregions)).
**Parameter:** `code` - 
**Parameter:** `levSetInd` - 
**Returns:**

**Remark:**
For some cell, the level set distance is 0 for all cells
which are cut by the level set.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.EncodeLevelSetDist(System.UInt16@,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.encodelevelsetdist(system.uint16@,system.int32,system.int32)"></a>
**Summary:** Encodes the distance layer index 'dist' for level-set 'levSetInd'
int the code 'code' ([BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetRegions](#bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetregions)).


### Field: BoSSS.Foundation.XDG.LevelSetTracker.TestNodes <a id="bosss.foundation.xdg.levelsettracker.testnodes"></a>
**Summary:** Node-set for determination of cut-cells (general version)
- index: reference element index
**Remark:**
Structured as follows:
- a set of quadrature nodes on each face
- nodes slightly exterior to the cell; 
Testing also sightly outside the cell is intended avoid missing a cut cell; this would be worse than a cut cell which is not cut.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.FaceNodes <a id="bosss.foundation.xdg.levelsettracker.facenodes"></a>
**Summary:** Node set for testing if the level-set coincides with a face or edge ([BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingfaces))
- index: reference element.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.TestNodes_QuadWeights <a id="bosss.foundation.xdg.levelsettracker.testnodes_quadweights"></a>
**Summary:** Quadrature weights 
- index: reference element index, correlates with 1st index of [BoSSS.Foundation.XDG.LevelSetTracker.TestNodes](#bosss.foundation.xdg.levelsettracker.testnodes)


### Field: BoSSS.Foundation.XDG.LevelSetTracker.NoOfTestNodesPerFace <a id="bosss.foundation.xdg.levelsettracker.nooftestnodesperface"></a>
**Summary:** Fore each node set in [BoSSS.Foundation.XDG.LevelSetTracker.TestNodes](#bosss.foundation.xdg.levelsettracker.testnodes), their correlation to the element faces
- 1st index: reference element index, correlates with 1st index of [BoSSS.Foundation.XDG.LevelSetTracker.TestNodes](#bosss.foundation.xdg.levelsettracker.testnodes)
- 2nd index: face index


### Field: BoSSS.Foundation.XDG.LevelSetTracker.NoOfTestNodesPerCoFace <a id="bosss.foundation.xdg.levelsettracker.nooftestnodespercoface"></a>
**Summary:** Fore each node set in [BoSSS.Foundation.XDG.LevelSetTracker.TestNodes](#bosss.foundation.xdg.levelsettracker.testnodes), their correlation to the element co-faces
- 1st index: reference element index, correlates with 1st index of [BoSSS.Foundation.XDG.LevelSetTracker.TestNodes](#bosss.foundation.xdg.levelsettracker.testnodes)
- 2nd index: co-face index


### Property: BoSSS.Foundation.XDG.LevelSetTracker.TestTransformer <a id="bosss.foundation.xdg.levelsettracker.testtransformer"></a>
**Summary:** Transformator for each level set to transform the Legendre coefficients to Bernstein coefficients
we then use there superior geometric properties to search for cut cells.
here the bernstein coefficients lie on a slight offset of the reference element


### Property: BoSSS.Foundation.XDG.LevelSetTracker.TestTransformerEdges <a id="bosss.foundation.xdg.levelsettracker.testtransformeredges"></a>
**Summary:** Transformator for each level set to transform the legendre coefficients to bernstein coefficients
we then use there superior geometric properties to search for cut cells.
here the bernstein coefficients lie exactly on the edges of the reference element


### Property: BoSSS.Foundation.XDG.LevelSetTracker.VersionCnt <a id="bosss.foundation.xdg.levelsettracker.versioncnt"></a>
**Summary:** a counter that is increased every time when [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[])) is called;


## Method: BoSSS.Foundation.XDG.LevelSetTracker.TestRegions <a id="bosss.foundation.xdg.levelsettracker.testregions"></a>
**Summary:** debug/test code


## Method: BoSSS.Foundation.XDG.LevelSetTracker.CheckLevelSetCFL(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.checklevelsetcfl(system.int32)"></a>
**Summary:** checks if the level set may has moved more than one cell

## Class: BoSSS.Foundation.XDG.LevelSetTracker.EssentialTrackerBackup <a id="bosss.foundation.xdg.levelsettracker.essentialtrackerbackup"></a>

**Summary:** The minimum amount of data required to restore the level-set-tracker state
**after mesh adaptation**


### Field: BoSSS.Foundation.XDG.LevelSetTracker.EssentialTrackerBackup.LevelSets <a id="bosss.foundation.xdg.levelsettracker.essentialtrackerbackup.levelsets"></a>
**Summary:** clone of the level-set fields, **BoSSS.Foundation.XDG.LevelSetTracker.m_LevelSetHistories**


### Field: BoSSS.Foundation.XDG.LevelSetTracker.EssentialTrackerBackup.Version <a id="bosss.foundation.xdg.levelsettracker.essentialtrackerbackup.version"></a>
**Summary:** level-set version index, [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.Version](#bosss.foundation.xdg.levelsettracker.levelsetregions.version)


### Field: BoSSS.Foundation.XDG.LevelSetTracker.EssentialTrackerBackup.time <a id="bosss.foundation.xdg.levelsettracker.essentialtrackerbackup.time"></a>
**Summary:** associated physical time, [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.Time](#bosss.foundation.xdg.levelsettracker.levelsetregions.time)

## Class: BoSSS.Foundation.XDG.LevelSetTracker.TrackerBackup <a id="bosss.foundation.xdg.levelsettracker.trackerbackup"></a>

**Summary:** Full backup of the tracker state at a respective time-step.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.TrackerBackup.Regions <a id="bosss.foundation.xdg.levelsettracker.trackerbackup.regions"></a>
**Summary:** backup of region code for each cell, [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.RegionsCode](#bosss.foundation.xdg.levelsettracker.levelsetregions.regionscode)


### Field: BoSSS.Foundation.XDG.LevelSetTracker.TrackerBackup.LevSetCoincidingFaces <a id="bosss.foundation.xdg.levelsettracker.trackerbackup.levsetcoincidingfaces"></a>
**Summary:** backup of [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetCoincidingFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetcoincidingfaces)


### Field: BoSSS.Foundation.XDG.LevelSetTracker.TrackerBackup.LevSetCoincidingCoFaces <a id="bosss.foundation.xdg.levelsettracker.trackerbackup.levsetcoincidingcofaces"></a>
**Summary:** backup of [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.m_LevSetCoincidingCoFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.m_levsetcoincidingcofaces)


## Method: BoSSS.Foundation.XDG.LevelSetTracker.TrackerBackup.Clone <a id="bosss.foundation.xdg.levelsettracker.trackerbackup.clone"></a>
**Summary:** non-shallow cloning


## Method: BoSSS.Foundation.XDG.LevelSetTracker.BackupTimeLevel(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.backuptimelevel(system.int32)"></a>
**Summary:** Backup of the internal state of the level-set tracker for a certain history stack index ('iHistory').
Not the entire state is backed up (cell masks, cut-cell quadrature rules, mass matrices, ..., are lost),
but everything essential to restore a certain state.
**Parameter:** `iHistory` - History stack index.
**Returns:**
Can be used as input for [BoSSS.Foundation.XDG.LevelSetTracker.ReplaceCurrentTimeLevel(BoSSS.Foundation.XDG.LevelSetTracker.TrackerBackup)](#bosss.foundation.xdg.levelsettracker.replacecurrenttimelevel(bosss.foundation.xdg.levelsettracker.trackerbackup)) or [BoSSS.Foundation.XDG.LevelSetTracker.ReplaceCurrentTimeLevel(BoSSS.Foundation.XDG.LevelSetTracker.EssentialTrackerBackup)](#bosss.foundation.xdg.levelsettracker.replacecurrenttimelevel(bosss.foundation.xdg.levelsettracker.essentialtrackerbackup)).


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ReplaceCurrentTimeLevel(BoSSS.Foundation.XDG.LevelSetTracker.EssentialTrackerBackup) <a id="bosss.foundation.xdg.levelsettracker.replacecurrenttimelevel(bosss.foundation.xdg.levelsettracker.essentialtrackerbackup)"></a>
**Summary:** Counterpart of [BoSSS.Foundation.XDG.LevelSetTracker.BackupTimeLevel(System.Int32)](#bosss.foundation.xdg.levelsettracker.backuptimelevel(system.int32)), 
but the region codes ([BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.RegionsCode](#bosss.foundation.xdg.levelsettracker.levelsetregions.regionscode)) are
re-computed by calling [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[])).
**Remark:**
Used for **mesh adaptation**,
i.e. when the mesh changes and region codes must be re-computed.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ReplaceCurrentTimeLevel(BoSSS.Foundation.XDG.LevelSetTracker.TrackerBackup) <a id="bosss.foundation.xdg.levelsettracker.replacecurrenttimelevel(bosss.foundation.xdg.levelsettracker.trackerbackup)"></a>
**Summary:** Counterpart of [BoSSS.Foundation.XDG.LevelSetTracker.BackupTimeLevel(System.Int32)](#bosss.foundation.xdg.levelsettracker.backuptimelevel(system.int32)), using the full backup.
**Parameter:** `fullBackup` - 
**Remark:**
Used for **mesh redistribution**  (MPI load balancing)
i.e. when the mesh remains essentially constant, but the (global and local) indexing of cells changes.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ResetCurrentTimeLevel(System.Double) <a id="bosss.foundation.xdg.levelsettracker.resetcurrenttimelevel(system.double)"></a>
**Summary:** used for cleaning up the current timestep when loading a restart
**Parameter:** `PhysTime` - 


## Method: BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[]) <a id="bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[])"></a>
**Summary:** Must be called after changing the level-set;
Invoking this method updates the state of cells (e.g. cut, -near, +near, etc.), [BoSSS.Foundation.XDG.LevelSetTracker.Regions](#bosss.foundation.xdg.levelsettracker.regions).
After this update, for every [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield) the method [BoSSS.Foundation.XDG.XDGField.OnNext(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions)](#bosss.foundation.xdg.xdgfield.onnext(bosss.foundation.xdg.levelsettracker.levelsetregions)) must be invoked;
**Parameter:** `__NearRegionWith` - new width of near region; if smaller than 0, unchanged
**Parameter:** `__LevSetAllowedMovement` - new values for the allowed level-set movement.
If this value is set to a number higher than the [BoSSS.Foundation.XDG.LevelSetTracker.NearRegionWidth](#bosss.foundation.xdg.levelsettracker.nearregionwidth), the CFL test for the 
corresponding 
level set is omitted.
**Parameter:** `incremental` - If true, the distance of near-cells can only increase by one.
E.g., if the level-set leaves the domain, setting this parameter to true ensures that the respective 
boundary cells are treated as near-cells for one 
[BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[]))-cycle.
This maintains a 'correct' near field when level-set leaves domain, which is necessary e.g. for operator matrix update.

Furthermore, it speeds up the detection of cut cells: the detection of cut cells is limited to the near-region,
which drastically reduces the amount of level-set evaluations.

Also, detection of topology changes/collisions *require* incremental update set to true.
**Parameter:** `PhysTime` - physical time associated with current Level Set state, see [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.Time](#bosss.foundation.xdg.levelsettracker.levelsetregions.time)


## Method: BoSSS.Foundation.XDG.LevelSetTracker.Invalidate <a id="bosss.foundation.xdg.levelsettracker.invalidate"></a>
**Summary:** Clears all internal references for this object, to make sure that any attempt to use it leads to an exception.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ObserverUpdate(System.Nullable{BoSSS.Foundation.XDG.BehaveUnder_LevSetMoovement}) <a id="bosss.foundation.xdg.levelsettracker.observerupdate(system.nullable{bosss.foundation.xdg.behaveunder_levsetmoovement})"></a>
**Summary:** Calls the **System.IObserver`1.OnNext(`0)** for all observers.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.ObserverHack <a id="bosss.foundation.xdg.levelsettracker.observerhack"></a>
**Summary:** Dirty Hack to support dynamic load balancing,
Calls the **System.IObserver`1.OnNext(`0)** for all observers


### Field: BoSSS.Foundation.XDG.LevelSetTracker.m_Observers <a id="bosss.foundation.xdg.levelsettracker.m_observers"></a>
**Summary:** See [BoSSS.Foundation.XDG.LevelSetTracker.Subscribe(System.IObserver{BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions})](#bosss.foundation.xdg.levelsettracker.subscribe(system.iobserver{bosss.foundation.xdg.levelsettracker.levelsetregions}));


## Method: BoSSS.Foundation.XDG.LevelSetTracker.Subscribe(System.IObserver{BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions}) <a id="bosss.foundation.xdg.levelsettracker.subscribe(system.iobserver{bosss.foundation.xdg.levelsettracker.levelsetregions})"></a>
**Summary:** At construction time, objects may register themselves at the level
set tracker in order to be updated when the level set information
changes.
**Parameter:** `observer` - The observer that wants to register.
**Remark:**
The reference to the subscribed will be "weak" (see
[BoSSS.Platform.WeakReference`1](BoSSS.Platform.md#bosss.platform.weakreference`1)) so that garbage collection will not
be affected by the subscription.

## Class: BoSSS.Foundation.XDG.LevelSetTracker.Unsubscriber <a id="bosss.foundation.xdg.levelsettracker.unsubscriber"></a>

**Summary:** Unsubscriber for objects that have subscribed to objects this
object through [BoSSS.Foundation.XDG.LevelSetTracker.Subscribe(System.IObserver{BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions})](#bosss.foundation.xdg.levelsettracker.subscribe(system.iobserver{bosss.foundation.xdg.levelsettracker.levelsetregions})).


### Field: BoSSS.Foundation.XDG.LevelSetTracker.Unsubscriber.owner <a id="bosss.foundation.xdg.levelsettracker.unsubscriber.owner"></a>
**Summary:** The creator of this object.


### Field: BoSSS.Foundation.XDG.LevelSetTracker.Unsubscriber.observer <a id="bosss.foundation.xdg.levelsettracker.unsubscriber.observer"></a>
**Summary:** The observer that may want to unregister itself.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.Unsubscriber.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Platform.WeakReference{System.IObserver{BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions}}) <a id="bosss.foundation.xdg.levelsettracker.unsubscriber.#ctor(bosss.foundation.xdg.levelsettracker,bosss.platform.weakreference{system.iobserver{bosss.foundation.xdg.levelsettracker.levelsetregions}})"></a>
**Summary:** Creates a new unsubscriber.
**Parameter:** `owner` - The creator of this object.
**Parameter:** `observer` - The observer that may want to unregister itself.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.Unsubscriber.Dispose <a id="bosss.foundation.xdg.levelsettracker.unsubscriber.dispose"></a>
**Summary:** Removes the given observer from the list of registered
observers of the observed object.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.Dispose <a id="bosss.foundation.xdg.levelsettracker.dispose"></a>
**Summary:** Disposes the references to all registered observers (see
[BoSSS.Foundation.XDG.LevelSetTracker.Subscribe(System.IObserver{BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions})](#bosss.foundation.xdg.levelsettracker.subscribe(system.iobserver{bosss.foundation.xdg.levelsettracker.levelsetregions})))


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetXQuadFactoryHelper(BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getxquadfactoryhelper(bosss.foundation.xdg.cutcellquadraturemethod,system.int32)"></a>
**Summary:** Central 'factory' for creating Level Set - related quadrature.
**Remark:**
The centralized approach should avoid multiple creation of the same quadrature rule.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetCachedOrders(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getcachedorders(system.int32)"></a>
**Summary:** The order of all cut-cell quadrature rules which are present in the cache.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetXDGSpaceMetrics(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getxdgspacemetrics(system.int32)"></a>
**Summary:** Cut Cell and Cut Edge metrics before agglomeration


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetXDGSpaceMetrics(BoSSS.Foundation.XDG.SpeciesId,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getxdgspacemetrics(bosss.foundation.xdg.speciesid,system.int32,system.int32)"></a>
**Summary:** Cut Cell and Cut Edge metrics before agglomeration


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetXDGSpaceMetrics(System.Collections.Generic.IEnumerable{BoSSS.Foundation.XDG.SpeciesId},System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.getxdgspacemetrics(system.collections.generic.ienumerable{bosss.foundation.xdg.speciesid},system.int32,system.int32)"></a>
**Summary:** Cut Cell and Cut Edge metrics before agglomeration


## Method: BoSSS.Foundation.XDG.LevelSetTracker.GetAgglomerator(BoSSS.Foundation.XDG.SpeciesId[],System.Int32,System.Double,System.Boolean,System.Boolean,System.Boolean,System.Double[],System.Double,System.String) <a id="bosss.foundation.xdg.levelsettracker.getagglomerator(bosss.foundation.xdg.speciesid[],system.int32,system.double,system.boolean,system.boolean,system.boolean,system.double[],system.double,system.string)"></a>
**Parameter:** `Spc` - all species, for which agglomeration should be performed
**Parameter:** `CutCellsQuadOrder` - cut-cell quadrature order for the quadrature rule that is used to determine cell volumes;
this should typically be the same order which is used to evaluate the XDG operator matrix.
**Parameter:** `__AgglomerationTreshold` - Volume fraction, which triggers cell agglomeration;
see [BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.AgglomerationThreshold](#bosss.foundation.xdg.multiphasecellagglomerator.agglomerationthreshold)
**Parameter:** `oldTs__AgglomerationTreshold` - Agglomeration thresholds for   _previous_ timesteps.
The number of entries in this array determines how many previous timesteps are considered
([BoSSS.Foundation.XDG.LevelSetTracker.HistoryLength](#bosss.foundation.xdg.levelsettracker.historylength)).
**Parameter:** `AgglomerateNewborn` - 'Newborn' cut-cells 
are agglomerated to cells which already exist in the previous  timestep.
**Parameter:** `AgglomerateDecased` - 'Deceased' cut-cells are agglomerated to cells which exist in the next timestep.
**Parameter:** `ExceptionOnFailedAgglomeration` - If true, an exception is thrown for 
any cell which should be agglomerated, if no neighbor is found.
**Parameter:** `NewbornAndDecasedThreshold` - Volume fraction threshold at which a cut-cell counts as newborn, resp. deceased, see 'AgglomerateNewborn', 'AgglomerateDecased';
**Parameter:** `Tag` - A string value to pass tags for debugs (e.g. LevelSetAgg)
**Returns:**


## Class: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1 <a id="bosss.foundation.xdg.levelsettracker.historystack`1"></a>

**Summary:** Base class for all types of histories,
i.e. scalar histories (constant in space)
and scalar- and vector-fields histories (not constant in space).


## Method: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.#ctor(`0) <a id="bosss.foundation.xdg.levelsettracker.historystack`1.#ctor(`0)"></a>
**Summary:** ctor


### Field: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.m_PushCount <a id="bosss.foundation.xdg.levelsettracker.historystack`1.m_pushcount"></a>
**Summary:** [BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.PushCount](#bosss.foundation.xdg.levelsettracker.historystack`1.pushcount)


### Property: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.PushCount <a id="bosss.foundation.xdg.levelsettracker.historystack`1.pushcount"></a>
**Summary:** Counts every call to [BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.Push(System.Func{`0,`0},System.Func{`0,`0,`0})](#bosss.foundation.xdg.levelsettracker.historystack`1.push(system.func{`0,`0},system.func{`0,`0,`0}))


### Field: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.m_Current <a id="bosss.foundation.xdg.levelsettracker.historystack`1.m_current"></a>
**Summary:** either a double for time-dependent scalars, which are constant in space (e.g. ambient pressure in Low-Mach solver)
or a [BoSSS.Foundation.DGField](BoSSS.Foundation.md#bosss.foundation.dgfield) or a [BoSSS.Foundation.VectorField`1](BoSSS.Foundation.md#bosss.foundation.vectorfield`1).


### Field: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.m_HistoryLength <a id="bosss.foundation.xdg.levelsettracker.historystack`1.m_historylength"></a>
**Summary:** see [BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.HistoryLength](#bosss.foundation.xdg.levelsettracker.historystack`1.historylength)


### Property: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.HistoryLength <a id="bosss.foundation.xdg.levelsettracker.historystack`1.historylength"></a>
**Summary:** the number of Timesteps that should stored in addition to the current one, at maximum, before elements are dropped.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.AvailableIndices <a id="bosss.foundation.xdg.levelsettracker.historystack`1.availableindices"></a>
**Summary:** 1 (including) to -[BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.GetPopulatedLength](#bosss.foundation.xdg.levelsettracker.historystack`1.getpopulatedlength) (including)


## Method: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.GetPopulatedLength <a id="bosss.foundation.xdg.levelsettracker.historystack`1.getpopulatedlength"></a>
**Summary:** returns the minimum of the two numbers:

number of [BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.Push(System.Func{`0,`0},System.Func{`0,`0,`0})](#bosss.foundation.xdg.levelsettracker.historystack`1.push(system.func{`0,`0},system.func{`0,`0,`0})) - operations carried out on this object
[BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.m_HistoryLength](#bosss.foundation.xdg.levelsettracker.historystack`1.m_historylength)

If this value is, e.g. 2, this means that timesteps 1, 0, -1 are available;
**Returns:**



### Property: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.PopulatedIndices <a id="bosss.foundation.xdg.levelsettracker.historystack`1.populatedindices"></a>
**Summary:** indexes of all available times, i.e. all valid indexes to access [BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.Item(System.Int32)](#bosss.foundation.xdg.levelsettracker.historystack`1.item(system.int32))


### Field: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.History <a id="bosss.foundation.xdg.levelsettracker.historystack`1.history"></a>
**Summary:** Sontainer for previous states.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.Push(System.Func{`0,`0},System.Func{`0,`0,`0}) <a id="bosss.foundation.xdg.levelsettracker.historystack`1.push(system.func{`0,`0},system.func{`0,`0,`0})"></a>
**Summary:** pushes a new variable set onto the top of the stack
**Remark:**
An example of the Push-operation, for [BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.HistoryLength](#bosss.foundation.xdg.levelsettracker.historystack`1.historylength)==3:


Timestep Index ->  1  0 -1 -2 
-----------------------------------
Before Push(..): | a  b  c  d 
| 
After Push(..):  | a  a  b  c


### Property: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.Item(System.Int32) <a id="bosss.foundation.xdg.levelsettracker.historystack`1.item(system.int32)"></a>
**Summary:** Gets access to previous (and actual) timesteps.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.HistoryStack`1.Current <a id="bosss.foundation.xdg.levelsettracker.historystack`1.current"></a>
**Summary:** The top item of the stack.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.DataHistories <a id="bosss.foundation.xdg.levelsettracker.datahistories"></a>
**Summary:** Stack for data of previous level-set states. 
- 1st index: level-set index
- 2nd index (into history): 1, 0, -1, ... for current, previous, et. timestep.

## Class: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData <a id="bosss.foundation.xdg.levelsettracker.levelsetdata"></a>

**Summary:** Caches for normals, curvature, etc, for each level-set.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GridDat <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.griddat"></a>
**Summary:** Link to the underlying background grid of the XDG discretization.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.Region <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.region"></a>
**Summary:** Region object which correlates with actual [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.HistoryIndex](#bosss.foundation.xdg.levelsettracker.levelsetdata.historyindex).


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.HistoryIndex <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.historyindex"></a>
**Summary:** Index into the level-set history, see e.g. [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetHistories](#bosss.foundation.xdg.levelsettracker.levelsethistories).


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevelSetIndex <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levelsetindex"></a>
**Summary:** Index of the corresponding level-set, see e.g. [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetHistories](#bosss.foundation.xdg.levelsettracker.levelsethistories).


### Property: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevelSet <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levelset"></a>
**Summary:** Access the level-set.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevSetValues(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.getlevsetvalues(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** Cached evaluation of the level set fields (values of the level-set field).
**Parameter:** `NS` - 
**Parameter:** `j0` - local index of first cell to evaluate
**Parameter:** `Len` - number of cells to evaluate
**Returns:**
values of the level set field at the nodes of the specified node set.

## Class: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevSetValueCache <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levsetvaluecache"></a>


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevSetValueCache.ComputeValues(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levsetvaluecache.computevalues(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)"></a>


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevSetValueCache.Allocate(System.Int32,System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levsetvaluecache.allocate(system.int32,system.int32,bosss.foundation.nodeset)"></a>

## Class: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevelSetGradientCache <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levelsetgradientcache"></a>

**Summary:** Caches the gradient of a level set


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevelSetGradientCache.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levelsetgradientcache.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata)"></a>
**Summary:** Constructs a value cache for the evaluation of the gradient of
the given level set.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevelSetGradientCache.ComputeValues(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levelsetgradientcache.computevalues(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** [BoSSS.Foundation.XDG.ILevelSet.EvaluateGradient(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray)](BoSSS.Foundation.md#bosss.foundation.xdg.ilevelset.evaluategradient(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray))


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.LevelSetGradientCache.Allocate(System.Int32,System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.levelsetgradientcache.allocate(system.int32,system.int32,bosss.foundation.nodeset)"></a>


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetGradients(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetgradients(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** Calculates the gradients of the level set in every affected cell
and every point contained the node set identified by
'NS'. The layout of the resulting array
is equivalent to [BoSSS.Foundation.XDG.ILevelSet.EvaluateGradient(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray)](BoSSS.Foundation.md#bosss.foundation.xdg.ilevelset.evaluategradient(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray)).
**Parameter:** `NS` - Nodes to evaluate at.
**Parameter:** `j0` - The first cell to be evaluated
**Parameter:** `Len` - The number of cell to be evaluated
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetReferenceGradients(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetreferencegradients(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** Calculates the gradients in the reference coordinate system of the level set in every affected cell
and every point contained the node set identified by
'NS'. The layout of the resulting array
is equivalent to [BoSSS.Foundation.XDG.ILevelSet.EvaluateGradient(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray)](BoSSS.Foundation.md#bosss.foundation.xdg.ilevelset.evaluategradient(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray)).
**Parameter:** `NS` - Nodes to evaluate at.
**Parameter:** `j0` - The first cell to be evaluated
**Parameter:** `Len` - The number of cell to be evaluated
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetNormals(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetnormals(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** Variant of [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetGradients(BoSSS.Foundation.NodeSet,System.Int32,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetgradients(bosss.foundation.nodeset,system.int32,system.int32)) which normalizes the
gradients before returning them
**Parameter:** `NS` - Nodes to evaluate at.

///
**Parameter:** `j0` - The first cell to be evaluated
**Parameter:** `Len` - The number of cell to be evaluated


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetReferenceNormals(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetreferencenormals(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** Variant of [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetReferenceGradients(BoSSS.Foundation.NodeSet,System.Int32,System.Int32)](#bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetreferencegradients(bosss.foundation.nodeset,system.int32,system.int32)) which normalizes the
gradients before returning them.
**Parameter:** `NS` - Nodes to evaluate at.

///
**Parameter:** `j0` - The first cell to be evaluated
**Parameter:** `Len` - The number of cell to be evaluated


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetNormalReferenceToPhysicalMetrics(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetnormalreferencetophysicalmetrics(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** Some integral transformation metrics....


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetReferenceHessian(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetreferencehessian(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** The Hessian of the level set field with respect to reference coordinates.
**Parameter:** `nodes` - 
**Parameter:** `j0` - first cell to evaluate
**Parameter:** `Len` - number of cells to evaluate
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.GetLevelSetReferenceCurvature(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.getlevelsetreferencecurvature(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** The curvature of the level set field with respect to reference coordinates.
**Parameter:** `NS` - 
**Parameter:** `j0` - first cell to evaluate
**Parameter:** `Len` - number of cells to evaluate
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData.Clone <a id="bosss.foundation.xdg.levelsettracker.levelsetdata.clone"></a>

## Class: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer"></a>

**Summary:** Initializer for a [BoSSS.Foundation.XDG.LevelSetTracker](#bosss.foundation.xdg.levelsettracker) during IO
operations


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.instance <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.instance"></a>
**Summary:** An instance of the represented tracker (if already constructed
via [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.Initialize(BoSSS.Foundation.IO.IInitializationContext)](#bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.initialize(bosss.foundation.io.iinitializationcontext))).


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.LevelSets <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.levelsets"></a>
**Summary:** See [BoSSS.Foundation.XDG.LevelSetTracker.LevelSets](#bosss.foundation.xdg.levelsettracker.levelsets)


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.NearRegionWidth <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.nearregionwidth"></a>
**Summary:** See [BoSSS.Foundation.XDG.LevelSetTracker.NearRegionWidth](#bosss.foundation.xdg.levelsettracker.nearregionwidth)


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.CutCellQuadratureType <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.cutcellquadraturetype"></a>
**Summary:** See [BoSSS.Foundation.XDG.LevelSetTracker.CutCellQuadratureType](#bosss.foundation.xdg.levelsettracker.cutcellquadraturetype)


### Field: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.SpeciesTable <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.speciestable"></a>
**Summary:** See [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesTable](#bosss.foundation.xdg.levelsettracker.speciestable)


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.Initialize(BoSSS.Foundation.IO.IInitializationContext) <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.initialize(bosss.foundation.io.iinitializationcontext)"></a>
**Summary:** Initializes the level set tracker.
**Parameter:** `c` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.Equals(BoSSS.Foundation.IO.Initializer{BoSSS.Foundation.XDG.LevelSetTracker}) <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.equals(bosss.foundation.io.initializer{bosss.foundation.xdg.levelsettracker})"></a>
**Summary:** Compares the given object 'other' with this one.


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.GetHashCode <a id="bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.gethashcode"></a>
**Summary:** Computes a hash code based on 
[BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.LevelSets](#bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.levelsets) and
[BoSSS.Foundation.XDG.LevelSetTracker.LevelSetTrackerInitializer.NearRegionWidth](#bosss.foundation.xdg.levelsettracker.levelsettrackerinitializer.nearregionwidth).


### Field: BoSSS.Foundation.XDG.LevelSetTracker.m_Initializer <a id="bosss.foundation.xdg.levelsettracker.m_initializer"></a>
**Summary:** Initializer of this object, if any.


### Property: BoSSS.Foundation.XDG.LevelSetTracker.Initializer <a id="bosss.foundation.xdg.levelsettracker.initializer"></a>
**Summary:** To support IO-architecture, NOT for direct user interaction. Note
that it is essential that this member always returns the SAME
object (reference-equals)!


## Method: BoSSS.Foundation.XDG.LevelSetTracker.LoadData(BoSSS.Foundation.IO.ITimestepInfo,System.Collections.Generic.IList{BoSSS.Foundation.IO.CellFieldDataSet},System.Collections.Generic.HashSet{System.Object}) <a id="bosss.foundation.xdg.levelsettracker.loaddata(bosss.foundation.io.itimestepinfo,system.collections.generic.ilist{bosss.foundation.io.cellfielddataset},system.collections.generic.hashset{system.object})"></a>
**Summary:** Makes each level set load the appropriate 'data'
for the given 'tsi'.
**Parameter:** `tsi` - Information about the time-step
**Parameter:** `data` - Data to be loaded
**Parameter:** `loadedObjects` - Cache for already loaded objects
**Remark:**
Causes an update of the level set tracker!

## Class: BoSSS.Foundation.XDG.LevelsetSign <a id="bosss.foundation.xdg.levelsetsign"></a>

**Summary:** used to encode the sign of the level set (in non-performance
critical regions) in one cell or edge;


### Field: BoSSS.Foundation.XDG.LevelsetSign.Negative <a id="bosss.foundation.xdg.levelsetsign.negative"></a>
**Summary:** level set is negative in the whole cell/edge, i.e.


### Field: BoSSS.Foundation.XDG.LevelsetSign.Both <a id="bosss.foundation.xdg.levelsetsign.both"></a>
**Summary:** both, positive and negative (usually a cut cell/edge or a cell/edge
in the near-region);


### Field: BoSSS.Foundation.XDG.LevelsetSign.Positive <a id="bosss.foundation.xdg.levelsetsign.positive"></a>
**Summary:** level set is positive

## Class: BoSSS.Foundation.XDG.LevelSetSignCode <a id="bosss.foundation.xdg.levelsetsigncode"></a>

**Summary:** encodes the sign of up to four level sets in four bits,
(at one specific point, while [BoSSS.Foundation.XDG.LevelsetSign](#bosss.foundation.xdg.levelsetsign) and [BoSSS.Foundation.XDG.LevelsetCellSignCode](#bosss.foundation.xdg.levelsetcellsigncode)
define all possibilities in one cell.);


### Field: BoSSS.Foundation.XDG.LevelSetSignCode.val <a id="bosss.foundation.xdg.levelsetsigncode.val"></a>
**Summary:** see [BoSSS.Foundation.XDG.LevelSetSignCode.Val](#bosss.foundation.xdg.levelsetsigncode.val);


### Property: BoSSS.Foundation.XDG.LevelSetSignCode.Val <a id="bosss.foundation.xdg.levelsetsigncode.val"></a>
**Summary:** Bit 0 corresponds with sign of level set 0, Bit 1 corresponds ...


## Method: BoSSS.Foundation.XDG.LevelSetSignCode.Equals(System.Object) <a id="bosss.foundation.xdg.levelsetsigncode.equals(system.object)"></a>
**Summary:** equality


## Method: BoSSS.Foundation.XDG.LevelSetSignCode.GetHashCode <a id="bosss.foundation.xdg.levelsetsigncode.gethashcode"></a>
**Summary:** hasch code


## Method: BoSSS.Foundation.XDG.LevelSetSignCode.op_Equality(BoSSS.Foundation.XDG.LevelSetSignCode,BoSSS.Foundation.XDG.LevelSetSignCode) <a id="bosss.foundation.xdg.levelsetsigncode.op_equality(bosss.foundation.xdg.levelsetsigncode,bosss.foundation.xdg.levelsetsigncode)"></a>
**Summary:** equality


## Method: BoSSS.Foundation.XDG.LevelSetSignCode.op_Inequality(BoSSS.Foundation.XDG.LevelSetSignCode,BoSSS.Foundation.XDG.LevelSetSignCode) <a id="bosss.foundation.xdg.levelsetsigncode.op_inequality(bosss.foundation.xdg.levelsetsigncode,bosss.foundation.xdg.levelsetsigncode)"></a>
**Summary:** inequality


## Method: BoSSS.Foundation.XDG.LevelSetSignCode.ComputeLevelSetBytecode(System.Double[]) <a id="bosss.foundation.xdg.levelsetsigncode.computelevelsetbytecode(system.double[])"></a>
**Summary:** Encodes the signs of the level set values into a byte code
**Parameter:** `levelSetValues` - The values of the level sets at a given point
**Returns:**
A byte code where the n-th bit (starting from the least significant
bit) is 0 if 'levelSetValues'[n] is less than zero
and 1 otherwise.


## Method: BoSSS.Foundation.XDG.LevelSetSignCode.GetSign(System.Int32) <a id="bosss.foundation.xdg.levelsetsigncode.getsign(system.int32)"></a>
**Summary:** extracts the sign of one level set
**Parameter:** `LevSetIdx` - 
**Returns:**
true: positive sign
false: negative sign


## Method: BoSSS.Foundation.XDG.LevelSetSignCode.SetSign(System.Int32,System.Boolean) <a id="bosss.foundation.xdg.levelsetsigncode.setsign(system.int32,system.boolean)"></a>
**Summary:** manipulates the sign of one level set;
**Parameter:** `LevSetIdx` - 
**Parameter:** `sign` - true: positive sign
false: negative sign


## Method: BoSSS.Foundation.XDG.LevelSetSignCode.SetSigns(System.Boolean[]) <a id="bosss.foundation.xdg.levelsetsigncode.setsigns(system.boolean[])"></a>
**Summary:** Manipulates the sign of all level sets

## Class: BoSSS.Foundation.XDG.LevelSetTopologyException <a id="bosss.foundation.xdg.levelsettopologyexception"></a>

**Summary:** thrown by [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[]));


## Method: BoSSS.Foundation.XDG.LevelSetTopologyException.#ctor(System.Collections.Generic.IEnumerable{System.ValueTuple{System.Int32,System.Int32,System.Int32,System.Int32,System.Int32}}) <a id="bosss.foundation.xdg.levelsettopologyexception.#ctor(system.collections.generic.ienumerable{system.valuetuple{system.int32,system.int32,system.int32,system.int32,system.int32}})"></a>
**Summary:** ctor

## Class: BoSSS.Foundation.XDG.LinearLevelSetFormVectorizer <a id="bosss.foundation.xdg.linearlevelsetformvectorizer"></a>


## Method: BoSSS.Foundation.XDG.LinearLevelSetFormVectorizer.#ctor(BoSSS.Foundation.XDG.ILevelSetForm) <a id="bosss.foundation.xdg.linearlevelsetformvectorizer.#ctor(bosss.foundation.xdg.ilevelsetform)"></a>
**Summary:** ctor.


### Field: BoSSS.Foundation.XDG.LinearLevelSetFormVectorizer.OrgComponent <a id="bosss.foundation.xdg.linearlevelsetformvectorizer.orgcomponent"></a>
**Summary:** The original component that is beeing vectorized.

## Class: BoSSS.Foundation.XDG.MappingExtensions <a id="bosss.foundation.xdg.mappingextensions"></a>

**Summary:** XDG-related extensions for [BoSSS.Foundation.UnsetteledCoordinateMapping](BoSSS.Foundation.md#bosss.foundation.unsetteledcoordinatemapping) and [BoSSS.Foundation.CoordinateMapping](BoSSS.Foundation.md#bosss.foundation.coordinatemapping)


## Method: BoSSS.Foundation.XDG.MappingExtensions.LocalUniqueCoordinateIndex(BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,System.Int32,BoSSS.Foundation.XDG.SpeciesId,System.Int32) <a id="bosss.foundation.xdg.mappingextensions.localuniquecoordinateindex(bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.levelsettracker,system.int32,system.int32,bosss.foundation.xdg.speciesid,system.int32)"></a>
**Summary:** computes a local unique coordinate index ("local" means local on this processor);
this index is unique over all fields (in this mapping), over all cells, over all basis functions, 
but it's only locally (on this processor) valid.
**Parameter:** `find` - the field or basis index (see [BoSSS.Foundation.UnsetteledCoordinateMapping.BasisS](BoSSS.Foundation.md#bosss.foundation.unsetteledcoordinatemapping.basiss));
**Parameter:** `j` - local cell index
**Parameter:** `n` - DG mode index
**Parameter:** `lsTrk` - 
**Parameter:** `map` - 
**Parameter:** `spc` - species
**Returns:**
A (MPI-) local index in the update range 
(between 0 and smaller than **ilPSP.IPartitioning.LocalLength**).
It can be converted into 
a (MPI-) global index by adding **ilPSP.IPartitioning.i0**.


## Method: BoSSS.Foundation.XDG.MappingExtensions.GetNumberOfModes(BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,System.Int32,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.mappingextensions.getnumberofmodes(bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.levelsettracker,system.int32,system.int32,bosss.foundation.xdg.speciesid)"></a>
**Summary:** Number of DG modes for a specific variable, cell and species.
**Parameter:** `find` - the field or basis index (see [BoSSS.Foundation.UnsetteledCoordinateMapping.BasisS](BoSSS.Foundation.md#bosss.foundation.unsetteledcoordinatemapping.basiss));
**Parameter:** `j` - local cell index
**Parameter:** `lsTrk` - 
**Parameter:** `map` - 
**Parameter:** `spc` - species


## Method: BoSSS.Foundation.XDG.MappingExtensions.GetNumberOfModes(BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,System.Int32,System.Int32) <a id="bosss.foundation.xdg.mappingextensions.getnumberofmodes(bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.levelsettracker,system.int32,system.int32,system.int32)"></a>
**Summary:** Number of DG modes for a specific variable, cell and species.
**Parameter:** `find` - the field or basis index (see [BoSSS.Foundation.UnsetteledCoordinateMapping.BasisS](BoSSS.Foundation.md#bosss.foundation.unsetteledcoordinatemapping.basiss));
**Parameter:** `j` - local cell index
**Parameter:** `lsTrk` - 
**Parameter:** `map` - 
**Parameter:** `spcIdx` - index


## Method: BoSSS.Foundation.XDG.MappingExtensions.LocalUniqueCoordinateIndex(BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,System.Int32,System.Int32,System.Int32) <a id="bosss.foundation.xdg.mappingextensions.localuniquecoordinateindex(bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.levelsettracker,system.int32,system.int32,system.int32,system.int32)"></a>
**Summary:** computes a local unique coordinate index ("local" means local on this processor);
this index is unique over all fields (in this mapping), over all cells, over all basis functions, 
but it's only locally (on this processor) valid.
**Parameter:** `find` - the field or basis index (see [BoSSS.Foundation.UnsetteledCoordinateMapping.BasisS](BoSSS.Foundation.md#bosss.foundation.unsetteledcoordinatemapping.basiss));
**Parameter:** `j` - local cell index
**Parameter:** `n` - DG mode index
**Parameter:** `lsTrk` - 
**Parameter:** `map` - 
**Parameter:** `spcIdx` - species index
**Returns:**
A (MPI-) local index in the update range 
(between 0 and smaller than **ilPSP.IPartitioning.LocalLength**).
It can be converted into 
a (MPI-) global index by adding **ilPSP.IPartitioning.i0**.


## Method: BoSSS.Foundation.XDG.MappingExtensions.GetBasisLengths(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32) <a id="bosss.foundation.xdg.mappingextensions.getbasislengths(bosss.foundation.unsetteledcoordinatemapping,system.int32)"></a>
**Summary:** Returns the length (number of DG modes for all species)


## Method: BoSSS.Foundation.XDG.MappingExtensions.GetNonXBasisLengths(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32) <a id="bosss.foundation.xdg.mappingextensions.getnonxbasislengths(bosss.foundation.unsetteledcoordinatemapping,system.int32)"></a>
**Summary:** Returns the length (number of DG modes for all species)


## Method: BoSSS.Foundation.XDG.MappingExtensions.XorNonXbasis(BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.mappingextensions.xornonxbasis(bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** Returns a bool-array to indicate whether the individual basis components [BoSSS.Foundation.UnsetteledCoordinateMapping.BasisS](BoSSS.Foundation.md#bosss.foundation.unsetteledcoordinatemapping.basiss) are XDG or normal DG

## Class: BoSSS.Foundation.XDG.MassMatrixFactory <a id="bosss.foundation.xdg.massmatrixfactory"></a>

**Summary:** Creation of XDG mass-matrices.


### Property: BoSSS.Foundation.XDG.MassMatrixFactory.XDGSpaceMetrics <a id="bosss.foundation.xdg.massmatrixfactory.xdgspacemetrics"></a>
**Summary:** owner object.


## Method: BoSSS.Foundation.XDG.MassMatrixFactory.#ctor(BoSSS.Foundation.XDG.XDGSpaceMetrics) <a id="bosss.foundation.xdg.massmatrixfactory.#ctor(bosss.foundation.xdg.xdgspacemetrics)"></a>
**Summary:** ctor.


### Property: BoSSS.Foundation.XDG.MassMatrixFactory.MaxBasis <a id="bosss.foundation.xdg.massmatrixfactory.maxbasis"></a>
**Summary:** the maximal supported basis if this factory


### Property: BoSSS.Foundation.XDG.MassMatrixFactory.MaxTraceBasis <a id="bosss.foundation.xdg.massmatrixfactory.maxtracebasis"></a>
**Summary:** the maximal supported basis if this factory


## Method: BoSSS.Foundation.XDG.MassMatrixFactory.GetMassMatrix(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IDictionary{BoSSS.Foundation.XDG.SpeciesId,System.Collections.Generic.IEnumerable{System.Double}},System.Boolean) <a id="bosss.foundation.xdg.massmatrixfactory.getmassmatrix(bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.idictionary{bosss.foundation.xdg.speciesid,system.collections.generic.ienumerable{system.double}},system.boolean)"></a>
**Summary:** computes the mass matrices for a given mapping.
**Parameter:** `mapping` - 
**Parameter:** `alpha` - 'Fine-grained' scaling for blocks, for each species and each variable in the 'mapping'.
The default value of null maps to 1.0 for each species and variable.
**Parameter:** `inverse` - Return the inverse mass matrix.


## Method: BoSSS.Foundation.XDG.MassMatrixFactory.GetMassMatrix(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Boolean) <a id="bosss.foundation.xdg.massmatrixfactory.getmassmatrix(bosss.foundation.unsetteledcoordinatemapping,system.boolean)"></a>
**Summary:** Computes the mass matrices for a given mapping, for all species in [BoSSS.Foundation.XDG.MassMatrixFactory.AvailableSpecies](#bosss.foundation.xdg.massmatrixfactory.availablespecies)


## Method: BoSSS.Foundation.XDG.MassMatrixFactory.GetMassMatrix(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Double[],System.Boolean,BoSSS.Foundation.XDG.SpeciesId[]) <a id="bosss.foundation.xdg.massmatrixfactory.getmassmatrix(bosss.foundation.unsetteledcoordinatemapping,system.double[],system.boolean,bosss.foundation.xdg.speciesid[])"></a>
**Summary:** Computes the mass matrices for a given mapping.


## Method: BoSSS.Foundation.XDG.MassMatrixFactory.GetMassMatrixBlocks(BoSSS.Foundation.Basis,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.massmatrixfactory.getmassmatrixblocks(bosss.foundation.basis,bosss.foundation.xdg.speciesid)"></a>
**Summary:** Provides access to a 'raw' form of the mass matrix, where only blocks for the cut cells
are stored
**Returns:**
don't mess with those values


### Property: BoSSS.Foundation.XDG.MassMatrixFactory.AvailableSpecies <a id="bosss.foundation.xdg.massmatrixfactory.availablespecies"></a>
**Summary:** a collection of all species that are available


### Field: BoSSS.Foundation.XDG.MassMatrixFactory.MassBlocks <a id="bosss.foundation.xdg.massmatrixfactory.massblocks"></a>
**Summary:** cached mass-matrix blocks for cut-cells


### Field: BoSSS.Foundation.XDG.MassMatrixFactory.TraceMassBlocks <a id="bosss.foundation.xdg.massmatrixfactory.tracemassblocks"></a>
**Summary:** cached mass-matrix blocks for cut-cells for TraceDG


## Method: BoSSS.Foundation.XDG.MassMatrixFactory.AccMassMatrix``1(``0,BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IDictionary{BoSSS.Foundation.XDG.SpeciesId,System.Collections.Generic.IEnumerable{System.Double}},System.Boolean) <a id="bosss.foundation.xdg.massmatrixfactory.accmassmatrix``1(``0,bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.idictionary{bosss.foundation.xdg.speciesid,system.collections.generic.ienumerable{system.double}},system.boolean)"></a>
**Summary:** computes the mass matrices for a given mapping and accumulates the mass matrix to some other matrix.

## Class: BoSSS.Foundation.XDG.MassMatrixFactory.MassMatrixBlockContainer <a id="bosss.foundation.xdg.massmatrixfactory.massmatrixblockcontainer"></a>


### Field: BoSSS.Foundation.XDG.MassMatrixFactory.MassMatrixBlockContainer.MassMatrixBlocks <a id="bosss.foundation.xdg.massmatrixfactory.massmatrixblockcontainer.massmatrixblocks"></a>
**Summary:** Mass matrix blocks
- 1st index: subgrid cell index (which map to local cell indices by [BoSSS.Foundation.XDG.MassMatrixFactory.MassMatrixBlockContainer.jSub2jCell](#bosss.foundation.xdg.massmatrixfactory.massmatrixblockcontainer.jsub2jcell))
- 2nd index: diagonal block row;
- 3rd index: diagonal block column;


### Field: BoSSS.Foundation.XDG.MassMatrixFactory.MassMatrixBlockContainer.jSub2jCell <a id="bosss.foundation.xdg.massmatrixfactory.massmatrixblockcontainer.jsub2jcell"></a>
**Summary:** mapping from sub-grid index (correlates to 1st index of [BoSSS.Foundation.XDG.MassMatrixFactory.MassMatrixBlockContainer.MassMatrixBlocks](#bosss.foundation.xdg.massmatrixfactory.massmatrixblockcontainer.massmatrixblocks)) to local cell index


### Field: BoSSS.Foundation.XDG.MassMatrixFactory.MassMatrixBlockContainer.jCell2jSub <a id="bosss.foundation.xdg.massmatrixfactory.massmatrixblockcontainer.jcell2jsub"></a>
**Summary:** mapping from cell index to subgrid index (correlates to 1st index of [BoSSS.Foundation.XDG.MassMatrixFactory.MassMatrixBlockContainer.MassMatrixBlocks](#bosss.foundation.xdg.massmatrixfactory.massmatrixblockcontainer.massmatrixblocks))


### Field: BoSSS.Foundation.XDG.MassMatrixFactory.MassMatrixBlockContainer.IntegrationDomain <a id="bosss.foundation.xdg.massmatrixfactory.massmatrixblockcontainer.integrationdomain"></a>
**Summary:** The integration domain for mass matrices; this contains only cut cells.

## Class: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator <a id="bosss.foundation.xdg.multiphasecellagglomerator"></a>

**Summary:** algebraic cell agglomeration to avoid small cut-cells;


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.TotalNumberOfAgglomerations <a id="bosss.foundation.xdg.multiphasecellagglomerator.totalnumberofagglomerations"></a>
**Summary:** number of agglomerations in all species


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.AgglomerationThreshold <a id="bosss.foundation.xdg.multiphasecellagglomerator.agglomerationthreshold"></a>
**Summary:** threshold factor that determines when cells are agglomerated


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.AgglomerationThreshold_Oldtimesteps <a id="bosss.foundation.xdg.multiphasecellagglomerator.agglomerationthreshold_oldtimesteps"></a>
**Summary:** similar to [BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.AgglomerationThreshold](#bosss.foundation.xdg.multiphasecellagglomerator.agglomerationthreshold), but for old timesteps


### Field: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.plotAgglomeration <a id="bosss.foundation.xdg.multiphasecellagglomerator.plotagglomeration"></a>
**Summary:** If agglomeration plots are demanded. A flag for debugging purposes in the agglomeration algorithm.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.CutCellQuadratureOrder <a id="bosss.foundation.xdg.multiphasecellagglomerator.cutcellquadratureorder"></a>
**Summary:** The quadrature order used for computing cell volumes and edge areas.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.HMFvariant <a id="bosss.foundation.xdg.multiphasecellagglomerator.hmfvariant"></a>
**Summary:** The kind of HMF which is be used for computing cell volumes.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.SpeciesList <a id="bosss.foundation.xdg.multiphasecellagglomerator.specieslist"></a>
**Summary:** All species for which agglomeration is available.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.Tracker <a id="bosss.foundation.xdg.multiphasecellagglomerator.tracker"></a>
**Summary:** Link to the tracker.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.NonAgglomeratedMetrics <a id="bosss.foundation.xdg.multiphasecellagglomerator.nonagglomeratedmetrics"></a>
**Summary:** Cut-cell length scales before agglomeration


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.XDG.SpeciesId[],System.Int32,System.Double,System.Boolean,System.Boolean,System.Boolean,System.Double[],System.Double,System.String) <a id="bosss.foundation.xdg.multiphasecellagglomerator.#ctor(bosss.foundation.xdg.levelsettracker,bosss.foundation.xdg.speciesid[],system.int32,system.double,system.boolean,system.boolean,system.boolean,system.double[],system.double,system.string)"></a>
**Summary:** ctor.
**Parameter:** `__AgglomerationTreshold` - see [BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.AgglomerationThreshold](#bosss.foundation.xdg.multiphasecellagglomerator.agglomerationthreshold)
**Parameter:** `oldTs__AgglomerationTreshold` - Agglomeration thresholds for  _previous_ timesteps.
The number of entries in this array determines how many previous timesteps are considered
([BoSSS.Foundation.XDG.LevelSetTracker.HistoryLength](#bosss.foundation.xdg.levelsettracker.historylength)).
**Parameter:** `AgglomerateNewborn` - 'Newborn' cut-cells 
are agglomerated to cells which already exist in the previous  timestep.
**Parameter:** `AgglomerateDecased` - 'Deceased' cut-cells are agglomerated to cells which exist in the next timestep.
**Parameter:** `ExceptionOnFailedAgglomeration` - If true, an exception is thrown for 
any cell which should be agglomerated, if no neighbour is found.
**Parameter:** `CutCellsQuadOrder` - cut-cell quadrature order for the quadrature rule that is used to determine cell volumes;
**Parameter:** `Spc` - 
**Parameter:** `lsTrk` - 
**Parameter:** `NewbornAndDecasedThreshold` - Volume fraction threshold at which a cut-cell counts as newborn, resp. deceased, see 'AgglomerateNewborn', 'AgglomerateDecased';
this should typically be the same order which is used to evaluate the XDG operator matrix.
**Parameter:** `Tag` - Tag to pass debug information


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.GetAgglomerator(BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.multiphasecellagglomerator.getagglomerator(bosss.foundation.xdg.speciesid)"></a>
**Summary:** returns the [BoSSS.Foundation.XDG.CellAgglomerator](#bosss.foundation.xdg.cellagglomerator) for species 'spc';

## Class: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.MiniMapping <a id="bosss.foundation.xdg.multiphasecellagglomerator.minimapping"></a>


### Field: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.MiniMapping.NS <a id="bosss.foundation.xdg.multiphasecellagglomerator.minimapping.ns"></a>
**Summary:** DOFs per cell, per variable, per species.
index: variable.


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.GetRowManipulationMatrix(BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.multiphasecellagglomerator.getrowmanipulationmatrix(bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** returns the projection operator


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.GetColManipulationMatrix(BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.multiphasecellagglomerator.getcolmanipulationmatrix(bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** returns the prolongation operator


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.ManipulateMatrixAndRHS``2(``0,``1,BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.multiphasecellagglomerator.manipulatematrixandrhs``2(``0,``1,bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** applies the agglomeration on a general matrix
**Parameter:** `Matrix` - the matrix that should be manipulated.
**Parameter:** `Rhs` - the right-hand-side that should be manipulated
**Parameter:** `ColMap` - 
**Parameter:** `RowMap` - 


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.ClearAgglomerated(BoSSS.Foundation.CoordinateMapping) <a id="bosss.foundation.xdg.multiphasecellagglomerator.clearagglomerated(bosss.foundation.coordinatemapping)"></a>
**Summary:** for all DG fields in 'Map', this clears all entries which correspond to agglomerated cells.


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.ClearAgglomerated``1(``0,BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.multiphasecellagglomerator.clearagglomerated``1(``0,bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** In a vector 'vec', this clears all entries which correspond to agglomerated cells.


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.NormInAgglomerated``1(``0,BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.multiphasecellagglomerator.norminagglomerated``1(``0,bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** computes the l2-Norm of the DG coordinates
in the agglomerated cells
**Remark:**
The l2-Norm of the DG coordinates
is NOT equal to the L2-Norm of the DG-field in the XDG-case,
since the basis is no longer orthonormal and therefore Parcival's equation does not hold.


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.Extrapolate(BoSSS.Foundation.CoordinateMapping) <a id="bosss.foundation.xdg.multiphasecellagglomerator.extrapolate(bosss.foundation.coordinatemapping)"></a>
**Summary:** For a list of DG fields, this method performs a
polynomial extrapolation from agglomeration target cells to agglomeration source cells.


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.Extrapolate``1(``0,BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.multiphasecellagglomerator.extrapolate``1(``0,bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** For a vector 'vec' 
which is interpreted as a set of DG fields,
defined through the mapping 'map', 
this method performs a
polynomial extrapolation from agglomeration target cells to agglomeration source cells.


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.PlotAgglomerationPairs(System.String) <a id="bosss.foundation.xdg.multiphasecellagglomerator.plotagglomerationpairs(system.string)"></a>
**Summary:** Diagnostic output: for each species, 'stays' which visualize the agglomeration operation, 
are plotted.
**Parameter:** `basename` - base name for the output files


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.CellLengthScales <a id="bosss.foundation.xdg.multiphasecellagglomerator.celllengthscales"></a>
**Summary:** The volume over cut cell surface ratio, i.e. $\frac{ | K^X |}{ | \partial K^X | }$, for each **agglomerated** cut-cell $K^X$.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.CellVolumeFrac <a id="bosss.foundation.xdg.multiphasecellagglomerator.cellvolumefrac"></a>
**Summary:** The volume fraction of agglomerated cut cells.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.CutCellVolumes <a id="bosss.foundation.xdg.multiphasecellagglomerator.cutcellvolumes"></a>
**Summary:** The volume of agglomerated cut cells.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.CellSurface <a id="bosss.foundation.xdg.multiphasecellagglomerator.cellsurface"></a>
**Summary:** The surface of agglomerated cut cells.


### Property: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.NumberOfAggomerationLevels <a id="bosss.foundation.xdg.multiphasecellagglomerator.numberofaggomerationlevels"></a>
**Summary:** Maximum over all [BoSSS.Foundation.XDG.CellAgglomerator.AgglomerationInfo.MaxLevel](#bosss.foundation.xdg.cellagglomerator.agglomerationinfo.maxlevel) member plus 1


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.LengthScaleAgg <a id="bosss.foundation.xdg.multiphasecellagglomerator.lengthscaleagg"></a>
**Summary:** Initializes [BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.CellLengthScales](#bosss.foundation.xdg.multiphasecellagglomerator.celllengthscales),
i.e. performs the agglomeration of length scales.


## Method: BoSSS.Foundation.XDG.MultiphaseCellAgglomerator.PrintInfo(System.IO.TextWriter,System.Boolean) <a id="bosss.foundation.xdg.multiphasecellagglomerator.printinfo(system.io.textwriter,system.boolean)"></a>
**Summary:** Prints human-readable information on the writer 'stw'

## Class: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1 <a id="bosss.foundation.xdg.necquadraturelevelset`1"></a>

**Summary:** integrator for coupling components, linear components;


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.ResultVector <a id="bosss.foundation.xdg.necquadraturelevelset`1.resultvector"></a>
**Summary:** Result of quadrature, Output storage


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_CodomainMap <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_codomainmap"></a>
**Summary:** Mapping of DG-DOF into [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.ResultVector](#bosss.foundation.xdg.necquadraturelevelset`1.resultvector)


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsA <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsa"></a>
**Summary:** All Domain and Parameter fields (domain first (0 to [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.DELTA](#bosss.foundation.xdg.necquadraturelevelset`1.delta)-1), then parameters) are defined by the operator, on the negative side of the level-set (species A)


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsB <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsb"></a>
**Summary:** All Domain and Parameter fields (domain first (0 to [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.DELTA](#bosss.foundation.xdg.necquadraturelevelset`1.delta)-1), then parameters) are defined by the operator, on the positive side of the level-set (species A)


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.DELTA <a id="bosss.foundation.xdg.necquadraturelevelset`1.delta"></a>
**Summary:** Number of domain fields


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_ValueRequired <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_valuerequired"></a>
**Summary:** Switch, whether the evaluation (the field value) of [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsA](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsa), [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsB](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsb) is actually necessary.


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_GradientRequired <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_gradientrequired"></a>
**Summary:** Switch, whether the evaluation (the gradient value) of [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsA](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsa), [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsB](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsb) is actually necessary.


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_lsTrk <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_lstrk"></a>
**Summary:** ye good old level set tracker


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_LsTrkHistoryIndex <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_lstrkhistoryindex"></a>
**Summary:** index into [BoSSS.Foundation.XDG.LevelSetTracker.RegionsHistory](#bosss.foundation.xdg.levelsettracker.regionshistory), etc.


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.time <a id="bosss.foundation.xdg.necquadraturelevelset`1.time"></a>
**Summary:** Physical time.


### Property: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_LevSetIdx <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_levsetidx"></a>
**Summary:** index of the level set to evaluate


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_SpeciesPair <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_speciespair"></a>
**Summary:** Negative and positive (with respect to level-set) species.


### Property: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.SpeciesA <a id="bosss.foundation.xdg.necquadraturelevelset`1.speciesa"></a>
**Summary:** Negative species/Species A


### Property: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.SpeciesB <a id="bosss.foundation.xdg.necquadraturelevelset`1.speciesb"></a>
**Summary:** Positive species/Species B


## Method: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.#ctor(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.XDG.XDifferentialOperatorMk2,`0,System.Collections.Generic.IList{BoSSS.Foundation.DGField},System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,System.Int32,System.Tuple{BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId},BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.necquadraturelevelset`1.#ctor(bosss.foundation.grid.igriddata,bosss.foundation.xdg.xdifferentialoperatormk2,`0,system.collections.generic.ilist{bosss.foundation.dgfield},system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.levelsettracker,system.int32,system.int32,system.tuple{bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid},bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** ctor.


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_FieldValuesPos <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_fieldvaluespos"></a>
**Summary:** values of domain and parameter fields, positive side of level Set 
- 1st index: parameter index, correlates with [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsA](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsa), [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsB](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsb)
- 2nd index: cell index, plus some offset
- 3rd index: node index


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_FieldValuesNeg <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_fieldvaluesneg"></a>
**Summary:** values of domain and parameter fields, positive side of level Set
- 1st index: parameter index, correlates with [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsA](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsa), [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsB](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsb)
- 2nd index: cell index, plus some offset
- 3rd index: node index


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_FieldGradientValuesPos <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_fieldgradientvaluespos"></a>
**Summary:** values of domain and parameter fields, positive side of level Set 
- 1st index: parameter index, correlates with [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsA](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsa), [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsB](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsb)
- 2nd index: cell index, plus some offset
- 3rd index: node index
- 4th index: spatial direction


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_FieldGradientValuesNeg <a id="bosss.foundation.xdg.necquadraturelevelset`1.m_fieldgradientvaluesneg"></a>
**Summary:** values of domain and parameter fields, positive side of level Set
- 1st index: parameter index, correlates with [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsA](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsa), [BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_DomainAndParamFieldsB](#bosss.foundation.xdg.necquadraturelevelset`1.m_domainandparamfieldsb)
- 2nd index: cell index, plus some offset
- 3rd index: node index
- 4th index: spatial direction


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.Koeff_V <a id="bosss.foundation.xdg.necquadraturelevelset`1.koeff_v"></a>
**Summary:** result buffers for **BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_NonlinLsForm_V**,
- 1st index: codomain variable/test function


### Field: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.Koeff_GradV <a id="bosss.foundation.xdg.necquadraturelevelset`1.koeff_gradv"></a>
**Summary:** result buffers for **BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.m_NonlinLsForm_GradV**, 
- 1st index: codomain variable/test function


## Method: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.AllocateBuffers(System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.necquadraturelevelset`1.allocatebuffers(system.int32,bosss.foundation.nodeset)"></a>
**Summary:** memory allocation.


## Method: BoSSS.Foundation.XDG.NECQuadratureLevelSet`1.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.necquadraturelevelset`1.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** writes the dammed result of the integration to the sparse matrix

## Class: BoSSS.Foundation.XDG.NonlinearLevelSetFormVectorizer <a id="bosss.foundation.xdg.nonlinearlevelsetformvectorizer"></a>


## Method: BoSSS.Foundation.XDG.NonlinearLevelSetFormVectorizer.#ctor(BoSSS.Foundation.XDG.ILevelSetForm) <a id="bosss.foundation.xdg.nonlinearlevelsetformvectorizer.#ctor(bosss.foundation.xdg.ilevelsetform)"></a>
**Summary:** ctor.


### Field: BoSSS.Foundation.XDG.NonlinearLevelSetFormVectorizer.OrgComponent <a id="bosss.foundation.xdg.nonlinearlevelsetformvectorizer.orgcomponent"></a>
**Summary:** The original component that is being vectorized.

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy"></a>

**Summary:** A subdivision strategy that adaptively subdivides a node into sub-nodes
if it is cut the interface.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.maxDivisions <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.maxdivisions"></a>
**Summary:** The maximum number of subdivisions of the simplex


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.baseVertexSet <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.basevertexset"></a>
**Summary:** Vertex set containing the vertices of the root simplex.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.subdivisionTree <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.subdivisiontree"></a>
**Summary:** The subdivision tree that handles the actual subdivisions of the
simplex.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.LevelSetData <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.levelsetdata"></a>
**Summary:** level-set evaluation


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.gridData <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.griddata"></a>
**Summary:** The omnipresent context.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.#ctor(BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.#ctor(bosss.foundation.grid.refelements.refelement,bosss.foundation.xdg.levelsettracker.levelsetdata,system.int32)"></a>
**Summary:** Initializes the subdivision of the given simplex. Initially, the
simplex remains undivided.
**Parameter:** `refElement` - The reference element to subdivide.
**Parameter:** `levelSetData` - Allows for the check if a cell is cut.
**Parameter:** `maxDivisions` - The maximum number of subdivisions of the simplex


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.EstimateMinDistance(System.Int32,BoSSS.Foundation.Grid.ExecutionMask) <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.estimatemindistance(system.int32,bosss.foundation.grid.executionmask)"></a>
**Summary:** Estimates the distance below which we consider an element (i.e.,
cell or edge) cut. This is important in the case of curved
interfaces.
**Parameter:** `element` - The element (edge or cell) in question.
**Parameter:** `mask` - The mask containing the given element 'element'.
**Returns:**
The minimal distance below which consider element
'element' cut.
**Remark:**
Uses different estimates depending on the element type. The case of
edges is straightforward (since we don't have enough information to
do something sophisticated). For cells, we use a modified version of
a formular given by MinGibou2007:
\f$ 
\max |\Phi(v)| \leq 0.5 * \mathrm{Lip}(\Phi) h_\mathrm{max}.
\f$ 
In particular, we assume that the Lipschitz constant is close to 1
which is true if the level set is signed distance. A more
sophisticated method would evaluate the gradients at the vertices
in order to estimate the Lipschitz constant, but this would be less
efficient.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.GetVertices(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,BoSSS.Foundation.Grid.ExecutionMask,System.Int32@) <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.getvertices(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,bosss.foundation.grid.executionmask,system.int32@)"></a>
**Summary:** Determines the vertices associated with the given element (either
a cell or an edge). In case of a cell, they're directly stored in
the given set 'set'. In case of an edge, the
stored vertices have to be transformed from the edge coordinate
system to the volume coordinate system.
**Parameter:** `element` - The index of either a cell or an edge
**Parameter:** `set` - The set containing the vertices
**Parameter:** `mask` - The mask containing 'element'.
**Parameter:** `cell` - On exit: The cell the given element 'element'
belongs to.
**Returns:**
The vertices associated with 'element'.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.RefElement <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.refelement"></a>
**Summary:** [BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy.RefElement](#bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy.refelement).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.AdaptiveSubdivisionStrategy.GetSubdivisionNodes(BoSSS.Foundation.Grid.ExecutionMask) <a id="bosss.foundation.xdg.quadrature.subdivision.adaptivesubdivisionstrategy.getsubdivisionnodes(bosss.foundation.grid.executionmask)"></a>
**Summary:** Constructs the adapted subdivisions for all cells in
'mask'. The size of each chunk will be exactly one
since, in general, we cannot expect subsequent cells to have the
same subdivisions.
**Parameter:** `mask` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy.GetSubdivisionNodes(BoSSS.Foundation.Grid.ExecutionMask)](#bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy.getsubdivisionnodes(bosss.foundation.grid.executionmask))
**Returns:**
The subdivisions for all elements in 'mask',

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.BruteForceSubdivisionStrategy <a id="bosss.foundation.xdg.quadrature.subdivision.bruteforcesubdivisionstrategy"></a>

**Summary:** Subdivision strategy that blindly subdivides a simplex into
sub-simplices up to a given level. As a result, the subdivisions are
the same for all elements (i.e., cells or edges).


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.BruteForceSubdivisionStrategy.numberOfSubdivisions <a id="bosss.foundation.xdg.quadrature.subdivision.bruteforcesubdivisionstrategy.numberofsubdivisions"></a>
**Summary:** The number of subdivisions of the original simplex to perform.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.BruteForceSubdivisionStrategy.#ctor(BoSSS.Foundation.Grid.RefElements.RefElement,System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.bruteforcesubdivisionstrategy.#ctor(bosss.foundation.grid.refelements.refelement,system.int32)"></a>
**Summary:** Initializes the strategy.
**Parameter:** `refElement` - The simplex to be subdivided.
**Parameter:** `numberOfSubdivisions` - The number of subdivisions, see
[BoSSS.Foundation.Grid.RefElements.RefElement.SubdivisionTreeNode](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement.subdivisiontreenode).


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.BruteForceSubdivisionStrategy.RefElement <a id="bosss.foundation.xdg.quadrature.subdivision.bruteforcesubdivisionstrategy.refelement"></a>
**Summary:** The simplex to be subdivided.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.BruteForceSubdivisionStrategy.GetSubdivisionNodes(BoSSS.Foundation.Grid.ExecutionMask) <a id="bosss.foundation.xdg.quadrature.subdivision.bruteforcesubdivisionstrategy.getsubdivisionnodes(bosss.foundation.grid.executionmask)"></a>
**Summary:** Uses [BoSSS.Foundation.Grid.RefElements.RefElement.SubdivisionTreeNode](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement.subdivisiontreenode) to create the brute
force subdivision which is the same for all cells. As a result, the
chunks of 'mask' are not altered.
**Parameter:** `mask` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy.GetSubdivisionNodes(BoSSS.Foundation.Grid.ExecutionMask)](#bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy.getsubdivisionnodes(bosss.foundation.grid.executionmask))
**Returns:**
[BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy.GetSubdivisionNodes(BoSSS.Foundation.Grid.ExecutionMask)](#bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy.getsubdivisionnodes(bosss.foundation.grid.executionmask))
**Remark:**
Currently, the nodes returned by
[BoSSS.Foundation.Grid.RefElements.RefElement.SubdivisionTreeNode](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement.subdivisiontreenode) are unnecessarily
boxed by this method. This should be changed by changing the return
type of [BoSSS.Foundation.Grid.RefElements.RefElement.SubdivisionTreeNode](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement.subdivisiontreenode) at some
point.

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory <a id="bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory"></a>

**Summary:** A quad rule factory that has special support for cut cells. Uses a
subdivision strategy (see [BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy](#bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy)) to
subdivide elements (i.e., cell or edges) and builds a quad rule that is
(hopefully) suitable for the integration in cut cells.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.cutNodeRule <a id="bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.cutnoderule"></a>
**Summary:** Quadrature rule to be used in cut leaves (see
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.IsCut](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.iscut)).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy,System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.#ctor(bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy,system.int32)"></a>
**Summary:** Constructs a quad rule factory using the given subdivision
strategy.
**Parameter:** `subdivisionStrategy` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.SubdivisionStrategy](#bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.subdivisionstrategy)
**Parameter:** `leafDivisions` - The additional number of subdivisions for the quadrature rule to be
used in cut leaves (see [BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.IsCut](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.iscut)).


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.SubdivisionStrategy <a id="bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.subdivisionstrategy"></a>
**Summary:** The strategy that should be used for the construction of the
cut-cell quadrature rules.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.RefElement <a id="bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.refelement"></a>
**Summary:** The simplex to be integrated over.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** Uses [BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.SubdivisionStrategy](#bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.subdivisionstrategy) to construct the subdivision
nodes of the given simplex. Then, each node is supplied with a
standard quadrature rule of the desired order.
**Parameter:** `mask` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32)](#bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32))
**Parameter:** `order` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32)](#bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32))
**Returns:**
A quadrature rule that is 'order'th order accurate
in every node constructed by [BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.SubdivisionStrategy](#bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.subdivisionstrategy) that
is not cut by the interface.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.CutCellQuadRuleFactory.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.subdivision.cutcellquadrulefactory.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy <a id="bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy"></a>

**Summary:** Defines the interface for algorithms that determine how to subdivide a
simplex into sub-simplices.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy.RefElement <a id="bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy.refelement"></a>
**Summary:** The simplex to be subdivided.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy.GetSubdivisionNodes(BoSSS.Foundation.Grid.ExecutionMask) <a id="bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy.getsubdivisionnodes(bosss.foundation.grid.executionmask)"></a>
**Summary:** Constructs the nodes that divide the subdivisions for all elements
of 'mask'. Depending on the strategy, the
subdivision may or may not vary from element to element.
**Parameter:** `mask` - A mask containing all elements (cells or edges) for which the nodes
should be computed.
**Returns:**
The subdivision nodes for each element in 'mask',
where elements with the same set of subdivision nodes are grouped
into a chunk. The chunks are subsets are subsets of the chunk of
the given mask.

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode"></a>

**Summary:** A subdivision node that maps the nodes of a [BoSSS.Foundation.Grid.RefElements.RefElement](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement)
(see [BoSSS.Foundation.XDG.Quadrature.Subdivision.ISubdivisionStrategy.RefElement](#bosss.foundation.xdg.quadrature.subdivision.isubdivisionstrategy.refelement)) to some sub-simplex.
The set of all subdivision nodes for one element (i.e., either cell or
edge) must cover the whole simplex _and_ the sub-simplices must be
disjoint.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.nullSubdivisionsNodes <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.nullsubdivisionsnodes"></a>
**Summary:** Cache for [BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.NullSubdivisionNode(System.Int32)](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.nullsubdivisionnode(system.int32)).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.#ctor(BoSSS.Platform.LinAlg.AffineTrafo) <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.#ctor(bosss.platform.linalg.affinetrafo)"></a>
**Summary:** Constructs an uncut subdivision node defined by the given
transformation.
**Parameter:** `transformation` - The transformation that transforms the vertices of the original
simplex to the vertices of the sub-simplex represented by this
node.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.#ctor(BoSSS.Platform.LinAlg.AffineTrafo,System.Boolean) <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.#ctor(bosss.platform.linalg.affinetrafo,system.boolean)"></a>
**Summary:** Constructs a subdivision node defined by the given transformation.
**Parameter:** `transformation` - The transformation that transforms the vertices of the original
simplex to the vertices of the sub-simplex represented by this
node.
**Parameter:** `isCut` - Defines whether this node is considered is cut by the interface.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.Transformation <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.transformation"></a>
**Summary:** The transformation that transforms the vertices of the original
simplex to the vertices of the sub-simplex represented by this
node.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.IsCut <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.iscut"></a>
**Summary:** Returns true of the given subdivision node is (potentially) cut by
the interface


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.NullSubdivisionNode(System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.nullsubdivisionnode(system.int32)"></a>
**Summary:** The ('spatialDimension' + 1)-dimensional identity
transformation representing a node which does not subdivide the
original simplex.
**Parameter:** `spatialDimension` - The spatial dimension of the simplex to (not) divide.
**Returns:**
A subdivision node with an identity transformation.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.Equals(System.Object) <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.equals(system.object)"></a>
**Summary:** See [BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.Equals(BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode)](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.equals(bosss.foundation.xdg.quadrature.subdivision.subdivisionnode))
**Parameter:** `obj` - See **System.Object.Equals(System.Object)**
**Returns:**
See [BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.Equals(BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode)](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.equals(bosss.foundation.xdg.quadrature.subdivision.subdivisionnode))


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.GetHashCode <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.gethashcode"></a>
**Summary:** Creates a hash code based on the hash codes of [BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.IsCut](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.iscut)
and [BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.Transformation](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.transformation).
**Returns:**
A hash code


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.Equals(BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode) <a id="bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.equals(bosss.foundation.xdg.quadrature.subdivision.subdivisionnode)"></a>
**Summary:** Equality check.
**Parameter:** `other` - The object to be checked against.
**Returns:**
True, if both objects have the same [BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.Transformation](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.transformation)
and the same value for [BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode.IsCut](#bosss.foundation.xdg.quadrature.subdivision.subdivisionnode.iscut). False, otherwise.

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset"></a>

**Summary:** Represents as set of vertices (i.e., each vertex is unique) and
associates them with unique ids, e.g. in order to allow for an
efficient checking for duplicates. Additionally, sets can be nested
which enables the usage of "layers of vertices". This can be useful if
vertices should be kept in distinct sets while, at the same time, a
vertex must not be contained in both sets (i.e. a set and its parent
set are distinct).

**Remark:**
Throughout this class, the word "local" refers to properties associated
with this set alone (i.e., not considering potential ancestors) while
"global" refers to properties with this set and all of its
ancestors.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.EPS <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.eps"></a>
**Summary:** The minimum distance below which two vertices are considered equal.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.listOfVertices <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.listofvertices"></a>
**Summary:** The vertex storage. The implementation ensures that this is
actually a set (and not a list) of vertices.
**Remark:**
We cannot use one of the built-in set implementations since this
would either be rather inefficient or, if using an ordered set,
require a complete ordering of the vertices which is not possible
(without loosing the ability to look for vertices that are the
same up to [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.EPS](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.eps)).


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.normToVertexIndexMap <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.normtovertexindexmap"></a>
**Summary:** A mapping between the norm of a vertex (see
[BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.Norm](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.norm)) and the indices to all vertices in
[BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.listOfVertices](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.listofvertices) that have the same norm.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.localVerticesAsArray <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.localverticesasarray"></a>
**Summary:** Cache for [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.LocalVertices](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.localvertices).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.#ctor(System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.#ctor(system.int32)"></a>
**Summary:** Constructs an empty set without any ancestors.
**Parameter:** `spatialDimension` - The spatial dimension of the vertices.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.#ctor(bosss.foundation.xdg.quadrature.subdivision.nestedvertexset)"></a>
**Summary:** Constructs an "empty" set based on 'parrentSet'.
**Parameter:** `parrentSet` - A parrent containing vertices that cannot be added to this set
because they're considered duplicates.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.NumberOfLocalVertices <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.numberoflocalvertices"></a>
**Summary:** The number of vertices contained in this set (i.e., not counting
the vertices in [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Parrent](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.parrent)).


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.SpatialDimension <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.spatialdimension"></a>
**Summary:** The spatial dimension of the vertices contained in this set.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Parrent <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.parrent"></a>
**Summary:** An (optional) parrent set. Any vertices in [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Parrent](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.parrent)
cannot be added to this set because they're considered duplicates.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.LocalVertices <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.localvertices"></a>
**Summary:** Returns an array of all vertices contained in this set (but not the
vertices contained in [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Parrent](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.parrent)). This operation is
cached (that is, if no vertices have been added since the last
call).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.RegisterVertex(System.Double[]) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.registervertex(system.double[])"></a>
**Summary:** Registers a new vertex in the set if it is not already present in
this set or one of its ancestors.
**Parameter:** `vertex` - An array containing the spatial coordinates of the vertex.
**Returns:**
The unique index of the vertex 'vertex' (i.e., the
index is unique within this set and its ancestors). This might be a
new index (if the vertex was previously unknown) or an existing
index (if the vertex is already present in this set or one of its
ancestors).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.VertexIsContainedInLocalSet(System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertexiscontainedinlocalset(system.int32)"></a>
**Summary:** Checks whether the given index 'globalVertexIndex'
is associated with a vertex in this set (i.e., ancestors are
not considered)
**Parameter:** `globalVertexIndex` - The index in question.
**Returns:**
True, if the vertex identified by
'globalVertexIndex' is contained in this set.
Otherwise, false is returned.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.GetLocalFromGlobalVertexIndex(System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.getlocalfromglobalvertexindex(system.int32)"></a>
**Summary:** Transforms the given index 'globalVertexIndex'
into a local vertex index (i.e., an index in the range
[0, [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.NumberOfLocalVertices](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.numberoflocalvertices)]
**Parameter:** `globalVertexIndex` - 
**Returns:**
The local index in the range [0, [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.NumberOfLocalVertices](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.numberoflocalvertices)]
associated with 'globalVertexIndex'.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.GetVertex(System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.getvertex(system.int32)"></a>
**Summary:** Retrieves a vertex by its global id.
**Parameter:** `globalVertexIndex` - The global id of the vertex to be retrieved.
**Returns:**
The spatial coordinates of the vertex with global id
'globalVertexIndex'.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.GetGlobalVertexIndex(BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex@) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.getglobalvertexindex(bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex@)"></a>
**Summary:** Tries to determine the global vertex index associated with the
given vertex.
**Parameter:** `vertex` - The vertex in question.
**Returns:**
The global vertex id of 'vertex' if it is
contained in this set or one of its ancestors. Otherwise, -1 will
be returned.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.GetLocalVertexIndex(BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex@) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.getlocalvertexindex(bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex@)"></a>
**Summary:** Tries to determine the local vertex index associated with the given
vertex.
**Parameter:** `vertex` - The vertex in question.
**Returns:**
The local vertex id of 'vertex' if it is
contained in this set. Otherwise, -1 will be returned.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.IndexOffset <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.indexoffset"></a>
**Summary:** The offset when transforming between local und global coordinates.
Obviously, this is equal to the number of vertices contained in all
ancestors of this set.

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex"></a>

**Summary:** A vertex (i.e., a point). Mainly exists because it caches the norm
of the vertex.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.coordinates <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.coordinates"></a>
**Summary:** [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.Coordinates](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.coordinates).


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.norm <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.norm"></a>
**Summary:** [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.Norm](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.norm).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.#ctor(System.Double[]) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.#ctor(system.double[])"></a>
**Summary:** Constructs a new vertex with spatial coordinates
'coordinates' and calculates the
[BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.Norm](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.norm) of the vertex.
**Parameter:** `coordinates` - 


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.Coordinates <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.coordinates"></a>
**Summary:** The spatial coordinates of the vertex.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex.Norm <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex.norm"></a>
**Summary:** Some norm of the coordinates of this vertex.
**Remark:**
Currently this is the squared L2-norm because we can calculate
it efficiently and do not care about the real norm.

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.VertexNormComparer <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertexnormcomparer"></a>

**Summary:** Compares two vertices based on their norm. In order to do so, it
consumes their indices into [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.VertexNormComparer.listOfVertices](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertexnormcomparer.listofvertices) and uses
the cached norm to impose the ordering. Is used for the ordering of
[BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.normToVertexIndexMap](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.normtovertexindexmap).


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.VertexNormComparer.listOfVertices <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertexnormcomparer.listofvertices"></a>
**Summary:** A list containing the vertices to be compared.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.VertexNormComparer.#ctor(System.Collections.Generic.List{BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.Vertex}) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertexnormcomparer.#ctor(system.collections.generic.list{bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertex})"></a>
**Summary:** Constructs a comparer for vertices in
'listOfVertices'.
**Parameter:** `listOfVertices` - Vertices to be compared.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.VertexNormComparer.Compare(System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertexnormcomparer.compare(system.int32,system.int32)"></a>
**Summary:** Compares the vertices identified by their local indices (i.e.,
the indicies into [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.VertexNormComparer.listOfVertices](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.vertexnormcomparer.listofvertices)).
**Parameter:** `x` - First operand
**Parameter:** `y` - Second operand
**Returns:**
**System.Collections.Generic.IComparer`1.Compare(`0,`0)**

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2 <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2"></a>

**Summary:** Variant of **System.Collections.SortedList** (which, in fact, is a
list-backed sorted dictionary rather than a list). That allows
multiple values per key and provides an efficient method for
iterating over the values in a range of keys (see 
[BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.ValuesInRange(`0,`0)](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.valuesinrange(`0,`0))).


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.storage <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.storage"></a>
**Summary:** The main part of the class which actually holds the data.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Add(`0,`1) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.add(`0,`1)"></a>
**Summary:** Varient of [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Add(`0,System.Collections.Generic.ICollection{`1})](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.add(`0,system.collections.generic.icollection{`1})) which
allows adding a single value (instead of a list of values).
**Parameter:** `key` - The descired dictionary key.
**Parameter:** `value` - The value to be stored.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.ValuesInRange(`0,`0) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.valuesinrange(`0,`0)"></a>
**Summary:** Provides an efficient iterator for all values whose keys are in
the range ['fromKey','toKey']
(borders excluded).
**Parameter:** `fromKey` - The start of the range.
**Parameter:** `toKey` - The end of the range.
**Returns:**
In iterator containing all values from (key, value) for which 
'fromKey' < key < 'toKey'
holds.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Add(`0,System.Collections.Generic.ICollection{`1}) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.add(`0,system.collections.generic.icollection{`1})"></a>
**Summary:** **System.Collections.Generic.IDictionary`2.Add(`0,`1)**
**Parameter:** `key` - **System.Collections.Generic.IDictionary`2.Add(`0,`1)**
**Parameter:** `values` - **System.Collections.Generic.IDictionary`2.Add(`0,`1)**
**Remark:**
Leaves are currently stored as standard
**System.Collections.Generic.List`1**s. This may change in the future.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.ContainsKey(`0) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.containskey(`0)"></a>
**Summary:** **System.Collections.Generic.IDictionary`2.ContainsKey(`0)**
**Parameter:** `key` - **System.Collections.Generic.IDictionary`2.ContainsKey(`0)**
**Returns:**
**System.Collections.Generic.IDictionary`2.ContainsKey(`0)**


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Keys <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.keys"></a>
**Summary:** **System.Collections.Generic.IDictionary`2.Keys**


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Remove(`0) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.remove(`0)"></a>
**Summary:** **System.Collections.Generic.IDictionary`2.Remove(`0)**

**System.Collections.Generic.IDictionary`2.Remove(`0)**


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.TryGetValue(`0,System.Collections.Generic.ICollection{`1}@) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.trygetvalue(`0,system.collections.generic.icollection{`1}@)"></a>
**Summary:** **System.Collections.Generic.IDictionary`2.TryGetValue(`0,`1@)**

**System.Collections.Generic.IDictionary`2.TryGetValue(`0,`1@)**


**System.Collections.Generic.IDictionary`2.TryGetValue(`0,`1@)**


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Values <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.values"></a>
**Summary:** **System.Collections.Generic.IDictionary`2.Values**


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Item(`0) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.item(`0)"></a>
**Summary:** **System.Collections.Generic.IDictionary`2.Item(`0)**

**System.Collections.Generic.IDictionary`2.Item(`0)**


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Add(System.Collections.Generic.KeyValuePair{`0,System.Collections.Generic.ICollection{`1}}) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.add(system.collections.generic.keyvaluepair{`0,system.collections.generic.icollection{`1}})"></a>
**Summary:** **System.Collections.Generic.ICollection`1.Add(`0)**
**Parameter:** `item` - **System.Collections.Generic.ICollection`1.Add(`0)**


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Clear <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.clear"></a>
**Summary:** **System.Collections.Generic.ICollection`1.Clear**


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Contains(System.Collections.Generic.KeyValuePair{`0,System.Collections.Generic.ICollection{`1}}) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.contains(system.collections.generic.keyvaluepair{`0,system.collections.generic.icollection{`1}})"></a>
**Summary:** **System.Collections.Generic.ICollection`1.Contains(`0)**
**Parameter:** `item` - **System.Collections.Generic.ICollection`1.Contains(`0)**
**Returns:**
True, if all elements in 'item'.Value are
associated with the key 'item'.Key in this
dictionary. Otherwise, false is returned.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.CopyTo(System.Collections.Generic.KeyValuePair{`0,System.Collections.Generic.ICollection{`1}}[],System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.copyto(system.collections.generic.keyvaluepair{`0,system.collections.generic.icollection{`1}}[],system.int32)"></a>
**Summary:** **System.Collections.Generic.ICollection`1.CopyTo(`0[],System.Int32)**
**Parameter:** `array` - **System.Collections.Generic.ICollection`1.CopyTo(`0[],System.Int32)**
**Parameter:** `arrayIndex` - **System.Collections.Generic.ICollection`1.CopyTo(`0[],System.Int32)**


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Count <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.count"></a>
**Summary:** **System.Collections.Generic.ICollection`1.Count**


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.IsReadOnly <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.isreadonly"></a>
**Summary:** **System.Collections.Generic.ICollection`1.IsReadOnly**


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.Remove(System.Collections.Generic.KeyValuePair{`0,System.Collections.Generic.ICollection{`1}}) <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.remove(system.collections.generic.keyvaluepair{`0,system.collections.generic.icollection{`1}})"></a>
**Summary:** Tries to remove all values in 'item'.Value
from the entry associated with 'item'.Key.
**Parameter:** `item` - **System.Collections.Generic.ICollection`1.Remove(`0)**
**Returns:**
True, if at least one item has been removed. Otherwise, false
will be returned.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.GetEnumerator <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.getenumerator"></a>
**Summary:** **System.Collections.Generic.IEnumerable`1.GetEnumerator**
**Returns:**
**System.Collections.Generic.IEnumerable`1.GetEnumerator**


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet.OrderedMultiDictionary`2.System#Collections#IEnumerable#GetEnumerator <a id="bosss.foundation.xdg.quadrature.subdivision.nestedvertexset.orderedmultidictionary`2.system#collections#ienumerable#getenumerator"></a>
**Summary:** **System.Collections.IEnumerable.GetEnumerator**
**Returns:**
**System.Collections.IEnumerable.GetEnumerator**

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree"></a>

**Summary:** Represents a subdivision-tree for a given [BoSSS.Foundation.Grid.RefElements.RefElement](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement). The
tree is a $n-tree where $n is the number of subdivisions for the
simplex (see [BoSSS.Foundation.Grid.RefElements.RefElement.GetSubdivisionTree(System.Int32)](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement.getsubdivisiontree(system.int32))).


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.refElement <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.refelement"></a>
**Summary:** The simplex to be subdivided


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.treeRoot <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.treeroot"></a>
**Summary:** The root node of the subdivision tree


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.depth <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.depth"></a>
**Summary:** The current depth of the tree


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.savedDepth <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.saveddepth"></a>
**Summary:** The depth of the tree at the last savepoint (see
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.SetSavePoint](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.setsavepoint)).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.#ctor(BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[]) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.#ctor(bosss.foundation.grid.refelements.refelement,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[])"></a>
**Summary:** Constructs a new tree with depth zero.
**Parameter:** `refElement` - The simplex to be subdivided
**Parameter:** `vertexSet` - A container for the vertices of the subdivisions simplices. Must
already contain the vertices of the root simplex.
**Parameter:** `rootVertexIndices` - Indices of the vertices of the root simplex in
'vertexSet'.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.SetSavePoint <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.setsavepoint"></a>
**Summary:** Takes a snapshot of the current tree. If
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.ResetToSavePoint](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.resettosavepoint) is called, this state will be
restored. This can be useful if a minimal number of subdivisions
of a simplex should be present in all cells.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.ResetToSavePoint <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.resettosavepoint"></a>
**Summary:** Restores the state after the last call to
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.SetSavePoint](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.setsavepoint).


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.ReadDistances(ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.readdistances(ilpsp.multidimensionalarray)"></a>
**Summary:** Distributes the given distance information to the leaves of this
tree (see [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Leaves](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.leaves)). A "distance", in this context,
denotes the signed distance to the interface to which this tree
should adapt.
**Parameter:** `distances` - A one-dimensional array containing the distances of the nodes of
the current leaves of the tree (see [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Leaves](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.leaves)). The
ordering of the distances corresponds to the ordering defined by
the [BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset) associated with the leaves.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Subdivide(BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Boolean,System.Double) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.subdivide(bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.boolean,system.double)"></a>
**Summary:** Subdivides all leaves of the current tree (see
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Leaves](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.leaves)) that can be considered "cut" by the
interface. A node is considered cut if the distances (provided via
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.ReadDistances(ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.readdistances(ilpsp.multidimensionalarray))) have different signs at the vertices
of a leave _or_ if the distance of at least one vertex is
smaller than 'minDistance'.
**Parameter:** `refinedVertexSet` - The vertex set that should hold the vertices of the newly created
nodes associated with the new leaves of the tree.
**Parameter:** `checkIsCut` - If true, leaves will only subdivided of it is considered cut. If
false, all leaves will be subdivided indifferently.
**Parameter:** `minDistance` - The minimum distance a vertx of a leave may have before the leave
is considered cut.
**Remark:**
The parameter 'minDistance' can be used to ensure
that all cut cells are captured in the case of a non-linear
interface. Here, the simple check if all vertex-distances have the
same sign is not sufficient since a curved interface can pass
through a cell without enclosing a vertex.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Leaves <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.leaves"></a>
**Summary:** All leaves of this tree.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.CollectLeavesRecursively(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Collections.Generic.List{BoSSS.Foundation.XDG.Quadrature.Subdivision.SubdivisionNode}) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.collectleavesrecursively(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.collections.generic.list{bosss.foundation.xdg.quadrature.subdivision.subdivisionnode})"></a>
**Summary:** Recursively collects all leaves of this tree.
**Parameter:** `node` - The root of the current branch of the recursion.
**Parameter:** `list` - On exit: Contains all leaves of this tree.

## Class: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node"></a>

**Summary:** A node of the subdivisions tree.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.level <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.level"></a>
**Summary:** [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo))


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.distances <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.distances"></a>
**Summary:** The distances of the vertices of this node to the interface.
The i-th entry belongs to the vertex with global index
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.globalVertexIndices](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.globalvertexindices)[i] in[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.vertexSet](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.vertexset).


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.owner <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.owner"></a>
**Summary:** The owner of this node.


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.globalVertexIndices <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.globalvertexindices"></a>
**Summary:** [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo))


### Field: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.vertexSet <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.vertexset"></a>
**Summary:** [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo))


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo)"></a>
**Summary:** Constructs a root node of a tree.
**Parameter:** `owner` - The creator of this object.
**Parameter:** `level` - The level of this node in the subdivision tree, i.e. the number
of ancestors.
**Parameter:** `vertexSet` - The set containing all vertices of all nodes on this
level of the subdivision tree (i.e., of this node and its
siblings).
**Parameter:** `vertexIndices` - The indices of the vertices of this node in
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.vertexSet](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.vertexset).
**Parameter:** `transformationFromRoot` - The affine transformation that transforms a vertex of the root
simplex to a vertex of this node.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo)"></a>
**Summary:** Creates a new child of 'parrent'.
**Parameter:** `owner` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo))
**Parameter:** `parrent` - The parrent of this node.
**Parameter:** `level` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo))
**Parameter:** `vertexSet` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo))
**Parameter:** `vertexIndices` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo))
**Parameter:** `transformationFromRoot` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo))


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.Children <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.children"></a>
**Summary:** All children of this nodes in the tree.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.SubdivideLeaves(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.subdivideleaves(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset)"></a>
**Summary:** Tells the node to subdivide itself if it is a leave of the
tree. If it is not a tree, the command is passed down to all
children.
**Parameter:** `leavesLevel` - The current depth of tree.
**Parameter:** `refinedVertexSet` - The vertex set that, on exit, holds the newly added vertices
of the new nodes.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.SubdivideCutLeaves(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Double) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.subdividecutleaves(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.double)"></a>
**Summary:** Tells the node to subdivide itself if it is a leave of the
tree. If it is not a tree, the command is passed down to all
children. In contrast to
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.SubdivideLeaves(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.subdivideleaves(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset)), nodes
are only cut if they are (potentially) cut be the interface.
**Parameter:** `leavesLevel` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.SubdivideLeaves(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.subdivideleaves(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset))
**Parameter:** `refinedVertexSet` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.SubdivideLeaves(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.subdivideleaves(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset))
**Parameter:** `minDistance` - The minimum distance a node may have from the interface before
the node is considered cut (even though the signs of the
distances in all vertices are the same). In the case of curved
interfaces, this is necessary to fix certain corner cases.
**Returns:**
True, if at least one node has been subdivided. Otherwise,
false is returned.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.ReadDistances(System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.readdistances(system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Passes the given distances to the leaves of tree where the
information is stored and used by [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.IsCut](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.iscut).
**Parameter:** `leavesLevel` - The current depth of the tree.
**Parameter:** `newDistances` - A one-dimensional array containing the distances of the nodes of
the current leaves of the tree. The ordering of the distances
corresponds to the ordering defined by the
[BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet](#bosss.foundation.xdg.quadrature.subdivision.nestedvertexset) (see
[BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.#ctor(BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree,System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Int32[],BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.#ctor(bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree,system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.int32[],bosss.platform.linalg.affinetrafo)))
associated with the leaves.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.Reset(System.Int32) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.reset(system.int32)"></a>
**Summary:** Clears all information stored in this node (i.e., the distances
to the interface). Additionally:


For nodes with level smaller than
'cutOffDepth': Resets all children


For nodes with level equal to 'cutOffDepth':
Deletes all children
**Parameter:** `cutOffDepth` - The minimal depth the tree must have after the reset. In other
words: After the reset, will have this depth.


### Property: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.IsCut <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.iscut"></a>
**Summary:** [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.IsPotentiallyCut(System.Double)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.ispotentiallycut(system.double))(0.0)
**Remark:**
Assuming minDistance = 0.0 is potentially harmful but so far,
no negative (or negligible) effects have been observed. A safer
way to do this (that would even relief us from the burden of
having to evaluate the level set in the leaves), would be to
simply consider all leaves as cut. However, numerical tests
suggest this is more expensive (since more leaves are
considered cut) and does not really improve the accuracy.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.IsPotentiallyCut(System.Double) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.ispotentiallycut(system.double)"></a>
**Summary:** Checks whether this node is cut by the interface. That is, it
checks if the signs of the distances in all vertices are the
same _and_ if all nodes have an absolute distance greater than
'minDistance'.
**Parameter:** `minDistance` - The minimal absolute distance a node may have before it is
considered cut.
**Returns:**
True, if the distances of the signs of the distances of the
vertices vary _or_ at least one vertex has an absolute distance
smaller than 'minDistance'. Otherwise, false
is returned.


## Method: BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.SubdivideLeaves(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Boolean,System.Double) <a id="bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.subdivideleaves(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.boolean,system.double)"></a>
**Summary:** Subdivides the leaves of thee tree.
**Parameter:** `leavesLevel` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.SubdivideCutLeaves(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Double)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.subdividecutleaves(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.double)).
**Parameter:** `refinedVertexSet` - [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.SubdivideCutLeaves(System.Int32,BoSSS.Foundation.XDG.Quadrature.Subdivision.NestedVertexSet,System.Double)](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.subdividecutleaves(system.int32,bosss.foundation.xdg.quadrature.subdivision.nestedvertexset,system.double)).
**Parameter:** `checkIsCut` - If true, leaves will only be subdivided if [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.IsCut](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.iscut)
returns true.
**Parameter:** `minDistance` - See [BoSSS.Foundation.XDG.Quadrature.Subdivision.SimplexSubdivisionTree.Node.IsCut](#bosss.foundation.xdg.quadrature.subdivision.simplexsubdivisiontree.node.iscut).
**Returns:**
True, if at least one node has been subdivided. Otherwise,
false is returned.

## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories"></a>

**Summary:** Provides a factory configuration for processing double cut cells based on specified parameters.
There are two types of integration: surface and volume
There are two types of frames: cell inner domain and cell boundary (will be then transformed into edge rules)


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData[],BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata[],bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** This would return a factory object with the configuration
**Parameter:** `lvlsets` - level set data
**Parameter:** `e` - reference element


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.m_SurfaceRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.m_surfacerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.m_VolumeRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.m_volumerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.m_EdgeRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.m_edgerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.m_CellBoundarySurfaceRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.m_cellboundarysurfacerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.m_CellBoundaryVolumeRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.m_cellboundaryvolumerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule

## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutBaseFactory`1 <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutbasefactory`1"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutBaseFactory`1.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutbasefactory`1.getquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** Returns the quadrature rule of given order for each cell in mask.
**Parameter:** `mask` - Cell mask for which quadrature nodes are requested
**Parameter:** `RequestedOrder` - Order of quadrature
**Returns:**
An array of quadrature rules for cells in mask


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutBaseFactory`1.GetSpecies <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutbasefactory`1.getspecies"></a>
**Summary:** Get array index of the species requested for Algoim data. 
**ilPSP.Utils.Algoim.GetSurfaceQuadratureRules(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32[],System.Int32[],System.Double[],System.Double[],System.Double[],System.Double[])**
**ilPSP.Utils.Algoim.GetVolumeQuadratureRules(System.Int32,System.Int32,System.Int32,System.Int32,System.Int32[],System.Int32[],System.Double[],System.Double[],System.Double[],System.Double[])**
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutBaseFactory`1.CreatePhiDataForEdge(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutbasefactory`1.createphidataforedge(bosss.foundation.xdg.levelsettracker.levelsetdata,system.int32,system.int32)"></a>
**Summary:** slight modified version to query points on the edge
**Parameter:** `lsData` - 
**Parameter:** `jCell` - 
**Parameter:** `edgeIndex` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutBaseFactory`1.GetNodesAndWeights(System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutbasefactory`1.getnodesandweights(system.int32,system.int32)"></a>
**Summary:** Get the quadrature nodes and weights for a cell. (either surface or volume, declared at the instantiation of the factory)
**Parameter:** `jCell` - local index of the cell
**Parameter:** `RequestedOrder` - requested order for quadrature
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutSurfaceFactory <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutsurfacefactory"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutSurfaceFactory.GetNodesAndWeights(System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutsurfacefactory.getnodesandweights(system.int32,system.int32)"></a>
**Summary:** Get the quadrature nodes and weights for a cell. (either surface or volume, declared at the instantiation of the factory)
**Parameter:** `jCell` - local index of the cell
**Parameter:** `RequestedOrder` - requested order for quadrature
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutSurfaceFactory.DivideQuadRules(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,System.Int32,BoSSS.Foundation.Quadrature.QuadRule) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutsurfacefactory.dividequadrules(bosss.foundation.xdg.levelsettracker.levelsetdata,system.int32,bosss.foundation.quadrature.quadrule)"></a>
**Summary:** Divides the quadrature rule depending on the value of level set into two
**Parameter:** `lsData` - 
**Parameter:** `jCell` - 
**Parameter:** `quadRule` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutVolumeFactory <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutvolumefactory"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutVolumeFactory.GetNodesAndWeights(System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutvolumefactory.getnodesandweights(system.int32,system.int32)"></a>
**Summary:** Get the quadrature nodes and weights for a cell. (either surface or volume, declared at the instantiation of the factory)
**Parameter:** `jCell` - local index of the cell
**Parameter:** `RequestedOrder` - requested order for quadrature
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutCellBoundaryVolFactory <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutcellboundaryvolfactory"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutCellBoundaryVolFactory.CombineEdgeRules(BoSSS.Foundation.Quadrature.QuadRule[]) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutcellboundaryvolfactory.combineedgerules(bosss.foundation.quadrature.quadrule[])"></a>
**Summary:** Combines different edge rules into a single CellBoundaryQuadRule rule.
**Parameter:** `rules` - An array of edge rules to be combined.
**Returns:**
A combined CellBoundaryQuadRule with arranged NumbersOfNodesPerFace.

## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutCellBoundarySurfFactory <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutcellboundarysurffactory"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimDoubleCutFactories.AlgoimDoubleCutCellBoundarySurfFactory.CombineEdgeRules(BoSSS.Foundation.Quadrature.QuadRule[]) <a id="bosss.foundation.xdg.quadrature.algoim.algoimdoublecutfactories.algoimdoublecutcellboundarysurffactory.combineedgerules(bosss.foundation.quadrature.quadrule[])"></a>
**Summary:** Combines different edge rules into a single CellBoundaryQuadRule rule.
**Parameter:** `rules` - An array of edge rules to be combined.
**Returns:**
A combined CellBoundaryQuadRule with arranged NumbersOfNodesPerFace.

## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories"></a>

**Summary:** Provides a factory configuration for processing based on specified parameters.


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Grid.RefElements.RefElement,System.Boolean,System.Boolean) <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.grid.refelements.refelement,system.boolean,system.boolean)"></a>
**Summary:** This would return a factory object with the configuration
**Parameter:** `ls` - level set data
**Parameter:** `e` - reference element
**Parameter:** `negativeLevelSet` - are the negative level sets considered (default positive, i.e., ls > 0)
**Parameter:** `callSurfaceAndVolumeAtOnce` - if enabled, performs calculation of volume and surface rules at once to reduce computational cost. 
(it can cause redundancy if both are not required at the same time)


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.SurfaceAndVolumeAtOnce <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.surfaceandvolumeatonce"></a>
**Summary:** Enables combined surface and volume quadrature rule calls with caching to avoid repeated polynomial interpolations. This speeds up computations when both rules are needed but may cause unnecessary calculations if only one rule is required.


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.VolumeSign <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.volumesign"></a>
**Summary:** A boolean to change the sign of level set. true: negative level set, false: positive level set (ls > 0).


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.m_SurfaceRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.m_surfacerules"></a>
**Summary:** - key: quadrature order 
- value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.m_CellBoundaryRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.m_cellboundaryrules"></a>
**Summary:** - key: quadrature order 
- value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.m_EdgeRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.m_edgerules"></a>
**Summary:** - key: quadrature order 
- value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.m_VolumeRules <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.m_volumerules"></a>
**Summary:** - key: quadrature order 
- value: quadrature rule

## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.AlgoimFactory <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.algoimfactory"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.AlgoimFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.algoimfactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** Returns the quadrature rule of given order for each cell in mask.
**Parameter:** `mask` - Cell mask for which quadrature nodes are requested
**Parameter:** `RequestedOrder` - Order of quadrature
**Returns:**
An array of quadrature rules for cells in mask


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.AlgoimFactory.CalculateQuadRuleSetCombo(System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.algoimfactory.calculatequadrulesetcombo(system.int32)"></a>
**Summary:** Combo rule calculation for surface and volume rules at the same time. Returns the values of either but stores both in cache once calculated
**Parameter:** `RequestedOrder` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.AlgoimFactory.GetNodesAndWeights(System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.algoimfactory.getnodesandweights(system.int32,system.int32)"></a>
**Summary:** Get the quadrature nodes and weights for a cell. (either surface or volume, declared at the instantiation of the factory)
**Parameter:** `jCell` - local index of the cell
**Parameter:** `RequestedOrder` - requested order for quadrature
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.AlgoimFactory.GetNodesAndWeightsCombo(System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.algoimfactory.getnodesandweightscombo(system.int32,system.int32)"></a>
**Summary:** GetNodesAndWeightsCombo (both for surface and volume at the same time)
**Parameter:** `jCell` - local index of the cell
**Parameter:** `RequestedOrder` - requested order for quadrature
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.AlgoimCellBoundaryFactory <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.algoimcellboundaryfactory"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories.AlgoimCellBoundaryFactory.CombineEdgeRules(BoSSS.Foundation.Quadrature.QuadRule[]) <a id="bosss.foundation.xdg.quadrature.algoim.algoimfactories.algoimcellboundaryfactory.combineedgerules(bosss.foundation.quadrature.quadrule[])"></a>
**Summary:** Combines different edge rules into a single CellBoundaryQuadRule rule.
**Parameter:** `rules` - An array of edge rules to be combined.
**Returns:**
A combined CellBoundaryQuadRule with arranged NumbersOfNodesPerFace.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadratureScheme <a id="bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadraturescheme"></a>

**Summary:** A quadrature scheme for [BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule](#bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadratureScheme.#ctor(System.Boolean,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadraturescheme.#ctor(system.boolean,bosss.foundation.grid.cellmask)"></a>
**Summary:** Default constructor.
**Parameter:** `useDefaultFactories` - 
**Parameter:** `domain` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadratureScheme.#ctor(System.Boolean,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule},BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadraturescheme.#ctor(system.boolean,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule},bosss.foundation.grid.cellmask)"></a>
**Summary:** Alternative constructor that saves a single call to
[BoSSS.Foundation.Quadrature.QuadratureScheme`2.AddFactoryDomainPair(BoSSS.Foundation.Quadrature.IQuadRuleFactory{`0},`1,System.Nullable{System.Int32})](BoSSS.Foundation.md#bosss.foundation.quadrature.quadraturescheme`2.addfactorydomainpair(bosss.foundation.quadrature.iquadrulefactory{`0},`1,system.nullable{system.int32}))
**Parameter:** `useDefaultFactories` - 
**Parameter:** `factory` - 
**Parameter:** `domain` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadratureScheme.GetDefaultDomain(BoSSS.Foundation.Grid.IGridData) <a id="bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadraturescheme.getdefaultdomain(bosss.foundation.grid.igriddata)"></a>
**Summary:** Returns [BoSSS.Foundation.Grid.CellMask.GetFullMask(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.Grid.MaskType)](BoSSS.Foundation.md#bosss.foundation.grid.cellmask.getfullmask(bosss.foundation.grid.igriddata,bosss.foundation.grid.masktype))
**Parameter:** `gridData` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadratureScheme.GetDefaultRuleFactory(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadraturescheme.getdefaultrulefactory(bosss.foundation.grid.igriddata,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Returns an instance of
[BoSSS.Foundation.Quadrature.CellBoundaryFromEdgeRuleFactory`1](BoSSS.Foundation.md#bosss.foundation.quadrature.cellboundaryfromedgerulefactory`1)
**Parameter:** `gridData` - 
**Parameter:** `elem` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule <a id="bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule"></a>

**Summary:** Quadrature for the boundary of the boundary (also known as the co-faces) of a three-dimensional
cell. That is, a quadrature rule for the line elements bounding the
three-dimensional reference element.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule.CreateEmpty(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule.createempty(system.int32,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Creates an empty rule
**Parameter:** `noOfNodes` - The desired number of nodes
**Parameter:** `element` - The selected reference element
**Returns:**
A quadrature rule with 'noOfNodes' nodes where all
relevant entries are zero.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule.NumbersOfNodesPerFaceOfFace <a id="bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule.numbersofnodesperfaceofface"></a>
**Summary:** 1st index: edge index, which is a (D-1)-dimensional manifold.
2nd index: edge of edge, which is a (D-2)-dimensional manifold.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory"></a>

**Summary:** A factory for quadrature rule that creates Gaussian quadrature rules on
sub-sections of the lines bounding a reference element (cf.
[BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule](#bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule)) in the style of
[BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory](#bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.EPSILON <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.epsilon"></a>
**Summary:** Minimal distance between two points


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.lineSimplex <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.linesimplex"></a>
**Summary:** Static line element


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.referenceLineSegments <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.referencelinesegments"></a>
**Summary:** The line segments of the reference element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.jumpType <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.jumptype"></a>
**Summary:** The considered jump type, i.e. whether to integrate over the
positive region, the negative region, or over both


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.lastOrder <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.lastorder"></a>
**Summary:** The last integration order used in [BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32)](#bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)).


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.levelSetIndex <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.levelsetindex"></a>
**Summary:** The index of the level set to be considered


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.cache <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.cache"></a>
**Summary:** Cache for the quadrature rules. The key denotes the cell index
**Remark:**
Is cleared every time the level set degree (cf.
[BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.lastOrder](#bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.lastorder)) is changed level set moves (see
[BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.OnNext(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions)](#bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.onnext(bosss.foundation.xdg.levelsettracker.levelsetregions)))


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes) <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm,bosss.foundation.xdg.quadrature.hmf.jumptypes)"></a>
**Summary:** Constructor


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.RootFindingAlgorithm <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.rootfindingalgorithm"></a>
**Summary:** Algorithm used for the root search on the individual line segments


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** Returns a set of [BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule](#bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule)s that
enables the integration over sub-segments of the edges of the edges
of a (three-dimensional) domain. This is obviously only useful if
the integrand has a discontinuity that is aligned with the zero
iso-contour of the level set function.
**Parameter:** `mask` - 
**Parameter:** `order` - 
**Returns:**



### Property: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.refelement"></a>
**Summary:** The reference element


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.GetReferenceLineSegments <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.getreferencelinesegments"></a>
**Summary:** Gathers the line segments bounding [BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.RefElement](#bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.refelement) in
reference coordinates.
**Returns:**
An array of line segments

1st index: Edge index
2nd index: Edge of edge index
**Remark:**
Each line segment will appear twice in the result, since it is
stored for each edge separately. However, this method ensures that
corresponding segments are represented by the same object (reference
equality) which ensures that this does not affect performance.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.OnCompleted <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.oncompleted"></a>
**Summary:** Empty.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.OnError(System.Exception) <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.onerror(system.exception)"></a>
**Summary:** Empty.
**Parameter:** `error` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineOnEdgeQuadRuleFactory.OnNext(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions) <a id="bosss.foundation.xdg.quadrature.hmf.cutlineonedgequadrulefactory.onnext(bosss.foundation.xdg.levelsettracker.levelsetregions)"></a>
**Summary:** Clears cached quadrature rules.
**Parameter:** `value` - 

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes <a id="bosss.foundation.xdg.quadrature.hmf.jumptypes"></a>

**Summary:** Different type of jumps assumed.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes.Implicit <a id="bosss.foundation.xdg.quadrature.hmf.jumptypes.implicit"></a>
**Summary:** Function is taken as is; jump is already contained in the function


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes.Heaviside <a id="bosss.foundation.xdg.quadrature.hmf.jumptypes.heaviside"></a>
**Summary:** Function is assumed zero for negative level set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes.OneMinusHeaviside <a id="bosss.foundation.xdg.quadrature.hmf.jumptypes.oneminusheaviside"></a>
**Summary:** Function is assumed zero for positive level set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes.Sign <a id="bosss.foundation.xdg.quadrature.hmf.jumptypes.sign"></a>
**Summary:** Function is multiplied by -1 for negative level and 1 for positive
level set.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory"></a>

**Summary:** Quadrature rule factory for Gaussian integrals over edges of
two-dimensional domains that are intersected by the level set (i.e.,
integrals over cut segments)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.lineSimplex <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.linesimplex"></a>
**Summary:** The line reference element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.levelSetIndex <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.levelsetindex"></a>
**Summary:** Index of the considered level set.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.referenceLineSegments <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.referencelinesegments"></a>
**Summary:** A collection of line segments bounding the volume reference element


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.jumpType <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.jumptype"></a>
**Summary:** Determines the domain of integration, i.e. whether the rule should
be valid for positive level set values, negative level set values,
or even for both


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.lastOrder <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.lastorder"></a>
**Summary:** Stores the integration of the set of quadrature rule request last
(cf. [BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32)](#bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)))


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.cache <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.cache"></a>
**Summary:** Cache for quadrature rules

key: local cell index
value: cell boundary rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.Tolerance <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.tolerance"></a>
**Summary:** Tolerance for the sign of the level set function. Using the example
of [BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes.Heaviside](#bosss.foundation.xdg.quadrature.hmf.jumptypes.heaviside), values phi with
phi - Tolerance > 0 are considered 'positive'.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,System.Double) <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.grid.refelements.refelement,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm,bosss.foundation.xdg.quadrature.hmf.jumptypes,system.double)"></a>
**Summary:** Constructs a new factory
**Parameter:** `Kref` - Reference element index
**Parameter:** `lsData` - 
**Parameter:** `rootFindingAlgorithm` - Selected root-finding algorithm for the line segments. Default is
[BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.DefaultRootFindingAlgorithm](#bosss.foundation.xdg.quadrature.hmf.linesegment.defaultrootfindingalgorithm)
**Parameter:** `jumpType` - Determines the domain of integration, i.e. whether the rule should
be valid for positive level set values, negative level set values,
or even for both
**Parameter:** `tolerace` - Tolerance for the sign of the level set function. Using the example
of [BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes.Heaviside](#bosss.foundation.xdg.quadrature.hmf.jumptypes.heaviside), values phi with
phi - Tolerance > 0 are considered 'positive'.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.RootFindingAlgorithm <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.rootfindingalgorithm"></a>
**Summary:** The selected root-finding algorithm


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** Returns a [BoSSS.Foundation.Quadrature.CellBoundaryQuadRule](BoSSS.Foundation.md#bosss.foundation.quadrature.cellboundaryquadrule) for each cell in the
given 'mask'. This rule consists of Gaussian
quadrature rules on each continuous line segment on the edges of a
given cell (where continuous means 'not intersected by the zero
level set'
**Parameter:** `mask` - 
**Parameter:** `order` - 
**Returns:**



### Field: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.iKref <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.ikref"></a>
**Summary:** Reference element index


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.refelement"></a>
**Summary:** Selected reference element


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.GetReferenceLineSegments <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.getreferencelinesegments"></a>
**Summary:** Determines the line segments bounding the selected reference
element (cf. [BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.RefElement](#bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.refelement)) in reference coordinates
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.OnCompleted <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.oncompleted"></a>
**Summary:** Does nothing.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.OnError(System.Exception) <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.onerror(system.exception)"></a>
**Summary:** Does nothing.
**Parameter:** `error` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory.OnNext(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions) <a id="bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory.onnext(bosss.foundation.xdg.levelsettracker.levelsetregions)"></a>
**Summary:** Clears the cache.
**Parameter:** `value` - 

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis"></a>

**Summary:** Represents a basis of vector-valued, divergence-free polynomials.

Divergence-free polynomials for 2D elements

Divergence-free polynomials for 3D elements


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.refelement"></a>
**Summary:** ref elm.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.#ctor(BoSSS.Foundation.Grid.Classic.GridData,BoSSS.Foundation.Grid.RefElements.RefElement,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.#ctor(bosss.foundation.grid.classic.griddata,bosss.foundation.grid.refelements.refelement,system.int32)"></a>
**Summary:** Constructors
**Parameter:** `gridData` - 
**Parameter:** `simplex` - 
**Parameter:** `order` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.GetPolynomials(BoSSS.Foundation.Grid.Classic.GridData,BoSSS.Foundation.Grid.RefElements.RefElement,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.getpolynomials(bosss.foundation.grid.classic.griddata,bosss.foundation.grid.refelements.refelement,system.int32)"></a>
**Summary:** Retrieves all polynomial for the given 'element'


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.PolynomialsSquare <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.polynomialssquare"></a>
**Summary:** Retrieves all two-dimensional polynomials for square elements.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.InitPolynomialsSquare <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.initpolynomialssquare"></a>
**Summary:** Retrieves all two-dimensional polynomials for square elements.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.PolynomialsTriangle <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.polynomialstriangle"></a>
**Summary:** Retrieves all two-dimensional polynomials for cube elements.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.InitPolynomialsTriangle <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.initpolynomialstriangle"></a>
**Summary:** Retrieves all two-dimensional polynomials for triangles
**Returns:**



### Property: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.PolynomialsCube <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.polynomialscube"></a>
**Summary:** Retrieves all two-dimensional polynomials for cube elements.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.InitPolynomialsCube <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.initpolynomialscube"></a>
**Summary:** Retrieves all three-dimensional polynomials for cube elements.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.PolynomialsTetra <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.polynomialstetra"></a>
**Summary:** Retrieves all two-dimensional polynomials for tetrahedral elements.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.DivergenceFreeBasis.InitPolynomialsTetra <a id="bosss.foundation.xdg.quadrature.hmf.divergencefreebasis.initpolynomialstetra"></a>
**Summary:** Retrieves all three-dimensional polynomials for tetrahedral elements.
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.HMF.ExactCircleLevelSetIntegration <a id="bosss.foundation.xdg.quadrature.hmf.exactcirclelevelsetintegration"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.ExactCircleLevelSetIntegration.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.exactcirclelevelsetintegration.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.ExactCircleLevelSetIntegration.RADIUS <a id="bosss.foundation.xdg.quadrature.hmf.exactcirclelevelsetintegration.radius"></a>
**Summary:** radius for each level set

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.IAnalyticLevelSet <a id="bosss.foundation.xdg.quadrature.hmf.ianalyticlevelset"></a>

**Summary:** Common interface for analytically prescribed level sets


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.IAnalyticLevelSet.GetRoots(BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.ianalyticlevelset.getroots(bosss.foundation.xdg.quadrature.hmf.linesegment,system.int32)"></a>
**Summary:** Determines the roots of the level set on
'lineSegment' in the given
'element'.
**Parameter:** `lineSegment` - The considered line segment
**Parameter:** `element` - The index of the considered element
**Returns:**
The parameter values t of the parametrization of
'lineSegment' for which this level set is zero in
element 'element'

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2 <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2"></a>

**Summary:** One-step rules (creating 
surface rules for integrals $\oint_{\frakI \cap K_j } \ldots \dS$ and 
volume  rules for integrals $\int_{ \frakB \cap K_j } \ldots \dV$ 
in one step), using Gauss and optionally, the Stokes theorem.
Supports only 2D.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.QRF <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.qrf"></a>


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.QRF.Rules <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.qrf.rules"></a>
**Summary:** cache
key: quadrature order; 
value: cached quadrature rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.QRF.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.qrf.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.refelement"></a>
**Summary:** grid reference element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.LevelSetIndex <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.levelsetindex"></a>
**Summary:** index of the respective level-set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.SurfaceNodesOnZeroLevset <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.surfacenodesonzerolevset"></a>
**Summary:** if true, the nodes for the surface integration are 'projected' onto the zero-level-set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.Docheck <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.docheck"></a>
**Summary:** if true, the accuracy of the quadrature is checked after solution of the system


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.UseAlsoStokes <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.usealsostokes"></a>
**Summary:** if true, also Stoke's theorem is used to create the surface rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Boolean,System.Boolean,System.Boolean) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},system.boolean,system.boolean,system.boolean)"></a>
**Summary:** ctor.
**Parameter:** `_SurfaceNodesOnZeroLevset` - if true, the nodes for the surface integration are 'projected' onto the zero-level-set
**Parameter:** `_DoCheck` - if true, the accuracy of the quadrature is checked after solution of the system
**Parameter:** `_LevelSetBoundaryLineFactory` - 
**Parameter:** `cellBoundaryFactory` - 
**Parameter:** `_UseAlsoStokes` - if true, also Stoke's theorem is used to create the surface rule
**Parameter:** `lsData` - 


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.MaxGrid <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.maxgrid"></a>
**Summary:** the intersection of the cut cells for Level Set [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.LevelSetIndex](#bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.levelsetindex)
and the subgrid for reference element [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.RefElement](#bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.refelement)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.m_SurfaceRules <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.m_surfacerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.m_VolumeRules <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.m_volumerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.StokesAnsatzMatrix_RefBasis(BoSSS.Foundation.Basis,BoSSS.Foundation.NodeSet,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.stokesansatzmatrix_refbasis(bosss.foundation.basis,bosss.foundation.nodeset,system.int32)"></a>
**Summary:** Matrix (LHS) for the Stokes/curvature Ansatz, in the _reference_ coordinate system.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.tangente(System.Double[],System.Double[],System.Double[]) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.tangente(system.double[],system.double[],system.double[])"></a>
**Summary:** Computes outward-pointing tangent
**Parameter:** `SurfN` - IN: surface normal
**Parameter:** `EdgeN` - IN: edge normal
**Parameter:** `tan` - OUT: outward-pointing tangent to level-set


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetComboRuleFactory2.StokesAnsatzRHS_RefBasis(BoSSS.Foundation.Basis,BoSSS.Foundation.Quadrature.CellBoundaryQuadratureScheme,BoSSS.Foundation.Grid.CellMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetcomborulefactory2.stokesansatzrhs_refbasis(bosss.foundation.basis,bosss.foundation.quadrature.cellboundaryquadraturescheme,bosss.foundation.grid.cellmask,system.int32)"></a>
**Summary:** RHS for the Stokes/curvature Ansatz, in the _reference_ coordinate system.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeSurfaceQuadRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgesurfacequadrulefactory"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeSurfaceQuadRuleFactory.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgesurfacequadrulefactory.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeSurfaceQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule},BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgesurfacequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule},bosss.foundation.xdg.quadrature.hmf.jumptypes)"></a>
**Summary:** Ctor

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory"></a>

**Summary:** For a 3D setting, this class implements the hierarchical moment-fitting (HMF) strategy to compute
two-dimensional volume integrals over the boundaries of cells that
are intersected by the level set, i.e integrals of the form
\[
\oint_{K_j \cap \{ \vec{x}; \varphi( \vec{x} ) \lt 0 \} } f \ dS
\]
In other words: If the (planar) edge
of a three-dimensional element is intersected by the level set, this
factory applies the HMF strategy in order to create accurate quadrature
rules for the integration over the negative/positive (depending on the
jump type, see
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes)](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm,bosss.foundation.xdg.quadrature.hmf.jumptypes)))
level set region.

**Remark:**
For details about the algorithm, see
Mueller, Kummer & Oberlack: Highly accurate surface and volume
integration on implicit domains by means of moment-fitting (2013)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.jumpType <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.jumptype"></a>
**Summary:** See
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes)](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm,bosss.foundation.xdg.quadrature.hmf.jumptypes))


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.CoFaceQuadRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.cofacequadrulefactory"></a>
**Summary:** Factory for one-dimensional integration rules for the edges of the
edges of the three-dimensional volume element


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.edgeSurfaceRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.edgesurfacerulefactory"></a>
**Summary:** Factory for the one-dimensional integration over the intersections
of the zero iso-contour of the level set function with the edges of
the three-dimensional volume element


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.baseRule <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.baserule"></a>
**Summary:** Base rule for the optimization procedure within the HMF procedure.
In essence, provides the (fixed) integration nodes


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.signTestRule <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.signtestrule"></a>
**Summary:** Rule used to determine the sign of the level set function for
uncut edges.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.basisValuesEdge <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.basisvaluesedge"></a>
**Summary:** Values of [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis) for a single edge.

1st index: Node index
2nd index: Polynomial index


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis"></a>
**Summary:** Vector-valued moment-fitting basis constructed from the
'anti-derivatives' of a standard basis. Here, the 'anti-derivative'
of a scalar polynomial $p$  is defined as
a vector-valued polynomial
$\vec{\Lambda}$  such that
$p = \nabla \cdot \vec{\Lambda}$


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lastOrder <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lastorder"></a>
**Summary:** The requested polynomial order in the last call of
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32)](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)); used for caching


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.cache <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.cache"></a>
**Summary:** **seems to be incorrectly implemented!!!**

Cache for quadrature rules
- Key: Local cell index
- Value: Quadrature rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.levelSetIndex <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.levelsetindex"></a>
**Summary:** Index of the considered level within the level-set tracker


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm,bosss.foundation.xdg.quadrature.hmf.jumptypes)"></a>
**Summary:** Constructor
**Parameter:** `lsData` - 
**Parameter:** `rootFindingAlgorithm` - One-dimensional root-finding algorithm for determining roots of the
level set function on edges of the edges of the volume simplex.
Default is [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.DefaultRootFindingAlgorithm](#bosss.foundation.xdg.quadrature.hmf.linesegment.defaultrootfindingalgorithm)
**Parameter:** `jumpType` - Determines the level set region to be integrated over (negative
level set values, positive level set values, or both)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** Constructs the quadrature rules all edges of all cells in
'mask'. For edges that are not intersected by the
zero iso-contour, standard Gaussian quadrature rules of
sufficiently high order will be used.
**Parameter:** `mask` - Cells for which quadrature rules shall be created
**Parameter:** `order` - Desired order of the moment-fitting system. Assuming that
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.edgeSurfaceRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.edgesurfacerulefactory) integrates the basis
polynomials exactly over the zero iso-contour (which it usually
doesn't!), the resulting quadrature rules will be exact up to this
order.
**Returns:**
A set of quadrature rules
**Remark:**
Since the selected level set is generally discontinuous across cell
boundaries, this method does not make use of the fact that
neighboring cells share edges. That is, the optimization will be
performed twice for each inner edge in 'mask'.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.refelement"></a>
**Summary:** The first reference element of the grid


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.GetOptimizedRules(BoSSS.Foundation.Grid.CellMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.getoptimizedrules(bosss.foundation.grid.cellmask,system.int32)"></a>
**Summary:** Uses a moment-fitting basis of order 'order' for
determining optimal weights of a quadrature rule for a sub-region
of each edge of each cell in the given 'mask'.
**Parameter:** `mask` - Cells for which rules shall be created
**Parameter:** `order` - Desired order of the moment-fitting system. Assuming that
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.edgeSurfaceRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.edgesurfacerulefactory) integrates the basis
polynomials exactly over the zero iso-contour (which it usually
doesn't), the resulting quadrature rules will be exact up to this
order.
**Returns:**
A set of quadrature rules


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.SwitchOrder(System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.switchorder(system.int32)"></a>
**Summary:** Updates [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis), [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.baseRule](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.baserule) and
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.basisValuesEdge](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.basisvaluesedge) every time a different order is
requested in [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32)](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32))
**Parameter:** `order` - The new order of the moment-fitting basis


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.CopyWeights(BoSSS.Foundation.Quadrature.CellBoundaryQuadRule,BoSSS.Foundation.Quadrature.CellBoundaryQuadRule,System.Int32,System.Double) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.copyweights(bosss.foundation.quadrature.cellboundaryquadrule,bosss.foundation.quadrature.cellboundaryquadrule,system.int32,system.double)"></a>
**Summary:** Copies the (scaled) weights for the local edge referenced by
'localEdge' from 'source' to
'target'
**Parameter:** `source` - Source quad rule
**Parameter:** `target` - Target quad rule
**Parameter:** `localEdge` - The considered edge of the volume element (cf.
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.RefElement](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.refelement))
**Parameter:** `scaling` - Scaling applied to the weights before saving them in
'target'.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.GetNumberOfLambdas <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.getnumberoflambdas"></a>
**Summary:** Computes the number of vector-valued basis function (cf.
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis))
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.EvaluateLambdas(System.Int32,BoSSS.Foundation.Quadrature.CellBoundaryQuadRule) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.evaluatelambdas(system.int32,bosss.foundation.quadrature.cellboundaryquadrule)"></a>
**Summary:** Evaluates the vector-valued anti-derivatives defining the
moment-fitting basis (cf. [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis)) in each node
of 'rule' in cell 'cell'
**Parameter:** `cell` - Local cell index
**Parameter:** `rule` - Evaluation nodes
**Returns:**
The values of [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis) in each node of
'rule'
- 1st index: Node index
- 2nd index: Basis function index
- 3rd index: Spatial dimension
**Remark:**
This method does not evaluate a Lambda which is constant since the
derivative of such function is zero. As a result, the integral over
this function is zero, too, which makes it useless for the
construction of a quadrature rule

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature"></a>

**Summary:** Used for the computation of the integral of the basis functions
(see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis)) over the boundary of an edge. More
specifically, the boundary of the edge is given by line elements
that are potentially cut by the zero iso-contour of the level set,
which is why this requires a special treatment; see
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.CoFaceQuadRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.cofacequadrulefactory).


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.owner <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.owner"></a>
**Summary:** Owner of this object


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.noOfItemsLocally <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.noofitemslocally"></a>
**Summary:** Number of items in the current execution mask


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.Results <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.results"></a>
**Summary:** Integration results for the last call to [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.Execute](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.execute)
- 1st index: Cell index within mask provided in constructor
- 2nd index: Local edge index
- 3rd index: Basis function (see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.EvaluateLambdas(System.Int32,BoSSS.Foundation.Quadrature.CellBoundaryQuadRule)](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.evaluatelambdas(system.int32,bosss.foundation.quadrature.cellboundaryquadrule))


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.#ctor(BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule},System.Int32,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.#ctor(bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule},system.int32,bosss.foundation.grid.cellmask)"></a>
**Summary:** Constructor


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.Execute <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.execute"></a>
**Summary:** Computes the integrals while overwriting [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.Results](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.results)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.CellEdgeBoundaryQuadRule,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.evaluate(system.int32,system.int32,bosss.foundation.xdg.quadrature.hmf.celledgeboundaryquadrule,ilpsp.multidimensionalarray)"></a>
**Summary:** For each face $E$  of each cell in
the given range and for each
$\vec{\Lambda}\$  in
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis):
Computes
\[ 
\int \limits_{\partial E} \vec{\Lambda} \cdot \vec{n} H(\varphi) \;ds,
\]
where $\vec{n}$  denotes the outer
unit normal vector on $\partial E$
(**not** $E$!). Moreover,
$H$ a weight function that depends
on the level set function $\varphi$.
Typically, $H$ is given by the
Heaviside function. For more details, see
[BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory](#bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Saves the integration results to [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaEdgeBoundaryQuadrature.Results](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdaedgeboundaryquadrature.results)
**Parameter:** `i0` - 
**Parameter:** `Length` - 
**Parameter:** `ResultsOfIntegration` - 

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature"></a>

**Summary:** Used for the computation of the integral of the basis functions
(see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis)) over the intersection of the zero
iso-contour of the level set with a face. This requires a special
treatment; see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.edgeSurfaceRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.edgesurfacerulefactory).


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.owner <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.owner"></a>
**Summary:** Owner of this object


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.noOfItemsLocally <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.noofitemslocally"></a>
**Summary:** Number of items in the current execution mask


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Results <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.results"></a>
**Summary:** Integration results for the last call to [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Execute](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.execute)
- 1st index: item index within execution mask provided with constructor
- 2nd index: cell face index
- 3rd index: Basis function (see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.EvaluateLambdas(System.Int32,BoSSS.Foundation.Quadrature.CellBoundaryQuadRule)](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.evaluatelambdas(system.int32,bosss.foundation.quadrature.cellboundaryquadrule))


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.#ctor(BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Int32,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.#ctor(bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},system.int32,bosss.foundation.grid.cellmask)"></a>
**Summary:** Constructor
**Parameter:** `owner` - 
**Parameter:** `surfaceRuleFactory` - 
**Parameter:** `maxLambdaDegree` - 
**Parameter:** `mask` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Execute <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.execute"></a>
**Summary:** Computes the integrals while overwriting [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Results](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.results)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CellBoundaryQuadRule,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.evaluate(system.int32,system.int32,bosss.foundation.quadrature.cellboundaryquadrule,ilpsp.multidimensionalarray)"></a>
**Summary:** For each face $E$ of each cell in
the given range and for each
$\vec{\Lambda}$  in
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis):
Computes
\[ 
\int_{ \{ \vec{x}; \varphi(\vec{x}) = 0 \}  \cap E} \vec{\Lambda} \cdot \vec{n}_I \;ds,
\]
where $\varphi$ is the level set
function and $\vec{n}_I$  denotes the
unit normal vector on
$\varphi \cap E$ 
(**not** $E$!)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Saves the integration results to [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Results](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdalevelsetsurfacequadrature.results)

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.QRF <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.qrf"></a>


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.QRF.Rules <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.qrf.rules"></a>
**Summary:** cache
key: quadrature order; 
value: cached quadrature rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.QRF.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.qrf.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2 <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2"></a>


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.Kref <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.kref"></a>
**Summary:** grid reference element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.LevelSetIndex <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.levelsetindex"></a>
**Summary:** index of the respective level-set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.SurfaceNodesOnZeroLevset <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.surfacenodesonzerolevset"></a>
**Summary:** if true, the nodes for the surface integration are 'projected' onto the zero-level-set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.Docheck <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.docheck"></a>
**Summary:** if true, the accuracy of the quadrature is checked after solution of the system


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.UseStokes <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.usestokes"></a>
**Summary:** if true, Stoke's theorem is used to create the surface rule


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.UseGauß <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.usegauß"></a>
**Summary:** if true, Gauß theorem is used to create the surface rule


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.tracker <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.tracker"></a>
**Summary:** the awesome level set tracker


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Boolean,System.Boolean,System.Boolean,System.Boolean) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},system.boolean,system.boolean,system.boolean,system.boolean)"></a>
**Summary:** Ctor.
**Parameter:** `levelSetData` - 
**Parameter:** `_SurfaceNodesOnZeroLevset` - if true, the nodes for the surface integration are 'projected' onto the zero-level-set
**Parameter:** `_DoCheck` - if true, the accuracy of the quadrature is checked after solution of the system
**Parameter:** `_LevelSetBoundaryLineFactory` - 
**Parameter:** `cellFaceFactory` - 
**Parameter:** `_UseGauß` - 
**Parameter:** `_UseStokes` - 


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.LevelSetData <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.levelsetdata"></a>
**Summary:** Evaluation of the level-set.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.MaxGrid <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.maxgrid"></a>
**Summary:** the intersection of the cut cells for Level Set [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.LevelSetIndex](#bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.levelsetindex)
and the subgrid for reference element [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.Kref](#bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.kref)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetQuadRuleFactory2.m_SurfaceRules <a id="bosss.foundation.xdg.quadrature.hmf.levelsetquadrulefactory2.m_surfacerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory"></a>

**Summary:** This factory uses the hierarchical moment-fitting (HMF) strategy in
order to produce quadrature rules which are, for each cell
$K$  in a volume mask, capable of computing
(an approximation of)
\[ 
\oint\limits_{\partial K \cap \{ \vec{x}; \varphi(\vec{x}) = 0 \} }  f \;dS,
\]
where $\varphi$  denotes the level set
function.

**Remark:**
For details about the algorithm, see
Mueller, Kummer & Oberlack: Highly accurate surface and volume
integration on implicit domains by means of moment-fitting (2013)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.edgeRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.edgerulefactory"></a>
**Summary:** Quadrature rule factory for the integration over the edges of the
volume simplex, cf. [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.localCellIndex2SubgridIndex <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.localcellindex2subgridindex"></a>
**Summary:** Mapping between local cell index and indices into current cell mask
(cf. [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32)](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)))


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.phiBasis <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phibasis"></a>
**Summary:** A vector-valued basis consisting of divergence-free vectors of
polynomials. These are required for the construction of the
moment-fitting system, cf. [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.GetOptimizedRules(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,System.Int32,ilPSP.MultidimensionalArray,System.Int32)](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.getoptimizedrules(bosss.foundation.nodeset,system.int32,system.int32,system.int32,ilpsp.multidimensionalarray,system.int32))


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.levelSetIndex <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.levelsetindex"></a>
**Summary:** Index of the considered level set within the level set tracker


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.trafosToBoundingBox <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.trafostoboundingbox"></a>
**Summary:** Transformations from the volume coordinate system of a cell to
the bounding box defined by the vertices with positive level set
values and the roots of the level set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.UseNodesOnLevset <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.usenodesonlevset"></a>
**Summary:** Indicates whether the integration nodes should be projected onto
the zero level set, or not. The latter approach is much more
efficient (since the projection is expensive), but also less
accurate.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.RestrictNodes <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.restrictnodes"></a>
**Summary:** If [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.UseNodesOnLevset](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.usenodesonlevset) is true, this switch
indicates whether projected nodes that land outside of the
corresponding cell should be kept (false) or discarded (true).
If [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.UseNodesOnLevset](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.usenodesonlevset) is false, this switch indicates
whether nodes located outside of the sub-cell of interest should
be kept (false) or discarded (true)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.UseGaussNodes <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.usegaussnodes"></a>


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.cachedRules <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.cachedrules"></a>
**Summary:** Cache for quad rules


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule}) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule})"></a>
**Summary:** Constructor
**Parameter:** `levelSetData` - 
**Parameter:** `edgeRuleFactory` - Quadrature rule factory for the integration over the edges of the
volume simplex. Note that the related quadrature rules must be able
to cope with discontinuous integrands. For example, see
[BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory](#bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory) and
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory)


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.refelement"></a>
**Summary:** The first reference element of the current grid.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** For each cell in the given 'mask': Constructs a
quadrature rule that can be used to evaluate
\f[ 
\oint\limits_{\partial K \cap \{ \vec{x}; \varphi(\vec{x}) = 0 \} }  f \;dS,
\f]
with relatively high accuracy (depending on the selected integration
'order')
**Parameter:** `mask` - Cells to be integrated over
**Parameter:** `order` - The desired order of the moment-fitting system. Note that the
integration result will not be exact, even for polynomial functions
f with degree < 'order'. However, increasing
the will typically strongly increase the integration accuracy
**Returns:**
A set of quadrature rules. Note that the quadrature nodes will not
necessarily coincide with the zero level set, depending on the
arguments passed to the constructor.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.nodeCountSafetyFactor <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.nodecountsafetyfactor"></a>
**Summary:** Minimum desired ratio between number of nodes and number of moment
equations. If not set, a value that is determined from numerical
experiments will be used. The value for the 2D case has been
verified independently by Martin Gehrke. The 3D value is still not
fully settled.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.ProjectNodesOntoLevelSet(System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.projectnodesontolevelset(system.int32,bosss.foundation.nodeset)"></a>
**Summary:** Projects the given 'Nodes' onto the zero level-set
of cell 'jCell'
**Parameter:** `jCell` - Local cell index
**Parameter:** `Nodes` - The nodes to be projected

1st index: Node index
2nd index: Spatial dimension
**Returns:**
The projection of all nodes in 'Nodes' onto the
zero level-set


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.GetOptimizedRules(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,System.Int32,ilPSP.MultidimensionalArray,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.getoptimizedrules(bosss.foundation.nodeset,system.int32,system.int32,system.int32,ilpsp.multidimensionalarray,system.int32)"></a>
**Summary:** Determines the (in some sense) optimal weights for the given
quadrature 'nodes' by solving the moment-fitting
system of degree 'phiDegree' in each cell in the
given range of cells, where right-hand side follows from the given
'quadResults'.
**Parameter:** `nodes` - Integration nodes
**Parameter:** `phiDegree` - Order of the moment-fitting system
**Parameter:** `i0` - First cell index
**Parameter:** `length` - Number of cells
**Parameter:** `quadResults` -
Integration results for each function in the divergence-free basis [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.phiBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phibasis)
- 1st index: Cell index within the current sub,set of cells, see also [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.localCellIndex2SubgridIndex](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.localcellindex2subgridindex)
- 2nd index: Local edge index of [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.RefElement](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.refelement)
- 3rd index: Basis function index
**Parameter:** `levSetIndex` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.GetOptimizedRule(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.getoptimizedrule(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray,system.int32)"></a>
**Summary:** Non-vectorized reference implementation of
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.GetOptimizedRules(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,System.Int32,ilPSP.MultidimensionalArray,System.Int32)](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.getoptimizedrules(bosss.foundation.nodeset,system.int32,system.int32,system.int32,ilpsp.multidimensionalarray,system.int32))
which is used for optimizing the weights in single cells
**Parameter:** `nodes` - 
**Parameter:** `phiDegree` - 
**Parameter:** `jCell` - 
**Parameter:** `quadResults` - 
**Parameter:** `levSetIndex` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.EvaluatePhis(System.Int32,System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.evaluatephis(system.int32,system.int32,bosss.foundation.nodeset)"></a>
**Summary:** Evaluates [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.phiBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phibasis) in all cells within the given
range
**Parameter:** `i0` - First cell index
**Parameter:** `length` - Number of cells
**Parameter:** `NS` - Node Set.
**Returns:**
The vector-valued basis values

1st index: Node index
2nd index: Basis function index
3rd index: Spatial dimension


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.NumberOfMoments <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.numberofmoments"></a>
**Summary:** Determines the number of basis functions represented by
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.phiBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phibasis)

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature"></a>

**Summary:** Used for the integration over the divergence-free basis functions
over the boundary of the current element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.owner <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.owner"></a>
**Summary:** Owner of this object.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.NoOfItemsLocally <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.noofitemslocally"></a>
**Summary:** Number of cells in the current sub-grid


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.#ctor(BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.#ctor(bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory,bosss.foundation.grid.cellmask)"></a>
**Summary:** Constructor
**Parameter:** `owner` - 
**Parameter:** `mask` - 


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.IntegrationResults <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.integrationresults"></a>
**Summary:** Results of the last integration


1st index: Cell index within the current sub-grid


2nd index: Local edge of the reference element


3rd index: Basis function index


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.Execute <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.execute"></a>
**Summary:** Performs the integration while overwriting old results in
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.IntegrationResults](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.integrationresults)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CellBoundaryQuadRule,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.evaluate(system.int32,system.int32,bosss.foundation.quadrature.cellboundaryquadrule,ilpsp.multidimensionalarray)"></a>
**Summary:** For each cell $K$  and for each
divergence-free basis polynomial
$\vec{\Phi}$ : Computes the
integral
$\int \limits_{\partial K} \vec{\Phi} H(\varphi) \;dS,$ 
where $\varphi$  is the level set
function and $H$  is an indicator
function that restricts the integration domain to positive
level set values (Heaviside) or negative level set values
(One minus Heaviside). This choice is implicitly given by
the edge rule factory supplied to
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule})](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule}))


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Saves the results of the integration to
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.IntegrationResults](#bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.integrationresults)
**Parameter:** `i0` - 
**Parameter:** `Length` - 
**Parameter:** `ResultsOfIntegration` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory.PhiQuadrature.GetQuadratureDegree(BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetSurfaceQuadRuleFactory) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory.phiquadrature.getquadraturedegree(bosss.foundation.xdg.quadrature.hmf.levelsetsurfacequadrulefactory)"></a>
**Summary:** Determines the required degree of the boundary integration
**Parameter:** `owner` - The owner of this object.
**Returns:**
'owner'.phiBasis.Degree in 2D, but
'owner'.phiBasis.Degree + 1 in 3D.
**Remark:**
In 2D, it is given by the degree p of the basis we want to
integrate, and, as the boundary integral can be evaluated
exactly guarantees a convergence order h^(p+1). In 3D,
however, the situation is a bit different: If we use order p on
the boundary, the related error converges with h^(p+1), but the
surface case is based on the divergence theorem, i.e. the
surface integral only converges with h^p. Since we want h^(p+1)
in both cases, we thus use p+1 for the boundary integral.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory"></a>

**Summary:** This factory produces quadrature rules which are, for each cell
$K$  in a volume mask, capable of computing
(an approximation of)
\[ 
\int\limits_{\{ \vec{x}; \varphi(\vec{x}) {\leq \atop \geq} 0 \} \cap K}  f \ d \vec{x},
\]
where $\varphi$ denotes the level set function.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.jumpType <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.jumptype"></a>
**Summary:** Determines the level set region to be integrated over (negative
level set values, positive level set values, or both)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.edgeRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.edgerulefactory"></a>
**Summary:** Factory for one- or two-dimensional integration rules for the edges
of the of the volume element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.surfaceRuleFactory <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.surfacerulefactory"></a>
**Summary:** Factory for the one- or two-dimensional integration over the
interface that is defined as the intersection of the zero 
iso-contour of the level set function with the three-dimensional
volume element


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.lambdaBasis <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdabasis"></a>
**Summary:** Vector-valued moment-fitting basis constructed from the
'anti-derivatives' of a standard basis. Here, the 'anti-derivative'
of a scalar polynomial $p$  is defined as
a vector-valued polynomial
$\vec{\Lambda}$  such that
$p = \nabla \cdot \vec{\Lambda}$


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.NodeCountSafetyFactor <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.nodecountsafetyfactor"></a>
**Summary:** Safety factor for the number of the nodes with respect to the
number of modes. A factor of 1 (default) indicates that at least
as many nodes as modes are used; a higher value may increase
robustness and runtime.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule},bosss.foundation.xdg.quadrature.hmf.jumptypes)"></a>
**Summary:** constructor.
**Parameter:** `lsData` - 
**Parameter:** `edgeRuleFactory` - Some factory that provides quadrature rules for the integration 
over 
\[ 
\partial K \cap \{ \vec{x}; \varphi(\vec{x}) {\leq \atop \geq} 0 \}.
\]
Here, $\partial K$  the boundary of
some cell $K$  and 
$\varphi$  denotes the level set function
**Parameter:** `surfaceRuleFactory` - Some factory that provides quadrature rules for the integration 
over the zero level set, i.e.
\[ 
\{ \vec{x}; \varphi(\vec{x}) = 0 \} \cap K.
\]
(ere, $\partial K$  the boundary of some
cell $K$  and 
$\varphi$  denotes the level set function
**Parameter:** `jumpType` - 


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.refelement"></a>
**Summary:** The reference element of the grid


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.GetQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.getquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** Constructs suitable quadrature rules cells in
'mask'.
**Parameter:** `mask` - Cells for which quadrature rules shall be created
**Parameter:** `order` - Desired order of the moment-fitting system. Assuming that
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.surfaceRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.surfacerulefactory) integrates the basis polynomials
exactly over the zero iso-contour (which it usually
doesn't!), the resulting quadrature rules will be exact up to this
order.
**Returns:**
A set of quadrature rules
**Remark:**
Since the selected level set is generally discontinuous across cell
boundaries, this method does not make use of the fact that
neighboring cells share edges. That is, the optimization will be
performed twice for each inner edge in 'mask'.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.GetOptimizedRules(BoSSS.Foundation.Grid.CellMask,BoSSS.Foundation.NodeSet,System.Double[0:,0:],System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.getoptimizedrules(bosss.foundation.grid.cellmask,bosss.foundation.nodeset,system.double[0:,0:],system.int32)"></a>
**Summary:** Uses a moment-fitting basis of order 'order' for
determining optimal weights of a quadrature rule for a sub-region
of each cell in the given 'mask'.
**Parameter:** `mask` - Cells for which rules shall be created
**Parameter:** `nodes` - Integration nodes
**Parameter:** `quadResults` - Integration results for each function in the
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdabasis)
**Parameter:** `order` - Desired order of the moment-fitting system. Assuming that
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.surfaceRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.surfacerulefactory) integrates the basis
polynomials exactly over the zero iso-contour (which it usually
doesn't), the resulting quadrature rules will be exact up to this
order.
**Returns:**
A set of quadrature rules


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.GetOptimizedRule(System.Int32,BoSSS.Platform.LinAlg.AffineTrafo,BoSSS.Foundation.NodeSet,System.Double[0:,0:],System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.getoptimizedrule(system.int32,bosss.platform.linalg.affinetrafo,bosss.foundation.nodeset,system.double[0:,0:],system.int32)"></a>
**Summary:** Non-vectorized reference implementation of
**],System.Int32)**
**Parameter:** `cell` - 
**Parameter:** `trafo` - 
**Parameter:** `nodes` - 
**Parameter:** `quadResults` - 
**Parameter:** `order` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.GetNumberOfLambdas(System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.getnumberoflambdas(system.int32)"></a>
**Summary:** Computes the number of vector-valued basis function (cf.
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdabasis))
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.EvaluateLambdas(System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.evaluatelambdas(system.int32,bosss.foundation.nodeset)"></a>
**Summary:** Evaluates the vector-valued anti-derivatives defining the
moment-fitting basis (cf. [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdabasis)) in each node
of all cells in the given range
**Parameter:** `NS` - Nodes at which to evaluate.
**Parameter:** `cell` - 
**Returns:**
The values of [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdabasis) in each node

1st index: Node index
2nd index: Basis function index
3rd index: Spatial dimension
**Remark:**
This method does not evaluate a Lambda which is constant since the
derivative of such function is zero. As a result, the integral over
this function is zero, too, which makes it useless for the
construction of a quadrature rule

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature"></a>

**Summary:** Used for the computation of the integral of the basis functions
(see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdabasis)) over the boundary of a cell. More
specifically, the boundary of the cell is given by
(D-1)-dimensional elements that are potentially cut by the zero
iso-contour of the level set, which is why this requires a special
treatment; see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.surfaceRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.surfacerulefactory).


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.owner <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.owner"></a>
**Summary:** Owner of this object


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.NoOfItemsLocally <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.noofitemslocally"></a>
**Summary:** Number of items in the current execution mask


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.localCellIndex2SubgridIndex <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.localcellindex2subgridindex"></a>
**Summary:** [BoSSS.Foundation.Grid.SubGrid.LocalCellIndex2SubgridIndex](BoSSS.Foundation.md#bosss.foundation.grid.subgrid.localcellindex2subgridindex)


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.Results <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.results"></a>
**Summary:** Integration results for the last call to [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.Execute](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.execute)


1st index: Cell index within
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.localCellIndex2SubgridIndex](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.localcellindex2subgridindex)


3rd index: Basis function (see
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.EvaluateLambdas(System.Int32,BoSSS.Foundation.NodeSet)](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.evaluatelambdas(system.int32,bosss.foundation.nodeset))


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.#ctor(BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.#ctor(bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},bosss.foundation.grid.cellmask)"></a>
**Parameter:** `owner` - 
**Parameter:** `edgeRuleFactory` - 
**Parameter:** `mask` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.Execute <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.execute"></a>
**Summary:** Computes the integrals while overwriting [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.Results](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.results)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CellBoundaryQuadRule,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.evaluate(system.int32,system.int32,bosss.foundation.quadrature.cellboundaryquadrule,ilpsp.multidimensionalarray)"></a>
**Summary:** For each cell $K$  in the given
range and for each $\vec{\Lambda}$  
in [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetEdgeVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetedgevolumequadrulefactory.lambdabasis):
Computes
$\int \limits_{\partial K} \vec{\Lambda} \cdot \vec{n} H(\varphi) \;ds,$ 
where $\vec{n}$  denotes the outer
unit normal vector on $\partial K$ .
Moreover $H$ a weight function that
depends on the level set function
$\varphi$ . Typically,
$H$  is given by the Heaviside
function. For more details, see
[BoSSS.Foundation.XDG.Quadrature.HMF.CutLineQuadRuleFactory](#bosss.foundation.xdg.quadrature.hmf.cutlinequadrulefactory)
**Parameter:** `i0` - 
**Parameter:** `Length` - 
**Parameter:** `QR` - 
**Parameter:** `EvalResult` - 


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Saves the integration results to [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaCellBoundaryQuadrature.Results](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdacellboundaryquadrature.results)
**Parameter:** `i0` - 
**Parameter:** `Length` - 
**Parameter:** `ResultsOfIntegration` - 

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature"></a>

**Summary:** Used for the computation of the integral of the basis functions
(see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdabasis)) over the intersection of the zero
iso-contour of the level set with an edge. This requires a special
treatment; see [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.surfaceRuleFactory](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.surfacerulefactory).


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.owner <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.owner"></a>
**Summary:** Owner of this object


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.NoOfItemsLocally <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.noofitemslocally"></a>
**Summary:** Number of items in the current sub-grid


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.localCellIndex2SubgridIndex <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.localcellindex2subgridindex"></a>
**Summary:** [BoSSS.Foundation.Grid.SubGrid.LocalCellIndex2SubgridIndex](BoSSS.Foundation.md#bosss.foundation.grid.subgrid.localcellindex2subgridindex)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.#ctor(BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.#ctor(bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule},bosss.foundation.grid.cellmask)"></a>
**Summary:** Constructor


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Results <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.results"></a>
**Summary:** Results of the last integration


1st index: Cell index within the current sub-grid


2nd index: Basis function index


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Execute <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.execute"></a>
**Summary:** Performs the integration while overwriting old results in
[BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Results](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.results)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.Quadrature.QuadRule,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.evaluate(system.int32,system.int32,bosss.foundation.quadrature.quadrule,ilpsp.multidimensionalarray)"></a>
**Summary:** For each cell $K$   in the given
range and for each $\vec{\Lambda}$ 
in [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.lambdaBasis](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdabasis):
Computes
$\int \limits_{\{\vec{x}; \varphi(\vec{x}) = 0 \}  \cap K} \vec{\Lambda} \cdot \vec{n}_I \;ds,$ 
where $\varphi$  is the level set
function and $\vec{n}_I$  denotes the
unit normal vector on $\varphi$


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Saves the results of the integration to [BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory.LambdaLevelSetSurfaceQuadrature.Results](#bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory.lambdalevelsetsurfacequadrature.results)
**Parameter:** `i0` - 
**Parameter:** `Length` - 
**Parameter:** `ResultsOfIntegration` - 

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2 <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2"></a>

**Summary:** This factory produces quadrature rules which are,
for each cell $K$  in a volume mask,
capable of computing (an approximation of)
\[ 
\int\limits_{\{ \vec{x}; \varphi(\vec{x}) {\leq \atop \geq} 0 \} \cap K}  f \ d \vec{x},
\]
where $\varphi$  denotes the level set function.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2.refelement"></a>
**Summary:** grid reference element.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2.#ctor(BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2.#ctor(bosss.foundation.grid.refelements.refelement,bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule},bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule},bosss.foundation.xdg.quadrature.hmf.jumptypes)"></a>
**Summary:** constructor.
**Parameter:** `edgeRuleFactory` - Some factory that provides quadrature rulz for the integration 
over 
\[ 
\partial K \cap \{ \vec{x}; \varphi(\vec{x}) {\leq \atop \geq} 0 \}.
\]
(Here, $\partial K$   the boundary of some cell 
$K$  and 
$\varphi$  denotes the level set function.)
**Parameter:** `surfaceRuleFactory` - Some factory that provides quadrature rulz for the integration 
over the zero level set, i.e.
\[ 
\{ \vec{x}; \varphi(\vec{x}) = 0 \} \cap K.
\]
(Here, $\partial K$   the boundary of some cell 
$K$  and 
$\varphi$  denotes the level set function.)
**Parameter:** `simplex` - 
**Parameter:** `jumpType` - 
**Parameter:** `LevSetData` - 
**Parameter:** `cellBoundaryFactory` - 


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2.LevelSetData <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2.levelsetdata"></a>
**Summary:** Evaluation of level-set fields


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2.ConstructRule_AllTheSameNodes(System.Int32,BoSSS.Foundation.Grid.SubGrid,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2.constructrule_allthesamenodes(system.int32,bosss.foundation.grid.subgrid,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** uses the same quadrature nodes in all cells

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2a <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2a"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2a.RhsCellEdgeB(BoSSS.Foundation.Quadrature.CellBoundaryQuadratureScheme,System.Int32,BoSSS.Foundation.Grid.Classic.GridData,System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CoordinateSystem,BoSSS.Foundation.Basis,System.Collections.BitArray,System.Int32[],ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2a.rhscelledgeb(bosss.foundation.quadrature.cellboundaryquadraturescheme,system.int32,bosss.foundation.grid.classic.griddata,system.int32,system.int32,bosss.foundation.quadrature.coordinatesystem,bosss.foundation.basis,system.collections.bitarray,system.int32[],ilpsp.multidimensionalarray)"></a>
**Summary:** compute RHS/ cell boundary terms/ from CELL BOUNDARY rule ('cellBndSchme')


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2a.RhsCellEdgeA(BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,System.Int32,BoSSS.Foundation.Grid.Classic.GridData,System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CoordinateSystem,BoSSS.Foundation.Basis,System.Collections.BitArray,System.Int32[],ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2a.rhscelledgea(bosss.foundation.quadrature.edgequadraturescheme,system.int32,bosss.foundation.grid.classic.griddata,system.int32,system.int32,bosss.foundation.quadrature.coordinatesystem,bosss.foundation.basis,system.collections.bitarray,system.int32[],ilpsp.multidimensionalarray)"></a>
**Summary:** compute RHS/ cell boundary terms/ from EDGE rule ('edgeScheme')

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2b <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2b"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2b.RhsCellEdgeA(BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,System.Int32,BoSSS.Foundation.Grid.Classic.GridData,System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CoordinateSystem,BoSSS.Foundation.Basis,System.Collections.BitArray,System.Int32[],ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2b.rhscelledgea(bosss.foundation.quadrature.edgequadraturescheme,system.int32,bosss.foundation.grid.classic.griddata,system.int32,system.int32,bosss.foundation.quadrature.coordinatesystem,bosss.foundation.basis,system.collections.bitarray,system.int32[],ilpsp.multidimensionalarray)"></a>
**Summary:** compute RHS/ cell boundary terms/ from EDGE rule ('edgeScheme')


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LevelSetVolumeQuadRuleFactory2b.RhsCellEdgeB(BoSSS.Foundation.Quadrature.CellBoundaryQuadratureScheme,System.Int32,BoSSS.Foundation.Grid.Classic.GridData,System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CoordinateSystem,BoSSS.Foundation.Basis,System.Collections.BitArray,System.Int32[],ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.hmf.levelsetvolumequadrulefactory2b.rhscelledgeb(bosss.foundation.quadrature.cellboundaryquadraturescheme,system.int32,bosss.foundation.grid.classic.griddata,system.int32,system.int32,bosss.foundation.quadrature.coordinatesystem,bosss.foundation.basis,system.collections.bitarray,system.int32[],ilpsp.multidimensionalarray)"></a>
**Summary:** compute RHS/ cell boundary terms/ from CELL BOUNDARY rule ('cellBndSchme')

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory"></a>

**Summary:** in a 2D calculation, this code should provide 
- a quadrature rule the cell boundary, [BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.GetLineFactory(System.Boolean)](#bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.getlinefactory(system.boolean))
- a point measure where the level-set enters and exits a cell, **BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.GetPointFactory**


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.#ctor(BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,System.Boolean,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm) <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.#ctor(bosss.foundation.grid.refelements.refelement,bosss.foundation.xdg.levelsettracker.levelsetdata,system.boolean,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm)"></a>
**Summary:** ctor


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.MaxGrid <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.maxgrid"></a>
**Summary:** the intersection of the cut cells for Level Set **BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.LevelSetIndex**
and the subgrid for reference element [BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.m_RefElement](#bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.m_refelement)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.iKref <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.ikref"></a>
**Summary:** index into [BoSSS.Foundation.Grid.Classic.GridData.CellData.RefElements](BoSSS.Foundation.md#bosss.foundation.grid.classic.griddata.celldata.refelements)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.m_RefElement <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.m_refelement"></a>
**Summary:** grid reference element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.LevelSetData <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.levelsetdata"></a>
**Summary:** Node-wise evaluation of the level-set field.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.QRF <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.qrf"></a>


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.QRF.Rules <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.qrf.rules"></a>
**Summary:** cache
key: quadrature order; 
value: cached quadrature rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.QRF.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.qrf.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.QRF.GetPosRule(System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.qrf.getposrule(system.int32)"></a>
**Summary:** Rule for an _uncut_ cell in the positive level-set region.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.QRF.GetNegRule(System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.qrf.getnegrule(system.int32)"></a>
**Summary:** Rule for an _uncut_ cell in the negative level-set region.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.GetLineFactory(System.Boolean) <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.getlinefactory(system.boolean)"></a>
**Summary:** returns the line integration
**Parameter:** `sign` -
- true: positive level-set domain
- false: negative domain
**Returns:**



### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.m_PointMeasure <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.m_pointmeasure"></a>
**Summary:** key: quadrature order 
value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.m_LineMeasurePos <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.m_linemeasurepos"></a>
**Summary:** Quadrature rules for the positive level set region 
- key: quadrature order 
- value: quadrature rule


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineAndPointQuadratureFactory.m_LineMeasureNeg <a id="bosss.foundation.xdg.quadrature.hmf.lineandpointquadraturefactory.m_linemeasureneg"></a>
**Summary:** Quadrature rules for the positive level set region 
- key: quadrature order 
- value: quadrature rule

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment <a id="bosss.foundation.xdg.quadrature.hmf.linesegment"></a>

**Summary:** Represents a (one-dimensional) line segment in two- or
three-dimensional space. The line segment generally lives in the
reference coordinate system and is parametrized via a parameter t
ranging from -1 to 1. Here, t=-1 marks the start point and t=1 marks
the end point of the segment.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.EPSILON <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.epsilon"></a>
**Summary:** Minimal distance between two points.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.DefaultRootFindingAlgorithm <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.defaultrootfindingalgorithm"></a>
**Summary:** Return an instance of [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SafeGuardedNewtonMethod](#bosss.foundation.xdg.quadrature.hmf.linesegment.safeguardednewtonmethod) where
the tolerance is set to 1e-10


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.length <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.length"></a>
**Summary:** The Cartesian length of this segment


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.refelement"></a>
**Summary:** Dingsbums


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.#ctor(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement,ilPSP.Vector,ilPSP.Vector,System.Int32,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.#ctor(system.int32,bosss.foundation.grid.refelements.refelement,ilpsp.vector,ilpsp.vector,system.int32,system.int32,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm)"></a>
**Summary:** Constructs a new segment with the given start and end points
**Parameter:** `spatialDimension` - The spatial dimension of start and end points
**Parameter:** `start` - The start point of the segment
**Parameter:** `end` - The end point of the segment
**Parameter:** `iVertexStart` - Optional vertex index of the start point in some list of vertices
containing 'start'. Used by some callers to evade
equality comparisons of double values.
**Parameter:** `iVertexEnd` - Optional vertex index of the end point in some list of vertices
containing 'end'. Used by some callers to evade
equality comparisons of double values.
**Parameter:** `Kräf` - Reference element.
**Parameter:** `rootFindingAlgorithm` - The desired root finding algorithm. By default,
[BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.DefaultRootFindingAlgorithm](#bosss.foundation.xdg.quadrature.hmf.linesegment.defaultrootfindingalgorithm) will be used.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SpatialDimension <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.spatialdimension"></a>
**Summary:** Spatial dimension of the computational domain.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Start <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.start"></a>
**Summary:** Start coordinates, usually in the reference coordinate system of the cell


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.iVertexStart <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.ivertexstart"></a>
**Summary:** Optional vertex index of the start point in some list of vertices
containing [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Start](#bosss.foundation.xdg.quadrature.hmf.linesegment.start). Used by some callers to evade
equality comparisons of double values.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.End <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.end"></a>
**Summary:** End coordinates, usually in the reference coordinate system of the cell


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.iVertexEnd <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.ivertexend"></a>
**Summary:** Optional vertex index of the end point in some list of vertices
containing [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.End](#bosss.foundation.xdg.quadrature.hmf.linesegment.end). Used by some callers to evade
equality comparisons of double values.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Length <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.length"></a>
**Summary:** The L2 distance between [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Start](#bosss.foundation.xdg.quadrature.hmf.linesegment.start) and [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.End](#bosss.foundation.xdg.quadrature.hmf.linesegment.end)


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.ProjectedPolynomialCoefficients <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.projectedpolynomialcoefficients"></a>
**Summary:** The coefficients of the polynomials that represents the projection
of a set of [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SpatialDimension](#bosss.foundation.xdg.quadrature.hmf.linesegment.spatialdimension)-dimensional polynomials
onto this line segment (see [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.ProjectBasisPolynomials(BoSSS.Foundation.Basis)](#bosss.foundation.xdg.quadrature.hmf.linesegment.projectbasispolynomials(bosss.foundation.basis)))

1st index: reference element index
2nd index: polynomial index 
3rd index: coefficient index


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Split(System.Double[]) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.split(system.double[])"></a>
**Summary:** Splits this segment at each point defined by
'splitPoints'.
**Parameter:** `splitPoints` - The split points given as a parameter
$t \in ]-1, 1[$  of a parametrization that varies
linearly between [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Start](#bosss.foundation.xdg.quadrature.hmf.linesegment.start) and [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.End](#bosss.foundation.xdg.quadrature.hmf.linesegment.end). In
particular, t=-1 is the start point and t=1 the end point.
**Returns:**
A list of ('splitPoints'.Length + 1) consecutive
line segments.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.StartCoord <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.startcoord"></a>
**Summary:** The start coordinate expressed in terms of the parametrization
described in [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Split(System.Double[])](#bosss.foundation.xdg.quadrature.hmf.linesegment.split(system.double[])) of the parent element


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.EndCoord <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.endcoord"></a>
**Summary:** The end coordinate expressed in terms of the parametrization
described in [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Split(System.Double[])](#bosss.foundation.xdg.quadrature.hmf.linesegment.split(system.double[])) of the parent element


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.GetPointOnSegment(System.Double) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.getpointonsegment(system.double)"></a>
**Summary:** Evaluates the [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SpatialDimension](#bosss.foundation.xdg.quadrature.hmf.linesegment.spatialdimension)-dimensional
coordinate of the point with parameter value t.
**Parameter:** `t` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.GetSegmentCoordinateForPoint(ilPSP.Vector) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.getsegmentcoordinateforpoint(ilpsp.vector)"></a>
**Summary:** Determines the parameter value t for a given 'pt'.
**Parameter:** `pt` - 
**Returns:**



### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Inverse <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.inverse"></a>
**Summary:** Returns a reversed line segment


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.ProjectBasisPolynomials(BoSSS.Foundation.Basis) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.projectbasispolynomials(bosss.foundation.basis)"></a>
**Summary:** Computes the projection of all
[BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SpatialDimension](#bosss.foundation.xdg.quadrature.hmf.linesegment.spatialdimension)-dimensional basis polynomials in
'basis' onto this line segment and stores the
result in [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.ProjectedPolynomialCoefficients](#bosss.foundation.xdg.quadrature.hmf.linesegment.projectedpolynomialcoefficients)
**Parameter:** `basis` - A basis containing the polynomials to be projected
**Remark:**
Don't ask me (B. Müller) how it works, so please don't touch it. I
remember that I coded it but even at that time, I didn't fully
understand why it works.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.GetPhysicalLength(BoSSS.Foundation.Grid.Classic.GridData,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.getphysicallength(bosss.foundation.grid.classic.griddata,system.int32)"></a>
**Summary:** Determines the length of the segment in cell
'cell' of the physical domain.
**Parameter:** `context` - 
**Parameter:** `cell` - 
**Returns:**



### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.RootFindingAlgorithm <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.rootfindingalgorithm"></a>
**Summary:** The root-finding algorithm to determine roots on this segment.


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.GetRoots(BoSSS.Foundation.XDG.ILevelSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.getroots(bosss.foundation.xdg.ilevelset,system.int32,system.int32)"></a>
**Summary:** Determines all roots of 'levelSet' on this segment
in cell 'cell'.
**Parameter:** `levelSet` - The level set whose roots are of interest
**Parameter:** `cell` - The cell where the evaluation takes place
**Parameter:** `iKref` - Reference element index.
**Returns:**
The parameter t of each root of 'levelSet' on this
segment in cell 'cell'


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Equals(BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.equals(bosss.foundation.xdg.quadrature.hmf.linesegment)"></a>
**Summary:** Segments are considered equal if the start and end coordinates are
equal (w.r.t. [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.EPSILON](#bosss.foundation.xdg.quadrature.hmf.linesegment.epsilon)). Here, the direction of the
segment is ignored which means that two segments are considered
equal even if start and points are exchanged.
**Parameter:** `other` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.EqualsImp(BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.equalsimp(bosss.foundation.xdg.quadrature.hmf.linesegment)"></a>
**Summary:** Implementation of [BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.Equals(BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment)](#bosss.foundation.xdg.quadrature.hmf.linesegment.equals(bosss.foundation.xdg.quadrature.hmf.linesegment))
**Parameter:** `other` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm"></a>

**Summary:** Interface for approximate one-dimensional root-finding algorithms.


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm.Tolerance <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm.tolerance"></a>
**Summary:** The desired tolerance of the root-finding algorithm


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm.GetRoots(BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment,BoSSS.Foundation.XDG.ILevelSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm.getroots(bosss.foundation.xdg.quadrature.hmf.linesegment,bosss.foundation.xdg.ilevelset,system.int32,system.int32)"></a>
**Summary:** Determines the roots of 'levelSet' on the
given 'segment' in cell 'cell'
**Parameter:** `segment` - 
**Parameter:** `levelSet` - 
**Parameter:** `cell` - 
**Parameter:** `iKref` - 
**Returns:**
Determines the parameter t for each root of
'levelSet' on 'segment' in
the given 'cell'.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.GSLRootFindingAlgorithm <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.gslrootfindingalgorithm"></a>

**Summary:** A root-finding algorithm making use of the GNU Scientific Library
(GSL; cf. [BoSSS.Platform.GSL](BoSSS.Platform.md#bosss.platform.gsl)).


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.GSLRootFindingAlgorithm.#ctor(System.Double) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.gslrootfindingalgorithm.#ctor(system.double)"></a>
**Summary:** Constructs a root-finder with the given
'tolerance'
**Parameter:** `tolerance` - 


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.GSLRootFindingAlgorithm.Tolerance <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.gslrootfindingalgorithm.tolerance"></a>
**Summary:** Tolerance of the algorithm


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.GSLRootFindingAlgorithm.GetRoots(BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment,BoSSS.Foundation.XDG.ILevelSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.gslrootfindingalgorithm.getroots(bosss.foundation.xdg.quadrature.hmf.linesegment,bosss.foundation.xdg.ilevelset,system.int32,system.int32)"></a>
**Summary:** Finds the roots using **BoSSS.Platform.GSL.gsl_poly_complex_solve(System.IntPtr,System.Int32,System.IntPtr,System.IntPtr)**
**Parameter:** `segment` - 
**Parameter:** `levelSet` - 
**Parameter:** `cell` - 
**Parameter:** `iKref` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SafeGuardedNewtonMethod <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.safeguardednewtonmethod"></a>

**Summary:** Implementation of a SIMPLE safe-guarded Newton algorithm following
Press et al.: Numerical recipes (Chapter 9.4)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SafeGuardedNewtonMethod.#ctor(System.Double) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.safeguardednewtonmethod.#ctor(system.double)"></a>
**Summary:** Constructs a new root-finder
**Parameter:** `tolerance` - 


### Property: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SafeGuardedNewtonMethod.Tolerance <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.safeguardednewtonmethod.tolerance"></a>
**Summary:** The selected tolerance


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SafeGuardedNewtonMethod.GetRoots(BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment,BoSSS.Foundation.XDG.ILevelSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.safeguardednewtonmethod.getroots(bosss.foundation.xdg.quadrature.hmf.linesegment,bosss.foundation.xdg.ilevelset,system.int32,system.int32)"></a>
**Summary:** Uses a safe-guarded Newton method to find all roots on
'segment'
**Parameter:** `segment` - 
**Parameter:** `levelSet` - 
**Parameter:** `cell` - 
**Parameter:** `iKref` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SafeGuardedNewtonMethod.Eval(System.Double,System.Double*,System.Int32) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.safeguardednewtonmethod.eval(system.double,system.double*,system.int32)"></a>
**Summary:** Evaluates the polynomial p with coefficients stored in an array
ending at 'pCoeff'
**Parameter:** `x` - One-dimensional coordinate
**Parameter:** `pCoeff` - Pointer to the last coefficient of a polynomial (i.e., the one
with the highest exponent)
**Parameter:** `numberOfCoefficients` - The number of coefficients
**Returns:**
p(x)


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.SafeGuardedNewtonMethod.Eval(System.Double,System.Double*,System.Int32,System.Double@,System.Double@) <a id="bosss.foundation.xdg.quadrature.hmf.linesegment.safeguardednewtonmethod.eval(system.double,system.double*,system.int32,system.double@,system.double@)"></a>
**Summary:** Evaluates the polynomial p with coefficients stored in an array
ending at 'pCoeff', as well as its
derivative p' at 'x'
**Parameter:** `x` - One-dimensional coordinate
**Parameter:** `pCoeff` - Pointer to the last coefficient of a polynomial (i.e., the one
with the highest exponent)
**Parameter:** `numberOfCoefficients` - The number of coefficients
**Parameter:** `p` - p(x)
**Parameter:** `dp` - p'(x)

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d"></a>

**Summary:** HMF-surface integrals in 2D, based on Stokes integral theorem.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.QRF <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.qrf"></a>


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.QRF.Rules <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.qrf.rules"></a>
**Summary:** cache
key: quadrature order; 
value: cached quadrature rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.QRF.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.qrf.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.refelement"></a>
**Summary:** grid reference element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.LevelSetIndex <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.levelsetindex"></a>
**Summary:** index of the respective level-set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.SurfaceNodesOnZeroLevset <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.surfacenodesonzerolevset"></a>
**Summary:** if true, the nodes for the surface integration are 'projected' onto the zero-level-set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.Docheck <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.docheck"></a>
**Summary:** if true, the accuracy of the quadrature is checked after solution of the system


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Boolean,System.Boolean) <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},system.boolean,system.boolean)"></a>
**Summary:** Ctor.
**Parameter:** `lsData` - 
**Parameter:** `_SurfaceNodesOnZeroLevset` - if true, the nodes for the surface integration are 'projected' onto the zero-level-set
**Parameter:** `_DoCheck` - if true, the accuracy of the quadrature is checked after solution of the system
**Parameter:** `_LevelSetBoundaryLineFactory` - 
**Parameter:** `cellBoundaryFactory` - 


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.MaxGrid <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.maxgrid"></a>
**Summary:** the intersection of the cut cells for Level Set [BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.LevelSetIndex](#bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.levelsetindex)
and the subgrid for reference element [BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.RefElement](#bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.refelement)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D.m_SurfaceRules <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d.m_surfacerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature"></a>

**Summary:** HMF-surface integrals in 2D, based on Stokes integral theorem.

## Class: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.QRF <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.qrf"></a>


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.QRF.Rules <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.qrf.rules"></a>
**Summary:** cache
key: quadrature order; 
value: cached quadrature rule


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.QRF.GetCachedRuleOrders <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.qrf.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.RefElement <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.refelement"></a>
**Summary:** grid reference element.


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.LevelSetIndex <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.levelsetindex"></a>
**Summary:** index of the respective level-set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.SurfaceNodesOnZeroLevset <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.surfacenodesonzerolevset"></a>
**Summary:** if true, the nodes for the surface integration are 'projected' onto the zero-level-set


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.Docheck <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.docheck"></a>
**Summary:** if true, the accuracy of the quadrature is checked after solution of the system


## Method: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Boolean,System.Boolean) <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.cellboundaryquadrule},system.boolean,system.boolean)"></a>
**Summary:** ctor.
**Parameter:** `lsData` - 
**Parameter:** `_SurfaceNodesOnZeroLevset` - if true, the nodes for the surface integration are 'projected' onto the zero-level-set
**Parameter:** `_DoCheck` - if true, the accuracy of the quadrature is checked after solution of the system
**Parameter:** `_LevelSetBoundaryLineFactory` - 
**Parameter:** `cellBoundaryFactory` - 


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.MaxGrid <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.maxgrid"></a>
**Summary:** the intersection of the cut cells for Level Set [BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.LevelSetIndex](#bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.levelsetindex)
and the subgrid for reference element [BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.RefElement](#bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.refelement)


### Field: BoSSS.Foundation.XDG.Quadrature.HMF.SurfaceStokes_2D_Curvature.m_SurfaceRules <a id="bosss.foundation.xdg.quadrature.hmf.surfacestokes_2d_curvature.m_surfacerules"></a>
**Summary:** key: quadrature order 
value: quadrature rule

## Class: BoSSS.Foundation.XDG.Quadrature.LevelSetIntegrationMetric <a id="bosss.foundation.xdg.quadrature.levelsetintegrationmetric"></a>

**Summary:** integration metric for $D-1$-dimensional integral over the level-set surface in each cell, i.e., 
\[
\oint_{K_j \cap \mathfrak{I}}  f \mathrm{dS} .
\]


### Property: BoSSS.Foundation.XDG.Quadrature.LevelSetIntegrationMetric.AlwaysUsePerNodeScaling <a id="bosss.foundation.xdg.quadrature.levelsetintegrationmetric.alwaysusepernodescaling"></a>
**Summary:** For the integral over the level-set-surface, the metric depends on the node (if the element transformation applies some shearing transformation),
therefore always true


## Method: BoSSS.Foundation.XDG.Quadrature.LevelSetIntegrationMetric.GetScalingsForLinearElements(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.Quadrature.QuadRule,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.levelsetintegrationmetric.getscalingsforlinearelements(bosss.foundation.grid.igriddata,bosss.foundation.quadrature.quadrule,system.int32,system.int32)"></a>
**Summary:** not used, because of reasons given for [BoSSS.Foundation.XDG.Quadrature.LevelSetIntegrationMetric.AlwaysUsePerNodeScaling](#bosss.foundation.xdg.quadrature.levelsetintegrationmetric.alwaysusepernodescaling)


## Method: BoSSS.Foundation.XDG.Quadrature.LevelSetIntegrationMetric.GetScalingsForNonlinElements(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.Quadrature.QuadRule,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.levelsetintegrationmetric.getscalingsfornonlinelements(bosss.foundation.grid.igriddata,bosss.foundation.quadrature.quadrule,system.int32,system.int32)"></a>

## Class: BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRuleFactory <a id="bosss.foundation.xdg.quadrature.levelsetonedgerulefactory"></a>

**Summary:** Generation of quadrature rules for level-sets which coincide with cell faces,
centrally triggered by
[BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingfaces)

## Class: BoSSS.Foundation.XDG.Quadrature.LevelSetBoundaryOnEdgeRuleFactory <a id="bosss.foundation.xdg.quadrature.levelsetboundaryonedgerulefactory"></a>

**Summary:** Generation of quadrature rules for level-sets which coincide with cell faces,
centrally triggered by
[BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingfaces)

## Class: BoSSS.Foundation.XDG.Quadrature.SurfaceElementBounaryFactoryForCoincidingEdges <a id="bosss.foundation.xdg.quadrature.surfaceelementbounaryfactoryforcoincidingedges"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.SurfaceElementBounaryFactoryForCoincidingEdges.GeometricalCellFace2Edges(BoSSS.Foundation.Grid.IGridData,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.surfaceelementbounaryfactoryforcoincidingedges.geometricalcellface2edges(bosss.foundation.grid.igriddata,system.int32,system.int32)"></a>
**Summary:** conversion ('jCellGeom','iFace') to grid edges


## Method: BoSSS.Foundation.XDG.Quadrature.SurfaceElementBounaryFactoryForCoincidingEdges.GeometricalCellCoFace2Edges(BoSSS.Foundation.Grid.IGridData,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.surfaceelementbounaryfactoryforcoincidingedges.geometricalcellcoface2edges(bosss.foundation.grid.igriddata,system.int32,system.int32)"></a>
**Summary:** conversion ('jCellGeom','iCoFace') to grid edges


## Method: BoSSS.Foundation.XDG.Quadrature.SurfaceElementBounaryFactoryForCoincidingEdges.ComputeMask(BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.surfaceelementbounaryfactoryforcoincidingedges.computemask(bosss.foundation.xdg.levelsettracker,system.int32,system.int32)"></a>
**Summary:** on which edges this class can actually provide working quadrature rules?


### Field: BoSSS.Foundation.XDG.Quadrature.SurfaceElementBounaryFactoryForCoincidingEdges.LevSetCoincidingFaces <a id="bosss.foundation.xdg.quadrature.surfaceelementbounaryfactoryforcoincidingedges.levsetcoincidingfaces"></a>
**Summary:** [BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingCoFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingcofaces)


### Field: BoSSS.Foundation.XDG.Quadrature.SurfaceElementBounaryFactoryForCoincidingEdges.LevSetCoincidingCoFaces <a id="bosss.foundation.xdg.quadrature.surfaceelementbounaryfactoryforcoincidingedges.levsetcoincidingcofaces"></a>
**Summary:** [BoSSS.Foundation.XDG.Quadrature.SurfaceElementBounaryFactoryForCoincidingEdges.LevSetCoincidingCoFaces](#bosss.foundation.xdg.quadrature.surfaceelementbounaryfactoryforcoincidingedges.levsetcoincidingcofaces)>

## Class: BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule <a id="bosss.foundation.xdg.quadrature.levelsetonedgerule"></a>

**Summary:** Generation of quadrature rules for level-sets which coincide with cell faces,
centrally triggered by
[BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions.LevSetCoincidingFaces](#bosss.foundation.xdg.levelsettracker.levelsetregions.levsetcoincidingfaces)


## Method: BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule.ComboQuadRule(System.Int32,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.levelsetonedgerule.comboquadrule(system.int32,system.int32,system.int32)"></a>
**Summary:** **This is a special case: level-set coincides with a cell-face; 
cell is either full or empty:**

Call this function when the **BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule.IsSpecialCell(System.Int32)** returns true.


## Method: BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule.SurfaceQuadRule(System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.levelsetonedgerule.surfacequadrule(system.int32,system.int32)"></a>
**Summary:** **This is a special case: level-set coincides with a cell-face; 
cell is either full or empty:**

Call this function when the **BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule.IsSpecialCell(System.Int32)** returns true.

Note:
Only one of the two cells on the special edge should have a surface rule, the other cell should be empty
Otherwise, the level-set components are integrates twice (or never)!

The convention which we use is:
- the cell with the **lower global index** has the full rule
- the other cell is empty
We use the global index here, so that the result is "stable" even if we are at an MPI boundary.
**Parameter:** `intOrder` - 
**Parameter:** `jCell` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule.BoundaryLineRule(System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.levelsetonedgerule.boundarylinerule(system.int32,system.int32)"></a>
**Summary:** **This is a special case: level-set coincides with a cell-face; 
cell is either full or empty:**

Call this function when the **BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule.IsSpecialCell(System.Int32)** returns true.

Note:
Only one of the two cells on the special edge should have a surface rule, the other cell should be empty
Otherwise, the level-set components are integrates twice (or never)!

The convention which we use is:
- the cell with the **lower global index** has the full rule
- the other cell is empty
We use the global index here, so that the result is "stable" even if we are at an MPI boundary.
**Parameter:** `intOrder` - 
**Parameter:** `jCell` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule.VolumeQuadRule(System.Int32,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.levelsetonedgerule.volumequadrule(system.int32,system.int32,system.int32)"></a>
**Summary:** **This is a special case: level-set coincides with a cell-face; 
cell is either full or empty:**

Call this function when the **BoSSS.Foundation.XDG.Quadrature.LevelSetOnEdgeRule.IsSpecialCell(System.Int32)** returns true.

Note:
Only one of the two cells on the special edge should have a surface rule, the other cell should be empty
Otherwise, the level-set components are integrates twice (or never)!

The convention which we use is:
- the cell with the **lower global index** has the full rule
- the other cell is empty
We use the global index here, so that the result is "stable" even if we are at an MPI boundary.

## Class: BoSSS.Foundation.XDG.Quadrature.Beck.BeckSettingsOverride <a id="bosss.foundation.xdg.quadrature.beck.becksettingsoverride"></a>

**Summary:** Just a hack to enable special handling of cells where levelset=1 lies on an edge


### Field: BoSSS.Foundation.XDG.Quadrature.Beck.BeckSettingsOverride.doubleCutCellOverride <a id="bosss.foundation.xdg.quadrature.beck.becksettingsoverride.doublecutcelloverride"></a>
**Summary:** switch to enable special handling for cells, where the levelset=1 lies on an edge

## Class: BoSSS.Foundation.XDG.Quadrature.Beck.BeckBaseScheme <a id="bosss.foundation.xdg.quadrature.beck.beckbasescheme"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Beck.BeckBaseScheme.CellToGlobalHR(System.Int32,BoSSS.Foundation.Grid.Classic.GridData) <a id="bosss.foundation.xdg.quadrature.beck.beckbasescheme.celltoglobalhr(system.int32,bosss.foundation.grid.classic.griddata)"></a>
**Summary:** Creates a Hyperrectangle corresponding to a Grid Cell
**Parameter:** `j` - Cell No.
**Parameter:** `gdat` - Grid
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Beck.BeckBaseScheme.EdgeToGlobalHR(System.Int32,BoSSS.Foundation.Grid.Classic.GridData) <a id="bosss.foundation.xdg.quadrature.beck.beckbasescheme.edgetoglobalhr(system.int32,bosss.foundation.grid.classic.griddata)"></a>
**Summary:** Creates a HyperRectangle From an Edge
**Parameter:** `j` - Edge No.
**Parameter:** `gdat` - Grid
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Beck.BeckBaseScheme.GetCell(System.Int32) <a id="bosss.foundation.xdg.quadrature.beck.beckbasescheme.getcell(system.int32)"></a>
**Summary:** This method reutrn a Hyperrectangle that is exactly the domain we want to integrate
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Beck.BeckBaseScheme.GetPhiEval(System.Int32) <a id="bosss.foundation.xdg.quadrature.beck.beckbasescheme.getphieval(system.int32)"></a>
**Summary:** This method returns a Hyperrectangle that is exactly the domain we want to integrate
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Beck.BeckBaseScheme.GetSymbols(BoSSS.Foundation.XDG.Quadrature.LevelSetCombination) <a id="bosss.foundation.xdg.quadrature.beck.beckbasescheme.getsymbols(bosss.foundation.xdg.quadrature.levelsetcombination)"></a>
**Summary:** utility function to get the Symbols used by Intersecting Quadrature
**Parameter:** `lscomb` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.BruteForceSettingsOverride <a id="bosss.foundation.xdg.quadrature.bruteforcesettingsoverride"></a>

**Summary:** Just a hack to enable special handling of cells where levelset=1 lies on an edge


### Field: BoSSS.Foundation.XDG.Quadrature.BruteForceSettingsOverride.doubleCutCellOverride <a id="bosss.foundation.xdg.quadrature.bruteforcesettingsoverride.doublecutcelloverride"></a>
**Summary:** switch to enable special handling for cells, where the levelset=1 lies on an edge

## Class: BoSSS.Foundation.XDG.Quadrature.BruteForceZeroScheme <a id="bosss.foundation.xdg.quadrature.bruteforcezeroscheme"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.BruteForceZeroScheme.#ctor(System.Action{System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray},System.Func{System.Int32,System.Double}) <a id="bosss.foundation.xdg.quadrature.bruteforcezeroscheme.#ctor(system.action{system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray},system.func{system.int32,system.double})"></a>

## Class: BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector <a id="bosss.foundation.xdg.quadrature.multilevelsetonedgedetector"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.IsSpecialCell(System.Int32) <a id="bosss.foundation.xdg.quadrature.multilevelsetonedgedetector.isspecialcell(system.int32)"></a>
**Summary:** Determine cells in which the **BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.iLevSet** lies on a face
**Parameter:** `j` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.IsActiveCell(System.Int32) <a id="bosss.foundation.xdg.quadrature.multilevelsetonedgedetector.isactivecell(system.int32)"></a>
**Summary:** Determines if the cell lies in the part of **BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.iLevSet** where **BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.jLevSet** is active
**Parameter:** `cell` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.IsActiveEdge(System.Int32) <a id="bosss.foundation.xdg.quadrature.multilevelsetonedgedetector.isactiveedge(system.int32)"></a>
**Summary:** Determines if the edge lies in the part of **BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.iLevSet** where **BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.jLevSet** is active
**Parameter:** `j` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.IsSpecialEdge(System.Int32) <a id="bosss.foundation.xdg.quadrature.multilevelsetonedgedetector.isspecialedge(system.int32)"></a>
**Summary:** Determine edges in which one of the neighbors is a [BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.IsSpecialCell(System.Int32)](#bosss.foundation.xdg.quadrature.multilevelsetonedgedetector.isspecialcell(system.int32))
**Parameter:** `j` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.MultiLevelSetOnEdgeDetector.GetSpecialFace(System.Int32) <a id="bosss.foundation.xdg.quadrature.multilevelsetonedgedetector.getspecialface(system.int32)"></a>
**Summary:** return the face index, for the special face in a certain cell

## Class: BoSSS.Foundation.XDG.Quadrature.Saye.SayeComboIntegrand`2 <a id="bosss.foundation.xdg.quadrature.saye.sayecombointegrand`2"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeComboIntegrand`2.ComboEvaluate(System.Int32,`1) <a id="bosss.foundation.xdg.quadrature.saye.sayecombointegrand`2.comboevaluate(system.int32,`1)"></a>
**Summary:** Returns surface and volume quadrature nodes, respectively.
**Parameter:** `Cell` - 
**Parameter:** `arg` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussComboRuleFactory <a id="bosss.foundation.xdg.quadrature.saye.sayegausscomborulefactory"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussComboRuleFactory.#ctor(BoSSS.Foundation.XDG.Quadrature.Saye.ISayeGaussComboRule,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.quadrature.saye.sayegausscomborulefactory.#ctor(bosss.foundation.xdg.quadrature.saye.isayegausscomborule,bosss.foundation.grid.cellmask)"></a>
**Summary:** Calculates surface and volume quadrature rules in one step, which is faster when both rules 
are needed. Before calling GetSurfaceRule() or GetVolumeRule() to receive the respective factories, call 
CalculateComboQuadRuleSet(...).


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussComboRuleFactory.GetSurfaceFactory <a id="bosss.foundation.xdg.quadrature.saye.sayegausscomborulefactory.getsurfacefactory"></a>
**Summary:** Returns factory for surface rules
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussComboRuleFactory.GetVolumeFactory <a id="bosss.foundation.xdg.quadrature.saye.sayegausscomborulefactory.getvolumefactory"></a>
**Summary:** Returns factory for volume rules
**Returns:**



## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussComboRuleFactory.CalculateComboQuadRuleSet(BoSSS.Foundation.Grid.ExecutionMask,System.Int32) <a id="bosss.foundation.xdg.quadrature.saye.sayegausscomborulefactory.calculatecomboquadruleset(bosss.foundation.grid.executionmask,system.int32)"></a>
**Summary:** Run this
**Parameter:** `mask` - 
**Parameter:** `order` - 

## Class: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussRule_Cube <a id="bosss.foundation.xdg.quadrature.saye.sayegaussrule_cube"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussRule_Cube.EvaluateBounds(BoSSS.Foundation.XDG.Quadrature.Saye.LinearSayeSpace{BoSSS.Foundation.Grid.RefElements.Cube},BoSSS.Foundation.XDG.Quadrature.Saye.LinearPSI{BoSSS.Foundation.Grid.RefElements.Cube},BoSSS.Foundation.NodeSet,System.Int32) <a id="bosss.foundation.xdg.quadrature.saye.sayegaussrule_cube.evaluatebounds(bosss.foundation.xdg.quadrature.saye.linearsayespace{bosss.foundation.grid.refelements.cube},bosss.foundation.xdg.quadrature.saye.linearpsi{bosss.foundation.grid.refelements.cube},bosss.foundation.nodeset,system.int32)"></a>
**Summary:** First order approximation of  delta >= sup_x|psi(x) - psi(x_center)|
**Parameter:** `Arg` - 
**Parameter:** `psi` - 
**Parameter:** `x_center` - 
**Parameter:** `cell` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.Saye.ISayeGaussComboRule <a id="bosss.foundation.xdg.quadrature.saye.isayegausscomborule"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.ISayeGaussComboRule.ComboEvaluate(System.Int32) <a id="bosss.foundation.xdg.quadrature.saye.isayegausscomborule.comboevaluate(system.int32)"></a>
**Summary:** 0: Volume Rule, 1: Surface Rule
Should be a struct anyways.
**Parameter:** `cell` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.Saye.SayeFactories <a id="bosss.foundation.xdg.quadrature.saye.sayefactories"></a>

**Summary:** Holds available factories for Saye quadrature.


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeFactories.SayeGaussRule_Volume3D(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm) <a id="bosss.foundation.xdg.quadrature.saye.sayefactories.sayegaussrule_volume3d(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm)"></a>
**Summary:** Gauss rules for $\oint_{\frakI \cap K_j } \ldots \dS$ in the 3D case


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeFactories.SayeGaussRule_NegativeVolume3D(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm) <a id="bosss.foundation.xdg.quadrature.saye.sayefactories.sayegaussrule_negativevolume3d(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm)"></a>
**Summary:** Gauss rules for $\oint_{\frakI \cap K_j } \ldots \dS$ in the 3D case


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeFactories.SayeGaussRule_Surface3D(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm) <a id="bosss.foundation.xdg.quadrature.saye.sayefactories.sayegaussrule_surface3d(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm)"></a>
**Summary:** Gauss rules for $\oint_{\frakI \cap K_j } \ldots \dS$ in the 3D case


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeFactories.SayeGaussRule_Volume2D(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm) <a id="bosss.foundation.xdg.quadrature.saye.sayefactories.sayegaussrule_volume2d(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm)"></a>
**Summary:** Gauss rules for $\int_{\frakA \cap K_j } \ldots \dV$ in the 2D case


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeFactories.SayeGaussRule_NegativeVolume2D(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm) <a id="bosss.foundation.xdg.quadrature.saye.sayefactories.sayegaussrule_negativevolume2d(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm)"></a>
**Summary:** Gauss rules for $\int_{\frakA \cap K_j } \ldots \dV$ in the 2D case


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeFactories.SayeGaussRule_Surface2D(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData,BoSSS.Foundation.XDG.Quadrature.HMF.LineSegment.IRootFindingAlgorithm) <a id="bosss.foundation.xdg.quadrature.saye.sayefactories.sayegaussrule_surface2d(bosss.foundation.xdg.levelsettracker.levelsetdata,bosss.foundation.xdg.quadrature.hmf.linesegment.irootfindingalgorithm)"></a>
**Summary:** Gauss rules for $\oint_{\frakI \cap K_j } \ldots \dS$ in the 2D case

## Class: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussRule_Square <a id="bosss.foundation.xdg.quadrature.saye.sayegaussrule_square"></a>


## Method: BoSSS.Foundation.XDG.Quadrature.Saye.SayeGaussRule_Square.EvaluateBounds(BoSSS.Foundation.XDG.Quadrature.Saye.SayeSquare,BoSSS.Foundation.XDG.Quadrature.Saye.LinearPSI{BoSSS.Foundation.Grid.RefElements.Square},BoSSS.Foundation.NodeSet,System.Int32) <a id="bosss.foundation.xdg.quadrature.saye.sayegaussrule_square.evaluatebounds(bosss.foundation.xdg.quadrature.saye.sayesquare,bosss.foundation.xdg.quadrature.saye.linearpsi{bosss.foundation.grid.refelements.square},bosss.foundation.nodeset,system.int32)"></a>
**Summary:** First order approximation of  delta >= sup_x|psi(x) - psi(x_center)|
**Parameter:** `Arg` - 
**Parameter:** `psi` - 
**Parameter:** `x_center` - 
**Parameter:** `cell` - 
**Returns:**


## Class: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator"></a>

**Summary:** Implementation of [BoSSS.Foundation.XDG.LevelSetIntegrator](#bosss.foundation.xdg.levelsetintegrator) that is able to
integrate an arbitrary scalar field over a level set. The idea behind
this class is write the integral of a scalar integrand g over the 
zero level set (given by $\Phi = 0$) I as
\f{multline*}
\int \limits_I g ds \\
= \int \limits_I g \vec{n}_I \vec{n}_I ds \\
= \int \limits_I g \frac{\nabla \Phi}{|\nabla \Phi|} \vec{n}_I ds
\f{multline*}
and using Gauss' theorem on the modified integrand
$\vec{g} = g \frac{\nabla \Phi}{|\nabla \Phi|}$


### Field: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_levSet <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_levset"></a>
**Summary:** The level set to be integrated over


### Field: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_LevelSetGradientBuffer <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_levelsetgradientbuffer"></a>
**Summary:** Buffer for the gradient of the level set, see
[BoSSS.Foundation.XDG.ILevelSet.EvaluateGradient(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray)](BoSSS.Foundation.md#bosss.foundation.xdg.ilevelset.evaluategradient(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray))


### Field: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_LevelSetHessianBuffer <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_levelsethessianbuffer"></a>
**Summary:** Buffer for the second derivatives of the levels et,
[BoSSS.Foundation.XDG.ILevelSet.EvaluateHessian(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray)](BoSSS.Foundation.md#bosss.foundation.xdg.ilevelset.evaluatehessian(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray))


### Field: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_WeighFunctionBuffer <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_weighfunctionbuffer"></a>
**Summary:** Buffer for the weight function, see
[BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateWeightFunction(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluateweightfunction(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray))


### Field: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_IntegrandBuffer <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_integrandbuffer"></a>
**Summary:** Buffer for the values of the field to be integrated, see
[BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_Field](#bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_field)


### Field: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_IntegrandGradientBuffer <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_integrandgradientbuffer"></a>
**Summary:** Buffer for the gradients of the field to be integrated, see
[BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_Field](#bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_field)


### Field: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_Field <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_field"></a>
**Summary:** The field to be integrated


## Method: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.SinglePhaseField,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Int32,BoSSS.Foundation.Grid.SubGrid,System.Int32) <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.#ctor(bosss.foundation.xdg.levelsettracker,bosss.foundation.singlephasefield,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule},bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.cellboundaryquadrule},system.int32,bosss.foundation.grid.subgrid,system.int32)"></a>
**Summary:** Constructs an integrator for the given field
'field'.
**Parameter:** `trk` - The tracker containing the level set to be integrated over
**Parameter:** `field` - The field to be integrated
**Parameter:** `volumeFactory` - [BoSSS.Foundation.XDG.LevelSetIntegrator.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Int32,BoSSS.Foundation.Grid.SubGrid,System.Int32)](#bosss.foundation.xdg.levelsetintegrator.#ctor(bosss.foundation.xdg.levelsettracker,system.int32,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule},bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.cellboundaryquadrule},system.int32,bosss.foundation.grid.subgrid,system.int32))
**Parameter:** `boundaryFactory` - [BoSSS.Foundation.XDG.LevelSetIntegrator.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Int32,BoSSS.Foundation.Grid.SubGrid,System.Int32)](#bosss.foundation.xdg.levelsetintegrator.#ctor(bosss.foundation.xdg.levelsettracker,system.int32,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule},bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.cellboundaryquadrule},system.int32,bosss.foundation.grid.subgrid,system.int32))
**Parameter:** `quadOrder` - [BoSSS.Foundation.XDG.LevelSetIntegrator.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Int32,BoSSS.Foundation.Grid.SubGrid,System.Int32)](#bosss.foundation.xdg.levelsetintegrator.#ctor(bosss.foundation.xdg.levelsettracker,system.int32,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule},bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.cellboundaryquadrule},system.int32,bosss.foundation.grid.subgrid,system.int32))
**Parameter:** `sgrd` - 
**Parameter:** `LevSetIdx` - 


## Method: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.EvaluateIntegrand(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.evaluateintegrand(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Evaluates the modified integrand which is
\f$ 
\vec{g} = g \frac{\nabla \Phi}{|\nabla \Phi|}
\f$ 
where g represents [BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.m_Field](#bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.m_field).


## Method: BoSSS.Foundation.XDG.Quadrature.ScalarFieldLevelSetIntegrator.EvaluateDivergenceOfIntegrand(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.quadrature.scalarfieldlevelsetintegrator.evaluatedivergenceofintegrand(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Evaluates the divergence of the modified integrand 
$\nabla \cdot \vec{g} = \nabla \cdot (g \frac{\nabla \Phi}{|\nabla \Phi|})$ 
which can be expanded to
$ 
\nabla \cdot \vec{g} = \nabla g \frac{\nabla \Phi}{|\nabla \Phi|} + g (
\frac{\Delta \Phi}{|\nabla \Phi|}
- \frac{\nabla \Phi}{|\nabla \Phi|} \frac{H(\Phi)}{|\nabla \Phi|} \frac{\nabla \Phi}{|\nabla \Phi|})
$ 
using the chain rule. HEre, $H(\Phi)$ 
denotes the Hessian of the level set (i.e., the second derivatives)

## Class: BoSSS.Foundation.XDG.Quadrature.SurfaceElementEdgeIntegrationMetric <a id="bosss.foundation.xdg.quadrature.surfaceelementedgeintegrationmetric"></a>

**Summary:** Integration metric for $D-2$-dimensional integral the boundary of surface elements for each edge.
This is a point in 2D and a line in 3D,
i.e., for an edge $e_i$ an integral of the type
\[
\int_{e_j \cap \mathfrak{I}}  f \mathrm{dl} .
\]


### Property: BoSSS.Foundation.XDG.Quadrature.SurfaceElementEdgeIntegrationMetric.AlwaysUsePerNodeScaling <a id="bosss.foundation.xdg.quadrature.surfaceelementedgeintegrationmetric.alwaysusepernodescaling"></a>
**Summary:** For the integral over the surface element boundary, 
the metric depends on the node (if the element transformation applies some shearing transformation),
but only in 3D


## Method: BoSSS.Foundation.XDG.Quadrature.SurfaceElementEdgeIntegrationMetric.GetScalingsForLinearElements(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.Quadrature.QuadRule,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.surfaceelementedgeintegrationmetric.getscalingsforlinearelements(bosss.foundation.grid.igriddata,bosss.foundation.quadrature.quadrule,system.int32,system.int32)"></a>
**Summary:** in 2D, the boundary of surface elements are just points -- one needs a count measure, where the integration metric is always 1


## Method: BoSSS.Foundation.XDG.Quadrature.SurfaceElementEdgeIntegrationMetric.GetScalingsForNonlinElements(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.Quadrature.QuadRule,System.Int32,System.Int32) <a id="bosss.foundation.xdg.quadrature.surfaceelementedgeintegrationmetric.getscalingsfornonlinelements(bosss.foundation.grid.igriddata,bosss.foundation.quadrature.quadrule,system.int32,system.int32)"></a>
**Summary:** In 3D, the integral transformation metric is the local stretching of a tangent.

## Class: BoSSS.Foundation.XDG.LevelSetIntegrator <a id="bosss.foundation.xdg.levelsetintegrator"></a>

**Summary:** Integrates some vector field over the manifold defined by a zero
level set. To do so, Gauss' theorem is applied to the surface integral
over the level set. This results into
- a surface integral over the parts of the edges of the integration
cell associated with species A and
- a volume integral over the sub-volume of the integration cell
associated with species A
which will be evaluated by this class.


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.m_LevSetTrk <a id="bosss.foundation.xdg.levelsetintegrator.m_levsettrk"></a>
**Summary:** The level set tracker tracking the level set to be integrated over


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.m_NoOfIntegrands <a id="bosss.foundation.xdg.levelsetintegrator.m_noofintegrands"></a>
**Summary:** The number of integrals to perform simultaneously


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.m_SurfaceIntegrator <a id="bosss.foundation.xdg.levelsetintegrator.m_surfaceintegrator"></a>
**Summary:** Integrator for the surface integrals


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.m_VoumeIntegrator <a id="bosss.foundation.xdg.levelsetintegrator.m_voumeintegrator"></a>
**Summary:** Integrator for the volume integrals


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.m_LevSetIdx <a id="bosss.foundation.xdg.levelsetintegrator.m_levsetidx"></a>
**Summary:** Index of the level set to be integrated over


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.m_IntegrationResult <a id="bosss.foundation.xdg.levelsetintegrator.m_integrationresult"></a>
**Summary:** Stores the integration result


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.m_SubGrid <a id="bosss.foundation.xdg.levelsetintegrator.m_subgrid"></a>
**Summary:** Restriction of the computational domain.


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,System.Int32,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule},BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule},System.Int32,BoSSS.Foundation.Grid.SubGrid,System.Int32) <a id="bosss.foundation.xdg.levelsetintegrator.#ctor(bosss.foundation.xdg.levelsettracker,system.int32,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule},bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.cellboundaryquadrule},system.int32,bosss.foundation.grid.subgrid,system.int32)"></a>
**Summary:** Constructs an integrator.
**Parameter:** `lsTrk` - The level set tracker tracking the level set to be integrated over
**Parameter:** `NoOfIntegrands` - The number of integrals to perform simultaneously
**Parameter:** `volumeFactory` - The quadrature rule factory for the volume integrals. Note that the
integrand is discontinuous and that special quadrature rules should
be used for this case.
**Parameter:** `boundaryFactory` - The quadrature rule factory for the surface integrals. Note that the
integrand is discontinuous and that special quadrature rules should
be used for this case.
**Parameter:** `quadOrder` - The desired quadrature rule (for surface and volume integrals)
**Parameter:** `LevSetIdx` - The id of the level set to be integrated over.
**Parameter:** `sgrd` - the subgrid which is used for the mapping the results
(see [BoSSS.Foundation.XDG.LevelSetIntegrator.Execute(ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.execute(ilpsp.multidimensionalarray))).


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateIntegrand(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsetintegrator.evaluateintegrand(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Override this method by evaluating the integrand of the surface
integral on all edges of all cells between
'j0' and 'j0' +
'Length'.
**Parameter:** `j0` - The index of the first cell to be integrated over.
**Parameter:** `Length` - The number of cells to be integrated over.
**Parameter:** `EvalResult` - On exit: Contains the result of the evaluation

1st index: Cell index - 'j0'
2nd index: Node index
3rd index: Integrand index
4th index: Spatial dimension (0, 1 or 2)
**Parameter:** `QuadNodes` - quadrature nodes


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateDivergenceOfIntegrand(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsetintegrator.evaluatedivergenceofintegrand(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Override this method by evaluating the divergence of the integrand
of the surface integral (i.e., by evaluating the integrand of the
volume integral) in all cells between 'j0' and
'j0' + 'Length'.
**Parameter:** `j0` - The index of the first cell to be integrated over.
**Parameter:** `Length` - The number of cells to be integrated over.
**Parameter:** `EvalResult` - On exit: Contains the result of the evaluation

1st index: Cell index - 'j0'
2nd index: Node index
3rd index: Integrand index
**Parameter:** `QuadNodes` - quadrature nodes


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.ExecuteA <a id="bosss.foundation.xdg.levelsetintegrator.executea"></a>
**Summary:** Calculates the integral(s) over the level set. Version with memory
allocation.
**Returns:**
The integral of the integrand [BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateIntegrand(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluateintegrand(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)) over the
level set.


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.Execute(ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsetintegrator.execute(ilpsp.multidimensionalarray)"></a>
**Summary:** Calculates the integral(s) over the level set. Version without
memory allocation.
**Parameter:** `IntegrationResult` - On Exit: Contains the integral of the integrand
[BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateIntegrand(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluateintegrand(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)) over the level set.


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateWeightFunction(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsetintegrator.evaluateweightfunction(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** This weight function is used to combine the result of the
integration over the volume with negative level set values with
the result of the integration over the volume with positive level
set values. Used by [BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator](#bosss.foundation.xdg.levelsetintegrator.surfaceintegrator) and
[BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator](#bosss.foundation.xdg.levelsetintegrator.volumeintegrator).
**Parameter:** `i0` - The first cell to be integrated over.
**Parameter:** `Length` - The number of cells to be integrated over.
**Parameter:** `outp` - On exit: The weight factor for each node.

1st index: Cell index - 'i0'
2nd index: Node index
**Parameter:** `nodes` - Quadrature nodes.
**Remark:**
The current implementation is built such that only the integral
over the larger sub-volume contributes to the integration result.
This avoids bad results in cells with very small sub-volumes (which
only contain very few integration points)

## Class: BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator <a id="bosss.foundation.xdg.levelsetintegrator.surfaceintegrator"></a>

**Summary:** Integrator for the surface integral.


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.m_Owner <a id="bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.m_owner"></a>
**Summary:** Creator of this object.


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.m_WeightBuffer <a id="bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.m_weightbuffer"></a>
**Summary:** Buffer for [BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateWeightFunction(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluateweightfunction(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray))


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.m_ResultBuffer <a id="bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.m_resultbuffer"></a>
**Summary:** Buffer for the integration results.


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.#ctor(BoSSS.Foundation.XDG.LevelSetIntegrator,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.CellBoundaryQuadRule}) <a id="bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.#ctor(bosss.foundation.xdg.levelsetintegrator,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.cellboundaryquadrule})"></a>
**Summary:** Constructs a surface integrator.
**Parameter:** `owner` - Creator of this object.
**Parameter:** `rule` - The quadrature rule to be used


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.AllocateBuffers(System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.allocatebuffers(system.int32,bosss.foundation.nodeset)"></a>
**Summary:** Allocates memory for [BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.m_WeightBuffer](#bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.m_weightbuffer) and
[BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.m_ResultBuffer](#bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.m_resultbuffer)


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.Quadrature.CellBoundaryQuadRule,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.evaluate(system.int32,system.int32,bosss.foundation.quadrature.cellboundaryquadrule,ilpsp.multidimensionalarray)"></a>
**Summary:** Evaluates the integrand of the surface integral by making use
of [BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateIntegrand(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluateintegrand(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)) and
[BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateWeightFunction(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluateweightfunction(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)).


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.SurfaceIntegrator.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsetintegrator.surfaceintegrator.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Stores the integration results in
[BoSSS.Foundation.XDG.LevelSetIntegrator.m_IntegrationResult](#bosss.foundation.xdg.levelsetintegrator.m_integrationresult) using the order defined by
[BoSSS.Foundation.XDG.LevelSetIntegrator.m_SubGrid](#bosss.foundation.xdg.levelsetintegrator.m_subgrid). Note that the result of the surface
integration is subtracted.
**Parameter:** `i0` - 
**Parameter:** `Length` - 
**Parameter:** `ResultsOfIntegration` - 

## Class: BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator <a id="bosss.foundation.xdg.levelsetintegrator.volumeintegrator"></a>

**Summary:** Integrator for the volume integral.


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator.m_Owner <a id="bosss.foundation.xdg.levelsetintegrator.volumeintegrator.m_owner"></a>
**Summary:** Creator of this object.


### Field: BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator.m_WeightBuffer <a id="bosss.foundation.xdg.levelsetintegrator.volumeintegrator.m_weightbuffer"></a>
**Summary:** Buffer for [BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateWeightFunction(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluateweightfunction(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray))


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator.#ctor(BoSSS.Foundation.XDG.LevelSetIntegrator,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.levelsetintegrator.volumeintegrator.#ctor(bosss.foundation.xdg.levelsetintegrator,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Constructs a volume integrator.
**Parameter:** `owner` - Creator of this object.
**Parameter:** `volumeRule` - quadrature rules and domain


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator.AllocateBuffers(System.Int32,BoSSS.Foundation.NodeSet) <a id="bosss.foundation.xdg.levelsetintegrator.volumeintegrator.allocatebuffers(system.int32,bosss.foundation.nodeset)"></a>
**Summary:** Allocates memory for [BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator.m_WeightBuffer](#bosss.foundation.xdg.levelsetintegrator.volumeintegrator.m_weightbuffer).


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.Quadrature.QuadRule,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsetintegrator.volumeintegrator.evaluate(system.int32,system.int32,bosss.foundation.quadrature.quadrule,ilpsp.multidimensionalarray)"></a>
**Summary:** Modulates the result of
[BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateDivergenceOfIntegrand(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluatedivergenceofintegrand(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)) by the weights
given by [BoSSS.Foundation.XDG.LevelSetIntegrator.EvaluateWeightFunction(BoSSS.Foundation.NodeSet,System.Int32,System.Int32,ilPSP.MultidimensionalArray)](#bosss.foundation.xdg.levelsetintegrator.evaluateweightfunction(bosss.foundation.nodeset,system.int32,system.int32,ilpsp.multidimensionalarray)).


## Method: BoSSS.Foundation.XDG.LevelSetIntegrator.VolumeIntegrator.SaveIntegrationResults(System.Int32,System.Int32,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.levelsetintegrator.volumeintegrator.saveintegrationresults(system.int32,system.int32,ilpsp.multidimensionalarray)"></a>
**Summary:** Stores the integration results in
[BoSSS.Foundation.XDG.LevelSetIntegrator.m_IntegrationResult](#bosss.foundation.xdg.levelsetintegrator.m_integrationresult) using the order defined by
[BoSSS.Foundation.XDG.LevelSetIntegrator.m_SubGrid](#bosss.foundation.xdg.levelsetintegrator.m_subgrid).
**Parameter:** `i0` - 
**Parameter:** `Length` - 
**Parameter:** `ResultsOfIntegration` - 

## Class: BoSSS.Foundation.XDG.LevelSetIntersectionIntegrationMetric <a id="bosss.foundation.xdg.levelsetintersectionintegrationmetric"></a>

**Summary:** integration metric for $D-2$-dimensional integral on the intersection of two level-sets. This is a point in 2D and a line in 3D,
i.e., for a cell $K_j$ this is an integral of the type:
\[
\int_{K_j  \cap \mathfrak{I}_2 \cap \mathfrak{I}_2}  f \mathrm{dl} .
\]


### Property: BoSSS.Foundation.XDG.LevelSetIntersectionIntegrationMetric.AlwaysUsePerNodeScaling <a id="bosss.foundation.xdg.levelsetintersectionintegrationmetric.alwaysusepernodescaling"></a>
**Summary:** For the integral over the level-set intersection, 
the metric depends on the node (if the element transformation applies some shearing transformation),
but only in 3D


## Method: BoSSS.Foundation.XDG.LevelSetIntersectionIntegrationMetric.GetScalingsForLinearElements(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.Quadrature.QuadRule,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsetintersectionintegrationmetric.getscalingsforlinearelements(bosss.foundation.grid.igriddata,bosss.foundation.quadrature.quadrule,system.int32,system.int32)"></a>
**Summary:** in 2D, the level-set intersection are just points -- one needs a count measure, where the integration metric is always 1


## Method: BoSSS.Foundation.XDG.LevelSetIntersectionIntegrationMetric.GetScalingsForNonlinElements(BoSSS.Foundation.Grid.IGridData,BoSSS.Foundation.Quadrature.QuadRule,System.Int32,System.Int32) <a id="bosss.foundation.xdg.levelsetintersectionintegrationmetric.getscalingsfornonlinelements(bosss.foundation.grid.igriddata,bosss.foundation.quadrature.quadrule,system.int32,system.int32)"></a>
**Summary:** In 3D, the integral transformation metric is the local stretching of a tangent.

## Class: BoSSS.Foundation.XDG.XQuadFactoryHelper <a id="bosss.foundation.xdg.xquadfactoryhelper"></a>

**Summary:** Auxiliary class that helps with the creation of XDG-quadrature schemes;
instances can be obtained via [BoSSS.Foundation.XDG.LevelSetTracker.GetXQuadFactoryHelper(BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32)](#bosss.foundation.xdg.levelsettracker.getxquadfactoryhelper(bosss.foundation.xdg.cutcellquadraturemethod,system.int32)).


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetData[],BoSSS.Foundation.XDG.CutCellQuadratureMethod) <a id="bosss.foundation.xdg.xquadfactoryhelper.#ctor(bosss.foundation.xdg.levelsettracker.levelsetdata[],bosss.foundation.xdg.cutcellquadraturemethod)"></a>
**Summary:** ctor.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper._GetSurfaceElement_BoundaryRuleFactory(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelper._getsurfaceelement_boundaryrulefactory(system.int32,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Returns a rule for the edges of surface-elements (elements on the zero-level-set surface, 
i.e. on $K \cap \mathfrak{I}$.
(point integrals in 2D, Line integrals in 3D)
**Returns:**
the returned factory produces [BoSSS.Foundation.Quadrature.CellBoundaryQuadRule](BoSSS.Foundation.md#bosss.foundation.quadrature.cellboundaryquadrule)'s


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetSurfaceElement_BoundaryRuleFactory(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelper.getsurfaceelement_boundaryrulefactory(system.int32,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Returns a rule factory for the boundary of surface-elements 
(elements on the zero-level-set surface), i.e. on $K \cap \mathfrak{I}$ .
This are point integrals in 2D and line integrals in 3D.
**Returns:**
the returned factory produces [BoSSS.Foundation.Quadrature.QuadRule](BoSSS.Foundation.md#bosss.foundation.quadrature.quadrule)'s on edges


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetSurfaceElement_BoundaryRuleFactory(System.Int32,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelper.getsurfaceelement_boundaryrulefactory(system.int32,system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Returns a rule factory for the boundary of surface-elements 
(elements on the zero-level-set surface), i.e. on $K \cap \mathfrak{I}$ .
This are point integrals in 2D and line integrals in 3D.
**Returns:**
the returned factory produces [BoSSS.Foundation.Quadrature.QuadRule](BoSSS.Foundation.md#bosss.foundation.quadrature.quadrule)'s on edges


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetCellFaceFactory(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes) <a id="bosss.foundation.xdg.xquadfactoryhelper.getcellfacefactory(system.int32,bosss.foundation.grid.refelements.refelement,bosss.foundation.xdg.quadrature.hmf.jumptypes)"></a>
**Summary:** Quadrature rule on cell boundaries


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetEdgeRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelper.getedgerulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Generates a quadrature rule factory for the cut edge integrals.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetEdgeRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelper.getedgerulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates an edge quadrature rule factory for edges cut by two level sets.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetVolRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelper.getvolrulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Generates a quadrature rule factory for the cut volume integrals.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetVolRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelper.getvolrulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates a volume quadrature rule factory for cells cut by two level sets.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetSurfaceFactory(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelper.getsurfacefactory(system.int32,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Generates a quadrature rule factory for integrating over the zero-level-set surface.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetSurfaceFactory(System.Int32,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelper.getsurfacefactory(system.int32,system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates a quadrature rule factory for integrating over a surface.
The surface is defined by two conditions: 'levSetIndex0' = 0 and on side 'jmp1' of 'levSetIndex1'


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.GetIntersectionRuleFactory(System.Int32,System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelper.getintersectionrulefactory(system.int32,system.int32,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates a quadrature rule factory the intersection of levelset0 and levelset1 where levelset0 = levelset1 = 0
This is a point in 2D, a line in 3D.

## Class: BoSSS.Foundation.XDG.XQuadFactoryHelper.ComplementaryRuleFactory <a id="bosss.foundation.xdg.xquadfactoryhelper.complementaryrulefactory"></a>

**Summary:** Creates, from a rule for the positive domain ([BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes.Heaviside](#bosss.foundation.xdg.quadrature.hmf.jumptypes.heaviside))
the rule for the negative domain and vice-versa.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelper.ComplementaryRuleFactory.GetCachedRuleOrders <a id="bosss.foundation.xdg.xquadfactoryhelper.complementaryrulefactory.getcachedruleorders"></a>
**Summary:** If there are any cached rules, this method returns their order.

## Class: BoSSS.Foundation.XDG.XQuadFactoryHelperAlgoim <a id="bosss.foundation.xdg.xquadfactoryhelperalgoim"></a>

**Summary:** Auxiliary class that helps with the creation of XDG-quadrature schemes for Algoim [BoSSS.Foundation.XDG.Quadrature.Algoim.AlgoimFactories](#bosss.foundation.xdg.quadrature.algoim.algoimfactories);
instances can be obtained via [BoSSS.Foundation.XDG.LevelSetTracker.GetXQuadFactoryHelper(BoSSS.Foundation.XDG.CutCellQuadratureMethod,System.Int32)](#bosss.foundation.xdg.levelsettracker.getxquadfactoryhelper(bosss.foundation.xdg.cutcellquadraturemethod,system.int32)).


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperAlgoim.CheckJmp(BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes) <a id="bosss.foundation.xdg.xquadfactoryhelperalgoim.checkjmp(bosss.foundation.xdg.quadrature.hmf.jumptypes)"></a>
**Summary:** Checks if the jump type is implemented and determines if negativeVolume is desired
**Parameter:** `jmp` - 


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperAlgoim.CheckKref(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelperalgoim.checkkref(system.int32,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Checks if reference element exists

## Class: BoSSS.Foundation.XDG.XQuadSchemeHelper <a id="bosss.foundation.xdg.xquadschemehelper"></a>

**Summary:** Provides quadrature schemes for typical XDG-cases;


### Property: BoSSS.Foundation.XDG.XQuadSchemeHelper.NonAgglomeratedMetrics <a id="bosss.foundation.xdg.xquadschemehelper.nonagglomeratedmetrics"></a>


### Property: BoSSS.Foundation.XDG.XQuadSchemeHelper.CutCellQuadratureMethod <a id="bosss.foundation.xdg.xquadschemehelper.cutcellquadraturemethod"></a>
**Summary:** Selected variant of the moment-fitting procedure


### Property: BoSSS.Foundation.XDG.XQuadSchemeHelper.GhostSupport <a id="bosss.foundation.xdg.xquadschemehelper.ghostsupport"></a>
**Summary:** If true, [BoSSS.Foundation.XDG.XQuadSchemeHelper.GetEdgeGhostScheme(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.Grid.EdgeMask)](#bosss.foundation.xdg.xquadschemehelper.getedgeghostscheme(bosss.foundation.xdg.speciesid,bosss.foundation.grid.edgemask)) is supported, otherwise not.
**Remark:**
Currently (april2016), nobody is using this feature,
therefore this is hard-coded to false.


### Property: BoSSS.Foundation.XDG.XQuadSchemeHelper.SpeciesList <a id="bosss.foundation.xdg.xquadschemehelper.specieslist"></a>
**Summary:** All species for which agglomeration is available.


### Property: BoSSS.Foundation.XDG.XQuadSchemeHelper.XDGSpaceMetrics <a id="bosss.foundation.xdg.xquadschemehelper.xdgspacemetrics"></a>
**Summary:** owner object.


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.#ctor(BoSSS.Foundation.XDG.XDGSpaceMetrics) <a id="bosss.foundation.xdg.xquadschemehelper.#ctor(bosss.foundation.xdg.xdgspacemetrics)"></a>
**Summary:** ctor.


### Field: BoSSS.Foundation.XDG.XQuadSchemeHelper.m_HMFEdgesDomain <a id="bosss.foundation.xdg.xquadschemehelper.m_hmfedgesdomain"></a>
**Summary:** All edges (for each reference element, for each level-set) for which the HMF must be used.
1st index: volume reference element
2nd index: level set


### Field: BoSSS.Foundation.XDG.XQuadSchemeHelper.m_CutEdges <a id="bosss.foundation.xdg.xquadschemehelper.m_cutedges"></a>
**Summary:** All edges which are cut by a level-set.
1st index: volume reference element
2nd index: level set
**Remark:**
Be aware that this might contain also edges like e,
which are, topologically inner edges of the cut-cell-subgrid but not cut by the level-set:

o----------o-----------o
|          |           |
|     **********       |
|     *    |   *       |
o ----*----o---*-------o
|     *    |   *       |
********     e    ************Level-Set
|          |           |
o----------o-----------o


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.GetCutEdges(BoSSS.Foundation.Grid.RefElements.RefElement,System.Int32) <a id="bosss.foundation.xdg.xquadschemehelper.getcutedges(bosss.foundation.grid.refelements.refelement,system.int32)"></a>
**Summary:** all edges which are cut by level set #'iLevSet' and which belong to a cell with
reference element 'Kref'.


### Field: BoSSS.Foundation.XDG.XQuadSchemeHelper.m_SpeciesSubgrid_InnerAndDomainEdges <a id="bosss.foundation.xdg.xquadschemehelper.m_speciessubgrid_inneranddomainedges"></a>
**Summary:** initialized by the constructor to avoid MPI-deadlocks;
keys: species 'S' 
value: an edge-mask containing all edges that are at least partly covered by species 'S'


### Field: BoSSS.Foundation.XDG.XQuadSchemeHelper.m_CutCellSubgrid_InnerEdges <a id="bosss.foundation.xdg.xquadschemehelper.m_cutcellsubgrid_inneredges"></a>
**Summary:** initialized by the constructor to avoid MPI-deadlocks;


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.Get_SurfaceElement_EdgeQuadScheme(BoSSS.Foundation.XDG.SpeciesId,System.Int32) <a id="bosss.foundation.xdg.xquadschemehelper.get_surfaceelement_edgequadscheme(bosss.foundation.xdg.speciesid,system.int32)"></a>
**Summary:** Edge quadrature for the surface elements, i.e., a $D-2$ dimensional integral.
For each cut background-cell $ K_j $, the surface element is $ K_j \cap \mathfrak{I} $ and its boundaries is  $ \partial K_j \cap \mathfrak{I} $; 
Therefore, one need to integrate over the line integrals:
\[
\int_{\partial K_j \cap \mathfrak{I} } \ldots \mathrm{dl} .
\]


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.Get_SurfaceElement_VolumeQuadScheme(BoSSS.Foundation.XDG.SpeciesId,System.Int32) <a id="bosss.foundation.xdg.xquadschemehelper.get_surfaceelement_volumequadscheme(bosss.foundation.xdg.speciesid,system.int32)"></a>
**Summary:** Volume quadrature for the surface elements, i.e., a $D-1$ dimensional integral.
For each cut background-cell $K_j$, the surface element is $K_j \cap \mathfrak{I}$; 
\[
\oint_{K_j \cap \mathfrak{I} } \ldots \mathrm{dS} .
\]


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.GetContactLineQuadScheme(BoSSS.Foundation.XDG.SpeciesId,System.Int32,System.Int32) <a id="bosss.foundation.xdg.xquadschemehelper.getcontactlinequadscheme(bosss.foundation.xdg.speciesid,system.int32,system.int32)"></a>
**Summary:** Intersection of two level-sets 'iLevSet0' and 'iLevSet1'
\[
\int_{K_j \cap \mathfrak{I}_0 \cap \mathfrak{I}_1 } \ldots \mathrm{dl} .
\]


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.GetEdgeQuadScheme(BoSSS.Foundation.XDG.SpeciesId,System.Boolean,BoSSS.Foundation.Grid.EdgeMask,System.Nullable{System.Int32}) <a id="bosss.foundation.xdg.xquadschemehelper.getedgequadscheme(bosss.foundation.xdg.speciesid,system.boolean,bosss.foundation.grid.edgemask,system.nullable{system.int32})"></a>
**Summary:** Edge quadrature for the surface elements, i.e. for each cut background-cell $K_j$ a quadrature to approximate
\[
\oint_{\partial K_j \cap \mathfrak{I} } \ldots \mathrm{dS} .
\]


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.IdentifyWing(System.Int32,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xquadschemehelper.identifywing(system.int32,bosss.foundation.xdg.speciesid)"></a>
**Summary:** For some species 'sp',
this function computes on which side/wing
of level-set no. 'levSetIdx')
the species is located.
**Remark:**
Nur ein Provisorium, das ganze Konzept ist noch etwas unausgereift. (Habe einen Nachmittag lang darueber nachgedacht, keinen bessere Idee gehabt,
und darum...).


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.IdentifyWingA(System.Int32,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xquadschemehelper.identifywinga(system.int32,bosss.foundation.xdg.speciesid)"></a>
**Summary:** Returns the Jumptype of the species.
Handle with care! Does this really work?
**Parameter:** `levSetIdx` - 
**Parameter:** `sp` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.SpeciesAreSeparatedByLevSet(System.Int32,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xquadschemehelper.speciesareseparatedbylevset(system.int32,bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid)"></a>
**Summary:** Does levSet separate species A and B?


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.GetEdgeGhostScheme(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.Grid.EdgeMask) <a id="bosss.foundation.xdg.xquadschemehelper.getedgeghostscheme(bosss.foundation.xdg.speciesid,bosss.foundation.grid.edgemask)"></a>
**Summary:** Quadrature scheme which is used for the penalty components on ghost edges, for species 'sp'.


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.GetEdgeMask(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.Grid.EdgeMask) <a id="bosss.foundation.xdg.xquadschemehelper.getedgemask(bosss.foundation.xdg.speciesid,bosss.foundation.grid.edgemask)"></a>
**Summary:** All edges that have to be considered for the integration of species 'sp'.
**Parameter:** `sp` - 
**Parameter:** `IntegrationDomainRestriction` - Optional restriction to the integration domain.


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.GetVolumeQuadScheme(BoSSS.Foundation.XDG.SpeciesId,System.Boolean,BoSSS.Foundation.Grid.CellMask,System.Nullable{System.Int32}) <a id="bosss.foundation.xdg.xquadschemehelper.getvolumequadscheme(bosss.foundation.xdg.speciesid,system.boolean,bosss.foundation.grid.cellmask,system.nullable{system.int32})"></a>
**Summary:** Fills up the volume scheme for species 'sp'.


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.GetLevelSetquadScheme(System.Int32,BoSSS.Foundation.Grid.CellMask,System.Nullable{System.Int32}) <a id="bosss.foundation.xdg.xquadschemehelper.getlevelsetquadscheme(system.int32,bosss.foundation.grid.cellmask,system.nullable{system.int32})"></a>
**Summary:** Quadrature scheme for the integration over the level-set, i.e. for each cut background-cell $K_j$ a quadrature to approximate
\f[
\oint_{K_j \cap \mathfrak{I} } \ldots \mathrm{dS} .
\f]


## Method: BoSSS.Foundation.XDG.XQuadSchemeHelper.RuleInfo(BoSSS.Foundation.XDG.SpeciesId,System.String,System.String,System.String,System.String,System.Int32,System.Int32) <a id="bosss.foundation.xdg.xquadschemehelper.ruleinfo(bosss.foundation.xdg.speciesid,system.string,system.string,system.string,system.string,system.int32,system.int32)"></a>
**Summary:** Writes diagnostic information about quadrature rules into csv-textfiles.

## Class: BoSSS.Foundation.XDG.ReducedRegionCode <a id="bosss.foundation.xdg.reducedregioncode"></a>

**Summary:** Encodes the cut-cell - state of a cell, for all four level sets.


### Field: BoSSS.Foundation.XDG.ReducedRegionCode.rrc <a id="bosss.foundation.xdg.reducedregioncode.rrc"></a>
**Summary:** 3adic representation of the reduced region for all four level sets;


### Property: BoSSS.Foundation.XDG.ReducedRegionCode._Val <a id="bosss.foundation.xdg.reducedregioncode._val"></a>
**Summary:** For one level set, the reduced region is one of the numbers 0,1 or 2:

2: the cell if in the positive FAR region: distance == 7, i.e. the code is 0xf
1:the cell if in the negative FAR region: distance == -1, i.e the code is 0x1
0:the cell is cut or in the near region: -6 < distance < 6

The reduced region code is build from the reduced regions of each level set 
by encoding them into a 3-adic representation.


## Method: BoSSS.Foundation.XDG.ReducedRegionCode.Equals(System.Object) <a id="bosss.foundation.xdg.reducedregioncode.equals(system.object)"></a>
**Summary:** equality


## Method: BoSSS.Foundation.XDG.ReducedRegionCode.GetHashCode <a id="bosss.foundation.xdg.reducedregioncode.gethashcode"></a>
**Summary:** hasch code


## Method: BoSSS.Foundation.XDG.ReducedRegionCode.op_Equality(BoSSS.Foundation.XDG.ReducedRegionCode,BoSSS.Foundation.XDG.ReducedRegionCode) <a id="bosss.foundation.xdg.reducedregioncode.op_equality(bosss.foundation.xdg.reducedregioncode,bosss.foundation.xdg.reducedregioncode)"></a>
**Summary:** equality


## Method: BoSSS.Foundation.XDG.ReducedRegionCode.op_Inequality(BoSSS.Foundation.XDG.ReducedRegionCode,BoSSS.Foundation.XDG.ReducedRegionCode) <a id="bosss.foundation.xdg.reducedregioncode.op_inequality(bosss.foundation.xdg.reducedregioncode,bosss.foundation.xdg.reducedregioncode)"></a>
**Summary:** inequality


## Method: BoSSS.Foundation.XDG.ReducedRegionCode.Extract(System.UInt16) <a id="bosss.foundation.xdg.reducedregioncode.extract(system.uint16)"></a>
**Summary:** Extracts the reduced region code.
**Parameter:** `RegionCode` - 
**Returns:**
the reduced region code for the "full" region code 'RegionCode';
this is a number between 0 (including) and 81 (excluding).

## Class: BoSSS.Foundation.XDG.FrameBase_TraceDGhandling <a id="bosss.foundation.xdg.framebase_tracedghandling"></a>

**Summary:** Specifies how TraceDG and XDG degrees of freedom (DOFs) are handled in the context of species framing.
Used to control which types of basis functions are included in the framed mapping/vector:


### Field: BoSSS.Foundation.XDG.FrameBase_TraceDGhandling.DG_XDG_and_TraceDG <a id="bosss.foundation.xdg.framebase_tracedghandling.dg_xdg_and_tracedg"></a>
**Summary:** Include all DOFs (standard DG, XDG, and TraceDG)


### Field: BoSSS.Foundation.XDG.FrameBase_TraceDGhandling.Without_TraceDG <a id="bosss.foundation.xdg.framebase_tracedghandling.without_tracedg"></a>
**Summary:** Exclude TraceDG DOFs; only standard DG and XDG are included.


### Field: BoSSS.Foundation.XDG.FrameBase_TraceDGhandling.Without_DG_and_XDG <a id="bosss.foundation.xdg.framebase_tracedghandling.without_dg_and_xdg"></a>
**Summary:** Exclude standard DG and XDG DOFs; only TraceDG is included.

## Class: BoSSS.Foundation.XDG.FrameBase <a id="bosss.foundation.xdg.framebase"></a>

**Summary:** common functionality for the framing classes [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1](#bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1) and [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1](#bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1).


## Method: BoSSS.Foundation.XDG.FrameBase.CreateWithoutTraceDG(BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.framebase.createwithouttracedg(bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** Replaces , in 'full':
- all [BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis)-objects with their non-cut counterparts ([BoSSS.Foundation.XDG.XDGBasis.NonX_Basis](#bosss.foundation.xdg.xdgbasis.nonx_basis).
- all [BoSSS.Foundation.XDG.TraceDGBasis](#bosss.foundation.xdg.tracedgbasis)-objects with **BoSSS.Foundation.XDG.FrameBase.EmptyBasis**


## Method: BoSSS.Foundation.XDG.FrameBase.CreateMapStandard(BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.framebase.createmapstandard(bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** Keeps all three, DG/XDG and TraceDG


## Method: BoSSS.Foundation.XDG.FrameBase.CreateMapWithoutXDG(BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.framebase.createmapwithoutxdg(bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** Replaces , in 'full':
- all [BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis)-objects with **BoSSS.Foundation.XDG.FrameBase.EmptyBasis**
- all [BoSSS.Foundation.XDG.TraceDGBasis](#bosss.foundation.xdg.tracedgbasis)-objects with their non-cut counterparts ([BoSSS.Foundation.XDG.XDGBasis.NonX_Basis](#bosss.foundation.xdg.xdgbasis.nonx_basis).


## Method: BoSSS.Foundation.XDG.FrameBase.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.UnsetteledCoordinateMapping,System.Boolean,BoSSS.Foundation.XDG.FrameBase_TraceDGhandling) <a id="bosss.foundation.xdg.framebase.#ctor(bosss.foundation.xdg.levelsettracker.levelsetregions,bosss.foundation.xdg.speciesid,bosss.foundation.unsetteledcoordinatemapping,system.boolean,bosss.foundation.xdg.framebase_tracedghandling)"></a>
**Summary:** ctor
**Parameter:** `regions` - l
**Parameter:** `spcId` - species which should be framed
**Parameter:** `__FullMap` - 
**Parameter:** `SupportExternal` - true: support also indices related to external/ghost cells
**Parameter:** `traceDGmode` -
- false: TraceDG DOFs are sent to Nirvana 
- true:  the opposite


### Property: BoSSS.Foundation.XDG.FrameBase.FrameMap <a id="bosss.foundation.xdg.framebase.framemap"></a>
**Summary:** Frame mapping, i.e. only the DG-basis of the related [BoSSS.Foundation.XDG.FrameBase.Species](#bosss.foundation.xdg.framebase.species).


### Property: BoSSS.Foundation.XDG.FrameBase.FullMap <a id="bosss.foundation.xdg.framebase.fullmap"></a>
**Summary:** Full mapping, i.e. including all species.


### Property: BoSSS.Foundation.XDG.FrameBase.Regions <a id="bosss.foundation.xdg.framebase.regions"></a>
**Summary:** regions halt


### Property: BoSSS.Foundation.XDG.FrameBase.Species <a id="bosss.foundation.xdg.framebase.species"></a>
**Summary:** the 'framed' species.


### Field: BoSSS.Foundation.XDG.FrameBase.IndexTrafoWithinCell <a id="bosss.foundation.xdg.framebase.indextrafowithincell"></a>
**Summary:** required for index transformations in external cells


## Method: BoSSS.Foundation.XDG.FrameBase.Frame2Full_Loc(System.Int64) <a id="bosss.foundation.xdg.framebase.frame2full_loc(system.int64)"></a>
**Summary:** conversion of framed index (index into this object) to full index (object which is framed),
for local indices
**Parameter:** `iFrame` - a local index


## Method: BoSSS.Foundation.XDG.FrameBase.Frame2Full(System.Int64) <a id="bosss.foundation.xdg.framebase.frame2full(system.int64)"></a>
**Summary:** conversion of framed index (index into this object) to full index (object which is framed).
**Parameter:** `iFrame` - a global index

## Class: BoSSS.Foundation.XDG.UnsetteledCoordinateMapping_Extensions <a id="bosss.foundation.xdg.unsetteledcoordinatemapping_extensions"></a>

**Summary:** XDG-related extension methods for [BoSSS.Foundation.UnsetteledCoordinateMapping](BoSSS.Foundation.md#bosss.foundation.unsetteledcoordinatemapping)


## Method: BoSSS.Foundation.XDG.UnsetteledCoordinateMapping_Extensions.GetSubvectorIndices(BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions,System.Int32[],System.Collections.Generic.ICollection{BoSSS.Foundation.XDG.SpeciesId},BoSSS.Foundation.Grid.CellMask,System.Boolean,BoSSS.Foundation.XDG.MultiphaseCellAgglomerator) <a id="bosss.foundation.xdg.unsetteledcoordinatemapping_extensions.getsubvectorindices(bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.levelsettracker.levelsetregions,system.int32[],system.collections.generic.icollection{bosss.foundation.xdg.speciesid},bosss.foundation.grid.cellmask,system.boolean,bosss.foundation.xdg.multiphasecellagglomerator)"></a>
**Summary:** returns global unique indices which correlate to a certain sub-set of ...

the mappings's basis ('mapping', [BoSSS.Foundation.UnsetteledCoordinateMapping.BasisS](BoSSS.Foundation.md#bosss.foundation.unsetteledcoordinatemapping.basiss)).
species ('_SpcIds').
cells ('cm').
**Parameter:** `mapping` - the mapping
**Parameter:** `Fields` - determines which fields should be in the sub-vector-indices-list
**Parameter:** `_SpcIds` - determines which species should be in the sub-vector-indices-list; null indicates all species.
**Parameter:** `cm` - determines which cells should be in the sub-vector-indices-list; null indicates all cells.
**Parameter:** `regions` - Determines which XDG-coordinate belongs to which species.
**Parameter:** `presenceTest` - if true, cells where some species has zero measure are excluded from the sub-vector-indices-list.
**Parameter:** `drk` - a cell-agglomeration object: if null, ignored; if provided,
cells which are eliminated by the agglomeration are excluded from the sub-vector-indices-list
**Returns:**
a list of global (over all MPI processes) unique indices.

## Class: BoSSS.Foundation.XDG.SpeciesId <a id="bosss.foundation.xdg.speciesid"></a>

**Summary:** 32-bit identifier for a species.

**Remark:**
species are specified as strings; Because string operations,
e.g. like comparison are relatively costly, a more efficient
32-Bit code is assigned with each species.


### Field: BoSSS.Foundation.XDG.SpeciesId.cntnt <a id="bosss.foundation.xdg.speciesid.cntnt"></a>
**Summary:** The actual id


## Method: BoSSS.Foundation.XDG.SpeciesId.Equals(System.Object) <a id="bosss.foundation.xdg.speciesid.equals(system.object)"></a>
**Summary:** equality


## Method: BoSSS.Foundation.XDG.SpeciesId.GetHashCode <a id="bosss.foundation.xdg.speciesid.gethashcode"></a>
**Summary:** hasch code


## Method: BoSSS.Foundation.XDG.SpeciesId.op_Equality(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.speciesid.op_equality(bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid)"></a>
**Summary:** equality


## Method: BoSSS.Foundation.XDG.SpeciesId.op_Inequality(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.speciesid.op_inequality(bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid)"></a>
**Summary:** inequality

## Class: BoSSS.Foundation.XDG.XDGField <a id="bosss.foundation.xdg.xdgfield"></a>

**Summary:** a DG field for a cut-cell-basis ([BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis));

## Class: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield"></a>

**Summary:** A single phase field that represents just one species (from all
species in the cut-cell field); It is zero within all cells in
which no DOF for the species are allocated. (The allocation is
controlled by the Level set Tracker.) This field is just a shallow
copy of the cut-cell-field, i.e. any manipulation on this object
will be reflected onto the owning (see [BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.Owner](#bosss.foundation.xdg.xdgfield.speciesshadowfield.owner))
cut-cell-field and vice-versa.


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.#ctor(BoSSS.Foundation.XDG.XDGField,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.#ctor(bosss.foundation.xdg.xdgfield,bosss.foundation.xdg.speciesid)"></a>
**Summary:** ctor


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.Coordinates <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.coordinates"></a>
**Summary:** DG Coordinates for the species [BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.SpeciesId](#bosss.foundation.xdg.xdgfield.speciesshadowfield.speciesid).


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.Identification <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.identification"></a>
**Summary:** Setting is forbidden for shadow fields.


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.Owner <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.owner"></a>
**Summary:** the linked cut-cell-field


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.SpeciesId <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.speciesid"></a>
**Summary:** identification for the species that this field represents


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.SpeciesName <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.speciesname"></a>
**Summary:** the name of the species that this field represents


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.Clone <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.clone"></a>
**Summary:** clone


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.LaplacianByFlux(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.SubGrid,BoSSS.Foundation.SubGridBoundaryModes,BoSSS.Foundation.SubGridBoundaryModes) <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.laplacianbyflux(system.double,bosss.foundation.dgfield,bosss.foundation.dgfield,bosss.foundation.grid.subgrid,bosss.foundation.subgridboundarymodes,bosss.foundation.subgridboundarymodes)"></a>
**Summary:** see [BoSSS.Foundation.DGField.LaplacianByFlux(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.SubGrid,BoSSS.Foundation.SubGridBoundaryModes,BoSSS.Foundation.SubGridBoundaryModes)](BoSSS.Foundation.md#bosss.foundation.dgfield.laplacianbyflux(system.double,bosss.foundation.dgfield,bosss.foundation.dgfield,bosss.foundation.grid.subgrid,bosss.foundation.subgridboundarymodes,bosss.foundation.subgridboundarymodes));


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.Laplacian(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.laplacian(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask)"></a>
**Summary:** see [BoSSS.Foundation.DGField.Laplacian(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask)](BoSSS.Foundation.md#bosss.foundation.dgfield.laplacian(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask));


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,System.Int32,System.Double) <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.evaluate(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,system.int32,system.double)"></a>
**Summary:** usual evaluation, just as [BoSSS.Foundation.DGField.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,System.Int32,System.Double)](BoSSS.Foundation.md#bosss.foundation.dgfield.evaluate(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,system.int32,system.double));


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.EvaluateGradient(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,System.Int32,System.Double) <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.evaluategradient(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,system.int32,system.double)"></a>
**Summary:** Evaluates the gradient


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.EvaluateEdge(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,System.Int32,System.Double) <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.evaluateedge(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,system.int32,system.double)"></a>
**Summary:** Not implemented yet.


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesShadowField.Initializer <a id="bosss.foundation.xdg.xdgfield.speciesshadowfield.initializer"></a>
**Summary:** not supported for shadow fields

## Class: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates <a id="bosss.foundation.xdg.xdgfield.speciescoordinates"></a>

**Summary:** Used by [BoSSS.Foundation.XDG.XDGField.SpeciesShadowField](#bosss.foundation.xdg.xdgfield.speciesshadowfield), a matrix that
represents the DG coordinates of exactly one species;


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.#ctor(BoSSS.Foundation.XDG.XDGField,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.#ctor(bosss.foundation.xdg.xdgfield,bosss.foundation.xdg.speciesid)"></a>
**Summary:** ctor;


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates._SpecisId <a id="bosss.foundation.xdg.xdgfield.speciescoordinates._specisid"></a>
**Summary:** identification handle for the species id that this coordinate matrix accesses


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.NoOfCols <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.noofcols"></a>
**Summary:** See **ilPSP.Utils.IMatrix.NoOfCols**


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.NoOfRows <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.noofrows"></a>
**Summary:** See **ilPSP.Utils.IMatrix.NoOfRows**


### Property: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.Item(System.Int32,System.Int32) <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.item(system.int32,system.int32)"></a>
**Summary:** See **ilPSP.Utils.IMatrix**


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.Clear <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.clear"></a>
**Summary:** See **ilPSP.Utils.IMatrix.Clear**


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.Scale(System.Double) <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.scale(system.double)"></a>
**Summary:** See **ilPSP.Utils.IMatrix.Scale(System.Double)**


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.Acc(System.Double,ilPSP.Utils.IMatrix) <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.acc(system.double,ilpsp.utils.imatrix)"></a>
**Summary:** accumulates 'a'*'M' to this matrix


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.CopyTo(System.Double[0:,0:],System.Int32,System.Int32) <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.copyto(system.double[0:,0:],system.int32,system.int32)"></a>
**Summary:** See **],System.Int32,System.Int32)**


## Method: BoSSS.Foundation.XDG.XDGField.SpeciesCoordinates.CopyTo``1(``0,System.Boolean,System.Int32) <a id="bosss.foundation.xdg.xdgfield.speciescoordinates.copyto``1(``0,system.boolean,system.int32)"></a>
**Summary:** See **ilPSP.Utils.IMatrix.CopyTo``1(``0,System.Boolean,System.Int32)**


## Method: BoSSS.Foundation.XDG.XDGField.Factory(BoSSS.Foundation.Basis,System.String) <a id="bosss.foundation.xdg.xdgfield.factory(bosss.foundation.basis,system.string)"></a>
**Summary:** a factory that creates [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)-DG-fields.
**Parameter:** `__Basis` - The basis that is used for this field;
Must be a [BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis)-object.
**Parameter:** `__Identification` - identification string for this field;
This can be null or empty, 
however, if IO should be performed for this object, the identification must be unique 
within a given context
**Returns:**
a [BoSSS.Foundation.SinglePhaseField](BoSSS.Foundation.md#bosss.foundation.singlephasefield)-instance


## Method: BoSSS.Foundation.XDG.XDGField.#ctor(BoSSS.Foundation.XDG.XDGBasis) <a id="bosss.foundation.xdg.xdgfield.#ctor(bosss.foundation.xdg.xdgbasis)"></a>
**Summary:** constructor
**Parameter:** `basis` - 


## Method: BoSSS.Foundation.XDG.XDGField.#ctor(BoSSS.Foundation.XDG.XDGBasis,System.String) <a id="bosss.foundation.xdg.xdgfield.#ctor(bosss.foundation.xdg.xdgbasis,system.string)"></a>
**Summary:** constructor
**Parameter:** `basis` - 
**Parameter:** `Identification` - identification string for this field;
This can be null or empty, 
however, if IO should be performed for this object, the identification must be unique 
within a given context


### Property: BoSSS.Foundation.XDG.XDGField.Basis <a id="bosss.foundation.xdg.xdgfield.basis"></a>
**Summary:** Identical to [BoSSS.Foundation.DGField.Basis](BoSSS.Foundation.md#bosss.foundation.dgfield.basis) but return an instance of
[BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis) instead of [BoSSS.Foundation.XDG.XDGField.Basis](#bosss.foundation.xdg.xdgfield.basis)
**Remark:**
A more elegant (i.e. polymorphic) way to accomplish this would be
to make the super class generic but since the functionality is
identical and so polymorphism is not an issue


### Field: BoSSS.Foundation.XDG.XDGField.m_SpeciesShadowFields <a id="bosss.foundation.xdg.xdgfield.m_speciesshadowfields"></a>
**Summary:** caches the return value of [BoSSS.Foundation.XDG.XDGField.GetSpeciesShadowField(BoSSS.Foundation.XDG.SpeciesId)](#bosss.foundation.xdg.xdgfield.getspeciesshadowfield(bosss.foundation.xdg.speciesid));


## Method: BoSSS.Foundation.XDG.XDGField.GetSpeciesShadowField(BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xdgfield.getspeciesshadowfield(bosss.foundation.xdg.speciesid)"></a>
**Summary:** creates the shadow field for the given Species
**Parameter:** `id` - 
**Returns:**

**Remark:**
return value is cached


## Method: BoSSS.Foundation.XDG.XDGField.GetSpeciesShadowField(System.String) <a id="bosss.foundation.xdg.xdgfield.getspeciesshadowfield(system.string)"></a>
**Summary:** see [BoSSS.Foundation.XDG.XDGField.GetSpeciesShadowField(BoSSS.Foundation.XDG.SpeciesId)](#bosss.foundation.xdg.xdgfield.getspeciesshadowfield(bosss.foundation.xdg.speciesid));


## Method: BoSSS.Foundation.XDG.XDGField.AccLaidBack(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.acclaidback(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask)"></a>
**Summary:** see [BoSSS.Foundation.DGField.Acc(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask)](BoSSS.Foundation.md#bosss.foundation.dgfield.acc(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask));
**Remark:**
the other field 'a' can be either a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)
or a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield).


## Method: BoSSS.Foundation.XDG.XDGField.Acc(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.acc(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask)"></a>
**Summary:** see [BoSSS.Foundation.DGField.Acc(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask)](BoSSS.Foundation.md#bosss.foundation.dgfield.acc(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask));
**Remark:**
the other field 'a' can be either a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)
or a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield).


## Method: BoSSS.Foundation.XDG.XDGField.EvaluateJumpHeight(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,System.Int32,System.Double,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xdgfield.evaluatejumpheight(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,system.int32,system.double,bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid)"></a>
**Summary:** Evaluates
$ 
f_A(x_i) - f_B(x_i)
$ 
in all nodes with spatial coordinates
$ x_i$  defined in
'NodeSet' in all cells in the range
['j0'; 'j0' + 'Len']
where $f_A(x)$  and
$f_B(x)$  are the values of the
polynomial defined by the coefficients stored for the species
identified by 'SpeciesIdA' and
'SpeciesIdB', respectively. The result will then
be stored in 'result'
**Parameter:** `j0` - The first cell in the evaluation range.
**Parameter:** `Len` - The length of the evaluation range.
**Parameter:** `NodeSet` - The node set.
**Parameter:** `result` - On exit, the result of the calculation will have been accumulated
here according to the formula
'result' := 'ResultPreScale'*'result' + jump

1st index: Cell index minus 'j0'
2nd index: Node index
**Parameter:** `ResultCellindexOffset` - An offset for the first index of 'result'
**Parameter:** `ResultPreScale` - Scaling of the original content of 'result'. Use
0.0 to overwrite existing value
**Parameter:** `SpeciesIdA` - Id of the first species to be evaluated
**Parameter:** `SpeciesIdB` - Id of the second species to be evaluated


## Method: BoSSS.Foundation.XDG.XDGField.Evaluate(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,System.Int32,System.Double) <a id="bosss.foundation.xdg.xdgfield.evaluate(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,system.int32,system.double)"></a>
**Summary:** Evaluates the cut-cell DG - field;
**Parameter:** `_j0` - local index of the first cell to evaluate
**Parameter:** `_Len` - Number of cells to evaluate
**Parameter:** `_NodeSet` - as usual, the node set;
**Parameter:** `_result` - on exit, result of the evaluations are accumulated there;
the original content is scaled by '_ResultPreScale';
1st index: cell index minus '_j0';
2nd index: node index;
**Parameter:** `_ResultCellindexOffset` - an offset for the first index of '_result';
**Parameter:** `_ResultPreScale` - see '_result'


## Method: BoSSS.Foundation.XDG.XDGField.EvaluateEdge(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,System.Int32,System.Double) <a id="bosss.foundation.xdg.xdgfield.evaluateedge(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,system.int32,system.double)"></a>
**Summary:** [BoSSS.Foundation.DGField.EvaluateEdge(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray,System.Int32,System.Double)](BoSSS.Foundation.md#bosss.foundation.dgfield.evaluateedge(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,ilpsp.multidimensionalarray,system.int32,system.double))


## Method: BoSSS.Foundation.XDG.XDGField.EvaluateGradient(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,System.Int32,System.Double) <a id="bosss.foundation.xdg.xdgfield.evaluategradient(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,system.int32,system.double)"></a>
**Summary:** Evaluates the gradient of the field;
**Parameter:** `j0` - local index of the first cell to evaluate
**Parameter:** `Len` - Number of cells to evaluate
**Parameter:** `NodeSet` - as usual, the node set;
**Parameter:** `result` - on exit, result of the evaluations are accumulated there;
the original content is scaled by 'ResultPreScale';
1st index: cell index minus 'j0';
2nd index: node index;
3rd index: spatial coordinate;
**Parameter:** `ResultCellindexOffset` - an offset for the first index of 'result';
**Parameter:** `ResultPreScale` - see 'result'


## Method: BoSSS.Foundation.XDG.XDGField.EvaluateMean(System.Int32,System.Int32,ilPSP.MultidimensionalArray,System.Int32,System.Double) <a id="bosss.foundation.xdg.xdgfield.evaluatemean(system.int32,system.int32,ilpsp.multidimensionalarray,system.int32,system.double)"></a>
**Summary:** evaluates the mean value over a cell;
of course, the mean value doesn't depend on node set or anything like that,
so no information about that has to be provided.
**Parameter:** `j0` - local index of the first cell to evaluate
**Parameter:** `Len` - Number of cells to evaluate
**Parameter:** `result` - on exit, result of the evaluations are accumulated there;
the original content is scaled by 'ResultPreScale';
1st index: cell index minus 'j0';
**Parameter:** `ResultCellindexOffset` - an offset for the first index of 'result';
**Parameter:** `ResultPreScale` - see 'result'


### Property: BoSSS.Foundation.XDG.XDGField.Coordinates <a id="bosss.foundation.xdg.xdgfield.coordinates"></a>
**Summary:** the DG coordinated of the cut field;
Note that this is a sparse structure, where not all elements are assigned;


## Method: BoSSS.Foundation.XDG.XDGField.Clone <a id="bosss.foundation.xdg.xdgfield.clone"></a>
**Summary:** guess what?


## Method: BoSSS.Foundation.XDG.XDGField.CloneAs <a id="bosss.foundation.xdg.xdgfield.cloneas"></a>
**Summary:** guess what?


### Property: BoSSS.Foundation.XDG.XDGField.UpdateBehaviour <a id="bosss.foundation.xdg.xdgfield.updatebehaviour"></a>
**Summary:** defines the Behavior of the DG coordinates during a [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[]))-call


## Method: BoSSS.Foundation.XDG.XDGField.GetCoordinates4Species(System.Int32,BoSSS.Foundation.XDG.SpeciesId,System.Double[]) <a id="bosss.foundation.xdg.xdgfield.getcoordinates4species(system.int32,bosss.foundation.xdg.speciesid,system.double[])"></a>
**Summary:** Gets the DG coordinates for a specific species in a specific cell;
**Parameter:** `jCell` - local cell index
**Parameter:** `specId` - species ID
**Parameter:** `ouput_DGcords4spec` - on exit, the DG coordinates for species 'specId'
**Returns:**
true, if the cell 'jCell' containes DOF for species 'specId',
otherwise false;


## Method: BoSSS.Foundation.XDG.XDGField.ClearSpecies(BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xdgfield.clearspecies(bosss.foundation.xdg.speciesid)"></a>
**Summary:** sets all DG coordinates that are associated with the species with
ID - number 'SpeciesId' (see [BoSSS.Foundation.XDG.LevelSetTracker.GetSpeciesId(System.String)](#bosss.foundation.xdg.levelsettracker.getspeciesid(system.string))) 
to 0.0. Note that this method does not clear the common DG coordinates (DG - coordinates
common to all species);
**Parameter:** `SpeciesId` - 


## Method: BoSSS.Foundation.XDG.XDGField.GetMPISendBufferSize(System.Int32) <a id="bosss.foundation.xdg.xdgfield.getmpisendbuffersize(system.int32)"></a>
**Summary:** see [BoSSS.Foundation.DGField.GetMPISendBufferSize(System.Int32)](BoSSS.Foundation.md#bosss.foundation.dgfield.getmpisendbuffersize(system.int32));
**Parameter:** `proc` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XDGField.GetMPIRecvBufferSize(System.Int32) <a id="bosss.foundation.xdg.xdgfield.getmpirecvbuffersize(system.int32)"></a>
**Summary:** see [BoSSS.Foundation.DGField.GetMPIRecvBufferSize(System.Int32)](BoSSS.Foundation.md#bosss.foundation.dgfield.getmpirecvbuffersize(system.int32));
**Parameter:** `proc` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XDGField.FillMPISendBuffer(System.Int32,System.Double[],System.Int32) <a id="bosss.foundation.xdg.xdgfield.fillmpisendbuffer(system.int32,system.double[],system.int32)"></a>
**Summary:** see [BoSSS.Foundation.DGField.FillMPISendBuffer(System.Int32,System.Double[],System.Int32)](BoSSS.Foundation.md#bosss.foundation.dgfield.fillmpisendbuffer(system.int32,system.double[],system.int32));
**Parameter:** `proc` - 
**Parameter:** `Buffer` - 
**Parameter:** `st` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XDGField.CopyFromMPIrecvBuffer(System.Int32,System.Double[],System.Int32) <a id="bosss.foundation.xdg.xdgfield.copyfrommpirecvbuffer(system.int32,system.double[],system.int32)"></a>
**Summary:** see [BoSSS.Foundation.DGField.CopyFromMPIrecvBuffer(System.Int32,System.Double[],System.Int32)](BoSSS.Foundation.md#bosss.foundation.dgfield.copyfrommpirecvbuffer(system.int32,system.double[],system.int32));
**Parameter:** `proc` - 
**Parameter:** `Buffer` - 
**Parameter:** `st` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XDGField.GetMeanValue(System.Int32) <a id="bosss.foundation.xdg.xdgfield.getmeanvalue(system.int32)"></a>
**Summary:** Not accurate for cut-cells.


## Method: BoSSS.Foundation.XDG.XDGField.SetMeanValue(System.Int32,System.Double) <a id="bosss.foundation.xdg.xdgfield.setmeanvalue(system.int32,system.double)"></a>
**Parameter:** `j` - 
**Parameter:** `v` - 


## Method: BoSSS.Foundation.XDG.XDGField.ProjectField(System.Double,BoSSS.Foundation.ScalarFunction,BoSSS.Foundation.Quadrature.CellQuadratureScheme) <a id="bosss.foundation.xdg.xdgfield.projectfield(system.double,bosss.foundation.scalarfunction,bosss.foundation.quadrature.cellquadraturescheme)"></a>
**Summary:** performs the projection of 'func' for each species.


## Method: BoSSS.Foundation.XDG.XDGField.ProjectFunction(System.Double,System.Func{ilPSP.Vector,System.Double[],System.Int32,System.Double},BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdgfield.projectfunction(system.double,system.func{ilpsp.vector,system.double[],system.int32,system.double},bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.dgfield[])"></a>
**Summary:** performs the projection of 'f' for each species.


## Method: BoSSS.Foundation.XDG.XDGField.AccConstant(System.Double,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.accconstant(system.double,bosss.foundation.grid.cellmask)"></a>
**Summary:** Add a constant to this field


## Method: BoSSS.Foundation.XDG.XDGField.Derivative(System.Double,BoSSS.Foundation.DGField,System.Int32,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.derivative(system.double,bosss.foundation.dgfield,system.int32,bosss.foundation.grid.cellmask)"></a>
**Summary:** symbolic derivation, cell by cell and species by species;
accumulates the derivative of DG field 'f' 
(along the 'd'-th axis) times 'alpha'
to this field, i.e. 
this = this + 'alpha'* $\frac{\partial}{\partial x_d}$ 'f';
**Parameter:** `f` - 
**Parameter:** `d` - 0 for the x-derivative, 1 for the y-derivative, 2 for the z-derivative
**Parameter:** `alpha` - scaling of 'f';
**Parameter:** `em` - An optional restriction to the domain in which the derivative is computed (it may, e.g.
be only required in boundary cells, so a computation over the whole domain 
would be a waste of computation power. A proper execution mask for this case would be e.g. 
[BoSSS.Foundation.Grid.Classic.GridData.BoundaryCells](BoSSS.Foundation.md#bosss.foundation.grid.classic.griddata.boundarycells).)

if null, the computation is carried out in the whole domain;
**Remark:**
The derivative is calculated by a cell-by-cell (symbolic) derivation of the DG polynomials, therefore the
(effective) DG polynomial degree is one lower than the degree of 'f';
In comparison to [BoSSS.Foundation.XDG.XDGField.DerivativeByFlux(System.Double,BoSSS.Foundation.DGField,System.Int32,BoSSS.Foundation.Grid.SubGrid,BoSSS.Foundation.SubGridBoundaryModes)](#bosss.foundation.xdg.xdgfield.derivativebyflux(system.double,bosss.foundation.dgfield,system.int32,bosss.foundation.grid.subgrid,bosss.foundation.subgridboundarymodes)), this method should be much faster,
because no quadrature is involved;
The field 'f' can be either a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield) or a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield);


## Method: BoSSS.Foundation.XDG.XDGField.DerivativeByFlux(System.Double,BoSSS.Foundation.DGField,System.Int32,BoSSS.Foundation.Grid.SubGrid,BoSSS.Foundation.SubGridBoundaryModes) <a id="bosss.foundation.xdg.xdgfield.derivativebyflux(system.double,bosss.foundation.dgfield,system.int32,bosss.foundation.grid.subgrid,bosss.foundation.subgridboundarymodes)"></a>
**Summary:** equal to implementation in base class, see
[BoSSS.Foundation.DGField.DerivativeByFlux(System.Double,BoSSS.Foundation.DGField,System.Int32,BoSSS.Foundation.Grid.SubGrid,BoSSS.Foundation.SubGridBoundaryModes)](BoSSS.Foundation.md#bosss.foundation.dgfield.derivativebyflux(system.double,bosss.foundation.dgfield,system.int32,bosss.foundation.grid.subgrid,bosss.foundation.subgridboundarymodes));
The DG coordinates of all species are computed equally;


## Method: BoSSS.Foundation.XDG.XDGField.CopyFrom(BoSSS.Foundation.DGField) <a id="bosss.foundation.xdg.xdgfield.copyfrom(bosss.foundation.dgfield)"></a>
**Summary:** initializes this field to be a copy of another field
**Parameter:** `other` - must be a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)-object


## Method: BoSSS.Foundation.XDG.XDGField.ProjectProduct(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask,System.Boolean) <a id="bosss.foundation.xdg.xdgfield.projectproduct(system.double,bosss.foundation.dgfield,bosss.foundation.dgfield,bosss.foundation.grid.cellmask,system.boolean)"></a>
**Summary:** executes [BoSSS.Foundation.DGField.ProjectProduct(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask,System.Boolean)](BoSSS.Foundation.md#bosss.foundation.dgfield.projectproduct(system.double,bosss.foundation.dgfield,bosss.foundation.dgfield,bosss.foundation.grid.cellmask,system.boolean)), for each species.


## Method: BoSSS.Foundation.XDG.XDGField.ProjectQuotient(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask,System.Boolean) <a id="bosss.foundation.xdg.xdgfield.projectquotient(system.double,bosss.foundation.dgfield,bosss.foundation.dgfield,bosss.foundation.grid.cellmask,system.boolean)"></a>
**Summary:** executes [BoSSS.Foundation.DGField.ProjectQuotient(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask,System.Boolean)](BoSSS.Foundation.md#bosss.foundation.dgfield.projectquotient(system.double,bosss.foundation.dgfield,bosss.foundation.dgfield,bosss.foundation.grid.cellmask,system.boolean)), for each species.


## Method: BoSSS.Foundation.XDG.XDGField.ProjectAbs(System.Double,BoSSS.Foundation.Grid.CellMask,BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdgfield.projectabs(system.double,bosss.foundation.grid.cellmask,bosss.foundation.dgfield[])"></a>
**Summary:** executes [BoSSS.Foundation.DGField.ProjectAbs(System.Double,BoSSS.Foundation.Grid.CellMask,BoSSS.Foundation.DGField[])](BoSSS.Foundation.md#bosss.foundation.dgfield.projectabs(system.double,bosss.foundation.grid.cellmask,bosss.foundation.dgfield[])), for each species.


## Method: BoSSS.Foundation.XDG.XDGField.ProjectPow(System.Double,BoSSS.Foundation.DGField,System.Double,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.projectpow(system.double,bosss.foundation.dgfield,system.double,bosss.foundation.grid.cellmask)"></a>
**Summary:** todo


## Method: BoSSS.Foundation.XDG.XDGField.ProjectToSinglePhaseField(System.Int32,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.projecttosinglephasefield(system.int32,bosss.foundation.grid.cellmask)"></a>
**Summary:** Converts a XDG-Field to a SinglePhaseField, while ignoring any negative Side-Effects like Gibbs' phenomena.
Can be executed on a subgrid only.

Factor for the Basis Degree of the returned Field.
A higher Polynomial Degree may be chosen to better represent kinks and jumps.


Returns Field only on a subgrid


## Method: BoSSS.Foundation.XDG.XDGField.L2NormSpecies(System.String,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.l2normspecies(system.string,bosss.foundation.grid.cellmask)"></a>
**Summary:** [BoSSS.Foundation.XDG.XDGField.L2NormSpecies(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.Grid.CellMask)](#bosss.foundation.xdg.xdgfield.l2normspecies(bosss.foundation.xdg.speciesid,bosss.foundation.grid.cellmask))


## Method: BoSSS.Foundation.XDG.XDGField.L2NormSpecies(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.xdgfield.l2normspecies(bosss.foundation.xdg.speciesid,bosss.foundation.grid.cellmask)"></a>
**Summary:** Canonical L2 Norm in the XDG space, i.e.
\[
\left( \int_{\Omega \cap \mathfrak{ s} \cap \text{ CM} }
u(\vec{ x})
\text{dV} \right)^{1/2},
\]
where 
$\mathfrak{s}$ denotes the domain of species 'spc' and
$\text{ CM} }$ denotes the optional cell mask 'cm'.
**Remark:**
The foundation for computing the L2-norm in cut cells is the following relation:
For any arbitrary (i.e. non-orthonormal) DG or XDG basis,
the norm of a Field 
$u = sum_{j} \phi_{j} \tilde{u}_{j}$ is given as:
\[
\left\| u \right\|_{L^2}^2 =
(u, u) = 
\int_\Omega 
\left( \sum_{j} \phi_{j} \tilde{u}_{j} \right) 
\left( \sum_{l} \phi_{l} \tilde{u}_{l} \right) 
dV = 
\sum_{j l} \tilde{u}_{j} \tilde{u}_{l} ( \phi_{j}, \phi_{l} )
=
\tilde{u}^T M \tilde{u},
\]
where $M$ denotes the mass matrix ($M_{j l} = ( \phi_ { j}, \phi_ { l} )$).


## Method: BoSSS.Foundation.XDG.XDGField.OnCompleted <a id="bosss.foundation.xdg.xdgfield.oncompleted"></a>
**Summary:** Do nothing.


## Method: BoSSS.Foundation.XDG.XDGField.OnError(System.Exception) <a id="bosss.foundation.xdg.xdgfield.onerror(system.exception)"></a>
**Summary:** Do nothing.
**Parameter:** `error` - 


### Field: BoSSS.Foundation.XDG.XDGField.m_TrackerVersion <a id="bosss.foundation.xdg.xdgfield.m_trackerversion"></a>
**Summary:** most recent entry for [BoSSS.Foundation.XDG.LevelSetTracker.VersionCnt](#bosss.foundation.xdg.levelsettracker.versioncnt)


## Method: BoSSS.Foundation.XDG.XDGField.OnNext(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions) <a id="bosss.foundation.xdg.xdgfield.onnext(bosss.foundation.xdg.levelsettracker.levelsetregions)"></a>
**Summary:** Updated the data structure of this cut-cell DG field to reflect the
latest status of the level set.
**Parameter:** `levelSetStatus` - 


## Method: BoSSS.Foundation.XDG.XDGField.ProjectFunctionXDG(System.Double,System.Func{ilPSP.Vector,System.Double[],System.Int32,System.Double},BoSSS.Foundation.XDG.XDGField[]) <a id="bosss.foundation.xdg.xdgfield.projectfunctionxdg(system.double,system.func{ilpsp.vector,system.double[],system.int32,system.double},bosss.foundation.xdg.xdgfield[])"></a>
**Summary:** Projects a function onto an XDG Field, using all species
**Parameter:** `alpha` - 
**Parameter:** `f` - 
**Parameter:** `U` - 


## Method: BoSSS.Foundation.XDG.XDGField.ProjectFunctionXDG(System.Double,System.Func{ilPSP.Vector,System.Double[],System.Int32,System.Double},System.Collections.Generic.IList{BoSSS.Foundation.XDG.SpeciesId},BoSSS.Foundation.XDG.XDGField[]) <a id="bosss.foundation.xdg.xdgfield.projectfunctionxdg(system.double,system.func{ilpsp.vector,system.double[],system.int32,system.double},system.collections.generic.ilist{bosss.foundation.xdg.speciesid},bosss.foundation.xdg.xdgfield[])"></a>
**Summary:** Projects a function onto an XDG Field, only on some prescribed species
**Parameter:** `alpha` - 
**Parameter:** `f` - A function $ (\vector{x}, U, \texttt{jcell}) \mapsto f $
**Parameter:** `speciesToEvaluateIDs` - 
**Parameter:** `U` - 

## Class: BoSSS.Foundation.XDG.XDGField.Picker <a id="bosss.foundation.xdg.xdgfield.picker"></a>

**Summary:** picks the result for respective species


## Method: BoSSS.Foundation.XDG.XDGField.EvaluateMultiphase(System.Int32,BoSSS.Foundation.NodeSet,BoSSS.Foundation.XDG.ReducedRegionCode,System.Int32,ilPSP.MultidimensionalArray,System.Int32,System.Double,BoSSS.Foundation.XDG.XDGField.EvaluateInternalSignature,ilPSP.MultidimensionalArray[]@,System.Func{System.Int32,System.Int32[]},BoSSS.Foundation.XDG.XDGField.Picker) <a id="bosss.foundation.xdg.xdgfield.evaluatemultiphase(system.int32,bosss.foundation.nodeset,bosss.foundation.xdg.reducedregioncode,system.int32,ilpsp.multidimensionalarray,system.int32,system.double,bosss.foundation.xdg.xdgfield.evaluateinternalsignature,ilpsp.multidimensionalarray[]@,system.func{system.int32,system.int32[]},bosss.foundation.xdg.xdgfield.picker)"></a>
**Summary:** evaluation of field in cut- or near - cells;


## Method: BoSSS.Foundation.XDG.XDGField.EvaluateStd(System.Int32,System.Int32,BoSSS.Foundation.NodeSet,ilPSP.MultidimensionalArray,System.Int32,System.Double,BoSSS.Foundation.XDG.XDGField.EvaluateInternalSignature) <a id="bosss.foundation.xdg.xdgfield.evaluatestd(system.int32,system.int32,bosss.foundation.nodeset,ilpsp.multidimensionalarray,system.int32,system.double,bosss.foundation.xdg.xdgfield.evaluateinternalsignature)"></a>
**Summary:** evaluation in standard cells (single phase cells)

## Class: BoSSS.Foundation.XDG.XDGField.XDGFieldInitializer <a id="bosss.foundation.xdg.xdgfield.xdgfieldinitializer"></a>

**Summary:** Specialized initializer for [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)s


## Method: BoSSS.Foundation.XDG.XDGField.XDGFieldInitializer.Initialize(BoSSS.Foundation.IO.IInitializationContext) <a id="bosss.foundation.xdg.xdgfield.xdgfieldinitializer.initialize(bosss.foundation.io.iinitializationcontext)"></a>
**Summary:** [BoSSS.Foundation.DGField.FieldInitializer](BoSSS.Foundation.md#bosss.foundation.dgfield.fieldinitializer)
**Parameter:** `c` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XDGField.XDGFieldInitializer.Equals(BoSSS.Foundation.IO.Initializer{BoSSS.Foundation.DGField}) <a id="bosss.foundation.xdg.xdgfield.xdgfieldinitializer.equals(bosss.foundation.io.initializer{bosss.foundation.dgfield})"></a>
**Summary:** Compares the given object 'other'
**Returns:**



## Method: BoSSS.Foundation.XDG.XDGField.XDGFieldInitializer.GetHashCode <a id="bosss.foundation.xdg.xdgfield.xdgfieldinitializer.gethashcode"></a>
**Summary:** Computes a hash code


### Property: BoSSS.Foundation.XDG.XDGField.Initializer <a id="bosss.foundation.xdg.xdgfield.initializer"></a>
**Summary:** To support IO-architecture, NOT for direct user interaction. Note
that it is essential that this member always returns the SAME
object (reference-equals)!


## Method: BoSSS.Foundation.XDG.XDGField.SerializeDGcoords(System.Int32) <a id="bosss.foundation.xdg.xdgfield.serializedgcoords(system.int32)"></a>
**Summary:** stores XDG coordinates species-wise and retains backward compatibility using a mysterious magic header


## Method: BoSSS.Foundation.XDG.XDGField.DeserializeDGcoords(System.Int32,System.Double[]) <a id="bosss.foundation.xdg.xdgfield.deserializedgcoords(system.int32,system.double[])"></a>
**Summary:** loads XDG coordinates species-wise and retains backward compatibility using a mysterious magic header


## Method: BoSSS.Foundation.XDG.XDGField.LoadData(BoSSS.Foundation.IO.ITimestepInfo,System.Collections.Generic.IList{BoSSS.Foundation.IO.CellFieldDataSet},System.Collections.Generic.HashSet{System.Object}) <a id="bosss.foundation.xdg.xdgfield.loaddata(bosss.foundation.io.itimestepinfo,system.collections.generic.ilist{bosss.foundation.io.cellfielddataset},system.collections.generic.hashset{system.object})"></a>
**Summary:** [BoSSS.Foundation.DGField.FieldInitializer](BoSSS.Foundation.md#bosss.foundation.dgfield.fieldinitializer)
**Parameter:** `tsi` - 
**Parameter:** `data` - 
**Parameter:** `loadedObjects` - 


## Method: BoSSS.Foundation.XDG.XDGField.ReportDependentFields <a id="bosss.foundation.xdg.xdgfield.reportdependentfields"></a>
**Summary:** Depends on the level set(s)
**Returns:**


## Class: BoSSS.Foundation.XDG.TestingIOExtensions <a id="bosss.foundation.xdg.testingioextensions"></a>

**Summary:** Another extension class


## Method: BoSSS.Foundation.XDG.TestingIOExtensions.AddDGField(BoSSS.Foundation.TestingIO,BoSSS.Foundation.XDG.XDGField) <a id="bosss.foundation.xdg.testingioextensions.adddgfield(bosss.foundation.testingio,bosss.foundation.xdg.xdgfield)"></a>
**Summary:** Adds an XDG field.


## Method: BoSSS.Foundation.XDG.TestingIOExtensions.LocalError(BoSSS.Foundation.TestingIO,BoSSS.Foundation.XDG.XDGField) <a id="bosss.foundation.xdg.testingioextensions.localerror(bosss.foundation.testingio,bosss.foundation.xdg.xdgfield)"></a>
**Summary:** Adds an XDG field.


## Method: BoSSS.Foundation.XDG.TestingIOExtensions.OverwriteDGField(BoSSS.Foundation.TestingIO,BoSSS.Foundation.XDG.XDGField) <a id="bosss.foundation.xdg.testingioextensions.overwritedgfield(bosss.foundation.testingio,bosss.foundation.xdg.xdgfield)"></a>
**Summary:** Overwrites the memory of a XDG field with the reference data

## Class: BoSSS.Foundation.XDG.TraceDGBasis <a id="bosss.foundation.xdg.tracedgbasis"></a>

**Summary:** Basis for trace-fields, i.e., fields on the level-set surface

**Remark:**
The [BoSSS.Foundation.XDG.TraceDGBasis](#bosss.foundation.xdg.tracedgbasis) class determines the number of degrees-of-freedom 
which are associated with each cell.
- in the FAR-field, trace fields have 0 DOFs
- in the NEAR- and CUT-cells, trace fields have a single set of DOFs, determined by the DG polynomial degree


## Method: BoSSS.Foundation.XDG.TraceDGBasis.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,System.Int32) <a id="bosss.foundation.xdg.tracedgbasis.#ctor(bosss.foundation.xdg.levelsettracker,system.int32)"></a>
**Summary:** ctor.
**Parameter:** `Degree` - 
**Parameter:** `levSetTracker` - 


## Method: BoSSS.Foundation.XDG.TraceDGBasis.GetLength(System.Int32) <a id="bosss.foundation.xdg.tracedgbasis.getlength(system.int32)"></a>


## Method: BoSSS.Foundation.XDG.TraceDGBasis.IsSubBasis(BoSSS.Foundation.Basis) <a id="bosss.foundation.xdg.tracedgbasis.issubbasis(bosss.foundation.basis)"></a>
**Summary:** determines whether this DG basis is a sub-basis (in a vector-space sense)
of another basis 'other'.
**Parameter:** `other` - 
**Returns:**



### Field: BoSSS.Foundation.XDG.TraceDGBasis.m_MinimalLength <a id="bosss.foundation.xdg.tracedgbasis.m_minimallength"></a>
**Summary:** see [BoSSS.Foundation.XDG.TraceDGBasis.MinimalLength](#bosss.foundation.xdg.tracedgbasis.minimallength);


### Field: BoSSS.Foundation.XDG.TraceDGBasis.m_MaximalLength <a id="bosss.foundation.xdg.tracedgbasis.m_maximallength"></a>
**Summary:** see [BoSSS.Foundation.XDG.TraceDGBasis.MaximalLength](#bosss.foundation.xdg.tracedgbasis.maximallength);


### Property: BoSSS.Foundation.XDG.TraceDGBasis.MaximalLength <a id="bosss.foundation.xdg.tracedgbasis.maximallength"></a>
**Summary:** This is the maximum number of degrees-of-freedom that can occur
in one cell, i.e. in a cell which contains all species
tracked by [BoSSS.Foundation.XDG.TraceDGBasis.Tracker](#bosss.foundation.xdg.tracedgbasis.tracker) at once;


### Property: BoSSS.Foundation.XDG.TraceDGBasis.MinimalLength <a id="bosss.foundation.xdg.tracedgbasis.minimallength"></a>
**Summary:** The number of basis functions in uncut cells, 
which is equal to the number of basis polynomials
[BoSSS.Foundation.Basis.Polynomials](BoSSS.Foundation.md#bosss.foundation.basis.polynomials)


### Property: BoSSS.Foundation.XDG.TraceDGBasis.Tracker <a id="bosss.foundation.xdg.tracedgbasis.tracker"></a>
**Summary:** the used tracker for the level set


## Method: BoSSS.Foundation.XDG.TraceDGBasis.Equals(System.Object) <a id="bosss.foundation.xdg.tracedgbasis.equals(system.object)"></a>
**Summary:** two [BoSSS.Foundation.XDG.TraceDGBasis](#bosss.foundation.xdg.tracedgbasis)-objects are equal, if their polynomial list ([BoSSS.Foundation.Basis.Polynomials](BoSSS.Foundation.md#bosss.foundation.basis.polynomials)) is equal (equal Guid for each entry).


## Method: BoSSS.Foundation.XDG.TraceDGBasis.GetHashCode <a id="bosss.foundation.xdg.tracedgbasis.gethashcode"></a>
**Summary:** default implementation;


### Property: BoSSS.Foundation.XDG.TraceDGBasis.NonX_Basis <a id="bosss.foundation.xdg.tracedgbasis.nonx_basis"></a>
**Summary:** creates the standard (not extended) DG basis of the same polynomial degree as this one.

## Class: BoSSS.Foundation.XDG.TraceDGBasis.TraceDGBasisInitializer <a id="bosss.foundation.xdg.tracedgbasis.tracedgbasisinitializer"></a>

**Summary:** This class contains all necessary information to recreate an [BoSSS.Foundation.XDG.TraceDGBasis](#bosss.foundation.xdg.tracedgbasis)


### Field: BoSSS.Foundation.XDG.TraceDGBasis.TraceDGBasisInitializer.TrackerInitializer <a id="bosss.foundation.xdg.tracedgbasis.tracedgbasisinitializer.trackerinitializer"></a>
**Summary:** Initializer of the tracker the represented basis depends on.


## Method: BoSSS.Foundation.XDG.TraceDGBasis.TraceDGBasisInitializer.Initialize(BoSSS.Foundation.IO.IInitializationContext) <a id="bosss.foundation.xdg.tracedgbasis.tracedgbasisinitializer.initialize(bosss.foundation.io.iinitializationcontext)"></a>
**Summary:** See [BoSSS.Foundation.Basis.BasisInitializer](BoSSS.Foundation.md#bosss.foundation.basis.basisinitializer)
**Parameter:** `c` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.TraceDGBasis.TraceDGBasisInitializer.Equals(BoSSS.Foundation.IO.Initializer{BoSSS.Foundation.Basis}) <a id="bosss.foundation.xdg.tracedgbasis.tracedgbasisinitializer.equals(bosss.foundation.io.initializer{bosss.foundation.basis})"></a>
**Summary:** Compares the given object 'other'


## Method: BoSSS.Foundation.XDG.TraceDGBasis.TraceDGBasisInitializer.GetHashCode <a id="bosss.foundation.xdg.tracedgbasis.tracedgbasisinitializer.gethashcode"></a>
**Summary:** Computes a hash code


### Field: BoSSS.Foundation.XDG.TraceDGBasis.m_Initializer <a id="bosss.foundation.xdg.tracedgbasis.m_initializer"></a>
**Summary:** Initializer of this basis object


### Property: BoSSS.Foundation.XDG.TraceDGBasis.Initializer <a id="bosss.foundation.xdg.tracedgbasis.initializer"></a>
**Summary:** To support IO-architecture, NOT for direct user interaction. Note
that it is essential that this member always returns the SAME
object (reference-equals)!

## Class: BoSSS.Foundation.XDG.TraceDGField <a id="bosss.foundation.xdg.tracedgfield"></a>

**Summary:** class for trace-fields, i.e., fields on the level-set surface  ([BoSSS.Foundation.XDG.TraceDGBasis](#bosss.foundation.xdg.tracedgbasis));


## Method: BoSSS.Foundation.XDG.TraceDGField.Factory(BoSSS.Foundation.Basis,System.String) <a id="bosss.foundation.xdg.tracedgfield.factory(bosss.foundation.basis,system.string)"></a>
**Summary:** a factory that creates **System.Diagnostics.Trace**-DG-fields.
**Parameter:** `__Basis` - The basis that is used for this field;
Must be a [BoSSS.Foundation.XDG.TraceDGBasis](#bosss.foundation.xdg.tracedgbasis)-object.
**Parameter:** `__Identification` - identification string for this field;
This can be null or empty, 
however, if IO should be performed for this object, the identification must be unique 
within a given context
**Returns:**
a [BoSSS.Foundation.XDG.TraceDGField](#bosss.foundation.xdg.tracedgfield)-instance


## Method: BoSSS.Foundation.XDG.TraceDGField.#ctor(BoSSS.Foundation.XDG.TraceDGBasis) <a id="bosss.foundation.xdg.tracedgfield.#ctor(bosss.foundation.xdg.tracedgbasis)"></a>
**Summary:** constructor
**Parameter:** `basis` - 


## Method: BoSSS.Foundation.XDG.TraceDGField.#ctor(BoSSS.Foundation.XDG.TraceDGBasis,System.String) <a id="bosss.foundation.xdg.tracedgfield.#ctor(bosss.foundation.xdg.tracedgbasis,system.string)"></a>
**Summary:** constructor
**Parameter:** `basis` - 
**Parameter:** `Identification` - identification string for this field;

This can be null or empty, 
however, if IO should be performed for this object, the identification must be unique 
within a given context


### Property: BoSSS.Foundation.XDG.TraceDGField.Basis <a id="bosss.foundation.xdg.tracedgfield.basis"></a>
**Summary:** Identical to [BoSSS.Foundation.DGField.Basis](BoSSS.Foundation.md#bosss.foundation.dgfield.basis) but return an instance of
[BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis) instead of [BoSSS.Foundation.XDG.TraceDGField.Basis](#bosss.foundation.xdg.tracedgfield.basis)
**Remark:**
A more elegant (i.e. polymorphic) way to accomplish this would be
to make the super class generic but since the functionality is
identical and so polymorphism is not an issue


## Method: BoSSS.Foundation.XDG.TraceDGField.AccLaidBack(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.tracedgfield.acclaidback(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask)"></a>
**Summary:** see [BoSSS.Foundation.DGField.Acc(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask)](BoSSS.Foundation.md#bosss.foundation.dgfield.acc(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask));
**Remark:**
the other field 'a' can be either a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)
or a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield).


## Method: BoSSS.Foundation.XDG.TraceDGField.Acc(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.xdg.tracedgfield.acc(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask)"></a>
**Summary:** see [BoSSS.Foundation.DGField.Acc(System.Double,BoSSS.Foundation.DGField,BoSSS.Foundation.Grid.CellMask)](BoSSS.Foundation.md#bosss.foundation.dgfield.acc(system.double,bosss.foundation.dgfield,bosss.foundation.grid.cellmask));
**Remark:**
the other field 'a' can be either a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)
or a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield).


## Method: BoSSS.Foundation.XDG.TraceDGField.Clone <a id="bosss.foundation.xdg.tracedgfield.clone"></a>
**Summary:** guess what?


## Method: BoSSS.Foundation.XDG.TraceDGField.CloneAs <a id="bosss.foundation.xdg.tracedgfield.cloneas"></a>
**Summary:** guess what?


### Property: BoSSS.Foundation.XDG.TraceDGField.UpdateBehaviour <a id="bosss.foundation.xdg.tracedgfield.updatebehaviour"></a>
**Summary:** defines the Behavior of the DG coordinates during a [BoSSS.Foundation.XDG.LevelSetTracker.UpdateTracker(System.Double,System.Int32,System.Boolean,System.Int32[])](#bosss.foundation.xdg.levelsettracker.updatetracker(system.double,system.int32,system.boolean,system.int32[]))-call


## Method: BoSSS.Foundation.XDG.TraceDGField.CopyFrom(BoSSS.Foundation.DGField) <a id="bosss.foundation.xdg.tracedgfield.copyfrom(bosss.foundation.dgfield)"></a>
**Summary:** initializes this field to be a copy of another field
**Parameter:** `other` - must be a [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)-object


## Method: BoSSS.Foundation.XDG.TraceDGField.OnCompleted <a id="bosss.foundation.xdg.tracedgfield.oncompleted"></a>
**Summary:** Do nothing.


## Method: BoSSS.Foundation.XDG.TraceDGField.OnError(System.Exception) <a id="bosss.foundation.xdg.tracedgfield.onerror(system.exception)"></a>
**Summary:** Do nothing.
**Parameter:** `error` - 


### Field: BoSSS.Foundation.XDG.TraceDGField.m_TrackerVersion <a id="bosss.foundation.xdg.tracedgfield.m_trackerversion"></a>
**Summary:** most recent entry for [BoSSS.Foundation.XDG.LevelSetTracker.VersionCnt](#bosss.foundation.xdg.levelsettracker.versioncnt)


## Method: BoSSS.Foundation.XDG.TraceDGField.OnNext(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions) <a id="bosss.foundation.xdg.tracedgfield.onnext(bosss.foundation.xdg.levelsettracker.levelsetregions)"></a>
**Summary:** Updated the data structure of this cut-cell DG field to reflect the
latest status of the level set.
**Parameter:** `levelSetStatus` - 

## Class: BoSSS.Foundation.XDG.TraceDGField.TraceDGFieldInitializer <a id="bosss.foundation.xdg.tracedgfield.tracedgfieldinitializer"></a>

**Summary:** Specialized initializer for [BoSSS.Foundation.XDG.TraceDGField](#bosss.foundation.xdg.tracedgfield)s


## Method: BoSSS.Foundation.XDG.TraceDGField.TraceDGFieldInitializer.Initialize(BoSSS.Foundation.IO.IInitializationContext) <a id="bosss.foundation.xdg.tracedgfield.tracedgfieldinitializer.initialize(bosss.foundation.io.iinitializationcontext)"></a>
**Summary:** [BoSSS.Foundation.DGField.FieldInitializer](BoSSS.Foundation.md#bosss.foundation.dgfield.fieldinitializer)
**Parameter:** `c` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.TraceDGField.TraceDGFieldInitializer.Equals(BoSSS.Foundation.IO.Initializer{BoSSS.Foundation.DGField}) <a id="bosss.foundation.xdg.tracedgfield.tracedgfieldinitializer.equals(bosss.foundation.io.initializer{bosss.foundation.dgfield})"></a>
**Summary:** Compares the given object 'other'
**Returns:**



## Method: BoSSS.Foundation.XDG.TraceDGField.TraceDGFieldInitializer.GetHashCode <a id="bosss.foundation.xdg.tracedgfield.tracedgfieldinitializer.gethashcode"></a>
**Summary:** Computes a hash code


### Property: BoSSS.Foundation.XDG.TraceDGField.Initializer <a id="bosss.foundation.xdg.tracedgfield.initializer"></a>
**Summary:** To support IO-architecture, NOT for direct user interaction. Note
that it is essential that this member always returns the SAME
object (reference-equals)!


## Method: BoSSS.Foundation.XDG.TraceDGField.LoadData(BoSSS.Foundation.IO.ITimestepInfo,System.Collections.Generic.IList{BoSSS.Foundation.IO.CellFieldDataSet},System.Collections.Generic.HashSet{System.Object}) <a id="bosss.foundation.xdg.tracedgfield.loaddata(bosss.foundation.io.itimestepinfo,system.collections.generic.ilist{bosss.foundation.io.cellfielddataset},system.collections.generic.hashset{system.object})"></a>
**Summary:** [BoSSS.Foundation.DGField.FieldInitializer](BoSSS.Foundation.md#bosss.foundation.dgfield.fieldinitializer)
**Parameter:** `tsi` - 
**Parameter:** `data` - 
**Parameter:** `loadedObjects` - 


## Method: BoSSS.Foundation.XDG.TraceDGField.ReportDependentFields <a id="bosss.foundation.xdg.tracedgfield.reportdependentfields"></a>
**Summary:** Depends on the level set(s)
**Returns:**


## Class: BoSSS.Foundation.XDG.XDGBasis <a id="bosss.foundation.xdg.xdgbasis"></a>

**Summary:** A Basis which depends on one ore more level sets (see [BoSSS.Foundation.XDG.XDGBasis.Tracker](#bosss.foundation.xdg.xdgbasis.tracker)).


## Method: BoSSS.Foundation.XDG.XDGBasis.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,System.Int32) <a id="bosss.foundation.xdg.xdgbasis.#ctor(bosss.foundation.xdg.levelsettracker,system.int32)"></a>
**Summary:** ctor.
**Parameter:** `Degree` - 
**Parameter:** `levSetTracker` - 


## Method: BoSSS.Foundation.XDG.XDGBasis.GetSpeciesI0(System.Int32) <a id="bosss.foundation.xdg.xdgbasis.getspeciesi0(system.int32)"></a>
**Summary:** returns the DG coordinate index for the first separate DG coordinate
(DG coordinates which are separate for each species) 
for the species with index 'SpeciesInd'.
**Parameter:** `SpeciesInd` - 
**Returns:**

**Remark:**
Note that the index of some species may vary from cell to cell: E.g.
consider a case with two species, "A" and "B". In cells which contain
only species "A", the species index for "A" is 0 and the species index for "B" 
is not assigned. 
In cell which contain both, "A" and "B", the index for "A" may be 1 and for "B" it may be 0.


## Method: BoSSS.Foundation.XDG.XDGBasis.GetLength(System.Int32) <a id="bosss.foundation.xdg.xdgbasis.getlength(system.int32)"></a>
**Parameter:** `jCell` - 
**Returns:**



### Property: BoSSS.Foundation.XDG.XDGBasis.DOFperSpeciesPerCell <a id="bosss.foundation.xdg.xdgbasis.dofperspeciespercell"></a>
**Summary:** the number of degrees-of-freedom for each species, for each cell.


## Method: BoSSS.Foundation.XDG.XDGBasis.IsSubBasis(BoSSS.Foundation.Basis) <a id="bosss.foundation.xdg.xdgbasis.issubbasis(bosss.foundation.basis)"></a>
**Summary:** determines whether this DG basis is a sub-basis (in a vector-space sense)
of another basis 'other'.
**Parameter:** `other` - 
**Returns:**



### Field: BoSSS.Foundation.XDG.XDGBasis.m_MinimalLength <a id="bosss.foundation.xdg.xdgbasis.m_minimallength"></a>
**Summary:** see [BoSSS.Foundation.XDG.XDGBasis.MinimalLength](#bosss.foundation.xdg.xdgbasis.minimallength);


### Field: BoSSS.Foundation.XDG.XDGBasis.m_MaximalLength <a id="bosss.foundation.xdg.xdgbasis.m_maximallength"></a>
**Summary:** see [BoSSS.Foundation.XDG.XDGBasis.MaximalLength](#bosss.foundation.xdg.xdgbasis.maximallength);


### Property: BoSSS.Foundation.XDG.XDGBasis.MaximalLength <a id="bosss.foundation.xdg.xdgbasis.maximallength"></a>
**Summary:** This is the maximum number of degrees-of-freedom that can occur
in one cell, i.e. in a cell which contains all species
tracked by [BoSSS.Foundation.XDG.XDGBasis.Tracker](#bosss.foundation.xdg.xdgbasis.tracker) at once;


### Property: BoSSS.Foundation.XDG.XDGBasis.MinimalLength <a id="bosss.foundation.xdg.xdgbasis.minimallength"></a>
**Summary:** The number of basis functions in uncut cells, 
which is equal to the number of basis polynomials
[BoSSS.Foundation.Basis.Polynomials](BoSSS.Foundation.md#bosss.foundation.basis.polynomials)


### Property: BoSSS.Foundation.XDG.XDGBasis.Tracker <a id="bosss.foundation.xdg.xdgbasis.tracker"></a>
**Summary:** the used tracker for the level set


## Method: BoSSS.Foundation.XDG.XDGBasis.Equals(System.Object) <a id="bosss.foundation.xdg.xdgbasis.equals(system.object)"></a>
**Summary:** two [BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis)-objects are equal, if their polynomial list
([BoSSS.Foundation.Basis.Polynomials](BoSSS.Foundation.md#bosss.foundation.basis.polynomials)) is equal (equal Guid for each entry),
and if [BoSSS.Foundation.XDG.XDGBasis.DOFperSpeciesPerCell](#bosss.foundation.xdg.xdgbasis.dofperspeciespercell) coincide.
**Parameter:** `obj` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XDGBasis.GetHashCode <a id="bosss.foundation.xdg.xdgbasis.gethashcode"></a>
**Summary:** default implementation;


### Property: BoSSS.Foundation.XDG.XDGBasis.NonX_Basis <a id="bosss.foundation.xdg.xdgbasis.nonx_basis"></a>
**Summary:** creates the standard (not extended) DG basis of the same polynomial degree as this one.


## Method: BoSSS.Foundation.XDG.XDGBasis.CellEval(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.xdgbasis.celleval(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** evaluation of basis function within cells


## Method: BoSSS.Foundation.XDG.XDGBasis.CellEvalGradient(BoSSS.Foundation.NodeSet,System.Int32,System.Int32) <a id="bosss.foundation.xdg.xdgbasis.cellevalgradient(bosss.foundation.nodeset,system.int32,system.int32)"></a>
**Summary:** evaluation of basis function gradient within cells

## Class: BoSSS.Foundation.XDG.XDGBasis.XDGBasisInitializer <a id="bosss.foundation.xdg.xdgbasis.xdgbasisinitializer"></a>

**Summary:** This class contains all necessary information to recreate an
[BoSSS.Foundation.XDG.XDGBasis](#bosss.foundation.xdg.xdgbasis)


### Field: BoSSS.Foundation.XDG.XDGBasis.XDGBasisInitializer.TrackerInitializer <a id="bosss.foundation.xdg.xdgbasis.xdgbasisinitializer.trackerinitializer"></a>
**Summary:** Initializer of the tracker the represented basis depends on.


## Method: BoSSS.Foundation.XDG.XDGBasis.XDGBasisInitializer.Initialize(BoSSS.Foundation.IO.IInitializationContext) <a id="bosss.foundation.xdg.xdgbasis.xdgbasisinitializer.initialize(bosss.foundation.io.iinitializationcontext)"></a>
**Summary:** See [BoSSS.Foundation.Basis.BasisInitializer](BoSSS.Foundation.md#bosss.foundation.basis.basisinitializer)
**Parameter:** `c` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XDGBasis.XDGBasisInitializer.Equals(BoSSS.Foundation.IO.Initializer{BoSSS.Foundation.Basis}) <a id="bosss.foundation.xdg.xdgbasis.xdgbasisinitializer.equals(bosss.foundation.io.initializer{bosss.foundation.basis})"></a>
**Summary:** Compares the given object 'other'


## Method: BoSSS.Foundation.XDG.XDGBasis.XDGBasisInitializer.GetHashCode <a id="bosss.foundation.xdg.xdgbasis.xdgbasisinitializer.gethashcode"></a>
**Summary:** Computes a hash code


### Field: BoSSS.Foundation.XDG.XDGBasis.m_Initializer <a id="bosss.foundation.xdg.xdgbasis.m_initializer"></a>
**Summary:** Initializer of this basis object


### Property: BoSSS.Foundation.XDG.XDGBasis.Initializer <a id="bosss.foundation.xdg.xdgbasis.initializer"></a>
**Summary:** To support IO-architecture, NOT for direct user interaction. Note
that it is essential that this member always returns the SAME
object (reference-equals)!

## Class: BoSSS.Foundation.XDG.BehaveUnder_LevSetMoovement <a id="bosss.foundation.xdg.behaveunder_levsetmoovement"></a>

**Summary:** see [BoSSS.Foundation.XDG.XDGField.UpdateBehaviour](#bosss.foundation.xdg.xdgfield.updatebehaviour);


### Field: BoSSS.Foundation.XDG.BehaveUnder_LevSetMoovement.JustReallocate <a id="bosss.foundation.xdg.behaveunder_levsetmoovement.justreallocate"></a>
**Summary:** just reallocates the memory structure of the cut-cell field;
The behavior in the near band is undefined;


### Field: BoSSS.Foundation.XDG.BehaveUnder_LevSetMoovement.PreserveMemory <a id="bosss.foundation.xdg.behaveunder_levsetmoovement.preservememory"></a>
**Summary:** the values of the DG coordinates are preserved; For new cells (i.e. 
cells where a new species just entered during the last level set movement),
the DG coordinates of the new species are unassigned.


### Field: BoSSS.Foundation.XDG.BehaveUnder_LevSetMoovement.AutoExtrapolate <a id="bosss.foundation.xdg.behaveunder_levsetmoovement.autoextrapolate"></a>
**Summary:** most expensive option: DG coordinates of new cells (i.e. 
cells where a new species just entered during the last level set movement),
are extrapolated from cells where the DG coordinates for the corresponding species are known.

## Class: BoSSS.Foundation.XDG.XDGSpaceMetrics <a id="bosss.foundation.xdg.xdgspacemetrics"></a>

**Summary:** Properties of the discrete XDG space. Note that the properties of discrete XDG space
(e.g. measures of cut-cells and the mass matrix) depend on the 
the chosen type ([BoSSS.Foundation.XDG.CutCellQuadratureMethod](#bosss.foundation.xdg.cutcellquadraturemethod)) and order of the cut-cell quadrature, 
therefore these are collected in this central object.
Instances of this object are obtained via [BoSSS.Foundation.XDG.LevelSetTracker.GetXDGSpaceMetrics(System.Collections.Generic.IEnumerable{BoSSS.Foundation.XDG.SpeciesId},System.Int32,System.Int32)](#bosss.foundation.xdg.levelsettracker.getxdgspacemetrics(system.collections.generic.ienumerable{bosss.foundation.xdg.speciesid},system.int32,system.int32)).


## Method: BoSSS.Foundation.XDG.XDGSpaceMetrics.#ctor(BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.XDG.XQuadFactoryHelperBase,System.Int32,BoSSS.Foundation.XDG.SpeciesId[],System.Int32) <a id="bosss.foundation.xdg.xdgspacemetrics.#ctor(bosss.foundation.xdg.levelsettracker,bosss.foundation.xdg.xquadfactoryhelperbase,system.int32,bosss.foundation.xdg.speciesid[],system.int32)"></a>
**Summary:** ctor.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.XQuadFactoryHelper <a id="bosss.foundation.xdg.xdgspacemetrics.xquadfactoryhelper"></a>
**Summary:** Provides access to quadrature factories; however, most of the time the user wants to use schemes, [BoSSS.Foundation.XDG.XDGSpaceMetrics.XQuadSchemeHelper](#bosss.foundation.xdg.xdgspacemetrics.xquadschemehelper).


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.XQuadSchemeHelper <a id="bosss.foundation.xdg.xdgspacemetrics.xquadschemehelper"></a>
**Summary:** Provides access to quadrature schemes on cut-cell domains.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.MassMatrixFactory <a id="bosss.foundation.xdg.xdgspacemetrics.massmatrixfactory"></a>
**Summary:** Ye olde provider of the best mass matrices in town.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.Tracker <a id="bosss.foundation.xdg.xdgspacemetrics.tracker"></a>
**Summary:** The owner object.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.GridDat <a id="bosss.foundation.xdg.xdgspacemetrics.griddat"></a>
**Summary:** Underlying background mesh of the XDG space.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.LevelSetRegions <a id="bosss.foundation.xdg.xdgspacemetrics.levelsetregions"></a>
**Summary:** Constant during object lifetime.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.LevelSetData <a id="bosss.foundation.xdg.xdgspacemetrics.levelsetdata"></a>
**Summary:** Data, e.g. level set gradients, 
constant during object lifetime. 
- index: level set index


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.NoOfLevelSets <a id="bosss.foundation.xdg.xdgspacemetrics.nooflevelsets"></a>
**Summary:** The number of level-sets used.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.CutCellQuadOrder <a id="bosss.foundation.xdg.xdgspacemetrics.cutcellquadorder"></a>
**Summary:** The quadrature order used for cut cells volumes.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.CutCellQuadratureType <a id="bosss.foundation.xdg.xdgspacemetrics.cutcellquadraturetype"></a>
**Summary:** The type of quadrature which is be used for computing.


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.SpeciesList <a id="bosss.foundation.xdg.xdgspacemetrics.specieslist"></a>
**Summary:** All species for which metrics are available, a subset of [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesIdS](#bosss.foundation.xdg.levelsettracker.speciesids).


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.TotalSpeciesList <a id="bosss.foundation.xdg.xdgspacemetrics.totalspecieslist"></a>
**Summary:** All species [BoSSS.Foundation.XDG.LevelSetTracker.SpeciesIdS](#bosss.foundation.xdg.levelsettracker.speciesids).


### Property: BoSSS.Foundation.XDG.XDGSpaceMetrics.CutCellMetrics <a id="bosss.foundation.xdg.xdgspacemetrics.cutcellmetrics"></a>
**Summary:** Cell measures and metrics for cut cells


## Method: BoSSS.Foundation.XDG.XDGSpaceMetrics.WriteAllQuadratureRulesToVtp <a id="bosss.foundation.xdg.xdgspacemetrics.writeallquadraturerulestovtp"></a>
**Summary:** Write all the quadrature rules (edge, volume and surface) as nodes + weights into vtp files

## Class: BoSSS.Foundation.XDG.XDGUtils <a id="bosss.foundation.xdg.xdgutils"></a>


## Method: BoSSS.Foundation.XDG.XDGUtils.GetIntegralOverZeroLevelSet(BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.ScalarFunctionEx,System.Int32,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xdgutils.getintegraloverzerolevelset(bosss.foundation.xdg.levelsettracker,bosss.foundation.scalarfunctionex,system.int32,bosss.foundation.xdg.speciesid)"></a>
**Summary:** Computes the Integral of a given function over the zero iso-contour of the Level-Set
**Parameter:** `LsTrk` - Level-Set tracker
**Parameter:** `func` - function which is integrated
**Parameter:** `HMForder` - 
**Parameter:** `spc` - species, over whose surface is integrated
**Returns:**
Integral of 'func' over all MPI processors

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2 <a id="bosss.foundation.xdg.xdifferentialoperatormk2"></a>

**Summary:** An operator which is specialized in XDG Fields, i.e.
it can have components which couple the phases.
Mk2: enables the definition of different equation components for each phase

An operator which is specialized in XDG Fields, i.e.
it can have components which couple the phases.
Mk2: enables the definition of different equation components for each phase


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.IsLinear <a id="bosss.foundation.xdg.xdifferentialoperatormk2.islinear"></a>
**Summary:** true, if the PDE defined by operator can entirely be solved by a linear solver,
i.e. the Jacobian matrix, resp. the operator matrix does **not** depend on the linearization point.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.FluxesAreNOTMultithreadSafe <a id="bosss.foundation.xdg.xdifferentialoperatormk2.fluxesarenotmultithreadsafe"></a>
**Summary:** Set to true, if **all** fluxes must be synchronized in multi-threaded execution.
**This will come at a performance degeneration.**
This is some lazy option: the default value is false,
i.e., fluxes are not synchronized.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.VectorFieldIndices <a id="bosss.foundation.xdg.xdifferentialoperatormk2.vectorfieldindices"></a>
**Summary:** [BoSSS.Foundation.IDifferentialOperator.VectorFieldIndices](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.vectorfieldindices)
**Remark:**
Note: two ore more domain variable names of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.DomainVar](#bosss.foundation.xdg.xdifferentialoperatormk2.domainvar) are considered to be part of a vector field, 
if these names have the same length but differ by **exactly one character**.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SolverSafeguard <a id="bosss.foundation.xdg.xdifferentialoperatormk2.solversafeguard"></a>
**Summary:** [BoSSS.Foundation.IDifferentialOperator.SolverSafeguard](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.solversafeguard)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.LinearizationHint <a id="bosss.foundation.xdg.xdifferentialoperatormk2.linearizationhint"></a>
**Summary:** A hint for implicit/nonlinear solvers, which linearization of the operator should be used


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Species <a id="bosss.foundation.xdg.xdifferentialoperatormk2.species"></a>
**Summary:** active species in this operator; all species that will try to find solutions for.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GhostEdgesOperator <a id="bosss.foundation.xdg.xdifferentialoperatormk2.ghostedgesoperator"></a>
**Summary:** Operator working on ghost edges, see e.g.
@article{burman_ghost_2010,                                                             
title = {Ghost penalty},                                                        
volume = {348},                                                                 
issn = {1631073X},                                                              
url = {http://linkinghub.elsevier.com/retrieve/pii/S1631073X10002827},          
doi = {10.1016/j.crma.2010.10.006},                                             
language = {en},                                                                
number = {21-22},                                                               
urldate = {2015-09-11},                                                         
journal = {Comptes Rendus Mathematique},                                        
author = {Burman, Erik},                                                        
month = nov,                                                                    
year = {2010},                                                                  
pages = {1217--1220}
}


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SurfaceElementOperator_Ls0 <a id="bosss.foundation.xdg.xdifferentialoperatormk2.surfaceelementoperator_ls0"></a>
**Summary:** Non-coupling surface terms; originally intended to implement the flux-form of the surface tension.
**Note: This only considers the 0-th level-set.**


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.ContactLineOperator_Ls0 <a id="bosss.foundation.xdg.xdifferentialoperatormk2.contactlineoperator_ls0"></a>
**Summary:** Non-coupling contact-line terms.
**Note: This only considers the 0-th level-set.**

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QrSchemPair <a id="bosss.foundation.xdg.xdifferentialoperatormk2.qrschempair"></a>

**Summary:** edge and cell scheme for a certain species


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QrSchemPair.EdgeScheme <a id="bosss.foundation.xdg.xdifferentialoperatormk2.qrschempair.edgescheme"></a>
**Summary:** if null, a default scheme is chosen for the integration


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QrSchemPair.CellScheme <a id="bosss.foundation.xdg.xdifferentialoperatormk2.qrschempair.cellscheme"></a>
**Summary:** if null, a default scheme is chosen for the integration


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetMatrixBuilder(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getmatrixbuilder(bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** create a matrix from this operator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetMatrixBuilder(BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getmatrixbuilder(bosss.foundation.xdg.levelsettracker,bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping,system.int32)"></a>
**Summary:** create a matrix from this operator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetEvaluatorEx(System.Collections.Generic.IList{BoSSS.Foundation.DGField},System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getevaluatorex(system.collections.generic.ilist{bosss.foundation.dgfield},system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** explicit evaluation of the operator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetEvaluatorEx(BoSSS.Foundation.XDG.LevelSetTracker,System.Collections.Generic.IList{BoSSS.Foundation.DGField},System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getevaluatorex(bosss.foundation.xdg.levelsettracker,system.collections.generic.ilist{bosss.foundation.dgfield},system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping,system.int32)"></a>
**Summary:** explicit evaluation of the operator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetFDJacobianBuilder(System.Collections.Generic.IList{BoSSS.Foundation.DGField},System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getfdjacobianbuilder(system.collections.generic.ilist{bosss.foundation.dgfield},system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** Computes the Jacobian matrix of the operator by finite differences.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetFDJacobianBuilder(BoSSS.Foundation.XDG.LevelSetTracker,System.Collections.Generic.IList{BoSSS.Foundation.DGField},System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getfdjacobianbuilder(bosss.foundation.xdg.levelsettracker,system.collections.generic.ilist{bosss.foundation.dgfield},system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping,system.int32)"></a>
**Summary:** Computes the Jacobian matrix of the operator by finite differences.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.CloneAs <a id="bosss.foundation.xdg.xdifferentialoperatormk2.cloneas"></a>
**Summary:** Clone Method
**Returns:**


## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1 <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1"></a>

**Summary:** This class acts as a frame for some other vector, and presents only those entries which are associated with a given species.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.#ctor(BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions,BoSSS.Foundation.XDG.SpeciesId,`0,BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.FrameBase_TraceDGhandling) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.#ctor(bosss.foundation.xdg.levelsettracker.levelsetregions,bosss.foundation.xdg.speciesid,`0,bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.framebase_tracedghandling)"></a>
**Summary:** ctor.
**Parameter:** `lsTrk_Regions` - see [BoSSS.Foundation.XDG.LevelSetTracker.Regions](#bosss.foundation.xdg.levelsettracker.regions)
**Parameter:** `spcId` - species which should be framed
**Parameter:** `Full` - the vector that should be framed
**Parameter:** `FullMap` - 
**Parameter:** `traceDGhandling` - 


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.#ctor(`0,BoSSS.Foundation.XDG.FrameBase) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.#ctor(`0,bosss.foundation.xdg.framebase)"></a>
**Summary:** ctor.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.Mapping <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.mapping"></a>
**Summary:** Mapping for the framed vector.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.IndexOf(System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.indexof(system.double)"></a>
**Summary:** not supported.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.Insert(System.Int32,System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.insert(system.int32,system.double)"></a>
**Summary:** not supported.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.RemoveAt(System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.removeat(system.int32)"></a>
**Summary:** not supported.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.Item(System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.item(system.int32)"></a>
**Summary:** set/get one element


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.Add(System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.add(system.double)"></a>
**Summary:** not supported


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.Clear <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.clear"></a>
**Summary:** Sets all entries to 0.0.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.Contains(System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.contains(system.double)"></a>
**Summary:** not supported.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.CopyTo(System.Double[],System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.copyto(system.double[],system.int32)"></a>
**Summary:** copy to array.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.Count <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.count"></a>
**Summary:** number of elements


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.IsReadOnly <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.isreadonly"></a>
**Summary:** depends on framed object


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.Remove(System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.remove(system.double)"></a>
**Summary:** not supported.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.GetEnumerator <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.getenumerator"></a>
**Summary:** %


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameVector`1.System#Collections#IEnumerable#GetEnumerator <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframevector`1.system#collections#ienumerable#getenumerator"></a>
**Summary:** %

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1 <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1"></a>

**Summary:** This class acts as a frame for some other matrix, and presents only those entries which are associated with a given species.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.Clone <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.clone"></a>
**Summary:** Pseudo-implementation.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.Clear <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.clear"></a>
**Summary:** Not Implemented.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.#ctor(`0,BoSSS.Foundation.XDG.LevelSetTracker.LevelSetRegions,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.UnsetteledCoordinateMapping,BoSSS.Foundation.XDG.FrameBase_TraceDGhandling) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.#ctor(`0,bosss.foundation.xdg.levelsettracker.levelsetregions,bosss.foundation.xdg.speciesid,bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.unsetteledcoordinatemapping,bosss.foundation.xdg.framebase_tracedghandling)"></a>
**Summary:** ctor.
**Parameter:** `full` - the full operator matrix, from which the species 'spcId' should e framed (extracted)
**Parameter:** `lsTrk_regions` - see [BoSSS.Foundation.XDG.LevelSetTracker.Regions](#bosss.foundation.xdg.levelsettracker.regions)
**Parameter:** `spcId` - the species of interest
**Parameter:** `fullMapRow` - row mapping for the operator matrix 'full'
**Parameter:** `fullMapCol` - column mapping for the operator matrix 'full'
**Parameter:** `traceDGhandling` - 


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.#ctor(`0,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.#ctor(`0,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase)"></a>
**Summary:** ctor.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.RowMapping <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.rowmapping"></a>
**Summary:** row mapping for the framed matrix


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.MPI_Comm <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.mpi_comm"></a>
**Summary:** mpi comm


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.ColMapping <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.colmapping"></a>
**Summary:** column mapping for the framed matrix


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.GetValues(System.Int64,System.Int64[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.getvalues(system.int64,system.int64[])"></a>
**Summary:** get a whole bunch of elements at once


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.SetValues(System.Int64,System.Int64[],System.Double[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.setvalues(system.int64,system.int64[],system.double[])"></a>
**Summary:** set a whole bunch of elements at once


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.Item(System.Int64,System.Int64) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.item(system.int64,system.int64)"></a>
**Summary:** set/get a specific entry


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.AccBlock(System.Int64,System.Int64,System.Double,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.accblock(system.int64,system.int64,system.double,ilpsp.multidimensionalarray)"></a>
**Summary:** Accumulates 'Block'*'alpha' to this matrix,
at the row/column offset 'i0' resp. 'j0'.
**Parameter:** `i0` - Row offset.
**Parameter:** `j0` - Column offset.
**Parameter:** `alpha` - Scaling factor for the accumulation operation.
**Parameter:** `Block` - Block to accumulate.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.AccBlock(System.Int64,System.Int64,System.Double,ilPSP.MultidimensionalArray,System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.accblock(system.int64,system.int64,system.double,ilpsp.multidimensionalarray,system.double)"></a>
**Summary:** Accumulates a block of entries to this matrix.
**Parameter:** `i0` - Row index offset.
**Parameter:** `j0` - Column index offset.
**Parameter:** `alpha` - Scaling factor for the accumulation.
**Parameter:** `Block` - Block to add.
**Parameter:** `beta` - pre-scaling


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.ReadBlock(System.Int64,System.Int64,ilPSP.MultidimensionalArray) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.readblock(system.int64,system.int64,ilpsp.multidimensionalarray)"></a>
**Summary:** Extracts a block of entries from this matrix and stores it in 'Block'
**Parameter:** `i0` - Row index offset.
**Parameter:** `j0` - Column index offset.
**Parameter:** `Block` - 


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.OccupationMutable <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.occupationmutable"></a>
**Summary:** depends on the framed matrix


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.GetDiagonalElement(System.Int64) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.getdiagonalelement(system.int64)"></a>
**Summary:** read the value of the diagonal element.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.SetDiagonalElement(System.Int64,System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.setdiagonalelement(system.int64,system.double)"></a>
**Summary:** setting of diagonal element.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.RowPartitioning <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.rowpartitioning"></a>
**Summary:** partitioning of rows over all MPI processes


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.ColPartition <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.colpartition"></a>
**Summary:** partitioning of columns over all MPI processes


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.NoOfRows <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.noofrows"></a>
**Summary:** total number of rows over all MPI processes


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.NoOfCols <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.noofcols"></a>
**Summary:** total number of rows over all MPI processes


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SpeciesFrameMatrix`1.SpMV``2(System.Double,``0,System.Double,``1) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.speciesframematrix`1.spmv``2(system.double,``0,system.double,``1)"></a>
**Summary:** not supported


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.#ctor(System.Int32,System.Int32,System.Int32,System.Func{System.Int32[],System.Int32[],System.Int32[],System.Int32},System.Collections.Generic.IEnumerable{System.String},System.String[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.#ctor(system.int32,system.int32,system.int32,system.func{system.int32[],system.int32[],system.int32[],system.int32},system.collections.generic.ienumerable{system.string},system.string[])"></a>
**Summary:** ctor, see [BoSSS.Foundation.DifferentialOperator.#ctor(System.Int32,System.Int32,System.Int32,System.Func{System.Int32[],System.Int32[],System.Int32[],System.Int32},System.String[])](BoSSS.Foundation.md#bosss.foundation.differentialoperator.#ctor(system.int32,system.int32,system.int32,system.func{system.int32[],system.int32[],system.int32[],system.int32},system.string[]))


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.#ctor(System.Int32,System.Int32,System.Func{System.Int32[],System.Int32[],System.Int32[],System.Int32},System.Collections.Generic.IEnumerable{System.String},System.String[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.#ctor(system.int32,system.int32,system.func{system.int32[],system.int32[],system.int32[],system.int32},system.collections.generic.ienumerable{system.string},system.string[])"></a>
**Summary:** ctor, see [BoSSS.Foundation.DifferentialOperator.#ctor(System.Int32,System.Int32,System.Func{System.Int32[],System.Int32[],System.Int32[],System.Int32},System.String[])](BoSSS.Foundation.md#bosss.foundation.differentialoperator.#ctor(system.int32,system.int32,system.func{system.int32[],system.int32[],system.int32[],system.int32},system.string[]))


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.#ctor(System.Collections.Generic.IList{System.String},System.Collections.Generic.IList{System.String},System.Func{System.Int32[],System.Int32[],System.Int32[],System.Int32},System.Collections.Generic.IEnumerable{System.String}) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.#ctor(system.collections.generic.ilist{system.string},system.collections.generic.ilist{system.string},system.func{system.int32[],system.int32[],system.int32[],system.int32},system.collections.generic.ienumerable{system.string})"></a>
**Summary:** ctor


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.#ctor(System.Double,System.String[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.#ctor(system.double,system.string[])"></a>
**Summary:** Almost empty constructor; Variable, Parameter, and Codomain/Equation names are specified by the 
order in which equation components are added.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.#ctor(System.Collections.Generic.IList{System.String},System.Collections.Generic.IList{System.String},System.Collections.Generic.IList{System.String},System.Func{System.Int32[],System.Int32[],System.Int32[],System.Int32},System.Collections.Generic.IEnumerable{System.String}) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.#ctor(system.collections.generic.ilist{system.string},system.collections.generic.ilist{system.string},system.collections.generic.ilist{system.string},system.func{system.int32[],system.int32[],system.int32[],system.int32},system.collections.generic.ienumerable{system.string})"></a>
**Summary:** ctor


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.EquationComponents <a id="bosss.foundation.xdg.xdifferentialoperatormk2.equationcomponents"></a>
**Summary:** for each variable in [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.CodomainVar](#bosss.foundation.xdg.xdifferentialoperatormk2.codomainvar), a
collection of equation components that define the operator.

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2._XEquationComponents <a id="bosss.foundation.xdg.xdifferentialoperatormk2._xequationcomponents"></a>

**Summary:** implementation of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.EquationComponents](#bosss.foundation.xdg.xdifferentialoperatormk2.equationcomponents);


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2._XEquationComponents.Item(System.String) <a id="bosss.foundation.xdg.xdifferentialoperatormk2._xequationcomponents.item(system.string)"></a>
**Summary:** Returns the collection of equation components for one variable in the codomain;
If the 'EqnName' is not known, and the operator is not committed yet ([BoSSS.Foundation.DifferentialOperator.Commit(System.Boolean)](BoSSS.Foundation.md#bosss.foundation.differentialoperator.commit(system.boolean))) a new 
equation/codomain name is appended.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2._XEquationComponents.GetEnumerator <a id="bosss.foundation.xdg.xdifferentialoperatormk2._xequationcomponents.getenumerator"></a>
**Summary:** Gets the enumerator over the equation components of the owner
**Returns:**
An enumerator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2._XEquationComponents.System#Collections#IEnumerable#GetEnumerator <a id="bosss.foundation.xdg.xdifferentialoperatormk2._xequationcomponents.system#collections#ienumerable#getenumerator"></a>
**Summary:** [BoSSS.Foundation.XDG.XDifferentialOperatorMk2._XEquationComponents.GetEnumerator](#bosss.foundation.xdg.xdifferentialoperatormk2._xequationcomponents.getenumerator)
**Returns:**
[BoSSS.Foundation.XDG.XDifferentialOperatorMk2._XEquationComponents.GetEnumerator](#bosss.foundation.xdg.xdifferentialoperatormk2._xequationcomponents.getenumerator)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.AgglomerationThreshold <a id="bosss.foundation.xdg.xdifferentialoperatormk2.agglomerationthreshold"></a>
**Summary:** Cell agglomeration threshold, see [BoSSS.Foundation.XDG.MultiphaseCellAgglomerator](#bosss.foundation.xdg.multiphasecellagglomerator)


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Commit(System.Boolean) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.commit(system.boolean)"></a>
**Summary:** finalizes the assembly of the operator;
Can be called only once in the lifetime of this object.
After calling this method, no adding/removing of equation components is possible.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.ParameterUpdates <a id="bosss.foundation.xdg.xdifferentialoperatormk2.parameterupdates"></a>
**Summary:** [BoSSS.Foundation.IDifferentialOperator.ParameterUpdates](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.parameterupdates)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.ParameterFactories <a id="bosss.foundation.xdg.xdifferentialoperatormk2.parameterfactories"></a>
**Summary:** [BoSSS.Foundation.IDifferentialOperator.ParameterFactories](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.parameterfactories)


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetAllParameterHandlers <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getallparameterhandlers"></a>
**Summary:** Returns all equation components which implement [BoSSS.Foundation.IParameterHandling](BoSSS.Foundation.md#bosss.foundation.iparameterhandling)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.HomotopyUpdate <a id="bosss.foundation.xdg.xdifferentialoperatormk2.homotopyupdate"></a>
**Summary:** [BoSSS.Foundation.IDifferentialOperator.HomotopyUpdate](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.homotopyupdate)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.CurrentHomotopyValue <a id="bosss.foundation.xdg.xdifferentialoperatormk2.currenthomotopyvalue"></a>
**Summary:** Can be used by a (most likely nonlinear) solver to walk along the homotopy path.
Setting (to a different value) fires all [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.HomotopyUpdate](#bosss.foundation.xdg.xdifferentialoperatormk2.homotopyupdate) events


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetJacobiOperator(System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getjacobioperator(system.int32)"></a>
**Summary:** An operator which computes the Jacobian matrix of this operator.
All components in this operator need to implement the [BoSSS.Foundation.ISupportsJacobianComponent](BoSSS.Foundation.md#bosss.foundation.isupportsjacobiancomponent) interface in order to support this operation.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2._GetJacobiOperator(System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2._getjacobioperator(system.int32)"></a>
**Summary:** An operator which computes the Jacobian matrix of this operator.
All components in this operator need to implement the [BoSSS.Foundation.ISupportsJacobianComponent](BoSSS.Foundation.md#bosss.foundation.isupportsjacobiancomponent) interface in order to support this operation.

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.TemporalOperatorContainer <a id="bosss.foundation.xdg.xdifferentialoperatormk2.temporaloperatorcontainer"></a>

**Summary:** Used by [BoSSS.Foundation.XDG.XDifferentialOperatorMk2._GetJacobiOperator(System.Int32)](#bosss.foundation.xdg.xdifferentialoperatormk2._getjacobioperator(system.int32)) to encapsulate the temporal operator
of this operator (because of the ownership, the temporal operator cannot be reused).


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.TemporalOperatorContainer.Commit <a id="bosss.foundation.xdg.xdifferentialoperatormk2.temporaloperatorcontainer.commit"></a>
**Summary:** locks the configuration of the operator


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.EdgeQuadraturSchemeProvider <a id="bosss.foundation.xdg.xdifferentialoperatormk2.edgequadraturschemeprovider"></a>
**Summary:** User-customizable factory, to specify the edge quadrature, see also [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QuadOrderFunction](#bosss.foundation.xdg.xdifferentialoperatormk2.quadorderfunction)
- 1st argument: current level-set tracker
- 2nd argument: species which should be integrated, one of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Species](#bosss.foundation.xdg.xdifferentialoperatormk2.species)
- 3rd argument: a default [BoSSS.Foundation.XDG.XQuadSchemeHelper](#bosss.foundation.xdg.xquadschemehelper)
- 4th argument: quadrature order
- 5th argument: level-set resp. tracker history.
- return: quadrature scheme


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.VolumeQuadraturSchemeProvider <a id="bosss.foundation.xdg.xdifferentialoperatormk2.volumequadraturschemeprovider"></a>
**Summary:** User-customizable factory, to specify the cell/volume quadrature, see also [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QuadOrderFunction](#bosss.foundation.xdg.xdifferentialoperatormk2.quadorderfunction)
- 1st argument: current level-set tracker
- 2nd argument: species which should be integrated, one of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Species](#bosss.foundation.xdg.xdifferentialoperatormk2.species)
- 3rd argument: a default [BoSSS.Foundation.XDG.XQuadSchemeHelper](#bosss.foundation.xdg.xquadschemehelper)
- 4th argument: quadrature order
- 5th argument: level-set resp. tracker history.
- return: quadrature scheme


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GhostEdgeQuadraturSchemeProvider <a id="bosss.foundation.xdg.xdifferentialoperatormk2.ghostedgequadraturschemeprovider"></a>
**Summary:** User-customizable factory, to specify the edge quadrature for the ghost-edges operator [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GhostEdgesOperator](#bosss.foundation.xdg.xdifferentialoperatormk2.ghostedgesoperator), see also [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QuadOrderFunction](#bosss.foundation.xdg.xdifferentialoperatormk2.quadorderfunction)
- 1st argument: current level-set tracker
- 2nd argument: species which should be integrated, one of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Species](#bosss.foundation.xdg.xdifferentialoperatormk2.species)
- 3rd argument: a default [BoSSS.Foundation.XDG.XQuadSchemeHelper](#bosss.foundation.xdg.xquadschemehelper)
- 4th argument: quadrature order
- 5th argument: level-set resp. tracker history.
- return: quadrature scheme


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SurfaceElement_EdgeQuadraturSchemeProvider <a id="bosss.foundation.xdg.xdifferentialoperatormk2.surfaceelement_edgequadraturschemeprovider"></a>
**Summary:** User-customizable factory, to specify the edge quadrature for the [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SurfaceElementOperator_Ls0](#bosss.foundation.xdg.xdifferentialoperatormk2.surfaceelementoperator_ls0), see also [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QuadOrderFunction](#bosss.foundation.xdg.xdifferentialoperatormk2.quadorderfunction)
- 1st argument: current level-set tracker
- 2nd argument: species which should be integrated, one of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Species](#bosss.foundation.xdg.xdifferentialoperatormk2.species)
- 3rd argument: a default [BoSSS.Foundation.XDG.XQuadSchemeHelper](#bosss.foundation.xdg.xquadschemehelper)
- 4th argument: quadrature order
- 5th argument: level-set resp. tracker history.
- return: quadrature scheme


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SurfaceElement_VolumeQuadraturSchemeProvider <a id="bosss.foundation.xdg.xdifferentialoperatormk2.surfaceelement_volumequadraturschemeprovider"></a>
**Summary:** User-customizable factory, to specify the cell/volume quadrature, see also [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QuadOrderFunction](#bosss.foundation.xdg.xdifferentialoperatormk2.quadorderfunction)
- 1st argument: current level-set tracker
- 2nd argument: species which should be integrated, one of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Species](#bosss.foundation.xdg.xdifferentialoperatormk2.species)
- 3rd argument: a default [BoSSS.Foundation.XDG.XQuadSchemeHelper](#bosss.foundation.xdg.xquadschemehelper)
- 4th argument: quadrature order
- 5th argument: level-set resp. tracker history.
- return: quadrature scheme


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.ContactLine_VolumeQuadratureSchemeProvider <a id="bosss.foundation.xdg.xdifferentialoperatormk2.contactline_volumequadratureschemeprovider"></a>
**Summary:** User-customizable factory, to specify the cell/volume quadrature, see also [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QuadOrderFunction](#bosss.foundation.xdg.xdifferentialoperatormk2.quadorderfunction)
- 1st argument: current level-set tracker
- 2nd argument: species which should be integrated, one of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Species](#bosss.foundation.xdg.xdifferentialoperatormk2.species)
- 3rd argument: a default [BoSSS.Foundation.XDG.XQuadSchemeHelper](#bosss.foundation.xdg.xquadschemehelper)
- 4th argument: quadrature order
- 5th argument: level-set resp. tracker history.
- return: quadrature scheme


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.m_UserDefinedValues <a id="bosss.foundation.xdg.xdifferentialoperatormk2.m_userdefinedvalues"></a>
**Summary:** internal access for hack in [BoSSS.Foundation.XDG.DependentXTemporalOperator](#bosss.foundation.xdg.dependentxtemporaloperator).


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.UserDefinedValues <a id="bosss.foundation.xdg.xdifferentialoperatormk2.userdefinedvalues"></a>
**Summary:** Modification of [BoSSS.Foundation.CoefficientSet.UserDefinedValues](BoSSS.Foundation.md#bosss.foundation.coefficientset.userdefinedvalues), **but only if** default setting for [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.OperatorCoefficientsProvider](#bosss.foundation.xdg.xdifferentialoperatormk2.operatorcoefficientsprovider) is used
- 1st key: species
- 2nd key: user-defined name 
- value: object to pass to [BoSSS.Foundation.IEquationComponentCoefficient.CoefficientUpdate(BoSSS.Foundation.CoefficientSet,System.Int32[],System.Int32)](BoSSS.Foundation.md#bosss.foundation.iequationcomponentcoefficient.coefficientupdate(bosss.foundation.coefficientset,system.int32[],system.int32))

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.DelOperatorCoefficientsProvider <a id="bosss.foundation.xdg.xdifferentialoperatormk2.deloperatorcoefficientsprovider"></a>

**Summary:** [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.OperatorCoefficientsProvider](#bosss.foundation.xdg.xdifferentialoperatormk2.operatorcoefficientsprovider)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.OperatorCoefficientsProvider <a id="bosss.foundation.xdg.xdifferentialoperatormk2.operatorcoefficientsprovider"></a>
**Summary:** User-customizable factory, to modify single values (e.g. Reynolds numbers)
within the operator components (those implementing [BoSSS.Foundation.IEquationComponentCoefficient](BoSSS.Foundation.md#bosss.foundation.iequationcomponentcoefficient))
Auxiliary data passed to equation components which implement [BoSSS.Foundation.IEquationComponentCoefficient](BoSSS.Foundation.md#bosss.foundation.iequationcomponentcoefficient).


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QuadOrderFunction <a id="bosss.foundation.xdg.xdifferentialoperatormk2.quadorderfunction"></a>
**Summary:** Function Mapping from Domain Variable Degrees, Parameter Degrees and CoDomain Variable Degrees to the Quadrature Order


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.IsValidDomainDegreeCombination(System.Int32[],System.Int32[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.isvaliddomaindegreecombination(system.int32[],system.int32[])"></a>
**Summary:** [BoSSS.Foundation.IDifferentialOperator.IsValidDomainDegreeCombination(System.Int32[],System.Int32[])](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.isvaliddomaindegreecombination(system.int32[],system.int32[]))


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Verify(System.Boolean) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.verify(system.boolean)"></a>
**Summary:** verifies all equation components;
**Remark:**
if a component has an illegal configuration (e.g. it's arguments
([BoSSS.Foundation.IEquationComponent.ArgumentOrdering](BoSSS.Foundation.md#bosss.foundation.iequationcomponent.argumentordering)) are not contained
in the domain variable list ([BoSSS.Foundation.XDG.XDifferentialOperatorMk2.DomainVar](#bosss.foundation.xdg.xdifferentialoperatormk2.domainvar))), an 
exception is thrown, if 'allowVarAddition' is set true, see also [BoSSS.Foundation.IDifferentialOperator.Commit(System.Boolean)](BoSSS.Foundation.md#bosss.foundation.idifferentialoperator.commit(system.boolean))


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GetOrderFromQuadOrderFunction(System.Collections.Generic.IEnumerable{BoSSS.Foundation.Basis},System.Collections.Generic.IEnumerable{BoSSS.Foundation.Basis},System.Collections.Generic.IEnumerable{BoSSS.Foundation.Basis}) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.getorderfromquadorderfunction(system.collections.generic.ienumerable{bosss.foundation.basis},system.collections.generic.ienumerable{bosss.foundation.basis},system.collections.generic.ienumerable{bosss.foundation.basis})"></a>
**Summary:** Evaluation of the [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.QuadOrderFunction](#bosss.foundation.xdg.xdifferentialoperatormk2.quadorderfunction).


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.CollectDependentVariables(System.String) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.collectdependentvariables(system.string)"></a>
**Summary:** for some codomain variable 'CodomVar',
this method collects 
all variables in the domain (see [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.DomainVar](#bosss.foundation.xdg.xdifferentialoperatormk2.domainvar))
on which 'CodomVar' depends on.
**Parameter:** `CodomVar` - 
**Returns:**
a sub-list of [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.DomainVar](#bosss.foundation.xdg.xdifferentialoperatormk2.domainvar);
**Remark:**
This method invokes [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Verify(System.Boolean)](#bosss.foundation.xdg.xdifferentialoperatormk2.verify(system.boolean));
the returned list is in the same order as


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.m_EquationComponents <a id="bosss.foundation.xdg.xdifferentialoperatormk2.m_equationcomponents"></a>
**Summary:** [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.EquationComponents](#bosss.foundation.xdg.xdifferentialoperatormk2.equationcomponents)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.IsCommitted <a id="bosss.foundation.xdg.xdifferentialoperatormk2.iscommitted"></a>
**Summary:** indicates whether the equation-assembly has been finished (by calling [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Commit(System.Boolean)](#bosss.foundation.xdg.xdifferentialoperatormk2.commit(system.boolean)))
or not.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.TotalNoOfComponents <a id="bosss.foundation.xdg.xdifferentialoperatormk2.totalnoofcomponents"></a>
**Summary:** total number of equation components, in all codomain variables


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.DomainVar <a id="bosss.foundation.xdg.xdifferentialoperatormk2.domainvar"></a>
**Summary:** names of (DG-) variables that represent the domain of this  differential operator;
These names/strings should not be confused with field identification strings
([BoSSS.Foundation.DGField.Identification](BoSSS.Foundation.md#bosss.foundation.dgfield.identification)), they have nothing to do with that.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.CodomainVar <a id="bosss.foundation.xdg.xdifferentialoperatormk2.codomainvar"></a>
**Summary:** names of (DG-) variables that represent the Co-Domain of this differential operator
These names/strings should not be confused with field identification strings
([BoSSS.Foundation.DGField.Identification](BoSSS.Foundation.md#bosss.foundation.dgfield.identification)), they have nothing to do with that.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.ParameterVar <a id="bosss.foundation.xdg.xdifferentialoperatormk2.parametervar"></a>
**Summary:** names of (DG-) variables which act as parameters; 
Their role is pretty similar to those of the domain variables, and for nonlinear
fluxes, there is no difference.
However, for linear fluxes, they can be used to provide some 
space-depended properties as DG-fields, e.g. for providing boundary conditions
or if the linear operator is some linearization of some nonlinear operator.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.ContainesComponentType_PerCodomainVar(System.String,System.Type[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.containescomponenttype_percodomainvar(system.string,system.type[])"></a>
**Summary:** Returns true, if at least one of the equation components 
for codomain variable 'CodomVar'
is of some type in 't'.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.ContainesComponentType(System.Type[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.containescomponenttype(system.type[])"></a>
**Summary:** Returns true, if at least one of the equation components 
of this operator
is of some type in 't'.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.TemporalOperator <a id="bosss.foundation.xdg.xdifferentialoperatormk2.temporaloperator"></a>
**Summary:** %


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.FreeMeanValue <a id="bosss.foundation.xdg.xdifferentialoperatormk2.freemeanvalue"></a>
**Summary:** Notifies the solver that the mean value for a specific value is floating.
An example is e.g. the pressure in the incompressible Navier-Stokes equation with all-walls boundary condition.
- key: the name of some domain variable
- value: false, if the mean value of the solution  is defined, true if the mean value  of the solution is floating (i.e. for some solution u, u + constant is also a solution).

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.MyDict <a id="bosss.foundation.xdg.xdifferentialoperatormk2.mydict"></a>

**Summary:** I hate shit like this class - so many dumb lines of code.

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear"></a>

**Summary:** Assembly of matrices for linear (or linearized) XDG operators


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.#ctor(BoSSS.Foundation.XDG.XDifferentialOperatorMk2,BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.#ctor(bosss.foundation.xdg.xdifferentialoperatormk2,bosss.foundation.xdg.levelsettracker,bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping,system.int32)"></a>
**Summary:** ctor


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.ctorSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.ctorspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates a matrix builder


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.ctorGhostSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.ctorghostspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates a matrix builder


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.ctorSurfaceElementSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.ctorsurfaceelementspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates a matrix builder


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.ctorContactLineSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.ctorcontactlinespeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates a matrix builder


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.ctorTraceDGBulkIntegrator(System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.ctortracedgbulkintegrator(system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates a matrix builder


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.ComputeAffine``1(``0) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.computeaffine``1(``0)"></a>
**Summary:** [BoSSS.Foundation.IEvaluatorLinear.ComputeAffine``1(``0)](BoSSS.Foundation.md#bosss.foundation.ievaluatorlinear.computeaffine``1(``0))


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.ComputeMatrix``2(``0,``1,System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.computematrix``2(``0,``1,system.double)"></a>
**Summary:** [BoSSS.Foundation.IEvaluatorLinear.ComputeMatrix``2(``0,``1,System.Double)](BoSSS.Foundation.md#bosss.foundation.ievaluatorlinear.computematrix``2(``0,``1,system.double))


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.GetTrxFields <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.gettrxfields"></a>
**Summary:** fields for MPI exchange


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorLinear.ComputeMatrix_Internal``2(``0,``1,System.Boolean,System.Double) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorlinear.computematrix_internal``2(``0,``1,system.boolean,system.double)"></a>
**Summary:** computation of operator matrix, currently only two species are supported


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.onlyfordebugging_DoSurface <a id="bosss.foundation.xdg.xdifferentialoperatormk2.onlyfordebugging_dosurface"></a>
**Summary:** Only for debugging;  can be used to turn surface integration in spatial operators off.

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorNonlin <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatornonlin"></a>

**Summary:** Explicit evaluation of (nonlinear and linear) XDG operators


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorNonlin.GetTrxFields <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatornonlin.gettrxfields"></a>
**Summary:** Returns domain fields and parameters.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorNonlin.ctorSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatornonlin.ctorspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates an evaluator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorNonlin.ctorGhostSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatornonlin.ctorghostspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates an evaluator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorNonlin.ctorSurfaceElementSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatornonlin.ctorsurfaceelementspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates an evaluator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorNonlin.ctorContactLineSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatornonlin.ctorcontactlinespeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates an evaluator


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorNonlin.ctorTraceDGBulkIntegrator(System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatornonlin.ctortracedgbulkintegrator(system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** creates an evaluator

## Class: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase"></a>


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.m_Owner <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.m_owner"></a>
**Summary:** equal to [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.Owner](#bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.owner)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.Owner <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.owner"></a>
**Summary:** the operator used to construct this object


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.CellLengthScales <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.celllengthscales"></a>
**Summary:** Dirty hack to provide length scales for the operator evaluation/matrix assembly, [BoSSS.Foundation.CoefficientSet.CellLengthScales](BoSSS.Foundation.md#bosss.foundation.coefficientset.celllengthscales)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.EdgeLengthScales <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.edgelengthscales"></a>
**Summary:** Dirty hack to provide length scales for the operator evaluation/matrix assembly, [BoSSS.Foundation.CoefficientSet.EdgeLengthScales](BoSSS.Foundation.md#bosss.foundation.coefficientset.edgelengthscales)


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.onlyfordebugging_RuleDiagnosis <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.onlyfordebugging_rulediagnosis"></a>
**Summary:** Write quadrature rules to text file, for debugging


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.#ctor(BoSSS.Foundation.XDG.XDifferentialOperatorMk2,BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IList{BoSSS.Foundation.DGField},System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping,System.Int32) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.#ctor(bosss.foundation.xdg.xdifferentialoperatormk2,bosss.foundation.xdg.levelsettracker,bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.ilist{bosss.foundation.dgfield},system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping,system.int32)"></a>
**Summary:** ctor


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.UsedQuadOrder <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.usedquadorder"></a>


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.TrackerHistoryIndex <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.trackerhistoryindex"></a>
**Summary:** Index into [BoSSS.Foundation.XDG.LevelSetTracker.RegionsHistory](#bosss.foundation.xdg.levelsettracker.regionshistory) and similar stacks.


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ctorSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.ctorspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** create integrator for bulk phase


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ctorTraceDGBulkIntegrator(System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.ctortracedgbulkintegrator(system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** create integrator for bulk components (stabilization components) for Trace DG


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ctorGhostSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.ctorghostspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** Create integrator for [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.GhostEdgesOperator](#bosss.foundation.xdg.xdifferentialoperatormk2.ghostedgesoperator)


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ctorSurfaceElementSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.ctorsurfaceelementspeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** Create integrator for [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.SurfaceElementOperator_Ls0](#bosss.foundation.xdg.xdifferentialoperatormk2.surfaceelementoperator_ls0)


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ctorContactLineSpeciesIntegrator(BoSSS.Foundation.XDG.SpeciesId,System.Int32,BoSSS.Foundation.Quadrature.CellQuadratureScheme,BoSSS.Foundation.Quadrature.EdgeQuadratureScheme,BoSSS.Foundation.XDG.FrameBase,BoSSS.Foundation.XDG.FrameBase,System.Boolean[],BoSSS.Foundation.DGField[],BoSSS.Foundation.DGField[]) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.ctorcontactlinespeciesintegrator(bosss.foundation.xdg.speciesid,system.int32,bosss.foundation.quadrature.cellquadraturescheme,bosss.foundation.quadrature.edgequadraturescheme,bosss.foundation.xdg.framebase,bosss.foundation.xdg.framebase,system.boolean[],bosss.foundation.dgfield[],bosss.foundation.dgfield[])"></a>
**Summary:** Create Integrator for [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.ContactLineOperator_Ls0](#bosss.foundation.xdg.xdifferentialoperatormk2.contactlineoperator_ls0)


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ctorLevSetFormIntegrator(System.Int32,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.Quadrature.ICompositeQuadRule{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.ctorlevsetformintegrator(system.int32,bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid,bosss.foundation.quadrature.icompositequadrule{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Create integrator for [BoSSS.Foundation.XDG.ILevelSetForm](#bosss.foundation.xdg.ilevelsetform) components


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ReqSpecies <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.reqspecies"></a>
**Summary:** all species to integrate, defined through [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.Species](#bosss.foundation.xdg.xdifferentialoperatormk2.species)


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.m_lsTrk <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.m_lstrk"></a>
**Summary:** %


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.m_Xowner <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.m_xowner"></a>
**Summary:** the spatial operator


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.SpeciesParams <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.speciesparams"></a>
**Summary:** Parameter fields for each species, for [BoSSS.Foundation.XDG.XDGField](#bosss.foundation.xdg.xdgfield)s the species shadow, see [BoSSS.Foundation.XDG.XDGField.GetSpeciesShadowField(BoSSS.Foundation.XDG.SpeciesId)](#bosss.foundation.xdg.xdgfield.getspeciesshadowfield(bosss.foundation.xdg.speciesid))


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.SpeciesCodomFrame_WithoutTraceDg <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.speciescodomframe_withouttracedg"></a>
**Summary:** for each species, the frame of the co-domain, no TraceDG


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.SpeciesDomainFrame_WithoutTraceDg <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.speciesdomainframe_withouttracedg"></a>
**Summary:** for each species, the frame of the domain, no TraceDG


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.SpeciesCodomFrame_WithTraceDg <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.speciescodomframe_withtracedg"></a>
**Summary:** for each species, the frame of the co-domain, TraceDG included


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.SpeciesDomainFrame_WithTraceDg <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.speciesdomainframe_withtracedg"></a>
**Summary:** for each species, the frame of the domain, TraceDG included


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.TraceDgCodomFrame <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.tracedgcodomframe"></a>
**Summary:** If TraceDG is used, the frame of the co-domain, without any DG or XDG components


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.TraceDgDomainFrame <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.tracedgdomainframe"></a>
**Summary:** If TraceDG is used,  the frame of the domain, without any DG or XDG components


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.CouplingRules <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.couplingrules"></a>
**Summary:** quadrature rules for each level set/species pair;
- 1st item: level-set index
- 2nd item: negative species/species A
- 3rd item positive species/species B
- 4th item respective quadrature rule


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.GetCoefficients(BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.CoefficientSet@,BoSSS.Foundation.CoefficientSet@) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.getcoefficients(bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid,bosss.foundation.coefficientset@,bosss.foundation.coefficientset@)"></a>


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.UpdateLevelSetCoefficients(System.Int32,BoSSS.Foundation.XDG.SpeciesId,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.updatelevelsetcoefficients(system.int32,bosss.foundation.xdg.speciesid,bosss.foundation.xdg.speciesid)"></a>
**Summary:** calls all [BoSSS.Foundation.XDG.ILevelSetEquationComponentCoefficient.CoefficientUpdate(BoSSS.Foundation.CoefficientSet,BoSSS.Foundation.CoefficientSet,System.Int32[],System.Int32)](#bosss.foundation.xdg.ilevelsetequationcomponentcoefficient.coefficientupdate(bosss.foundation.coefficientset,bosss.foundation.coefficientset,system.int32[],system.int32)) methods


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.NotifySpecies(BoSSS.Foundation.DifferentialOperator,BoSSS.Foundation.XDG.LevelSetTracker,BoSSS.Foundation.XDG.SpeciesId) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.notifyspecies(bosss.foundation.differentialoperator,bosss.foundation.xdg.levelsettracker,bosss.foundation.xdg.speciesid)"></a>
**Summary:** calls all [BoSSS.Foundation.XDG.IEquationComponentSpeciesNotification.SetParameter(System.String)](#bosss.foundation.xdg.iequationcomponentspeciesnotification.setparameter(system.string)) methods


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.m_SubGrid_InCells <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.m_subgrid_incells"></a>


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.SubGridBoundaryTreatment <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.subgridboundarytreatment"></a>
**Summary:** State set by [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ActivateSubgridBoundary(BoSSS.Foundation.Grid.CellMask,BoSSS.Foundation.SubGridBoundaryModes)](#bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.activatesubgridboundary(bosss.foundation.grid.cellmask,bosss.foundation.subgridboundarymodes))


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.ActivateSubgridBoundary(BoSSS.Foundation.Grid.CellMask,BoSSS.Foundation.SubGridBoundaryModes) <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.activatesubgridboundary(bosss.foundation.grid.cellmask,bosss.foundation.subgridboundarymodes)"></a>
**Summary:** Restricts the evaluation of the operator to a specific cell mask.
**Parameter:** `Mask` - cell mask where the operator should be evaluated
**Parameter:** `subGridBoundaryTreatment` - defines what is to be done at edges where one neighboring cell is part of the cell mask 'Mask', 
but the other neighboring cell is *not* part of the cell mask 'Mask'.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.CodomainMapping <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.codomainmapping"></a>
**Summary:** coordinate mapping for the codomain variables;


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.m_Parameters <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.m_parameters"></a>
**Summary:** [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.Parameters](#bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.parameters)


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.Parameters <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.parameters"></a>
**Summary:** parameter mapping


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.DomainMapping <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.domainmapping"></a>
**Summary:** coordinate mapping for the domain variables;


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.GridData <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.griddata"></a>
**Summary:** Grid, on which this evaluator operates on.


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.time <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.time"></a>
**Summary:** Time passed e.g. to [BoSSS.Foundation.CommonParams.time](BoSSS.Foundation.md#bosss.foundation.commonparams.time), [BoSSS.Foundation.CommonParamsBnd.time](BoSSS.Foundation.md#bosss.foundation.commonparamsbnd.time) and [BoSSS.Foundation.CommonParamsVol.time](BoSSS.Foundation.md#bosss.foundation.commonparamsvol.time).


## Method: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.GetTrxFields <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.gettrxfields"></a>
**Summary:** Should return all DG fields which should be exchanged, see [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.m_TRX](#bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.m_trx).


### Property: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.MPITtransceive <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.mpittransceive"></a>
**Summary:** Turn MPI sending/receiving of parameters and domain fields on/off.


### Field: BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.m_TRX <a id="bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.m_trx"></a>
**Summary:** Transceiver for the fields within [BoSSS.Foundation.XDG.XDifferentialOperatorMk2.XEvaluatorBase.DomainMapping](#bosss.foundation.xdg.xdifferentialoperatormk2.xevaluatorbase.domainmapping)

## Class: BoSSS.Foundation.XDG.CutCellQuadratureMethod <a id="bosss.foundation.xdg.cutcellquadraturemethod"></a>

**Summary:** Different variants of the moment-fitting procedure for the creation
of the surface and volume quadrature rules.


### Field: BoSSS.Foundation.XDG.CutCellQuadratureMethod.Classic <a id="bosss.foundation.xdg.cutcellquadraturemethod.classic"></a>
**Summary:** The original hierarchical moment fitting method published in 2013 which uses a two-step 
procedure: The surface rules are created first and then used to
create the volume rules


### Field: BoSSS.Foundation.XDG.CutCellQuadratureMethod.OneStepGauss <a id="bosss.foundation.xdg.cutcellquadraturemethod.onestepgauss"></a>
**Summary:** One-step variant proposed by Florian (see XNSE paper, submitted
2015). Surface and volume rules are created using a single
moment-fitting by additionally enforcing Gauss' theorem on the
discrete level.


### Field: BoSSS.Foundation.XDG.CutCellQuadratureMethod.OneStepGaussAndStokes <a id="bosss.foundation.xdg.cutcellquadraturemethod.onestepgaussandstokes"></a>
**Summary:** Same as [BoSSS.Foundation.XDG.CutCellQuadratureMethod.OneStepGauss](#bosss.foundation.xdg.cutcellquadraturemethod.onestepgauss), but additionally enforces
Stokes' theorem on a discrete level.


### Field: BoSSS.Foundation.XDG.CutCellQuadratureMethod.TwoStepStokesAndGauss <a id="bosss.foundation.xdg.cutcellquadraturemethod.twostepstokesandgauss"></a>
**Summary:** Two step-procedure: using Stokes theorem to create surface rules, 
and the Gauss theorem to create Volume rules.


### Field: BoSSS.Foundation.XDG.CutCellQuadratureMethod.ExactCircle <a id="bosss.foundation.xdg.cutcellquadraturemethod.exactcircle"></a>
**Summary:** Only for debugging purpose, see [BoSSS.Foundation.XDG.Quadrature.HMF.ExactCircleLevelSetIntegration](#bosss.foundation.xdg.quadrature.hmf.exactcirclelevelsetintegration), [BoSSS.Foundation.XDG.Quadrature.HMF.ExactCircleLevelSetIntegration.RADIUS](#bosss.foundation.xdg.quadrature.hmf.exactcirclelevelsetintegration.radius)


### Field: BoSSS.Foundation.XDG.CutCellQuadratureMethod.Saye <a id="bosss.foundation.xdg.cutcellquadraturemethod.saye"></a>
**Summary:** Gaussian quadrature rules for [BoSSS.Foundation.Grid.RefElements.Square](BoSSS.Foundation.md#bosss.foundation.grid.refelements.square) and [BoSSS.Foundation.Grid.RefElements.Cube](BoSSS.Foundation.md#bosss.foundation.grid.refelements.cube) elements,
obtained throug recursive subdivision, as described in 
(Saye 2015)
**Remark:**
High-Order Quadrature Methods for Implicitly Defined Surfaces and Volumes in Hyperrectangles,
R. Saye, SIAM Journal on Scientific Computing, 2015


### Field: BoSSS.Foundation.XDG.CutCellQuadratureMethod.Algoim <a id="bosss.foundation.xdg.cutcellquadraturemethod.algoim"></a>
**Summary:** Gaussian quadrature rules for [BoSSS.Foundation.Grid.RefElements.Square](BoSSS.Foundation.md#bosss.foundation.grid.refelements.square) and [BoSSS.Foundation.Grid.RefElements.Cube](BoSSS.Foundation.md#bosss.foundation.grid.refelements.cube) elements,
obtained through recursive subdivision, as described in 
(Saye 2022)

## Class: BoSSS.Foundation.XDG.XQuadFactoryHelperBase <a id="bosss.foundation.xdg.xquadfactoryhelperbase"></a>


### Property: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.CutCellQuadratureType <a id="bosss.foundation.xdg.xquadfactoryhelperbase.cutcellquadraturetype"></a>
**Summary:** Used type of the HMF.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetSurfaceFactory(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getsurfacefactory(system.int32,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Generates a quadrature rule factory for integrating over the zero-level-set surface.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetSurfaceFactory(System.Int32,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getsurfacefactory(system.int32,system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates a quadrature rule factory for integrating over a surface.
The surface is defined by two conditions: levelset0 = 0 and on side jmp1 of levelset1
[BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetSurfaceFactory(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement)](#bosss.foundation.xdg.xquadfactoryhelperbase.getsurfacefactory(system.int32,bosss.foundation.grid.refelements.refelement))
**Parameter:** `levSetIndex0` - Index of the primary level set defining the surface quadrature rule.
**Parameter:** `levSetIndex1` - Index of the auxiliary level set for species differentiation.
**Parameter:** `jmp1` - Specifies the side of 'levSetIndex1' that defines the phase of interest.
**Parameter:** `KrefVol` - The reference element used for the quadrature rule.
**Parameter:** `backupFactory` - Factory for generating fallback quadrature rules.
**Returns:**



## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetEdgeRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getedgerulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Generates a quadrature rule factory for the cut edge integrals.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetEdgeRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getedgerulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates an edge quadrature rule factory for edges cut by two level sets. [BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetEdgeRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement)](#bosss.foundation.xdg.xquadfactoryhelperbase.getedgerulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement))


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetVolRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getvolrulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Generates a quadrature rule factory for the cut volume integrals.


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetVolRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getvolrulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates a volume quadrature rule factory for cells cut by two level sets. [BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetVolRuleFactory(System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement)](#bosss.foundation.xdg.xquadfactoryhelperbase.getvolrulefactory(system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement))


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetSurfaceElement_BoundaryRuleFactory(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getsurfaceelement_boundaryrulefactory(system.int32,bosss.foundation.grid.refelements.refelement)"></a>
**Summary:** Returns a rule factory for the boundary of surface-elements 
(elements on the zero-level-set surface), i.e. on \f$  K \cap \mathfrak{I}\f$ .
This are point integrals in 2D and line integrals in 3D.
**Returns:**
the returned factory produces [BoSSS.Foundation.Quadrature.QuadRule](BoSSS.Foundation.md#bosss.foundation.quadrature.quadrule)'s on edges


## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetSurfaceElement_BoundaryRuleFactory(System.Int32,System.Int32,BoSSS.Foundation.XDG.Quadrature.HMF.JumpTypes,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getsurfaceelement_boundaryrulefactory(system.int32,system.int32,bosss.foundation.xdg.quadrature.hmf.jumptypes,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates a volume quadrature rule factory for cells cut by two level sets. [BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetSurfaceElement_BoundaryRuleFactory(System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement)](#bosss.foundation.xdg.xquadfactoryhelperbase.getsurfaceelement_boundaryrulefactory(system.int32,bosss.foundation.grid.refelements.refelement))
The surface is defined by two conditions: levelset0 = 0 and on side jmp1 of levelset1
**Parameter:** `levSetIndex0` - 
**Parameter:** `levSetIndex1` - 
**Parameter:** `jmp1` - 
**Parameter:** `KrefVol` - 
**Parameter:** `backupFactory` - 
**Returns:**



## Method: BoSSS.Foundation.XDG.XQuadFactoryHelperBase.GetIntersectionRuleFactory(System.Int32,System.Int32,BoSSS.Foundation.Grid.RefElements.RefElement,BoSSS.Foundation.Quadrature.IQuadRuleFactory{BoSSS.Foundation.Quadrature.QuadRule}) <a id="bosss.foundation.xdg.xquadfactoryhelperbase.getintersectionrulefactory(system.int32,system.int32,bosss.foundation.grid.refelements.refelement,bosss.foundation.quadrature.iquadrulefactory{bosss.foundation.quadrature.quadrule})"></a>
**Summary:** Generates a quadrature rule factory the intersection of levelset0 and levelset1 where levelset0 = levelset1 = 0
This is a point in 2D, a line in 3D.

## Class: BoSSS.Foundation.XDG.ConstantXTemporalOperator <a id="bosss.foundation.xdg.constantxtemporaloperator"></a>

**Summary:** A constant, diagonal operator


## Method: BoSSS.Foundation.XDG.ConstantXTemporalOperator.#ctor(BoSSS.Foundation.XDG.XDifferentialOperatorMk2,System.Double) <a id="bosss.foundation.xdg.constantxtemporaloperator.#ctor(bosss.foundation.xdg.xdifferentialoperatormk2,system.double)"></a>
**Summary:** Ctor, the same factor in the temporal derivative for all
**Parameter:** `__owner` - 
**Parameter:** `diagonalValue` - 


## Method: BoSSS.Foundation.XDG.ConstantXTemporalOperator.#ctor(BoSSS.Foundation.XDG.XDifferentialOperatorMk2,System.ValueTuple{System.String,System.Double[]}[]) <a id="bosss.foundation.xdg.constantxtemporaloperator.#ctor(bosss.foundation.xdg.xdifferentialoperatormk2,system.valuetuple{system.string,system.double[]}[])"></a>
**Summary:** Ctor
**Parameter:** `__owner` - 
**Parameter:** `diagonal` - For each species, the temporal operator/mass matrix diagonal (per variable), 
i.e. if '__owner' has 4 domain and 4 codomain variables,
this must have 4 entries per species too, providing a single factor for the temporal derivative of each equation.


### Property: BoSSS.Foundation.XDG.ConstantXTemporalOperator.DiagonalScale <a id="bosss.foundation.xdg.constantxtemporaloperator.diagonalscale"></a>
**Summary:** For each species, the temporal operator/mass matrix diagonal (per variable), 
i.e. if the spatial operator has 4 domain and 4 codomain variables,
this must have 4 entries per species too, providing a single factor for the temporal derivative of each equation.


## Method: BoSSS.Foundation.XDG.ConstantXTemporalOperator.Commit <a id="bosss.foundation.xdg.constantxtemporaloperator.commit"></a>
**Summary:** locks the configuration of the operator


## Method: BoSSS.Foundation.XDG.ConstantXTemporalOperator.GetMassMatrixBuilder(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.constantxtemporaloperator.getmassmatrixbuilder(bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** Returns an matrix builder which always accumulates the same diagonal matrix.


## Method: BoSSS.Foundation.XDG.ConstantXTemporalOperator.SetTrackerHack(BoSSS.Foundation.XDG.LevelSetTracker) <a id="bosss.foundation.xdg.constantxtemporaloperator.settrackerhack(bosss.foundation.xdg.levelsettracker)"></a>
**Summary:** Dirty hack to support e.g. the IBM solver (state sept2020) which uses only DG 
fields but employs an [BoSSS.Foundation.XDG.XDifferentialOperatorMk2](#bosss.foundation.xdg.xdifferentialoperatormk2);
may be deleted, eventually.

## Class: BoSSS.Foundation.XDG.ConstantXTemporalOperator.InternalBla <a id="bosss.foundation.xdg.constantxtemporaloperator.internalbla"></a>


### Property: BoSSS.Foundation.XDG.ConstantXTemporalOperator.InternalBla.time <a id="bosss.foundation.xdg.constantxtemporaloperator.internalbla.time"></a>
**Summary:** No effect, operator is constant in time


### Property: BoSSS.Foundation.XDG.ConstantXTemporalOperator.InternalBla.MPITtransceive <a id="bosss.foundation.xdg.constantxtemporaloperator.internalbla.mpittransceive"></a>
**Summary:** ignored - no effect


### Property: BoSSS.Foundation.XDG.ConstantXTemporalOperator.InternalBla.Owner <a id="bosss.foundation.xdg.constantxtemporaloperator.internalbla.owner"></a>


## Method: BoSSS.Foundation.XDG.ConstantXTemporalOperator.InternalBla.ComputeAffine``1(``0) <a id="bosss.foundation.xdg.constantxtemporaloperator.internalbla.computeaffine``1(``0)"></a>
**Summary:** No effect;


## Method: BoSSS.Foundation.XDG.ConstantXTemporalOperator.InternalBla.ComputeMatrix``2(``0,``1,System.Double) <a id="bosss.foundation.xdg.constantxtemporaloperator.internalbla.computematrix``2(``0,``1,system.double)"></a>
**Summary:** Computation of mass matrix, makes use of [BoSSS.Foundation.XDG.MassMatrixFactory](#bosss.foundation.xdg.massmatrixfactory)

## Class: BoSSS.Foundation.XDG.DependentXTemporalOperator <a id="bosss.foundation.xdg.dependentxtemporaloperator"></a>

**Summary:** Temporal operator which is fully customizable, i.e. can be configured through [BoSSS.Foundation.XDG.DependentXTemporalOperator.EquationComponents](#bosss.foundation.xdg.dependentxtemporaloperator.equationcomponents)
in analog fashion to the spatial operator.


## Method: BoSSS.Foundation.XDG.DependentXTemporalOperator.#ctor(BoSSS.Foundation.XDG.XDifferentialOperatorMk2) <a id="bosss.foundation.xdg.dependentxtemporaloperator.#ctor(bosss.foundation.xdg.xdifferentialoperatormk2)"></a>
**Summary:** Ctor
**Parameter:** `__owner` - 


### Property: BoSSS.Foundation.XDG.DependentXTemporalOperator.EquationComponents <a id="bosss.foundation.xdg.dependentxtemporaloperator.equationcomponents"></a>
**Summary:** Components of the Mass matrix


## Method: BoSSS.Foundation.XDG.DependentXTemporalOperator.Commit <a id="bosss.foundation.xdg.dependentxtemporaloperator.commit"></a>
**Summary:** locks the configuration of the operator


## Method: BoSSS.Foundation.XDG.DependentXTemporalOperator.GetMassMatrixBuilder(BoSSS.Foundation.UnsetteledCoordinateMapping,System.Collections.Generic.IList{BoSSS.Foundation.DGField},BoSSS.Foundation.UnsetteledCoordinateMapping) <a id="bosss.foundation.xdg.dependentxtemporaloperator.getmassmatrixbuilder(bosss.foundation.unsetteledcoordinatemapping,system.collections.generic.ilist{bosss.foundation.dgfield},bosss.foundation.unsetteledcoordinatemapping)"></a>
**Summary:** as defined by interface



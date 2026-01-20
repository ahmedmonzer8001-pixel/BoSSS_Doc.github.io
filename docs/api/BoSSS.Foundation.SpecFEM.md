---
title: "BoSSSFoundationSpecFEM"
---
# Namespace: BoSSS.Foundation.SpecFEM

## Class: BoSSS.Foundation.SpecFEM.SpecFemBasis <a id="bosss.foundation.specfem.specfembasis"></a>

**Summary:** A Spectral Element (high order continuous FEM) basis


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.#ctor(BoSSS.Foundation.Grid.Classic.GridData,System.Int32,ilPSP.LinSolvers.ISparseSolver) <a id="bosss.foundation.specfem.specfembasis.#ctor(bosss.foundation.grid.classic.griddata,system.int32,ilpsp.linsolvers.isparsesolver)"></a>
**Summary:** ctor.
**Parameter:** `p` - The number of nodes per edge - this, in consequence, determines the SpecFEM-space, resp. the polynomial degree of the interpolation.
**Parameter:** `grdDat` - The grid, upon which the SpecFEM-Basis is build.
**Parameter:** `__MassSolver` - optional specification of the mass matrix solver.


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.NodeMultiplicity <a id="bosss.foundation.specfem.specfembasis.nodemultiplicity"></a>


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.CellNodes <a id="bosss.foundation.specfem.specfembasis.cellnodes"></a>
**Summary:** Nodes for the reference cell in local coordinates
- 1st index: reference element
- 2nd index: node index
- 3rd index: spatial dimension


### Field: BoSSS.Foundation.SpecFEM.SpecFemBasis.UNodes <a id="bosss.foundation.specfem.specfembasis.unodes"></a>
**Summary:** - 1st index: reference element.
- 2nd index: type 
- 3rd index: unit (face index, vertex index, ...)


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.NodesPerCell <a id="bosss.foundation.specfem.specfembasis.nodespercell"></a>
**Summary:** Number of Nodes in one cell;
- index: reference element


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.NodalBasis <a id="bosss.foundation.specfem.specfembasis.nodalbasis"></a>
**Summary:** the nodal basis polynomials.
- 1st index: reference element index
- 2nd index: node index.


### Field: BoSSS.Foundation.SpecFEM.SpecFemBasis.m_Type <a id="bosss.foundation.specfem.specfembasis.m_type"></a>
**Summary:** The Node type for each node of a cell, i.e. whether the node is a cell- (1D,2D,3D), face- (only 2D and 3D), co-face- (only 3D), or vertex node (1D,2D,3D);
- 1st index: reference element
- 2nd index: cell node;


### Field: BoSSS.Foundation.SpecFEM.SpecFemBasis.m_EntityIndex <a id="bosss.foundation.specfem.specfembasis.m_entityindex"></a>
**Summary:** The entity index, see also [BoSSS.Foundation.Grid.RefElements.RefElement.GetNodeSet(System.Int32,BoSSS.Foundation.NodeSet@,System.Int32[]@,System.Int32[]@,System.Int32[])](BoSSS.Foundation.md#bosss.foundation.grid.refelements.refelement.getnodeset(system.int32,bosss.foundation.nodeset@,system.int32[]@,system.int32[]@,system.int32[])).
If the k-th node is 
- a cell node, the EntityIndex[k] is 0
- a face/edge node, the EntityIndex[k] is the index of the face within the reference element
- a co-face/co-edge node, the EntityIndex[k] is the index of the co-face within the reference element
- a vertex node, the EntityIndex[k] is the index of the vertex within the reference element
- 1st index: reference element;
- 2nd index: cell node;


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.GetModal2NodalOperator(BoSSS.Foundation.Basis) <a id="bosss.foundation.specfem.specfembasis.getmodal2nodaloperator(bosss.foundation.basis)"></a>
**Summary:** Returns the matrix to transform from
a coordinate vector with respect to DG basis [BoSSS.Foundation.Basis](BoSSS.Foundation.md#bosss.foundation.basis)
int the nodal DG basis.


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.GetNodal2ModalOperator(BoSSS.Foundation.Basis) <a id="bosss.foundation.specfem.specfembasis.getnodal2modaloperator(bosss.foundation.basis)"></a>
**Summary:** Returns the matrix to transform from
a coordinate vector with respect to the nodal DG basis
into the DG basis [BoSSS.Foundation.Basis](BoSSS.Foundation.md#bosss.foundation.basis).


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.GetNodeScatterMatrix <a id="bosss.foundation.specfem.specfembasis.getnodescattermatrix"></a>
**Summary:** Scattering operator from global nodes to cell-wise nodes


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.GetNullSpaceMatrix <a id="bosss.foundation.specfem.specfembasis.getnullspacematrix"></a>
**Summary:** An implicit description of the SEM space;


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.GetNullSpaceMatrix(System.Int32[][]@) <a id="bosss.foundation.specfem.specfembasis.getnullspacematrix(system.int32[][]@)"></a>
**Summary:** An implicit description of the SEM space;


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.ContainingDGBasis <a id="bosss.foundation.specfem.specfembasis.containingdgbasis"></a>
**Summary:** the minimal DG Basis which contains this SpecFEM Basis


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.GlobalNodes <a id="bosss.foundation.specfem.specfembasis.globalnodes"></a>
**Summary:** Nodes in global coordinates.


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.KnotenZuordnung(ilPSP.MultidimensionalArray,BoSSS.Platform.LinAlg.AffineTrafo,ilPSP.MultidimensionalArray) <a id="bosss.foundation.specfem.specfembasis.knotenzuordnung(ilpsp.multidimensionalarray,bosss.platform.linalg.affinetrafo,ilpsp.multidimensionalarray)"></a>
**Summary:** Geometrical matching of nodes.
**Parameter:** `NodesIn` - First set of nodes.
**Parameter:** `ict` - 
**Parameter:** `NodesOut` - second set of nodes.
**Returns:**
A permutation R, so that for all valid indices k, 
'NodesOut'[R[k]] == 'ict'('NodesIn'[k]).


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.IdentifyVertice(ilPSP.MultidimensionalArray,System.Int32[],System.Int32[],System.Int32) <a id="bosss.foundation.specfem.specfembasis.identifyvertice(ilpsp.multidimensionalarray,system.int32[],system.int32[],system.int32)"></a>
**Summary:** builds the cell-to-node ([BoSSS.Foundation.SpecFEM.SpecFemBasis.CellNode_To_Node](#bosss.foundation.specfem.specfembasis.cellnode_to_node)) mapping for Vertex nodes


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.ForeignNodeMapping <a id="bosss.foundation.specfem.specfembasis.foreignnodemapping"></a>
**Summary:** compute global indices and processor ranks (of respective owner processors) for foreign nodes


### Field: BoSSS.Foundation.SpecFEM.SpecFemBasis.ForeignNodes_GlobalIndex <a id="bosss.foundation.specfem.specfembasis.foreignnodes_globalindex"></a>
**Summary:** foreach foreign node, the global node index


### Field: BoSSS.Foundation.SpecFEM.SpecFemBasis.ForeignNodes_OwnerRank <a id="bosss.foundation.specfem.specfembasis.foreignnodes_ownerrank"></a>
**Summary:** foreach foreign node, the MPI-rank of the owner process


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.GridDat <a id="bosss.foundation.specfem.specfembasis.griddat"></a>
**Summary:** the associated grid


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.GetEntityIndex(System.Int32,System.Int32@,System.Int32@) <a id="bosss.foundation.specfem.specfembasis.getentityindex(system.int32,system.int32@,system.int32@)"></a>
**Summary:** For a global node index 'k', this returns either the respective cell-, edge- or vertex-index
which which the node is associated.
**Parameter:** `k` - a global node index
**Parameter:** `EntityIndex` - On exit, 
either a cell index, if 'k' is in the range of volume/cell nodes,
or an edge index, if 'k' is in ther range of edge nodes,
or a vertex index, if 'k' is in the range of vertex nodes.
**Parameter:** `_type` - the node type


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.GetNoOfLocalNodes(System.Int32) <a id="bosss.foundation.specfem.specfembasis.getnooflocalnodes(system.int32)"></a>
**Summary:** Number of local nodes (on current MPI process), for different node types ('type');
includes shared/foreign/owned but NOT periodic/external.
**Parameter:** `type` - node type index:

in 1D: 0 for volume/cell nodes, 1 for vertex nodes/edges (in 1D, the edges of the grid are 0-dimensional nodes)
in 2D: 0 for volume/cell nodes, 1 for edge nodes and 2 for vertex nodes. 
in 3D: 0 for volume/cell nodes, 1 for edge nodes (located on faces), 2 for co-edges (edges of faces), 3 for vertex nodes.
**Returns:**



### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.NoOfLocalNodes <a id="bosss.foundation.specfem.specfembasis.nooflocalnodes"></a>
**Summary:** local Number Of Nodes on this MPI process
(includes shared/foreign/owned but NOT periodic).


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.NoOfLocalOwnedNodes <a id="bosss.foundation.specfem.specfembasis.nooflocalownednodes"></a>
**Summary:** local Number Of Nodes owned by MPI process


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.NodePartition <a id="bosss.foundation.specfem.specfembasis.nodepartition"></a>
**Summary:** partition of nodes among MPI processes


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.GlobalNoOfNodes <a id="bosss.foundation.specfem.specfembasis.globalnoofnodes"></a>
**Summary:** Global Number of Nodes (over all MPI processes), i.e. dimension of the SEM vector space.


### Field: BoSSS.Foundation.SpecFEM.SpecFemBasis.CellNode_To_Node <a id="bosss.foundation.specfem.specfembasis.cellnode_to_node"></a>
**Summary:** Transformation from cell-node index to local node index:
- 1st index: cell index
- 2nd index: node index within cell


### Field: BoSSS.Foundation.SpecFEM.SpecFemBasis.MPI_SendLists <a id="bosss.foundation.specfem.specfembasis.mpi_sendlists"></a>
**Summary:** For each MPI processor rank p, a list of indices which determines the DOFs that must be send
to rank p during the scatter-operation **BoSSS.Foundation.SpecFEM.Transceiver.Scatter(ilPSP.MultidimensionalArray)**. 
- 1st index: MPI rank p, if an entry is null, no data is send to the corresponding processor.
- 2nd index: enumeration.
content: indices of locally owned DOFs.


### Field: BoSSS.Foundation.SpecFEM.SpecFemBasis.MPI_InsertLists <a id="bosss.foundation.specfem.specfembasis.mpi_insertlists"></a>
**Summary:** For each MPI processor rank p, a list of indices which determines 
where the DOFs which this rank receices from rank  p should be inserted
during the scatter-operation **BoSSS.Foundation.SpecFEM.Transceiver.Scatter(ilPSP.MultidimensionalArray)**. 
- 1st index: MPI rank p, if an entry is null, no data is received from processor p.
- 2nd index: enumeration.
content: indices of borrowed DOFs.


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.InitGlobalNodes <a id="bosss.foundation.specfem.specfembasis.initglobalnodes"></a>
**Summary:** Computes the coordinates of the global nodes in physical coordinates.


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.MassMatrix <a id="bosss.foundation.specfem.specfembasis.massmatrix"></a>
**Summary:** the SpecFEM mass matrix;


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.ComputeMassMatrix(BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.specfem.specfembasis.computemassmatrix(bosss.foundation.grid.cellmask)"></a>
**Summary:** computes the Mass-Matrix of this SpecFEM-Basis.
**Parameter:** `cm` - optional restriction onto a subgrid
**Returns:**



### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.MassSolver <a id="bosss.foundation.specfem.specfembasis.masssolver"></a>
**Summary:** a linear solver for the omnipresent problem 
[BoSSS.Foundation.SpecFEM.SpecFemBasis.MassMatrix](#bosss.foundation.specfem.specfembasis.massmatrix)*x = b.


## Method: BoSSS.Foundation.SpecFEM.SpecFemBasis.ComputeMassMatrixChk <a id="bosss.foundation.specfem.specfembasis.computemassmatrixchk"></a>
**Summary:** test code for mass matrix computation


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.MaxDegree <a id="bosss.foundation.specfem.specfembasis.maxdegree"></a>
**Summary:** maximum polynomial degree of the nodal basis


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.MaxFullDegree <a id="bosss.foundation.specfem.specfembasis.maxfulldegree"></a>
**Summary:** the maximum degree that is available in all directions


### Property: BoSSS.Foundation.SpecFEM.SpecFemBasis.MaxFullDGBasis <a id="bosss.foundation.specfem.specfembasis.maxfulldgbasis"></a>
**Summary:** a DG basis of degree [BoSSS.Foundation.SpecFEM.SpecFemBasis.MaxFullDegree](#bosss.foundation.specfem.specfembasis.maxfulldegree).

## Class: BoSSS.Foundation.SpecFEM.SpecFemField <a id="bosss.foundation.specfem.specfemfield"></a>

**Summary:** SpecFEM Representation of a scalar field


## Method: BoSSS.Foundation.SpecFEM.SpecFemField.#ctor(BoSSS.Foundation.SpecFEM.SpecFemBasis) <a id="bosss.foundation.specfem.specfemfield.#ctor(bosss.foundation.specfem.specfembasis)"></a>
**Summary:** ctor;


### Property: BoSSS.Foundation.SpecFEM.SpecFemField.Coordinates <a id="bosss.foundation.specfem.specfemfield.coordinates"></a>
**Summary:** Coordinates with respect to the nodal basis;
- 1st index: node index.


## Method: BoSSS.Foundation.SpecFEM.SpecFemField.AccToDGField(System.Double,BoSSS.Foundation.ConventionalDGField,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.specfem.specfemfield.acctodgfield(system.double,bosss.foundation.conventionaldgfield,bosss.foundation.grid.cellmask)"></a>
**Summary:** accumulate this field to a DG field
**Parameter:** `alpha` - 
**Parameter:** `DGField` - 
**Parameter:** `mask` - optional cell mask


## Method: BoSSS.Foundation.SpecFEM.SpecFemField.ProjectDGFieldMaximum(System.Double,BoSSS.Foundation.ConventionalDGField) <a id="bosss.foundation.specfem.specfemfield.projectdgfieldmaximum(system.double,bosss.foundation.conventionaldgfield)"></a>
**Summary:** projects some DG field onto this
**Parameter:** `alpha` - 
**Parameter:** `DGField` - 


## Method: BoSSS.Foundation.SpecFEM.SpecFemField.ProjectDGFieldCheaply(System.Double,BoSSS.Foundation.ConventionalDGField) <a id="bosss.foundation.specfem.specfemfield.projectdgfieldcheaply(system.double,bosss.foundation.conventionaldgfield)"></a>
**Summary:** projects some DG field onto this
**Parameter:** `alpha` - 
**Parameter:** `DGField` - 


## Method: BoSSS.Foundation.SpecFEM.SpecFemField.ProjectDGField(System.Double,BoSSS.Foundation.ConventionalDGField,BoSSS.Foundation.Grid.CellMask) <a id="bosss.foundation.specfem.specfemfield.projectdgfield(system.double,bosss.foundation.conventionaldgfield,bosss.foundation.grid.cellmask)"></a>
**Summary:** projects some DG field onto this
**Parameter:** `alpha` - 
**Parameter:** `DGField` - 
**Parameter:** `_cm` - optional restriction to computational domain
**Remark:**
This method computes an exact
L2-projection of the DG-field onto the SpecFEM-space, so a global linear system, which contains all
DOF's, has to be solved.
In contrast, [BoSSS.Foundation.SpecFEM.SpecFemField.ProjectDGFieldCheaply(System.Double,BoSSS.Foundation.ConventionalDGField)](#bosss.foundation.specfem.specfemfield.projectdgfieldcheaply(system.double,bosss.foundation.conventionaldgfield)) performs an approximate projection which only involves
local operations for each cell.

## Class: BoSSS.Foundation.SpecFEM.Transceiver <a id="bosss.foundation.specfem.transceiver"></a>

**Summary:** MPI data exchange for Spectral Elements


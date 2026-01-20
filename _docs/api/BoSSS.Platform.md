---
title: "BoSSSPlatform"
parent: "API Reference"
nav_order: 7
---
# Namespace: BoSSS.Platform

## Class: BoSSS.Platform.LinAlg.AffineManifold <a id="bosss.platform.linalg.affinemanifold"></a>

**Summary:** Affine, D-1 dimensional manifold M;
x is in M, if [BoSSS.Platform.LinAlg.AffineManifold.Normal](#bosss.platform.linalg.affinemanifold.normal)*x = [BoSSS.Platform.LinAlg.AffineManifold.a](#bosss.platform.linalg.affinemanifold.a).


## Method: BoSSS.Platform.LinAlg.AffineManifold.#ctor(System.Int32) <a id="bosss.platform.linalg.affinemanifold.#ctor(system.int32)"></a>
**Summary:** constructs an empty, degenerate manifold
**Parameter:** `D` - 


## Method: BoSSS.Platform.LinAlg.AffineManifold.#ctor(System.Double[],System.Double[]) <a id="bosss.platform.linalg.affinemanifold.#ctor(system.double[],system.double[])"></a>
**Summary:** constructs an affine manifold from normal vector and offset point
**Parameter:** `_Normal` - normal onto the affine manifold
**Parameter:** `_Offset` - one point in the plane, can be null


## Method: BoSSS.Platform.LinAlg.AffineManifold.#ctor(ilPSP.Vector,ilPSP.Vector) <a id="bosss.platform.linalg.affinemanifold.#ctor(ilpsp.vector,ilpsp.vector)"></a>
**Summary:** constructs an affine manifold from normal vector and offset point
**Parameter:** `_Normal` - normal onto the affine manifold
**Parameter:** `_Offset` - one point in the plane, can be null


## Method: BoSSS.Platform.LinAlg.AffineManifold.FromPoints(ilPSP.Vector[]) <a id="bosss.platform.linalg.affinemanifold.frompoints(ilpsp.vector[])"></a>
**Summary:** constructs an affine manifold from a set of points
**Parameter:** `pts` - points on the manifold;
1st index: point index.


## Method: BoSSS.Platform.LinAlg.AffineManifold.FromPoints(System.Double[0:,0:]) <a id="bosss.platform.linalg.affinemanifold.frompoints(system.double[0:,0:])"></a>
**Summary:** constructs an affine manifold from a set of points
**Parameter:** `pts` - points on the manifold;
1st index: point index.
2nd index: spatial dimension.


## Method: BoSSS.Platform.LinAlg.AffineManifold.FromPoints(ilPSP.MultidimensionalArray) <a id="bosss.platform.linalg.affinemanifold.frompoints(ilpsp.multidimensionalarray)"></a>
**Summary:** constructs an affine manifold from a set of points
**Parameter:** `pts` - points on the manifold;
1st index: point index.
2nd index: spatial dimension.


### Field: BoSSS.Platform.LinAlg.AffineManifold.Normal <a id="bosss.platform.linalg.affinemanifold.normal"></a>
**Summary:** surface normal


### Field: BoSSS.Platform.LinAlg.AffineManifold.a <a id="bosss.platform.linalg.affinemanifold.a"></a>
**Summary:** affine offset (result of scalar product of [BoSSS.Platform.LinAlg.AffineManifold.Normal](#bosss.platform.linalg.affinemanifold.normal)*x, with x being an arbitrary point in the surface)


## Method: BoSSS.Platform.LinAlg.AffineManifold.PointDistance(System.Double[]) <a id="bosss.platform.linalg.affinemanifold.pointdistance(system.double[])"></a>
**Summary:** the distance of some point to the affine manifold/plane, in multiples of the norm of [BoSSS.Platform.LinAlg.AffineManifold.Normal](#bosss.platform.linalg.affinemanifold.normal);


## Method: BoSSS.Platform.LinAlg.AffineManifold.PointDistance(ilPSP.Vector) <a id="bosss.platform.linalg.affinemanifold.pointdistance(ilpsp.vector)"></a>
**Summary:** the distance of some point to the affine manifold/plane, in multiples of the norm of [BoSSS.Platform.LinAlg.AffineManifold.Normal](#bosss.platform.linalg.affinemanifold.normal);


## Method: BoSSS.Platform.LinAlg.AffineManifold.ProjectPoint(ilPSP.Vector) <a id="bosss.platform.linalg.affinemanifold.projectpoint(ilpsp.vector)"></a>
**Summary:** returns the point in this affine manifold (plane) which is closest to 'pt'


## Method: BoSSS.Platform.LinAlg.AffineManifold.Equals(System.Object,System.Double) <a id="bosss.platform.linalg.affinemanifold.equals(system.object,system.double)"></a>
**Summary:** equality check: tests if two objects represent the same affine manifold/plane


## Method: BoSSS.Platform.LinAlg.AffineManifold.Equals(System.Object) <a id="bosss.platform.linalg.affinemanifold.equals(system.object)"></a>
**Summary:** equality check: tests if two objects represent the same affine manifold/plane


## Method: BoSSS.Platform.LinAlg.AffineManifold.GetHashCode <a id="bosss.platform.linalg.affinemanifold.gethashcode"></a>
**Summary:** hash


## Method: BoSSS.Platform.LinAlg.AffineManifold.Clone <a id="bosss.platform.linalg.affinemanifold.clone"></a>
**Summary:** non-shallow cloning
**Returns:**



## Method: BoSSS.Platform.LinAlg.AffineManifold.Intersect2D(BoSSS.Platform.LinAlg.AffineManifold,BoSSS.Platform.LinAlg.AffineManifold) <a id="bosss.platform.linalg.affinemanifold.intersect2d(bosss.platform.linalg.affinemanifold,bosss.platform.linalg.affinemanifold)"></a>
**Summary:** Intersection of two 1D affine manifolds in 2D space

## Class: BoSSS.Platform.LinAlg.AffineTrafo <a id="bosss.platform.linalg.affinetrafo"></a>

**Summary:** represents an affine - linear transformation;

**Remark:**
The transformation of some point $\vec{x}$ into it's 
image $\vec{y}$
is defined as

y = [BoSSS.Platform.LinAlg.AffineTrafo.Matrix](#bosss.platform.linalg.affinetrafo.matrix)*$\vec{x}$ + [BoSSS.Platform.LinAlg.AffineTrafo.Affine](#bosss.platform.linalg.affinetrafo.affine)


## Method: BoSSS.Platform.LinAlg.AffineTrafo.#ctor(System.Int32,System.Int32) <a id="bosss.platform.linalg.affinetrafo.#ctor(system.int32,system.int32)"></a>
**Summary:** initializes a zero transformation
**Parameter:** `D_cod` - spatial dimension of codomain
**Parameter:** `D_dom` - spatial dimension of domain


## Method: BoSSS.Platform.LinAlg.AffineTrafo.#ctor(System.Int32) <a id="bosss.platform.linalg.affinetrafo.#ctor(system.int32)"></a>
**Summary:** initializes a zero transformation
**Parameter:** `D` - spatial dimension


## Method: BoSSS.Platform.LinAlg.AffineTrafo.ToString <a id="bosss.platform.linalg.affinetrafo.tostring"></a>
**Returns:**



## Method: BoSSS.Platform.LinAlg.AffineTrafo.#ctor(ilPSP.Utils.IMatrix,System.Double[]) <a id="bosss.platform.linalg.affinetrafo.#ctor(ilpsp.utils.imatrix,system.double[])"></a>
**Summary:** initializes a transformation with matrix and affine vector.


## Method: BoSSS.Platform.LinAlg.AffineTrafo.#ctor <a id="bosss.platform.linalg.affinetrafo.#ctor"></a>
**Summary:** empty ctor.


### Field: BoSSS.Platform.LinAlg.AffineTrafo.Matrix <a id="bosss.platform.linalg.affinetrafo.matrix"></a>
**Summary:** linear part of the transformation;


### Field: BoSSS.Platform.LinAlg.AffineTrafo.Affine <a id="bosss.platform.linalg.affinetrafo.affine"></a>
**Summary:** affine part of the transformation;


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Transform(ilPSP.Vector) <a id="bosss.platform.linalg.affinetrafo.transform(ilpsp.vector)"></a>
**Summary:** Computes [BoSSS.Platform.LinAlg.AffineTrafo.Matrix](#bosss.platform.linalg.affinetrafo.matrix)*'vtx' + [BoSSS.Platform.LinAlg.AffineTrafo.Affine](#bosss.platform.linalg.affinetrafo.affine);
**Parameter:** `vtx` - the vector/point/vertex that should be transformed;
**Returns:**

**Remark:**
This method should not be used for performance-critical
issues; One reason for this is that it allocates a small array
for return value.


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Transform(System.Double[]) <a id="bosss.platform.linalg.affinetrafo.transform(system.double[])"></a>
**Summary:** Computes [BoSSS.Platform.LinAlg.AffineTrafo.Matrix](#bosss.platform.linalg.affinetrafo.matrix)*'vtx' + [BoSSS.Platform.LinAlg.AffineTrafo.Affine](#bosss.platform.linalg.affinetrafo.affine);
**Parameter:** `vtx` - the vector/point/vertex that should be transformed;
**Returns:**

**Remark:**
This method should not be used for performance-critical
issues; One reason for this is that it allocates a small array
for return value.


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Transform(System.Double[],System.Double[]) <a id="bosss.platform.linalg.affinetrafo.transform(system.double[],system.double[])"></a>
**Summary:** applies this transformation to a series of vectors


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Transform(ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray) <a id="bosss.platform.linalg.affinetrafo.transform(ilpsp.multidimensionalarray,ilpsp.multidimensionalarray)"></a>
**Summary:** Applies this transformation to a series of vectors.


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Transform(System.Double[0:,0:]) <a id="bosss.platform.linalg.affinetrafo.transform(system.double[0:,0:])"></a>
**Summary:** applies this transformation to a series of vectors


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Transform(ilPSP.MultidimensionalArray) <a id="bosss.platform.linalg.affinetrafo.transform(ilpsp.multidimensionalarray)"></a>
**Summary:** applies this transformation to a series of vectors


## Method: BoSSS.Platform.LinAlg.AffineTrafo.TransformInverse(ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray) <a id="bosss.platform.linalg.affinetrafo.transforminverse(ilpsp.multidimensionalarray,ilpsp.multidimensionalarray)"></a>
**Summary:** Inverse transformation; if dimension ans co-dimension do not match, a projection is performed


## Method: BoSSS.Platform.LinAlg.AffineTrafo.TransformInverse(ilPSP.MultidimensionalArray) <a id="bosss.platform.linalg.affinetrafo.transforminverse(ilpsp.multidimensionalarray)"></a>
**Summary:** Inverse transformation; if dimension ans co-dimension do not match, a projection is performed


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Invert <a id="bosss.platform.linalg.affinetrafo.invert"></a>
**Summary:** computes the inverse transformation.

Quite surprising, ey?
**Returns:**



### Property: BoSSS.Platform.LinAlg.AffineTrafo.DomainDimension <a id="bosss.platform.linalg.affinetrafo.domaindimension"></a>
**Summary:** dimension of domain


### Property: BoSSS.Platform.LinAlg.AffineTrafo.CodomainDimension <a id="bosss.platform.linalg.affinetrafo.codomaindimension"></a>
**Summary:** dimension of codomain


## Method: BoSSS.Platform.LinAlg.AffineTrafo.op_Multiply(BoSSS.Platform.LinAlg.AffineTrafo,BoSSS.Platform.LinAlg.AffineTrafo) <a id="bosss.platform.linalg.affinetrafo.op_multiply(bosss.platform.linalg.affinetrafo,bosss.platform.linalg.affinetrafo)"></a>
**Summary:** composition of two transformations;
**Parameter:** `left` - 
**Parameter:** `right` - 
**Returns:**
returns a transformation, which's application is equivalent to
first applying 'right' and secondly applying 'left';
**Remark:**
let be M and o matrix (see [BoSSS.Platform.LinAlg.AffineTrafo.Matrix](#bosss.platform.linalg.affinetrafo.matrix)) and affine vector (see [BoSSS.Platform.LinAlg.AffineTrafo.Affine](#bosss.platform.linalg.affinetrafo.affine))
of the 'left' Transformation and, respectively N and p
matrix and vector of 'right'.
Then the matrix of the returned value is M*N, and the vector of the returned 
transformation is M*p + o;


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Identity(System.Int32) <a id="bosss.platform.linalg.affinetrafo.identity(system.int32)"></a>
**Summary:** creates an identity transformation
**Parameter:** `D` - spatial dimension
**Returns:**



## Method: BoSSS.Platform.LinAlg.AffineTrafo.FromPoints(ilPSP.MultidimensionalArray,ilPSP.MultidimensionalArray) <a id="bosss.platform.linalg.affinetrafo.frompoints(ilpsp.multidimensionalarray,ilpsp.multidimensionalarray)"></a>
**Summary:** computes matrix and affine vector of the affine-linear transformation
that maps the vectors in the 'preimage' to 'image';
**Parameter:** `preimage` - The preimage: $(D+1)$  vectors of dimension $D$;

1st index: vector/vertex index, length is $D+1$
2nd index: spatial dimension, lenght is D

Tip: use **])**
if the sequence of indices is not appropriate;
**Parameter:** `image` - The image: $(D+1)$ vectors of dimension $D$;

1st index: vector/vertex index, length is $D + 1$
2nd index: spatial dimension, length is $D$


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Some2DRotation(System.Double) <a id="bosss.platform.linalg.affinetrafo.some2drotation(system.double)"></a>
**Summary:** Returns a 2D transformation.


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Rotation3D(ilPSP.Vector,System.Double) <a id="bosss.platform.linalg.affinetrafo.rotation3d(ilpsp.vector,system.double)"></a>
**Summary:** 3D rotation around an arbitrary axis
see also: https://en.wikipedia.org/wiki/Rotation_matrix#Rotation_matrix_from_axis_and_angle
**Parameter:** `Axis` - rotation axis
**Parameter:** `theta` - angle in radians
**Returns:**



## Method: BoSSS.Platform.LinAlg.AffineTrafo.FromPoints(System.Double[0:,0:],System.Double[0:,0:]) <a id="bosss.platform.linalg.affinetrafo.frompoints(system.double[0:,0:],system.double[0:,0:])"></a>
**Summary:** computes matrix and affine vector of the affine-linear transformation
that maps the vectors in the 'preimage' to 'image';
**Parameter:** `preimage` - The preimage: L vectors of dimension D_dom;

1st index: vector/vertex index, length is L
2nd index: spatial dimension, length is D_dom

Tip: use **])**
if the sequence of indices is not appropriate;
**Parameter:** `image` - The image: L vectors of dimension D_cod;

1st index: vector/vertex index, length is L
2nd index: spatial dimension, length is D_cod
**Remark:**
L*D_cod == D_cod + L*D_dom


## Method: BoSSS.Platform.LinAlg.AffineTrafo.CloneAs <a id="bosss.platform.linalg.affinetrafo.cloneas"></a>
**Summary:** creates a non-shallow copy


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Clone <a id="bosss.platform.linalg.affinetrafo.clone"></a>
**Summary:** creates a non-shallow copy


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Equals(System.Object) <a id="bosss.platform.linalg.affinetrafo.equals(system.object)"></a>
**Summary:** See [BoSSS.Platform.LinAlg.AffineTrafo.Equals(BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.platform.linalg.affinetrafo.equals(bosss.platform.linalg.affinetrafo))
**Parameter:** `obj` - See **System.Object.Equals(System.Object)**
**Returns:**
See [BoSSS.Platform.LinAlg.AffineTrafo.Equals(BoSSS.Platform.LinAlg.AffineTrafo)](#bosss.platform.linalg.affinetrafo.equals(bosss.platform.linalg.affinetrafo))


## Method: BoSSS.Platform.LinAlg.AffineTrafo.GetHashCode <a id="bosss.platform.linalg.affinetrafo.gethashcode"></a>
**Summary:** Builds a hash code based on the hashes of [BoSSS.Platform.LinAlg.AffineTrafo.Affine](#bosss.platform.linalg.affinetrafo.affine) and
[BoSSS.Platform.LinAlg.AffineTrafo.Matrix](#bosss.platform.linalg.affinetrafo.matrix).
**Returns:**
A hash of this object


## Method: BoSSS.Platform.LinAlg.AffineTrafo.Equals(BoSSS.Platform.LinAlg.AffineTrafo) <a id="bosss.platform.linalg.affinetrafo.equals(bosss.platform.linalg.affinetrafo)"></a>
**Summary:** Checks this object for equality to the given transformation based
on [BoSSS.Platform.LinAlg.AffineTrafo.Affine](#bosss.platform.linalg.affinetrafo.affine) and [BoSSS.Platform.LinAlg.AffineTrafo.Matrix](#bosss.platform.linalg.affinetrafo.matrix).
**Parameter:** `other` - The object to be compared with.
**Returns:**
True, if [BoSSS.Platform.LinAlg.AffineTrafo.Affine](#bosss.platform.linalg.affinetrafo.affine) and [BoSSS.Platform.LinAlg.AffineTrafo.Matrix](#bosss.platform.linalg.affinetrafo.matrix) of the given
transformation are equal to the entities in this object. False,
otherwise.


## Method: BoSSS.Platform.LinAlg.AffineTrafo.ApproximateEquals(BoSSS.Platform.LinAlg.AffineTrafo,System.Double) <a id="bosss.platform.linalg.affinetrafo.approximateequals(bosss.platform.linalg.affinetrafo,system.double)"></a>
**Summary:** approximately equal
**Parameter:** `other` - 
**Parameter:** `RelTol` - relative tolerance for comparison
**Returns:**


## Class: BoSSS.Platform.BlockDiagonalMatrix <a id="bosss.platform.blockdiagonalmatrix"></a>

**Summary:** Special, block-diagonal sparse matrix


## Method: BoSSS.Platform.BlockDiagonalMatrix.#ctor(ilPSP.IPartitioning,ilPSP.IPartitioning,System.Int32,System.Int32) <a id="bosss.platform.blockdiagonalmatrix.#ctor(ilpsp.ipartitioning,ilpsp.ipartitioning,system.int32,system.int32)"></a>
**Summary:** Constructor, the size of the block-diagonals is determined by 'RowBlkSz'*'ColBlkSz'


### Property: BoSSS.Platform.BlockDiagonalMatrix.MPI_Comm <a id="bosss.platform.blockdiagonalmatrix.mpi_comm"></a>
**Summary:** MPI Communicator on which this object lives on.


## Method: BoSSS.Platform.BlockDiagonalMatrix.#ctor <a id="bosss.platform.blockdiagonalmatrix.#ctor"></a>
**Summary:** used by [BoSSS.Platform.BlockDiagonalMatrix.Clone](#bosss.platform.blockdiagonalmatrix.clone)


## Method: BoSSS.Platform.BlockDiagonalMatrix.Clone <a id="bosss.platform.blockdiagonalmatrix.clone"></a>
**Summary:** creates a non-shallow copy


### Property: BoSSS.Platform.BlockDiagonalMatrix.NoOfRowsPerBlock <a id="bosss.platform.blockdiagonalmatrix.noofrowsperblock"></a>
**Summary:** Number of rows in the the diagonal blocks; note that the blocks are
not necessarily quadratic.


### Property: BoSSS.Platform.BlockDiagonalMatrix.NoOfColsPerBlock <a id="bosss.platform.blockdiagonalmatrix.noofcolsperblock"></a>
**Summary:** Number of columns in the the diagonal blocks; note that the blocks
are not necessarily quadratic.


### Field: BoSSS.Platform.BlockDiagonalMatrix.Blox <a id="bosss.platform.blockdiagonalmatrix.blox"></a>
**Summary:** Main storage of this object

1st index: Block index
2nd index: Row within block
3rd index: Column within block


## Method: BoSSS.Platform.BlockDiagonalMatrix.#ctor(ilPSP.IPartitioning,System.Int32) <a id="bosss.platform.blockdiagonalmatrix.#ctor(ilpsp.ipartitioning,system.int32)"></a>
**Summary:** ctor, creates a matrix with quadratic blocks.


## Method: BoSSS.Platform.BlockDiagonalMatrix.#ctor(System.Int32,System.Int32) <a id="bosss.platform.blockdiagonalmatrix.#ctor(system.int32,system.int32)"></a>
**Summary:** ctor, creates a matrix with quadratic blocks.


## Method: BoSSS.Platform.BlockDiagonalMatrix.#ctor(ilPSP.LinSolvers.MsrMatrix,System.Int32,System.Int32) <a id="bosss.platform.blockdiagonalmatrix.#ctor(ilpsp.linsolvers.msrmatrix,system.int32,system.int32)"></a>
**Summary:** Ctor, creates a matrix initialized with the diagonal blocks of
'Src'.
**Parameter:** `Src` - 
**Parameter:** `ColBlkSz` - number of columns per block; all blocks in the matrix have the same size
**Parameter:** `RowBlkSz` - number of rows per block; all blocks in the matrix have the same size


## Method: BoSSS.Platform.BlockDiagonalMatrix.GetIndex(System.Int32,System.Int32,System.Int32,System.Int32@,System.Int32@) <a id="bosss.platform.blockdiagonalmatrix.getindex(system.int32,system.int32,system.int32,system.int32@,system.int32@)"></a>
**Summary:** Determines the indices ('i', 'j')
into the matrix for a given position ('block',
'rowInBlock', 'columnInBlock').
**Parameter:** `block` - 
**Parameter:** `rowInBlock` - 
**Parameter:** `columnInBlock` - 
**Parameter:** `i` - 
**Parameter:** `j` - 


### Property: BoSSS.Platform.BlockDiagonalMatrix.NoOfBlocks <a id="bosss.platform.blockdiagonalmatrix.noofblocks"></a>
**Summary:** The total number of diagonal blocks.


## Method: BoSSS.Platform.BlockDiagonalMatrix.AccBlock(System.Int64,System.Int64,System.Double,ilPSP.MultidimensionalArray) <a id="bosss.platform.blockdiagonalmatrix.accblock(system.int64,system.int64,system.double,ilpsp.multidimensionalarray)"></a>
**Summary:** Accumulates 'Block'*'alpha' to this matrix,
at the row/column offset 'i0' resp. 'j0'.
**Parameter:** `i0` - Row offset.
**Parameter:** `j0` - Column offset.
**Parameter:** `alpha` - Scaling factor for the accumulation operation.
**Parameter:** `Block` - Block to accumulate.


## Method: BoSSS.Platform.BlockDiagonalMatrix.AccBlock(System.Int64,System.Int64,System.Double,ilPSP.MultidimensionalArray,System.Double) <a id="bosss.platform.blockdiagonalmatrix.accblock(system.int64,system.int64,system.double,ilpsp.multidimensionalarray,system.double)"></a>
**Summary:** Accumulates a block of entries to this matrix.
**Parameter:** `i0` - Row index offset.
**Parameter:** `j0` - Column index offset.
**Parameter:** `alpha` - Scaling factor for the accumulation.
**Parameter:** `Block` - Block to add.
**Parameter:** `beta` - pre-scaling


## Method: BoSSS.Platform.BlockDiagonalMatrix.ReadBlock(System.Int64,System.Int64,ilPSP.MultidimensionalArray) <a id="bosss.platform.blockdiagonalmatrix.readblock(system.int64,system.int64,ilpsp.multidimensionalarray)"></a>
**Summary:** Extracts a block of entries from this matrix and stores it in 'Block'
**Parameter:** `i0` - Row index offset.
**Parameter:** `j0` - Column index offset.
**Parameter:** `Block` - 


### Property: BoSSS.Platform.BlockDiagonalMatrix.Item(System.Int32,System.Int32,System.Int32) <a id="bosss.platform.blockdiagonalmatrix.item(system.int32,system.int32,system.int32)"></a>
**Summary:** Provides direct access to the matrix using the block index
'block' and the row and column index within
this block.


## Method: BoSSS.Platform.BlockDiagonalMatrix.SpMV``2(System.Double,``0,System.Double,``1) <a id="bosss.platform.blockdiagonalmatrix.spmv``2(system.double,``0,system.double,``1)"></a>
**Summary:** matrix/vector product:
'acc'='acc'*'beta'
+ 'alpha'*this*'a'


### Property: BoSSS.Platform.BlockDiagonalMatrix.ColPartition <a id="bosss.platform.blockdiagonalmatrix.colpartition"></a>
**Summary:** column partition that is induced by the row partition


## Method: BoSSS.Platform.BlockDiagonalMatrix.op_Multiply(BoSSS.Platform.BlockDiagonalMatrix,ilPSP.LinSolvers.MsrMatrix) <a id="bosss.platform.blockdiagonalmatrix.op_multiply(bosss.platform.blockdiagonalmatrix,ilpsp.linsolvers.msrmatrix)"></a>
**Summary:** matrix-matrix-multiplication, see [BoSSS.Platform.BlockDiagonalMatrix.Multiply(BoSSS.Platform.BlockDiagonalMatrix,ilPSP.LinSolvers.MsrMatrix)](#bosss.platform.blockdiagonalmatrix.multiply(bosss.platform.blockdiagonalmatrix,ilpsp.linsolvers.msrmatrix)).


## Method: BoSSS.Platform.BlockDiagonalMatrix.Multiply(BoSSS.Platform.BlockDiagonalMatrix,ilPSP.LinSolvers.MsrMatrix) <a id="bosss.platform.blockdiagonalmatrix.multiply(bosss.platform.blockdiagonalmatrix,ilpsp.linsolvers.msrmatrix)"></a>
**Summary:** multiplies an [BoSSS.Platform.BlockDiagonalMatrix](#bosss.platform.blockdiagonalmatrix) by an **ilPSP.LinSolvers.MsrMatrix**


## Method: BoSSS.Platform.BlockDiagonalMatrix.Invert <a id="bosss.platform.blockdiagonalmatrix.invert"></a>
**Summary:** Calculates the inverse of this matrix and returns the result.
**Returns:**
Inverse of this matrix


### Property: BoSSS.Platform.BlockDiagonalMatrix.NoOfRows <a id="bosss.platform.blockdiagonalmatrix.noofrows"></a>
**Summary:** number of matrix rows


### Property: BoSSS.Platform.BlockDiagonalMatrix.NoOfCols <a id="bosss.platform.blockdiagonalmatrix.noofcols"></a>
**Summary:** number of matrix columns


## Method: BoSSS.Platform.BlockDiagonalMatrix.Clear <a id="bosss.platform.blockdiagonalmatrix.clear"></a>
**Summary:** Sets all entries to zero


## Method: BoSSS.Platform.BlockDiagonalMatrix.Scale(System.Double) <a id="bosss.platform.blockdiagonalmatrix.scale(system.double)"></a>
**Summary:** Scales each entry by 'a'
**Parameter:** `a` - 


## Method: BoSSS.Platform.BlockDiagonalMatrix.Acc(System.Double,ilPSP.Utils.IMatrix) <a id="bosss.platform.blockdiagonalmatrix.acc(system.double,ilpsp.utils.imatrix)"></a>
**Summary:** Accumulates 'a'*'M' to this
matrix. Note that
**Parameter:** `a` - 
**Parameter:** `M` - The matrix to be added. Note that the given matrix must not contain
entries outside of the diagonal blocks represented by this matrix.


## Method: BoSSS.Platform.BlockDiagonalMatrix.CopyTo(System.Double[0:,0:],System.Int32,System.Int32) <a id="bosss.platform.blockdiagonalmatrix.copyto(system.double[0:,0:],system.int32,system.int32)"></a>
**Summary:** Copies the entries of this matrix to 'dest'.
**Parameter:** `dest` - 
**Parameter:** `i0` - 
**Parameter:** `i1` - 


## Method: BoSSS.Platform.BlockDiagonalMatrix.CopyTo``1(``0,System.Boolean,System.Int32) <a id="bosss.platform.blockdiagonalmatrix.copyto``1(``0,system.boolean,system.int32)"></a>
**Summary:** Not implemented (not used in the code anyway?)
**Parameter:** `array` - 
**Parameter:** `RowWise` - 
**Parameter:** `arrayoffset` - 


## Method: BoSSS.Platform.BlockDiagonalMatrix.GetBlock(System.Int32) <a id="bosss.platform.blockdiagonalmatrix.getblock(system.int32)"></a>
**Summary:** Creates a copy of block 'blockIndex'
**Parameter:** `blockIndex` - Index of the block
**Returns:**
A copy of the selected block as a matrix


## Method: BoSSS.Platform.BlockDiagonalMatrix.SaveToTextFile(System.String,System.IO.FileMode) <a id="bosss.platform.blockdiagonalmatrix.savetotextfile(system.string,system.io.filemode)"></a>
**Summary:** Saves the contents of this matrix into a text file for debugging
purposes.
**Parameter:** `fileName` - 
**Parameter:** `fm` - 

## Class: BoSSS.Platform.Enum`1 <a id="bosss.platform.enum`1"></a>

**Summary:** Utility methods for **System.Enum**s exploiting generics.


## Method: BoSSS.Platform.Enum`1.Parse(System.String) <a id="bosss.platform.enum`1.parse(system.string)"></a>
**Summary:** Parses the given string value into an enum of type
. The case of the given value
'value' is considered relevant.
**Parameter:** `value` - The value to be parsed
**Returns:**
The parsed enum


## Method: BoSSS.Platform.Enum`1.Parse(System.String,System.Boolean) <a id="bosss.platform.enum`1.parse(system.string,system.boolean)"></a>
**Summary:** Parses the given string value into an enum of type
. Depending on
'ignoreCase', the case of
'value' is or is not considered relevant.
**Parameter:** `value` - The value to be parsed
**Parameter:** `ignoreCase` - **System.Enum.Parse(System.Type,System.String,System.Boolean)**
**Returns:**
The parsed enum


## Method: BoSSS.Platform.Enum`1.ParseOrDefault(System.String) <a id="bosss.platform.enum`1.parseordefault(system.string)"></a>
**Summary:** Tries to parse the given string value (case insensitive comparison)
and returns the default value of  in
case this was not successful.
**Parameter:** `value` - The value to be parsed
**Returns:**
The enum value corresponding to 'value' if it
exists. Otherwise, default() is
returned.


## Method: BoSSS.Platform.Enum`1.TryParse(System.String,`0@) <a id="bosss.platform.enum`1.tryparse(system.string,`0@)"></a>
**Summary:** Tries to parse the given string value (case insensitive comparison)
**Parameter:** `value` - The value to be parsed
**Parameter:** `result` - On exit: the enum value corresponding to 'value'
if it exists. Otherwise, default().
**Returns:**
True, if the parsing of 'value' was successful;
false otherwise.


## Method: BoSSS.Platform.Enum`1.GetValues <a id="bosss.platform.enum`1.getvalues"></a>
**Summary:** Type-safe variant of **System.Enum.GetValues(System.Type)**.
**Returns:**
The list of constants defined in .


## Method: BoSSS.Platform.Enum`1.CheckIsEnum <a id="bosss.platform.enum`1.checkisenum"></a>
**Summary:** Checks whether the passed type parameter
really is an enum since this
generic type constraint is not supported by C#.

## Class: BoSSS.Platform.ExpirableLazy`1 <a id="bosss.platform.expirablelazy`1"></a>

**Summary:** A custom variant of the Lazy{T} class where the stored value is 
automatically re-evaluated if it is no longer up-to-date.


### Field: BoSSS.Platform.ExpirableLazy`1.m_Value <a id="bosss.platform.expirablelazy`1.m_value"></a>
**Summary:** Value of the object, if it has been created yet


### Field: BoSSS.Platform.ExpirableLazy`1.valueFun <a id="bosss.platform.expirablelazy`1.valuefun"></a>
**Summary:** The function for the creation of the value upon access.


### Field: BoSSS.Platform.ExpirableLazy`1.isUpToDateFun <a id="bosss.platform.expirablelazy`1.isuptodatefun"></a>
**Summary:** The function that determines whether the represented value is
still up to date.


## Method: BoSSS.Platform.ExpirableLazy`1.#ctor(System.Func{`0},System.Func{`0,System.Boolean}) <a id="bosss.platform.expirablelazy`1.#ctor(system.func{`0},system.func{`0,system.boolean})"></a>
**Summary:** Constructs a wrapper for a lazy object.
**Parameter:** `valueFun` - The function for the creation of the value upon access.
**Parameter:** `isUpToDateFun` - The function that determines whether the represented value is
still up to date. If not, 'valueFun' will be
called again in order to update the represented
[BoSSS.Platform.ExpirableLazy`1.Value](#bosss.platform.expirablelazy`1.value)


### Property: BoSSS.Platform.ExpirableLazy`1.IsValueCreated <a id="bosss.platform.expirablelazy`1.isvaluecreated"></a>
**Summary:** Returns true if the value has already been created.


### Property: BoSSS.Platform.ExpirableLazy`1.Value <a id="bosss.platform.expirablelazy`1.value"></a>
**Summary:** Cached access to the lazy object.

## Class: BoSSS.Platform.Utils.Geom.BoundingBox <a id="bosss.platform.utils.geom.boundingbox"></a>

**Summary:** primitive bounding box


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.#ctor <a id="bosss.platform.utils.geom.boundingbox.#ctor"></a>
**Summary:** private ctor for serialization


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.#ctor(System.Int32) <a id="bosss.platform.utils.geom.boundingbox.#ctor(system.int32)"></a>
**Summary:** creates an empty bounding box
**Parameter:** `D` - dimension of the bounding box


### Property: BoSSS.Platform.Utils.Geom.BoundingBox.AspectRatio <a id="bosss.platform.utils.geom.boundingbox.aspectratio"></a>
**Summary:** the aspect ratio of the bounding box.


### Property: BoSSS.Platform.Utils.Geom.BoundingBox.Diameter <a id="bosss.platform.utils.geom.boundingbox.diameter"></a>
**Summary:** Distance between [BoSSS.Platform.Utils.Geom.BoundingBox.Min](#bosss.platform.utils.geom.boundingbox.min) and [BoSSS.Platform.Utils.Geom.BoundingBox.Max](#bosss.platform.utils.geom.boundingbox.max).


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.#ctor(System.Double[][]) <a id="bosss.platform.utils.geom.boundingbox.#ctor(system.double[][])"></a>
**Summary:** creates a box that contains a given cloud of points;
**Parameter:** `_points` -
cloud of points
- 1st index: point index;
- 2nd index: spatial coordinate;


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.#ctor(System.Double[0:,0:]) <a id="bosss.platform.utils.geom.boundingbox.#ctor(system.double[0:,0:])"></a>
**Summary:** Creates a box that contains a given cloud of points;
**Parameter:** `_points` -
cloud of points;
- 1st index: point index;
- 2nd index: spatial coordinate;


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.#ctor(ilPSP.MultidimensionalArray) <a id="bosss.platform.utils.geom.boundingbox.#ctor(ilpsp.multidimensionalarray)"></a>
**Summary:** Creates a box that contains a given cloud of points;
**Parameter:** `_points` -
cloud of points;
- 1st index: point index;
- 2nd index: spatial coordinate;


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.ExtendByFactor(System.Double) <a id="bosss.platform.utils.geom.boundingbox.extendbyfactor(system.double)"></a>
**Summary:** extends the bounding box by some factor into each direction
**Parameter:** `extFactor` - must be larger or equal to 0; a factor of 0 keeps the bounding box unchanged.


### Field: BoSSS.Platform.Utils.Geom.BoundingBox.Min <a id="bosss.platform.utils.geom.boundingbox.min"></a>
**Summary:** the lower bound of the bounding box


### Field: BoSSS.Platform.Utils.Geom.BoundingBox.Max <a id="bosss.platform.utils.geom.boundingbox.max"></a>
**Summary:** the upper bound of the bounding box


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.MPIsync(MPI.Wrappers.MPI_Comm) <a id="bosss.platform.utils.geom.boundingbox.mpisync(mpi.wrappers.mpi_comm)"></a>
**Summary:** takes minimum/maximum of [BoSSS.Platform.Utils.Geom.BoundingBox.Min](#bosss.platform.utils.geom.boundingbox.min)/[BoSSS.Platform.Utils.Geom.BoundingBox.Max](#bosss.platform.utils.geom.boundingbox.max) over all MPI processors in the communicator 'comm'


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.MPIsync <a id="bosss.platform.utils.geom.boundingbox.mpisync"></a>
**Summary:** takes minimum/maximum of [BoSSS.Platform.Utils.Geom.BoundingBox.Min](#bosss.platform.utils.geom.boundingbox.min)/[BoSSS.Platform.Utils.Geom.BoundingBox.Max](#bosss.platform.utils.geom.boundingbox.max) over all MPI processors in the world communicator


### Property: BoSSS.Platform.Utils.Geom.BoundingBox.h_min <a id="bosss.platform.utils.geom.boundingbox.h_min"></a>
**Summary:** Minimum witdh across all spatial dimensions.


### Property: BoSSS.Platform.Utils.Geom.BoundingBox.h_max <a id="bosss.platform.utils.geom.boundingbox.h_max"></a>
**Summary:** Maximum witdh across all spatial dimensions.


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.Clear <a id="bosss.platform.utils.geom.boundingbox.clear"></a>
**Summary:** Empties this box.


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.AddPoints(System.Double[0:,0:]) <a id="bosss.platform.utils.geom.boundingbox.addpoints(system.double[0:,0:])"></a>
**Summary:** Adds a list of points to this bounding box.


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.AddPoints(ilPSP.MultidimensionalArray) <a id="bosss.platform.utils.geom.boundingbox.addpoints(ilpsp.multidimensionalarray)"></a>
**Summary:** adds a list of points to this bounding box
**Parameter:** `_points` - 


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.AddPoint(System.Double[]) <a id="bosss.platform.utils.geom.boundingbox.addpoint(system.double[])"></a>
**Summary:** adds a point to the bounding box, i.e. enlarges it when the point is outside and does not change it
when the point is inside.


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.AddPoint(ilPSP.Vector) <a id="bosss.platform.utils.geom.boundingbox.addpoint(ilpsp.vector)"></a>
**Summary:** adds a point to the bounding box, i.e. enlarges it when the point is outside and does not change it
when the point is inside (3D - version);
**Parameter:** `pt` - 


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.AddBB(BoSSS.Platform.Utils.Geom.BoundingBox) <a id="bosss.platform.utils.geom.boundingbox.addbb(bosss.platform.utils.geom.boundingbox)"></a>
**Summary:** increases the size of this bounding box to contain the box 'other'


### Property: BoSSS.Platform.Utils.Geom.BoundingBox.IsEmpty <a id="bosss.platform.utils.geom.boundingbox.isempty"></a>
**Summary:** true if the volume of the bounding box is zero (in any measure of dimension higher or equal to 1)


### Property: BoSSS.Platform.Utils.Geom.BoundingBox.D <a id="bosss.platform.utils.geom.boundingbox.d"></a>
**Summary:** spatial dimension (length of [BoSSS.Platform.Utils.Geom.BoundingBox.Min](#bosss.platform.utils.geom.boundingbox.min), [BoSSS.Platform.Utils.Geom.BoundingBox.Max](#bosss.platform.utils.geom.boundingbox.max));


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.Contains(System.Double[]) <a id="bosss.platform.utils.geom.boundingbox.contains(system.double[])"></a>
**Summary:** tests whether a point is inside this bounding box or not


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.ContainsStrict(System.Double[]) <a id="bosss.platform.utils.geom.boundingbox.containsstrict(system.double[])"></a>
**Summary:** tests whether a point is inside this bounding box or not


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.Contains(BoSSS.Platform.Utils.Geom.BoundingBox) <a id="bosss.platform.utils.geom.boundingbox.contains(bosss.platform.utils.geom.boundingbox)"></a>
**Summary:** true, of the bounding box 'other' is fully contained in this box
**Parameter:** `other` - 
**Returns:**



## Method: BoSSS.Platform.Utils.Geom.BoundingBox.Clone <a id="bosss.platform.utils.geom.boundingbox.clone"></a>
**Summary:** creates a non-shallow copy of this bounding box


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.LeaveBoxFromCode(BoSSS.Platform.Utils.Geom.BoundingBox,BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.boundingbox.leaveboxfromcode(bosss.platform.utils.geom.boundingbox,bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** computes the leave bounding-box of a geometric binary tree
**Parameter:** `subBB` - on exit, the bounding box associated with the branch code 'code';
The output is not returned (via return value) to avoid heap allocation.
**Parameter:** `code` - branch code


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.SubBoxFromCode(BoSSS.Platform.Utils.Geom.BoundingBox,BoSSS.Platform.Utils.Geom.BoundingBoxCode) <a id="bosss.platform.utils.geom.boundingbox.subboxfromcode(bosss.platform.utils.geom.boundingbox,bosss.platform.utils.geom.boundingboxcode)"></a>
**Summary:** computes the leave bounding-box of a geometric binary tree
**Parameter:** `subBB` - on exit, the bounding box associated with the branch code 'bbCode';
The output is not returned (via return value) to avoid heap allocation.
**Parameter:** `bbCode` - bounding box code


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.Overlap(BoSSS.Platform.Utils.Geom.BoundingBox) <a id="bosss.platform.utils.geom.boundingbox.overlap(bosss.platform.utils.geom.boundingbox)"></a>
**Summary:** True, if this bounding box overlaps with another one.


## Method: BoSSS.Platform.Utils.Geom.BoundingBox.Distance(System.Double[]) <a id="bosss.platform.utils.geom.boundingbox.distance(system.double[])"></a>
**Summary:** finds the minimum distance of point 'pt' to the box;
**Parameter:** `pt` - 
**Returns:**


## Class: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode <a id="bosss.platform.utils.geom.geombintreebranchcode"></a>

**Summary:** This structure represents the so-called _branch code_ of a binary geometric tree:

We construct a binary geometric tree by cutting a bounding box symmetrically along the x-Axis,
then along the y-Axis, (then the z-Axis, if present), and again by x-Axis, y-Axis, ... 
The first cut corresponds with the most-significant bit (2^31, in integer representation) of [BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.Code](#bosss.platform.utils.geom.geombintreebranchcode.code), the second 
cut corresponds with the 2^30-bit, ...


### Field: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.Code <a id="bosss.platform.utils.geom.geombintreebranchcode.code"></a>
**Summary:** variable to store the branch code


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.CreateFormPoint(BoSSS.Platform.Utils.Geom.BoundingBox,System.Double[]) <a id="bosss.platform.utils.geom.geombintreebranchcode.createformpoint(bosss.platform.utils.geom.boundingbox,system.double[])"></a>
**Summary:** finds the branch (denoted by the branch code of the binary geometric tree) of some point
**Parameter:** `bb` - 
**Parameter:** `pt` - 
**Returns:**



## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.CompareTo(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.geombintreebranchcode.compareto(bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** compares the [BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.Code](#bosss.platform.utils.geom.geombintreebranchcode.code)


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.op_LessThan(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.geombintreebranchcode.op_lessthan(bosss.platform.utils.geom.geombintreebranchcode,bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** comparison operator


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.op_GreaterThan(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.geombintreebranchcode.op_greaterthan(bosss.platform.utils.geom.geombintreebranchcode,bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** comparison operator


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.op_LessThanOrEqual(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.geombintreebranchcode.op_lessthanorequal(bosss.platform.utils.geom.geombintreebranchcode,bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** comparison operator


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.op_GreaterThanOrEqual(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.geombintreebranchcode.op_greaterthanorequal(bosss.platform.utils.geom.geombintreebranchcode,bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** comparison operator


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.op_Equality(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.geombintreebranchcode.op_equality(bosss.platform.utils.geom.geombintreebranchcode,bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** comparison operator


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.op_Inequality(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.geombintreebranchcode.op_inequality(bosss.platform.utils.geom.geombintreebranchcode,bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** comparison operator


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.Equals(System.Object) <a id="bosss.platform.utils.geom.geombintreebranchcode.equals(system.object)"></a>
**Summary:** comparison operator


## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.Combine(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,System.Int32@) <a id="bosss.platform.utils.geom.geombintreebranchcode.combine(bosss.platform.utils.geom.geombintreebranchcode,bosss.platform.utils.geom.geombintreebranchcode,system.int32@)"></a>
**Parameter:** `a` - 
**Parameter:** `b` - 
**Parameter:** `commonBits` - on exit, the number of common branches in codes 'a' and 'b'
**Returns:**



## Method: BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode.GetHashCode <a id="bosss.platform.utils.geom.geombintreebranchcode.gethashcode"></a>
**Summary:** comparison operator

## Class: BoSSS.Platform.Utils.Geom.BoundingBoxCode <a id="bosss.platform.utils.geom.boundingboxcode"></a>

**Summary:** This represents the data that identifies a bounding box in a binary geometric tree;


### Field: BoSSS.Platform.Utils.Geom.BoundingBoxCode.Branch <a id="bosss.platform.utils.geom.boundingboxcode.branch"></a>
**Summary:** Branch code of the bounding box; only the last [BoSSS.Platform.Utils.Geom.BoundingBoxCode.SignificantBits](#bosss.platform.utils.geom.boundingboxcode.significantbits) bits are 
of interest (here, the last bit is the most significant one, i.e. the bit that corresponds with 2^31).


### Field: BoSSS.Platform.Utils.Geom.BoundingBoxCode.SignificantBits <a id="bosss.platform.utils.geom.boundingboxcode.significantbits"></a>
**Summary:** Number of subdivisions of the Root Bounding Box;
**Remark:**
number of significant bits of the branch code [BoSSS.Platform.Utils.Geom.BoundingBoxCode.Branch](#bosss.platform.utils.geom.boundingboxcode.branch); 
If this is 0, this structure represents the root box of the binary geometric tree.
If 1, the most significant bit of [BoSSS.Platform.Utils.Geom.BoundingBoxCode.Branch](#bosss.platform.utils.geom.boundingboxcode.branch) will be taken into account,
if 2, the two most significant bits of [BoSSS.Platform.Utils.Geom.BoundingBoxCode.Branch](#bosss.platform.utils.geom.boundingboxcode.branch) will be ...


## Method: BoSSS.Platform.Utils.Geom.BoundingBoxCode.GetBitMask <a id="bosss.platform.utils.geom.boundingboxcode.getbitmask"></a>
**Summary:** Returns the bitmask that marks the significant bits of the branch code [BoSSS.Platform.Utils.Geom.BoundingBoxCode.Branch](#bosss.platform.utils.geom.boundingboxcode.branch);


## Method: BoSSS.Platform.Utils.Geom.BoundingBoxCode.IsInside(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode) <a id="bosss.platform.utils.geom.boundingboxcode.isinside(bosss.platform.utils.geom.geombintreebranchcode)"></a>
**Summary:** true, if the branch notated by 'code' is contained in this box


## Method: BoSSS.Platform.Utils.Geom.BoundingBoxCode.IsInside(BoSSS.Platform.Utils.Geom.BoundingBoxCode) <a id="bosss.platform.utils.geom.boundingboxcode.isinside(bosss.platform.utils.geom.boundingboxcode)"></a>
**Summary:** true, if the box notated by 'code' is fully contained in this box


## Method: BoSSS.Platform.Utils.Geom.BoundingBoxCode.GetSubBox(System.Boolean) <a id="bosss.platform.utils.geom.boundingboxcode.getsubbox(system.boolean)"></a>
**Summary:** gets the code of either the 'left' or the 'right' sub-box of this box
**Parameter:** `leftOrRight` - if false, the 'left' branch, i.e. the box with lower coordinate values;
if false, the 'right' branch, i.e. the box with higher coordinate values;
**Returns:**


## Class: BoSSS.Platform.Utils.Geom.Rotation2D <a id="bosss.platform.utils.geom.rotation2d"></a>

**Summary:** 2D Rotation about the origin


## Method: BoSSS.Platform.Utils.Geom.Rotation2D.#ctor(System.Double) <a id="bosss.platform.utils.geom.rotation2d.#ctor(system.double)"></a>
**Summary:** Initializes the Rotation Matrix
**Parameter:** `phi` - 


## Method: BoSSS.Platform.Utils.Geom.Rotation2D.Transform(System.Double[]) <a id="bosss.platform.utils.geom.rotation2d.transform(system.double[])"></a>
**Summary:** Rotate the Coordinate
**Parameter:** `X` - input coordinate
**Returns:**
rotated coordinate


## Method: BoSSS.Platform.Utils.Geom.Rotation2D.Transform(System.Double[],System.Double) <a id="bosss.platform.utils.geom.rotation2d.transform(system.double[],system.double)"></a>
**Summary:** Rotate the Coordinate about the angle phi
**Parameter:** `X` - input coordinate
**Parameter:** `phi` - rotation angle
**Returns:**
rotated coordinate

## Class: BoSSS.Platform.Utils.Geom.SimpleGeoTools <a id="bosss.platform.utils.geom.simplegeotools"></a>

**Summary:** Various geometric utilities


## Method: BoSSS.Platform.Utils.Geom.SimpleGeoTools.CrossProduct2D(System.Double[],System.Double[]) <a id="bosss.platform.utils.geom.simplegeotools.crossproduct2d(system.double[],system.double[])"></a>
**Summary:** Calculates the cross product of two vectors in 2D
**Parameter:** `a` - 
**Parameter:** `b` - 
**Returns:**



## Method: BoSSS.Platform.Utils.Geom.SimpleGeoTools.DistanceFromPointToLine(System.Double[],System.Double[],System.Double[]) <a id="bosss.platform.utils.geom.simplegeotools.distancefrompointtoline(system.double[],system.double[],system.double[])"></a>
**Summary:** Calculates the shortest distance from a point to a line
**Parameter:** `X` - The point of interest
**Parameter:** `anyPointOnLine` - Any point on the line
**Parameter:** `directionVector` - Direction vector of the line
**Returns:**
Distance to the line


## Method: BoSSS.Platform.Utils.Geom.SimpleGeoTools.SmoothJump(System.Double,System.Double,System.Int32,System.Double) <a id="bosss.platform.utils.geom.simplegeotools.smoothjump(system.double,system.double,system.int32,system.double)"></a>
**Summary:** Smooths, e.g., an initial condition over the range h/p using a tanh profile
**Parameter:** `distance` - The distance to e.g. a shock
**Parameter:** `cellSize` - The cell size h
**Parameter:** `dgDegree` - The DG polynomial order
**Parameter:** `smoothingWidth` - Width of the smoothing
**Returns:**


## Class: BoSSS.Platform.Utils.Geom.PointLocalization <a id="bosss.platform.utils.geom.pointlocalization"></a>

**Summary:** This class constructs a binary geometrical tree (see [BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode](#bosss.platform.utils.geom.geombintreebranchcode))
from a cloud of points.


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.#ctor(ilPSP.MultidimensionalArray,System.Double,System.Int32[]) <a id="bosss.platform.utils.geom.pointlocalization.#ctor(ilpsp.multidimensionalarray,system.double,system.int32[])"></a>
**Summary:** Easy-to-use constructor.
**Parameter:** `_points` - a cloud of points
**Parameter:** `BoundingBoxExtensionFactor` - extends the bounding box of the points ([BoSSS.Platform.Utils.Geom.PointLocalization.PointsBB](#bosss.platform.utils.geom.pointlocalization.pointsbb)) by this factor (minimum is zero)
**Parameter:** `Permutation` - output; permutation of '_points' by sorting in tree; if null, an internal buffer is allocated


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.#ctor(ilPSP.MultidimensionalArray,BoSSS.Platform.Utils.Geom.BoundingBox,System.Int32[]) <a id="bosss.platform.utils.geom.pointlocalization.#ctor(ilpsp.multidimensionalarray,bosss.platform.utils.geom.boundingbox,system.int32[])"></a>
**Summary:** Expert's constructor.
**Parameter:** `_points` - 
**Parameter:** `BB` - predefined bounding box, must contain all points in '_points'
**Parameter:** `Permutation` - output; permutation of '_points' by sorting in tree; if null, an internal buffer is allocated


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.InitTree <a id="bosss.platform.utils.geom.pointlocalization.inittree"></a>
**Summary:** initializes **BoSSS.Platform.Utils.Geom.PointLocalization.__tree** on demand


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.VerifyRec(System.Int32,System.Int32,BoSSS.Platform.Utils.Geom.BoundingBoxCode,System.Int32) <a id="bosss.platform.utils.geom.pointlocalization.verifyrec(system.int32,system.int32,bosss.platform.utils.geom.boundingboxcode,system.int32)"></a>
**Summary:** only for debug/testing purpose; verifies if the tree is build correctly
**Parameter:** `i0` - for recursion start, set to 0
**Parameter:** `Len` - for recursion start, set to [BoSSS.Platform.Utils.Geom.PointLocalization.Codes](#bosss.platform.utils.geom.pointlocalization.codes).Length
**Parameter:** `cd` - for recursion start, set to default value of [BoSSS.Platform.Utils.Geom.BoundingBoxCode](#bosss.platform.utils.geom.boundingboxcode)
**Parameter:** `idx` - for recursion start, set to 0


### Field: BoSSS.Platform.Utils.Geom.PointLocalization.Points <a id="bosss.platform.utils.geom.pointlocalization.points"></a>
**Summary:** points, sorted according to their codes;

- 1st index: point index; 
- 2nd index: spatial coordinate;


### Field: BoSSS.Platform.Utils.Geom.PointLocalization.Codes <a id="bosss.platform.utils.geom.pointlocalization.codes"></a>
**Summary:** for each point in [BoSSS.Platform.Utils.Geom.PointLocalization.Points](#bosss.platform.utils.geom.pointlocalization.points), its branch code.


### Field: BoSSS.Platform.Utils.Geom.PointLocalization.PointsBB <a id="bosss.platform.utils.geom.pointlocalization.pointsbb"></a>
**Summary:** bounding box of all points, possibly extended a bit


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.FindNextPoint(ilPSP.Vector) <a id="bosss.platform.utils.geom.pointlocalization.findnextpoint(ilpsp.vector)"></a>
**Summary:** finds the next point out of [BoSSS.Platform.Utils.Geom.PointLocalization.Points](#bosss.platform.utils.geom.pointlocalization.points) to 'pt'.


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.FindNearPoints(System.Collections.Generic.ICollection{System.Int32},System.Double,System.Double[]) <a id="bosss.platform.utils.geom.pointlocalization.findnearpoints(system.collections.generic.icollection{system.int32},system.double,system.double[])"></a>
**Summary:** Finds all points (in [BoSSS.Platform.Utils.Geom.PointLocalization.Points](#bosss.platform.utils.geom.pointlocalization.points)) within
the radius 'eps' around point 'pt';
**Parameter:** `IndicesIntoPoints` - Output; on exit, the indices of all found points (1st index of [BoSSS.Platform.Utils.Geom.PointLocalization.Points](#bosss.platform.utils.geom.pointlocalization.points));
**Parameter:** `eps` - 
**Parameter:** `pt` - 


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.GetPointsInBranch(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,System.Int32,System.Int32@,System.Int32@) <a id="bosss.platform.utils.geom.pointlocalization.getpointsinbranch(bosss.platform.utils.geom.geombintreebranchcode,system.int32,system.int32@,system.int32@)"></a>
**Parameter:** `branchCode` - the branch code; only the bits 32 to 32-'BranchDepth' are taken into account
**Parameter:** `BranchDepth` - num
**Parameter:** `i0` - 
**Parameter:** `Len` - 


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.GetPointsInBranchRecursive(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,System.Int32,System.Int32@,System.Int32@,System.UInt32,System.Int32) <a id="bosss.platform.utils.geom.pointlocalization.getpointsinbranchrecursive(bosss.platform.utils.geom.geombintreebranchcode,system.int32,system.int32@,system.int32@,system.uint32,system.int32)"></a>
**Summary:** old implementation of [BoSSS.Platform.Utils.Geom.PointLocalization.GetPointsInBranch(BoSSS.Platform.Utils.Geom.GeomBinTreeBranchCode,System.Int32,System.Int32@,System.Int32@)](#bosss.platform.utils.geom.pointlocalization.getpointsinbranch(bosss.platform.utils.geom.geombintreebranchcode,system.int32,system.int32@,system.int32@))

## Class: BoSSS.Platform.Utils.Geom.PointLocalization.TreeNode <a id="bosss.platform.utils.geom.pointlocalization.treenode"></a>


### Field: BoSSS.Platform.Utils.Geom.PointLocalization.TreeNode.iMid <a id="bosss.platform.utils.geom.pointlocalization.treenode.imid"></a>
**Summary:** index into [BoSSS.Platform.Utils.Geom.PointLocalization.Points](#bosss.platform.utils.geom.pointlocalization.points) (1st index) and [BoSSS.Platform.Utils.Geom.PointLocalization.Codes](#bosss.platform.utils.geom.pointlocalization.codes) which separates the
'left' and 'right' tree branch


### Field: BoSSS.Platform.Utils.Geom.PointLocalization.TreeNode.Left <a id="bosss.platform.utils.geom.pointlocalization.treenode.left"></a>
**Summary:** index of 1st child in array (bit of corresponding level is 0)


### Field: BoSSS.Platform.Utils.Geom.PointLocalization.TreeNode.Right <a id="bosss.platform.utils.geom.pointlocalization.treenode.right"></a>
**Summary:** index of 2nd child in array (bit of corresponding level is 1)


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.TreeNode.CollectInArray(BoSSS.Platform.Utils.Geom.PointLocalization.TreeNodeTmp,BoSSS.Platform.Utils.Geom.PointLocalization.TreeNode[],System.Int32@) <a id="bosss.platform.utils.geom.pointlocalization.treenode.collectinarray(bosss.platform.utils.geom.pointlocalization.treenodetmp,bosss.platform.utils.geom.pointlocalization.treenode[],system.int32@)"></a>
**Summary:** converts a tree, represented as [BoSSS.Platform.Utils.Geom.PointLocalization.TreeNodeTmp](#bosss.platform.utils.geom.pointlocalization.treenodetmp) (heap objects)
into a compact array of value types
**Parameter:** `treeTmp` - 
**Parameter:** `targ` - 
**Parameter:** `cnt` - 

## Class: BoSSS.Platform.Utils.Geom.PointLocalization.TreeNodeTmp <a id="bosss.platform.utils.geom.pointlocalization.treenodetmp"></a>


## Method: BoSSS.Platform.Utils.Geom.PointLocalization.TreeNodeTmp.NoOfElements <a id="bosss.platform.utils.geom.pointlocalization.treenodetmp.noofelements"></a>
**Summary:** computes the total number of elements in the tree

## Class: BoSSS.Platform.GSL <a id="bosss.platform.gsl"></a>

**Summary:** Some parts of the GNU scientific library which are used by certain parts of BoSSS


## Method: BoSSS.Platform.GSL.gsl_sf_elljac_e(System.Double,System.Double,System.Double[],System.Double[],System.Double[]) <a id="bosss.platform.gsl.gsl_sf_elljac_e(system.double,system.double,system.double[],system.double[],system.double[])"></a>
**Summary:** Jacobian elliptic functions sn(u|m), cn(u|m), dn(u|m) (see
https://www.gnu.org/software/gsl/manual/html_node/Elliptic-Functions-_0028Jacobi_0029.html#Elliptic-Functions-_0028Jacobi_0029)
**Parameter:** `u` - Evaluation point
**Parameter:** `m` - Modulus of the elliptic function. Note that the definition of this
modulus is different from the Maple definition, for example, which
uses sqrt(m) instead.
**Parameter:** `sn` - Sinus of the Jacobi amplitude function
JacobiAM('u', 'm')
**Parameter:** `cn` - Co-sinus of the Jacobi amplitude function
JacobiAM('u', 'm')
**Parameter:** `dn` - Derivative of the Jacobi amplitude function
JacobiAM('u', 'm')
**Returns:**


## Class: BoSSS.Platform.PolygonTesselation <a id="bosss.platform.polygontesselation"></a>


## Method: BoSSS.Platform.PolygonTesselation.Sign(ilPSP.Vector,ilPSP.Vector,ilPSP.Vector) <a id="bosss.platform.polygontesselation.sign(ilpsp.vector,ilpsp.vector,ilpsp.vector)"></a>
**Parameter:** `p1` - 
**Parameter:** `p2` - 
**Parameter:** `p3` - 
**Returns:**



## Method: BoSSS.Platform.PolygonTesselation.PointInConvexPolygon(System.Collections.Generic.IEnumerable{ilPSP.Vector},ilPSP.Vector,System.Double) <a id="bosss.platform.polygontesselation.pointinconvexpolygon(system.collections.generic.ienumerable{ilpsp.vector},ilpsp.vector,system.double)"></a>
**Summary:** Includes points on edge of polygon.
**Parameter:** `_Polygon` - A positively oriented polygon
**Parameter:** `point` - 
**Parameter:** `accuracy` - 
**Returns:**


## Class: BoSSS.Platform.FloatingPointArithmetic <a id="bosss.platform.floatingpointarithmetic"></a>


## Method: BoSSS.Platform.FloatingPointArithmetic.IsEqual(System.Double,System.Double,System.Double,System.Double) <a id="bosss.platform.floatingpointarithmetic.isequal(system.double,system.double,system.double,system.double)"></a>
**Summary:** Checks for equality by using relative error


## Method: BoSSS.Platform.FloatingPointArithmetic.IsEqual(ilPSP.Vector,ilPSP.Vector,System.Double,System.Double) <a id="bosss.platform.floatingpointarithmetic.isequal(ilpsp.vector,ilpsp.vector,system.double,system.double)"></a>
**Summary:** Checks for equality by using relative error
**Parameter:** `a` - 
**Parameter:** `b` - 
**Parameter:** `accuracy` - 
**Parameter:** `zeroAccuracy` - 
**Returns:**


## Class: BoSSS.Platform.PolygonClipping <a id="bosss.platform.polygonclipping"></a>


## Method: BoSSS.Platform.PolygonClipping.ComputeIntersection(ilPSP.Vector,ilPSP.Vector,ilPSP.Vector,ilPSP.Vector,System.Double@,System.Double@,ilPSP.Vector@) <a id="bosss.platform.polygonclipping.computeintersection(ilpsp.vector,ilpsp.vector,ilpsp.vector,ilpsp.vector,system.double@,system.double@,ilpsp.vector@)"></a>
**Summary:** Intersection of line 'S1'--'S2' and 'E1'--'E2'
**Parameter:** `S1` - 
**Parameter:** `S2` - 
**Parameter:** `E1` - 
**Parameter:** `E2` - 
**Parameter:** `alpha1` - coordinate of 'I' on the line 'S1'--'S2'
**Parameter:** `alpha2` - coordinate of 'I' on the line 'E1'--'E2'
**Parameter:** `I` - 
**Returns:**


## Class: BoSSS.Platform.ObjectExtensions <a id="bosss.platform.objectextensions"></a>

**Summary:** Extension methods for **System.Object**


## Method: BoSSS.Platform.ObjectExtensions.Cast``1(System.Object) <a id="bosss.platform.objectextensions.cast``1(system.object)"></a>
**Summary:** Provides a more convenient syntax for cast operations.
**Parameter:** `obj` - The object to be casted
**Returns:**
The casted object


## Method: BoSSS.Platform.ObjectExtensions.As``1(System.Object) <a id="bosss.platform.objectextensions.as``1(system.object)"></a>
**Summary:** Provides a more convenient syntax for 'as' operations.
**Parameter:** `obj` - The object to be converted to
**Returns:**
The converted object


## Method: BoSSS.Platform.ObjectExtensions.IfNotNull``2(``0,System.Func{``0,``1}) <a id="bosss.platform.objectextensions.ifnotnull``2(``0,system.func{``0,``1})"></a>
**Summary:** Returns the result of 'function'('obj'),
if 'obj' is not null;
otherwise, the default value of .


## Method: BoSSS.Platform.ObjectExtensions.ToEnumerable``1(``0) <a id="bosss.platform.objectextensions.toenumerable``1(``0)"></a>
**Summary:** Turns a single element into something that is enumerable (i.e., no
array or something needs to be created by hand)
**Parameter:** `obj` - 
**Returns:**
A sequence containing 'obj' only.

## Class: BoSSS.Platform.ReferenceComparer <a id="bosss.platform.referencecomparer"></a>

**Summary:** Compares two objects for equality using reference comparison (see
**System.Object.ReferenceEquals(System.Object,System.Object)**)


### Field: BoSSS.Platform.ReferenceComparer.Instance <a id="bosss.platform.referencecomparer.instance"></a>
**Summary:** A static instance.


## Method: BoSSS.Platform.ReferenceComparer.Equals(System.Object,System.Object) <a id="bosss.platform.referencecomparer.equals(system.object,system.object)"></a>
**Summary:** See **System.Object.ReferenceEquals(System.Object,System.Object)**
**Parameter:** `x` - 
**Parameter:** `y` - 
**Returns:**



## Method: BoSSS.Platform.ReferenceComparer.GetHashCode(System.Object) <a id="bosss.platform.referencecomparer.gethashcode(system.object)"></a>
**Summary:** See **System.Object.GetHashCode**
**Parameter:** `obj` - 
**Returns:**


## Class: BoSSS.Platform.WeakReference`1 <a id="bosss.platform.weakreference`1"></a>

**Summary:** Implementation of **System.WeakReference** using generics.

**Remark:**
Adapted from
http://blogs.microsoft.co.il/blogs/pavely/archive/2011/06/04/a-proper-weakreference-class.aspx


### Field: BoSSS.Platform.WeakReference`1.m_Handle <a id="bosss.platform.weakreference`1.m_handle"></a>
**Summary:** Weak reference to the object.


## Method: BoSSS.Platform.WeakReference`1.#ctor(`0) <a id="bosss.platform.weakreference`1.#ctor(`0)"></a>
**Summary:** Constructs the weak reference.
**Parameter:** `referencedObject` - The object to be referenced weakly.


### Property: BoSSS.Platform.WeakReference`1.Target <a id="bosss.platform.weakreference`1.target"></a>
**Summary:** The referenced object if is still alive. Otherwise, null is
returned.


### Property: BoSSS.Platform.WeakReference`1.IsAlive <a id="bosss.platform.weakreference`1.isalive"></a>
**Summary:** True, if the referenced object has not yet been collected by the
garbage collector. False, otherwise.


## Method: BoSSS.Platform.WeakReference`1.Equals(BoSSS.Platform.WeakReference{`0}) <a id="bosss.platform.weakreference`1.equals(bosss.platform.weakreference{`0})"></a>
**Summary:** Checks whether this object is equal to the given object.
**Parameter:** `otherReference` - The reference in question.
**Returns:**
True, if the given object references the same object as this
object. False, otherwise.


## Method: BoSSS.Platform.WeakReference`1.Equals(System.Object) <a id="bosss.platform.weakreference`1.equals(system.object)"></a>
**Summary:** Checks whether this object is equal to the given object.
**Parameter:** `obj` - The object in question.
**Returns:**
True, if the given object is a weak reference referencing the same
object as this object. False, otherwise.


## Method: BoSSS.Platform.WeakReference`1.GetHashCode <a id="bosss.platform.weakreference`1.gethashcode"></a>
**Summary:** **System.Object.GetHashCode**
**Returns:**
The hash code of the referenced object.


## Method: BoSSS.Platform.WeakReference`1.Finalize <a id="bosss.platform.weakreference`1.finalize"></a>
**Summary:** Frees the reference to the referenced object.


## Method: BoSSS.Platform.WeakReference`1.op_Equality(BoSSS.Platform.WeakReference{`0},BoSSS.Platform.WeakReference{`0}) <a id="bosss.platform.weakreference`1.op_equality(bosss.platform.weakreference{`0},bosss.platform.weakreference{`0})"></a>
**Summary:** [BoSSS.Platform.WeakReference`1.Equals(BoSSS.Platform.WeakReference{`0})](#bosss.platform.weakreference`1.equals(bosss.platform.weakreference{`0}))


## Method: BoSSS.Platform.WeakReference`1.op_Inequality(BoSSS.Platform.WeakReference{`0},BoSSS.Platform.WeakReference{`0}) <a id="bosss.platform.weakreference`1.op_inequality(bosss.platform.weakreference{`0},bosss.platform.weakreference{`0})"></a>
**Summary:** not [BoSSS.Platform.WeakReference`1.Equals(BoSSS.Platform.WeakReference{`0})](#bosss.platform.weakreference`1.equals(bosss.platform.weakreference{`0}))
**Returns:**
The negation of the result of [BoSSS.Platform.WeakReference`1.Equals(BoSSS.Platform.WeakReference{`0})](#bosss.platform.weakreference`1.equals(bosss.platform.weakreference{`0})).


## Method: BoSSS.Platform.WeakReference`1.Dispose <a id="bosss.platform.weakreference`1.dispose"></a>
**Summary:** Frees the reference to the referenced object.

## Class: ilPSP.LinSolvers.BMext <a id="ilpsp.linsolvers.bmext"></a>

**Summary:** Extension functions for the [ilPSP.LinSolvers.BlockMsrMatrix](#ilpsp.linsolvers.blockmsrmatrix).


## Method: ilPSP.LinSolvers.BMext.GetSubMatrix``2(ilPSP.LinSolvers.BlockMsrMatrix,``0,``1) <a id="ilpsp.linsolvers.bmext.getsubmatrix``2(ilpsp.linsolvers.blockmsrmatrix,``0,``1)"></a>
**Summary:** Driver routine for [ilPSP.LinSolvers.BlockMsrMatrix.AccSubMatrixTo``4(System.Double,ilPSP.LinSolvers.IMutableMatrixEx,``0,``1,``2,``3)](#ilpsp.linsolvers.blockmsrmatrix.accsubmatrixto``4(system.double,ilpsp.linsolvers.imutablematrixex,``0,``1,``2,``3))


## Method: ilPSP.LinSolvers.BMext.GetSubMatrix``2(ilPSP.LinSolvers.BlockMsrMatrix,``0,``1,MPI.Wrappers.MPI_Comm) <a id="ilpsp.linsolvers.bmext.getsubmatrix``2(ilpsp.linsolvers.blockmsrmatrix,``0,``1,mpi.wrappers.mpi_comm)"></a>
**Summary:** Driver routine for [ilPSP.LinSolvers.BlockMsrMatrix.AccSubMatrixTo``4(System.Double,ilPSP.LinSolvers.IMutableMatrixEx,``0,``1,``2,``3)](#ilpsp.linsolvers.blockmsrmatrix.accsubmatrixto``4(system.double,ilpsp.linsolvers.imutablematrixex,``0,``1,``2,``3))


## Method: ilPSP.LinSolvers.BMext.ToBlockMsrMatrix(ilPSP.LinSolvers.IMutableMatrixEx,ilPSP.IBlockPartitioning,ilPSP.IBlockPartitioning) <a id="ilpsp.linsolvers.bmext.toblockmsrmatrix(ilpsp.linsolvers.imutablematrixex,ilpsp.iblockpartitioning,ilpsp.iblockpartitioning)"></a>
**Summary:** converts an arbitrary mutable matrix to an [ilPSP.LinSolvers.BlockMsrMatrix](#ilpsp.linsolvers.blockmsrmatrix).


## Method: ilPSP.LinSolvers.BMext.AccEyeSp(ilPSP.LinSolvers.BlockMsrMatrix,System.Double) <a id="ilpsp.linsolvers.bmext.acceyesp(ilpsp.linsolvers.blockmsrmatrix,system.double)"></a>
**Summary:** Adds 'factor' to all diagonal entries of 'M'.


## Method: ilPSP.LinSolvers.BMext.GetBlock(ilPSP.LinSolvers.BlockMsrMatrix,System.Int64,System.Int64) <a id="ilpsp.linsolvers.bmext.getblock(ilpsp.linsolvers.blockmsrmatrix,system.int64,system.int64)"></a>
**Summary:** Extraction of a block from a [ilPSP.LinSolvers.BlockMsrMatrix](#ilpsp.linsolvers.blockmsrmatrix);

This is a convenience routine, which
causes memory allocation, and therefore impacts performance slightly negatively.
For best performance, use [ilPSP.LinSolvers.BlockMsrMatrix.ReadBlock(System.Int64,System.Int64,ilPSP.MultidimensionalArray)](#ilpsp.linsolvers.blockmsrmatrix.readblock(system.int64,system.int64,ilpsp.multidimensionalarray)) instead.


## Method: ilPSP.LinSolvers.BMext.SetBlock(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.MultidimensionalArray,System.Int64,System.Int64) <a id="ilpsp.linsolvers.bmext.setblock(ilpsp.linsolvers.blockmsrmatrix,ilpsp.multidimensionalarray,system.int64,system.int64)"></a>
**Summary:** Setting a block from a [ilPSP.LinSolvers.BlockMsrMatrix](#ilpsp.linsolvers.blockmsrmatrix);

This is a convenience routine, which
causes memory allocation, and therefore impacts performance slightly negatively.
For best performance, use [ilPSP.LinSolvers.BlockMsrMatrix.AccBlock(System.Int64,System.Int64,System.Double,ilPSP.MultidimensionalArray,System.Double)](#ilpsp.linsolvers.blockmsrmatrix.accblock(system.int64,system.int64,system.double,ilpsp.multidimensionalarray,system.double)) instead.

## Class: ilPSP.LinSolvers.BlockMsrMatrix <a id="ilpsp.linsolvers.blockmsrmatrix"></a>

**Summary:** Class for sparse matrices - it is mutable and used during equation
assembly. When the system of equations is complete, this object can be
handed over to an **ilPSP.LinSolvers.ISparseSolver** - implementation that
solves the system. For performance reasons, this solver typically will
convert this matrix into his internal format.
This matrix is addressed by global row/column indices;

**Remark:**
MSR stands for 'M'utuble 'S'parse 'R'ow;


### Property: ilPSP.LinSolvers.BlockMsrMatrix.MPI_Comm <a id="ilpsp.linsolvers.blockmsrmatrix.mpi_comm"></a>
**Summary:** MPI Communicator on which this object lives on


### Field: ilPSP.LinSolvers.BlockMsrMatrix.m_RowPartitioning <a id="ilpsp.linsolvers.blockmsrmatrix.m_rowpartitioning"></a>
**Summary:** [ilPSP.LinSolvers.BlockMsrMatrix.RowPartitioning](#ilpsp.linsolvers.blockmsrmatrix.rowpartitioning);


### Property: ilPSP.LinSolvers.BlockMsrMatrix._RowPartitioning <a id="ilpsp.linsolvers.blockmsrmatrix._rowpartitioning"></a>
**Summary:** distribution of matrix rows over MPI processors


### Field: ilPSP.LinSolvers.BlockMsrMatrix.m_ColPartitioning <a id="ilpsp.linsolvers.blockmsrmatrix.m_colpartitioning"></a>
**Summary:** [ilPSP.LinSolvers.BlockMsrMatrix.RowPartitioning](#ilpsp.linsolvers.blockmsrmatrix.rowpartitioning);


### Property: ilPSP.LinSolvers.BlockMsrMatrix._ColPartitioning <a id="ilpsp.linsolvers.blockmsrmatrix._colpartitioning"></a>
**Summary:** distribution of matrix rows over MPI processors


### Property: ilPSP.LinSolvers.BlockMsrMatrix.RowPartitioning <a id="ilpsp.linsolvers.blockmsrmatrix.rowpartitioning"></a>
**Summary:** distribution of matrix rows over MPI processors


### Property: ilPSP.LinSolvers.BlockMsrMatrix.ColPartition <a id="ilpsp.linsolvers.blockmsrmatrix.colpartition"></a>
**Summary:** distribution of matrix rows over MPI processors


## Method: ilPSP.LinSolvers.BlockMsrMatrix.#ctor(ilPSP.IBlockPartitioning) <a id="ilpsp.linsolvers.blockmsrmatrix.#ctor(ilpsp.iblockpartitioning)"></a>
**Summary:** Constructor for a quadratic matrix.
**Parameter:** `Part` - Used for [ilPSP.LinSolvers.BlockMsrMatrix._RowPartitioning](#ilpsp.linsolvers.blockmsrmatrix._rowpartitioning) and [ilPSP.LinSolvers.BlockMsrMatrix._ColPartitioning](#ilpsp.linsolvers.blockmsrmatrix._colpartitioning).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.#ctor(ilPSP.IBlockPartitioning,ilPSP.IBlockPartitioning) <a id="ilpsp.linsolvers.blockmsrmatrix.#ctor(ilpsp.iblockpartitioning,ilpsp.iblockpartitioning)"></a>
**Summary:** Constructor for a quadratic or rectangular matrix.
**Parameter:** `rowPart` - See [ilPSP.LinSolvers.BlockMsrMatrix._RowPartitioning](#ilpsp.linsolvers.blockmsrmatrix._rowpartitioning).
**Parameter:** `colPart` - See [ilPSP.LinSolvers.BlockMsrMatrix._ColPartitioning](#ilpsp.linsolvers.blockmsrmatrix._colpartitioning).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.#ctor <a id="ilpsp.linsolvers.blockmsrmatrix.#ctor"></a>
**Summary:** private/empty constructor.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.RecyclePermute(ilPSP.IBlockPartitioning,ilPSP.IBlockPartitioning,System.Int64[0:,0:],System.Int64[0:,0:]) <a id="ilpsp.linsolvers.blockmsrmatrix.recyclepermute(ilpsp.iblockpartitioning,ilpsp.iblockpartitioning,system.int64[0:,0:],system.int64[0:,0:])"></a>
**Summary:** A utility function to aid the XDG moving interface time-stepper, 
i.e. the application of a row- and column permutation which is local to certain blocks.
The memory of the actual matrix is 'recycled' i.e. unchanged rows are copied shallow. 
After this operation, this matrix becomes unusable.
**Parameter:** `OldColIndices2New` - 
**Parameter:** `OldRowIndices2New` - 
**Parameter:** `newColPart` - Column blocking for the returned matrix.
**Parameter:** `newRowPart` - Row blocking for the returned matrix.
**Returns:**

**Remark:**
Since this is a very special-purpose function, which is only useful for the XDG moving interface time-stepper, it is questionable
to put it here; on the other hand, we need to access tons of private members to be efficient, 
therefore it is difficult to implement this method in some other place.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.m_BlockRows <a id="ilpsp.linsolvers.blockmsrmatrix.m_blockrows"></a>
**Summary:** - array index: local block row
- dictionary key: block column
- dictionary value: a block entry, [ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.jBlkCol](#ilpsp.linsolvers.blockmsrmatrix.blockentry.jblkcol) equals the key.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.m_ExternalBlock <a id="ilpsp.linsolvers.blockmsrmatrix.m_externalblock"></a>
**Summary:** Marker for rows with blocks/entries in the external range of the [ilPSP.LinSolvers.BlockMsrMatrix._ColPartitioning](#ilpsp.linsolvers.blockmsrmatrix._colpartitioning).
- index: local block row.
- value: true if the row contains an external block.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.m_ExternalBlockIndicesByProcessor <a id="ilpsp.linsolvers.blockmsrmatrix.m_externalblockindicesbyprocessor"></a>
**Summary:** Tracking of external blocks, i.e. blocks outside of the local range of the column partitioning.
- key: MPI processor rank (within [ilPSP.LinSolvers.BlockMsrMatrix.MPI_Comm](#ilpsp.linsolvers.blockmsrmatrix.mpi_comm))
- value: set of block indices which are owned by the respective processor.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.ComPatternValid <a id="ilpsp.linsolvers.blockmsrmatrix.compatternvalid"></a>
**Summary:** Flag which indicates that [ilPSP.LinSolvers.BlockMsrMatrix.ReceiveLists](#ilpsp.linsolvers.blockmsrmatrix.receivelists) resp. [ilPSP.LinSolvers.BlockMsrMatrix.SendLists](#ilpsp.linsolvers.blockmsrmatrix.sendlists) contains valid data.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.ReceiveLists <a id="ilpsp.linsolvers.blockmsrmatrix.receivelists"></a>
**Summary:** - key: MPI processor rank within the [ilPSP.LinSolvers.BlockMsrMatrix.MPI_Comm](#ilpsp.linsolvers.blockmsrmatrix.mpi_comm) communicator
- value: index ranges which are received from respective processor.
- 0th index into value:
- 1st index into value: either 0 (start of index range) or 1 (end of index range)


### Field: ilPSP.LinSolvers.BlockMsrMatrix.SendLists <a id="ilpsp.linsolvers.blockmsrmatrix.sendlists"></a>
**Summary:** - key: MPI processor rank within the [ilPSP.LinSolvers.BlockMsrMatrix.MPI_Comm](#ilpsp.linsolvers.blockmsrmatrix.mpi_comm) communicator
- value: index ranges which have to be sent to other processor


## Method: ilPSP.LinSolvers.BlockMsrMatrix.UpdateCommPattern(MPI.Wrappers.MPI_Comm) <a id="ilpsp.linsolvers.blockmsrmatrix.updatecommpattern(mpi.wrappers.mpi_comm)"></a>
**Summary:** Update of [ilPSP.LinSolvers.BlockMsrMatrix.ReceiveLists](#ilpsp.linsolvers.blockmsrmatrix.receivelists) and [ilPSP.LinSolvers.BlockMsrMatrix.SendLists](#ilpsp.linsolvers.blockmsrmatrix.sendlists)

## Class: ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry <a id="ilpsp.linsolvers.blockmsrmatrix.blockentry"></a>

**Summary:** Pointers/indices for a matrix block into the memory bank.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.jBlkCol <a id="ilpsp.linsolvers.blockmsrmatrix.blockentry.jblkcol"></a>
**Summary:** Block-column index.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.MembnkIdx <a id="ilpsp.linsolvers.blockmsrmatrix.blockentry.membnkidx"></a>
**Summary:** Memory bank index.
- 1st index: sub-block row 
- 2nd index: sub-block column
- content: index into [ilPSP.LinSolvers.BlockMsrMatrix.m_Membanks](#ilpsp.linsolvers.blockmsrmatrix.m_membanks).


### Field: ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.InMembnk <a id="ilpsp.linsolvers.blockmsrmatrix.blockentry.inmembnk"></a>
**Summary:** Block index within memory bank
- 1st index: sub-block row 
- 2nd index: sub-block column
- content: 1st index into [ilPSP.LinSolvers.BlockMsrMatrix.Membank.Mem](#ilpsp.linsolvers.blockmsrmatrix.membank.mem).


### Property: ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.IsEmpty <a id="ilpsp.linsolvers.blockmsrmatrix.blockentry.isempty"></a>
**Summary:** True, if all entries in [ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.MembnkIdx](#ilpsp.linsolvers.blockmsrmatrix.blockentry.membnkidx) and [ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.InMembnk](#ilpsp.linsolvers.blockmsrmatrix.blockentry.inmembnk) are negative.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.Clone <a id="ilpsp.linsolvers.blockmsrmatrix.blockentry.clone"></a>
**Summary:** Cloning.


### Property: ilPSP.LinSolvers.BlockMsrMatrix.Item(System.Int64,System.Int64) <a id="ilpsp.linsolvers.blockmsrmatrix.item(system.int64,system.int64)"></a>
**Summary:** get/set an entry; Setting a zero element (to a value unequal to zero)
allocates a new entry; Setting an entry to 0.0 releases the
corresponding memory;
**Remark:**
Note that setting entries to 0.0 does not releases memory, if memory for the entry was allocated before.
In the block-matrix structure, this would cause to much overhead.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.AccBlock(System.Int64,System.Int64,System.Double,ilPSP.MultidimensionalArray) <a id="ilpsp.linsolvers.blockmsrmatrix.accblock(system.int64,system.int64,system.double,ilpsp.multidimensionalarray)"></a>
**Summary:** Accumulates 'Block'*'alpha' to this matrix,
at the row/column offset 'i0' resp. 'j0'.
**Parameter:** `i0` - Row offset.
**Parameter:** `j0` - Column offset.
**Parameter:** `alpha` - Scaling factor for the accumulation operation.
**Parameter:** `Block` - Block to accumulate.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.AccBlock(System.Int64,System.Int64,System.Double,ilPSP.MultidimensionalArray,System.Double) <a id="ilpsp.linsolvers.blockmsrmatrix.accblock(system.int64,system.int64,system.double,ilpsp.multidimensionalarray,system.double)"></a>
**Summary:** Accumulates 'Block'*'alpha' to this matrix,
at the row/column offset 'i0' resp. 'j0'.
**Parameter:** `i0` - Row offset.
**Parameter:** `j0` - Column offset.
**Parameter:** `alpha` - Scaling factor for the accumulation operation.
**Parameter:** `Block` - Block to accumulate.
**Parameter:** `beta` - Scaling applied to this matrix before accumulation;
Note: if set to 0.0, this will also clear NAN's, etc.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.ReadBlock(System.Int64,System.Int64,ilPSP.MultidimensionalArray) <a id="ilpsp.linsolvers.blockmsrmatrix.readblock(system.int64,system.int64,ilpsp.multidimensionalarray)"></a>
**Summary:** Extracts a block from this matrix and stores it into 'Block'.
**Parameter:** `i0` - Row index to start reading form.
**Parameter:** `j0` - Column index to start reading form.
**Parameter:** `Block` - Output; allocated by caller.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.ClearBlock(System.Int64,System.Int64,System.Int32,System.Int32) <a id="ilpsp.linsolvers.blockmsrmatrix.clearblock(system.int64,system.int64,system.int32,system.int32)"></a>
**Summary:** Clears a block in this matrix and frees the allocated memory.
**Parameter:** `i0` - Row index to start clearing.
**Parameter:** `j0` - Column index to start clearing.
**Parameter:** `I` - Number of rows to clear.
**Parameter:** `J` - Number of columns to clear.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.TranslateIndex(System.Int64,ilPSP.IBlockPartitioning,System.Boolean,System.Int64@,System.Int32@,System.Int64@,System.Int32@,System.Int32@,System.Int32@,System.Int32@,System.Int32@,System.Int32@,System.Int32@) <a id="ilpsp.linsolvers.blockmsrmatrix.translateindex(system.int64,ilpsp.iblockpartitioning,system.boolean,system.int64@,system.int32@,system.int64@,system.int32@,system.int32@,system.int32@,system.int32@,system.int32@,system.int32@,system.int32@)"></a>
**Summary:** Computes all kinds of indices from a global index.
**Parameter:** `i` - Row or column index.
**Parameter:** `part` - Partitioning.
**Parameter:** `SupportExternal` - If true, 'i' can be outside of the range of local indices of 'part'.
**Parameter:** `iBlk` - On exit, global (over all MPI processes) block index.
**Parameter:** `iBlkLoc` - On exit, local (on this MPI process) block index.
**Parameter:** `i0` - Global start index of the block
**Parameter:** `iLoc` - Index within block.
**Parameter:** `BlkT` - Block type, see **ilPSP.IBlockPartitioning.GetBlockType(System.Int64)**
**Parameter:** `Sblk_idx` - Sub block index.
**Parameter:** `i0_Sblk` - First block index in sub block.
**Parameter:** `ISblk` - Size/length of sub block
**Parameter:** `NoOfSblk` - Number of sub blocks in block.
**Parameter:** `RemainingVoidWidth` - If in void region ('i0_Sblk' smaller than 0), the distance to the next sub-block or the end of the block.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetExternalSubblockIndices(ilPSP.IBlockPartitioning,System.Int64,System.Int64@,System.Int64@) <a id="ilpsp.linsolvers.blockmsrmatrix.getexternalsubblockindices(ilpsp.iblockpartitioning,system.int64,system.int64@,system.int64@)"></a>
**Summary:** Computes the blocking for external indices (outside of the local range, i.e. smaller than **ilPSP.IPartitioning.i0** or larger or equal to **ilPSP.IPartitioning.iE**).
**Parameter:** `part` - 
**Parameter:** `iBlk` - Input; an external block index.
**Parameter:** `i0` - first index of the block
**Parameter:** `iE` - first index of the next block
**Returns:**
owner rank of the external sub-block


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetExternalSubblockIndices(ilPSP.IBlockPartitioning,System.Int64,System.Int64@,System.Int64@,System.Int64@) <a id="ilpsp.linsolvers.blockmsrmatrix.getexternalsubblockindices(ilpsp.iblockpartitioning,system.int64,system.int64@,system.int64@,system.int64@)"></a>
**Summary:** Computes the blocking for external indices (outside of the local range, i.e. smaller than **ilPSP.IPartitioning.i0** or larger or equal to **ilPSP.IPartitioning.iE**).
**Parameter:** `part` - 
**Parameter:** `i` - Input; an external index
**Parameter:** `iBlk` - block index
**Parameter:** `i0` - first index of the block
**Parameter:** `iE` - last index of the block


## Method: ilPSP.LinSolvers.BlockMsrMatrix.AllocSblk(ilPSP.LinSolvers.BlockMsrMatrix.Membank@,System.Int32@,System.Int32@,System.Int32,System.Int32) <a id="ilpsp.linsolvers.blockmsrmatrix.allocsblk(ilpsp.linsolvers.blockmsrmatrix.membank@,system.int32@,system.int32@,system.int32,system.int32)"></a>
**Summary:** Allocates memory for a sub block.
**Parameter:** `B` - On exit, the memory bank at which the sub block was allocated.
**Parameter:** `ISblk` - Number of rows for sub block.
**Parameter:** `JSblk` - Number of columns for sub block.
**Parameter:** `MembnkIdx` - Memory bank index, see [ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.MembnkIdx](#ilpsp.linsolvers.blockmsrmatrix.blockentry.membnkidx).
**Parameter:** `InMembnk` - Block index within memory bank, 
i.e. first index into [ilPSP.LinSolvers.BlockMsrMatrix.Membank.Mem](#ilpsp.linsolvers.blockmsrmatrix.membank.mem), see [ilPSP.LinSolvers.BlockMsrMatrix.BlockEntry.InMembnk](#ilpsp.linsolvers.blockmsrmatrix.blockentry.inmembnk).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.FreeSblk(System.Int32,System.Int32) <a id="ilpsp.linsolvers.blockmsrmatrix.freesblk(system.int32,system.int32)"></a>
**Summary:** Releases a sub-block.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetRow(System.Int64,System.Int64[]@,System.Double[]@) <a id="ilpsp.linsolvers.blockmsrmatrix.getrow(system.int64,system.int64[]@,system.double[]@)"></a>
**Summary:** see **ilPSP.LinSolvers.IMutableMatrixEx.GetOccupiedColumnIndices(System.Int64,System.Int64[]@)**;
the returned array is a non-shallow copy of the row;


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetRowInternal(System.Int64,System.Int64[]@,System.Double[]@,System.Boolean) <a id="ilpsp.linsolvers.blockmsrmatrix.getrowinternal(system.int64,system.int64[]@,system.double[]@,system.boolean)"></a>
**Summary:** Common implementation for [ilPSP.LinSolvers.BlockMsrMatrix.GetRow(System.Int64,System.Int64[]@,System.Double[]@)](#ilpsp.linsolvers.blockmsrmatrix.getrow(system.int64,system.int64[]@,system.double[]@)) and [ilPSP.LinSolvers.BlockMsrMatrix.GetOccupiedColumnIndices(System.Int64,System.Int64[]@)](#ilpsp.linsolvers.blockmsrmatrix.getoccupiedcolumnindices(system.int64,system.int64[]@)).


### Field: ilPSP.LinSolvers.BlockMsrMatrix.m_Membanks <a id="ilpsp.linsolvers.blockmsrmatrix.m_membanks"></a>
**Summary:** All stores sub-blocks.

## Class: ilPSP.LinSolvers.BlockMsrMatrix.Membank <a id="ilpsp.linsolvers.blockmsrmatrix.membank"></a>

**Summary:** Memory bank, stores sub-blocks of equal size,


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Membank.#ctor(System.Int32,System.Int32,System.Int32) <a id="ilpsp.linsolvers.blockmsrmatrix.membank.#ctor(system.int32,system.int32,system.int32)"></a>
**Summary:** ctor.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.Membank.Mem <a id="ilpsp.linsolvers.blockmsrmatrix.membank.mem"></a>
**Summary:** Storage to store sub-blocks.
- 1st index: enumeration of sub-blocks
- 2nd index: sub-block row index
- 3rd index: sub-block column index.


### Property: ilPSP.LinSolvers.BlockMsrMatrix.Membank.SubblockNoRows <a id="ilpsp.linsolvers.blockmsrmatrix.membank.subblocknorows"></a>
**Summary:** Number of rows in each sub-block


### Property: ilPSP.LinSolvers.BlockMsrMatrix.Membank.SubblockNoCols <a id="ilpsp.linsolvers.blockmsrmatrix.membank.subblocknocols"></a>
**Summary:** Number of columns in each sub-block


### Field: ilPSP.LinSolvers.BlockMsrMatrix.Membank.Occupied <a id="ilpsp.linsolvers.blockmsrmatrix.membank.occupied"></a>
**Summary:** Marks which parts of [ilPSP.LinSolvers.BlockMsrMatrix.Membank.Mem](#ilpsp.linsolvers.blockmsrmatrix.membank.mem) are occupied (true).
Index correlates with first index of [ilPSP.LinSolvers.BlockMsrMatrix.Membank.Mem](#ilpsp.linsolvers.blockmsrmatrix.membank.mem),


### Field: ilPSP.LinSolvers.BlockMsrMatrix.Membank.NextFree <a id="ilpsp.linsolvers.blockmsrmatrix.membank.nextfree"></a>
**Summary:** First free entry in [ilPSP.LinSolvers.BlockMsrMatrix.Membank.Mem](#ilpsp.linsolvers.blockmsrmatrix.membank.mem), correlates with first index of [ilPSP.LinSolvers.BlockMsrMatrix.Membank.Mem](#ilpsp.linsolvers.blockmsrmatrix.membank.mem).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Membank.GetFastBlockAccessInfo(System.Double[]@,System.Int32@,System.Int32@,System.Int32@,System.Boolean@,System.Int32) <a id="ilpsp.linsolvers.blockmsrmatrix.membank.getfastblockaccessinfo(system.double[]@,system.int32@,system.int32@,system.int32@,system.boolean@,system.int32)"></a>
**Parameter:** `RawMem` - 
**Parameter:** `Offset` - 
**Parameter:** `CI` - Cycle for advancing the row index.
**Parameter:** `CJ` - Cycle for advancing the column index.
**Parameter:** `isDense` - 
**Parameter:** `InMembnk` - Memory bank index, i.e. first index into [ilPSP.LinSolvers.BlockMsrMatrix.Membank.Mem](#ilpsp.linsolvers.blockmsrmatrix.membank.mem).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Membank.Clone <a id="ilpsp.linsolvers.blockmsrmatrix.membank.clone"></a>
**Summary:** Cloning.


### Property: ilPSP.LinSolvers.BlockMsrMatrix.AssumeSymmetric <a id="ilpsp.linsolvers.blockmsrmatrix.assumesymmetric"></a>
**Summary:** A flag which indicates that a solver can assume this matrix to be symmetric;
For performance reasons, we rely on the user to set this correctly (checking
for symmetry is very expensive even on one pro


## Method: ilPSP.LinSolvers.BlockMsrMatrix.CloneAs <a id="ilpsp.linsolvers.blockmsrmatrix.cloneas"></a>
**Summary:** creates a non-shallow copy of this object


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Clone <a id="ilpsp.linsolvers.blockmsrmatrix.clone"></a>
**Summary:** creates a non-shallow copy of this object


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Clear <a id="ilpsp.linsolvers.blockmsrmatrix.clear"></a>
**Summary:** Sets all entries to 0, all memory is released.


### Property: ilPSP.LinSolvers.BlockMsrMatrix.UsedMemory <a id="ilpsp.linsolvers.blockmsrmatrix.usedmemory"></a>
**Summary:** Number of Bytes used


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetMemoryInfo(System.Int64@,System.Int64@) <a id="ilpsp.linsolvers.blockmsrmatrix.getmemoryinfo(system.int64@,system.int64@)"></a>
**Summary:** Computes the amount of memory allocated resp. used by this matrix.
**Parameter:** `Allocated` - Allocated memory, in bytes
**Parameter:** `Used` - Actually used memory (always smaller or equal to 'Allocated') memory.


### Field: ilPSP.LinSolvers.BlockMsrMatrix.SPMV_tot <a id="ilpsp.linsolvers.blockmsrmatrix.spmv_tot"></a>
**Summary:** Ad-hoc performance instrumentation


### Field: ilPSP.LinSolvers.BlockMsrMatrix.SpMV_local <a id="ilpsp.linsolvers.blockmsrmatrix.spmv_local"></a>
**Summary:** Ad-hoc performance instrumentation


### Field: ilPSP.LinSolvers.BlockMsrMatrix.SpMV_initSending <a id="ilpsp.linsolvers.blockmsrmatrix.spmv_initsending"></a>
**Summary:** Ad-hoc performance instrumentation


### Field: ilPSP.LinSolvers.BlockMsrMatrix.SpMV_receive <a id="ilpsp.linsolvers.blockmsrmatrix.spmv_receive"></a>
**Summary:** Ad-hoc performance instrumentation


### Field: ilPSP.LinSolvers.BlockMsrMatrix.SpMV_external <a id="ilpsp.linsolvers.blockmsrmatrix.spmv_external"></a>
**Summary:** Ad-hoc performance instrumentation


### Field: ilPSP.LinSolvers.BlockMsrMatrix.SpMV_indextrans <a id="ilpsp.linsolvers.blockmsrmatrix.spmv_indextrans"></a>
**Summary:** Ad-hoc performance instrumentation


## Method: ilPSP.LinSolvers.BlockMsrMatrix.PerfStatToString <a id="ilpsp.linsolvers.blockmsrmatrix.perfstattostring"></a>
**Summary:** Write the ad-hoc instrumentation to Console


## Method: ilPSP.LinSolvers.BlockMsrMatrix.ResetPerfStat <a id="ilpsp.linsolvers.blockmsrmatrix.resetperfstat"></a>
**Summary:** resets performance stopwatches
**Returns:**



## Method: ilPSP.LinSolvers.BlockMsrMatrix.PrintPerfStat <a id="ilpsp.linsolvers.blockmsrmatrix.printperfstat"></a>
**Summary:** Write the ad-hoc instrumentation to Console


## Method: ilPSP.LinSolvers.BlockMsrMatrix.SpMV``2(System.Double,``0,System.Double,``1) <a id="ilpsp.linsolvers.blockmsrmatrix.spmv``2(system.double,``0,system.double,``1)"></a>
**Summary:** Sparse Matrix/Vector multiplication;
the calculation 
'acc' = 'acc'*'beta' + this*'_a'*'alpha'
is performed;
**Parameter:** `alpha` - 
**Parameter:** `_a` - input; vector to be multiplied with this matrix from the right
**Parameter:** `beta` - 
**Parameter:** `acc` - length of accumulator must be at least the update length


## Method: ilPSP.LinSolvers.BlockMsrMatrix.VerifyDataStructure(System.String) <a id="ilpsp.linsolvers.blockmsrmatrix.verifydatastructure(system.string)"></a>
**Summary:** Tests the integrity of the block matrix data structure.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.WriteSubMatrixTo``4(ilPSP.LinSolvers.IMutableMatrixEx,``0,``1,``2,``3) <a id="ilpsp.linsolvers.blockmsrmatrix.writesubmatrixto``4(ilpsp.linsolvers.imutablematrixex,``0,``1,``2,``3)"></a>
**Summary:** Similar to [ilPSP.LinSolvers.BlockMsrMatrix.AccSubMatrixTo``4(System.Double,ilPSP.LinSolvers.IMutableMatrixEx,``0,``1,``2,``3)](#ilpsp.linsolvers.blockmsrmatrix.accsubmatrixto``4(system.double,ilpsp.linsolvers.imutablematrixex,``0,``1,``2,``3)), 
but the destination ('target') is cleared before the accumulation.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.AccSubMatrixTo``4(System.Double,ilPSP.LinSolvers.IMutableMatrixEx,``0,``1,``2,``3) <a id="ilpsp.linsolvers.blockmsrmatrix.accsubmatrixto``4(system.double,ilpsp.linsolvers.imutablematrixex,``0,``1,``2,``3)"></a>
**Summary:** See [ilPSP.LinSolvers.BlockMsrMatrix.AccSubMatrixTo``6(System.Double,ilPSP.LinSolvers.IMutableMatrixEx,``0,``1,``2,``3,``4,``5)](#ilpsp.linsolvers.blockmsrmatrix.accsubmatrixto``6(system.double,ilpsp.linsolvers.imutablematrixex,``0,``1,``2,``3,``4,``5)), with less paramters.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.AccSubMatrixTo``6(System.Double,ilPSP.LinSolvers.IMutableMatrixEx,``0,``1,``2,``3,``4,``5) <a id="ilpsp.linsolvers.blockmsrmatrix.accsubmatrixto``6(system.double,ilpsp.linsolvers.imutablematrixex,``0,``1,``2,``3,``4,``5)"></a>
**Summary:** Extracts a submatrix from this matrix and accumulates it to another matrix.
**Parameter:** `alpha` - scaling factor
**Parameter:** `RowIndicesSource` - Row indices into this matrix, in the local range (**ilPSP.IPartitioning.IsInLocalRange(System.Int64)**).
**Parameter:** `RowIndicesTarget` - if null is specified, this array is assumed to be
{0,1, ... , 'RowIndicesSource'.Length-1]};
**Parameter:** `ColumnIndicesSource` - Column indices into this matrix, in the local range (**ilPSP.IPartitioning.IsInLocalRange(System.Int64)**).
**Parameter:** `ColIndicesTarget` - if null is specified, this array is assumed to be
{0,1, ... , 'ColumnIndicesSource'.Length-1]};
**Parameter:** `Target` - Output:
The ['RowIndicesTarget'[i],'ColIndicesTarget'[j]]-th
entry of the returned matrix is equal to the 
['RowIndicesSource'[i],'ColumnIndicesSource'[j]]-th
entry of this matrix.
**Parameter:** `ExternalColIndicesTarget` - 
**Parameter:** `ExternalColumnIndicesSource` - Additional/optional row indices into this matrix in the external range (**ilPSP.IPartitioning.IsInLocalRange(System.Int64)** evaluates to false).
These are not exchanged over MPI.
**Remark:**
Note on MPI parallelization: it is *not* necessary to exchange column indices, this can be done by the method internally.
The parameters 'ExternalColumnIndicesSource' and 'ExternalColIndicesTarget' can be used if
the 'ColIndicesTarget' is on another MPI communicator as this object ([ilPSP.LinSolvers.BlockMsrMatrix.MPI_Comm](#ilpsp.linsolvers.blockmsrmatrix.mpi_comm)).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Transpose <a id="ilpsp.linsolvers.blockmsrmatrix.transpose"></a>
**Summary:** Computes the transpose of this matrix.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.SymmetryDeviation <a id="ilpsp.linsolvers.blockmsrmatrix.symmetrydeviation"></a>
**Summary:** Computes the deviation of this matrix from symmetry
**Returns:**
The accumulated sum of the differences between corresponding
off-diagonal entries.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.CheckIfUnitMatrix(System.Boolean,System.Double) <a id="ilpsp.linsolvers.blockmsrmatrix.checkifunitmatrix(system.boolean,system.double)"></a>
**Summary:** Checks if a matrix is a unit matrix.
**Parameter:** `quick` - Specifies whether to perform a quick check (look only the number of elements) or a thorough one (explicitly reaching the memory).
**Parameter:** `threshold` - The tolerance for comparing values to 0 or 1.
**Returns:**
True if the matrix is a unit matrix, false otherwise.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.CheckIfSquareMatrix <a id="ilpsp.linsolvers.blockmsrmatrix.checkifsquarematrix"></a>
**Summary:** Computes the deviation of this matrix from symmetry
**Returns:**
The accumulated sum of the differences between corresponding
off-diagonal entries.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Acc(System.Double,ilPSP.LinSolvers.BlockMsrMatrix) <a id="ilpsp.linsolvers.blockmsrmatrix.acc(system.double,ilpsp.linsolvers.blockmsrmatrix)"></a>
**Summary:** Performs the operation: this = this + 'Ascale'*'A';
**Parameter:** `A` - another matrix with same size and equal [ilPSP.LinSolvers.BlockMsrMatrix.RowPartitioning](#ilpsp.linsolvers.blockmsrmatrix.rowpartitioning);
**Parameter:** `Ascale` - scaling


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Scale(System.Double) <a id="ilpsp.linsolvers.blockmsrmatrix.scale(system.double)"></a>
**Summary:** multiplies this matrix by the factor 'a'
**Parameter:** `a` - 


## Method: ilPSP.LinSolvers.BlockMsrMatrix.op_Multiply(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix) <a id="ilpsp.linsolvers.blockmsrmatrix.op_multiply(ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix)"></a>
**Summary:** matrix-matrix-multiplication, see [ilPSP.LinSolvers.BlockMsrMatrix.Multiply(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix)](#ilpsp.linsolvers.blockmsrmatrix.multiply(ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix)).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.op_Multiply(System.Double,ilPSP.LinSolvers.BlockMsrMatrix) <a id="ilpsp.linsolvers.blockmsrmatrix.op_multiply(system.double,ilpsp.linsolvers.blockmsrmatrix)"></a>
**Summary:** Multiply matrix 'M' by a scalar 'a'.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.op_Multiply(ilPSP.LinSolvers.BlockMsrMatrix,System.Double) <a id="ilpsp.linsolvers.blockmsrmatrix.op_multiply(ilpsp.linsolvers.blockmsrmatrix,system.double)"></a>
**Summary:** Multiply matrix 'M' by a scalar 'a'.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.op_Addition(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix) <a id="ilpsp.linsolvers.blockmsrmatrix.op_addition(ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix)"></a>
**Summary:** summation of matrices, see [ilPSP.LinSolvers.BlockMsrMatrix.Acc(System.Double,ilPSP.LinSolvers.BlockMsrMatrix)](#ilpsp.linsolvers.blockmsrmatrix.acc(system.double,ilpsp.linsolvers.blockmsrmatrix)).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.op_Subtraction(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix) <a id="ilpsp.linsolvers.blockmsrmatrix.op_subtraction(ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix)"></a>
**Summary:** Difference of matrices, see [ilPSP.LinSolvers.BlockMsrMatrix.Acc(System.Double,ilPSP.LinSolvers.BlockMsrMatrix)](#ilpsp.linsolvers.blockmsrmatrix.acc(system.double,ilpsp.linsolvers.blockmsrmatrix)).


### Property: ilPSP.LinSolvers.BlockMsrMatrix.NoOfCols <a id="ilpsp.linsolvers.blockmsrmatrix.noofcols"></a>
**Summary:** total number of columns (over all MPI processors)


### Property: ilPSP.LinSolvers.BlockMsrMatrix.NoOfRows <a id="ilpsp.linsolvers.blockmsrmatrix.noofrows"></a>
**Summary:** total number of rows (over all MPI processors)


## Method: ilPSP.LinSolvers.BlockMsrMatrix.AllocateEvenWhenZero(System.Int32,System.Int32) <a id="ilpsp.linsolvers.blockmsrmatrix.allocateevenwhenzero(system.int32,system.int32)"></a>
**Summary:** Allocates memory for some entry, even if the entry is zero;
**Parameter:** `i` - global (over all MPI processes) row index
**Parameter:** `j` - global (over all MPI processes) column index


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetValues(System.Int64,System.Int64[]) <a id="ilpsp.linsolvers.blockmsrmatrix.getvalues(system.int64,system.int64[])"></a>
**Summary:** see **ilPSP.LinSolvers.IMutableMatrix.GetValues(System.Int64,System.Int64[])**;


## Method: ilPSP.LinSolvers.BlockMsrMatrix.SetValues(System.Int64,System.Int64[],System.Double[]) <a id="ilpsp.linsolvers.blockmsrmatrix.setvalues(system.int64,system.int64[],system.double[])"></a>
**Summary:** see **ilPSP.LinSolvers.IMutableMatrix.SetValues(System.Int64,System.Int64[],System.Double[])**;


### Property: ilPSP.LinSolvers.BlockMsrMatrix.OccupationMutable <a id="ilpsp.linsolvers.blockmsrmatrix.occupationmutable"></a>
**Summary:** always true, see **ilPSP.LinSolvers.IMutableMatrix.OccupationMutable**;


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetDiagonalElement(System.Int64) <a id="ilpsp.linsolvers.blockmsrmatrix.getdiagonalelement(system.int64)"></a>
**Summary:** see **ilPSP.LinSolvers.ISparseMatrix.GetDiagonalElement(System.Int64)**;


## Method: ilPSP.LinSolvers.BlockMsrMatrix.SetDiagonalElement(System.Int64,System.Double) <a id="ilpsp.linsolvers.blockmsrmatrix.setdiagonalelement(system.int64,system.double)"></a>
**Summary:** see **ilPSP.LinSolvers.ISparseMatrix.SetDiagonalElement(System.Int64,System.Double)**;


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetOccupiedColumnIndices(System.Int64,System.Int64[]@) <a id="ilpsp.linsolvers.blockmsrmatrix.getoccupiedcolumnindices(system.int64,system.int64[]@)"></a>
**Summary:** see **ilPSP.LinSolvers.IMutableMatrixEx.GetOccupiedColumnIndices(System.Int64,System.Int64[]@)**


## Method: ilPSP.LinSolvers.BlockMsrMatrix.GetOccupiedRowBlockIndices(System.Int64,System.Boolean) <a id="ilpsp.linsolvers.blockmsrmatrix.getoccupiedrowblockindices(system.int64,system.boolean)"></a>
**Summary:** Returns the block-column index of all non-zero blocks in block-row 'iBlk'
**Parameter:** `alsoExternal` - True: also return block indices in the external range 
(**ilPSP.IBlockPartitioning.FirstBlock**, **ilPSP.IBlockPartitioning.LocalNoOfBlocks**), 
i.e. coupling with other MPI processors
**Parameter:** `iBlk` - row block index in the local range

## Class: ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow <a id="ilpsp.linsolvers.blockmsrmatrix.tempblockrow"></a>

**Summary:** Utility class used by [ilPSP.LinSolvers.BlockMsrMatrix.Multiply(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix)](#ilpsp.linsolvers.blockmsrmatrix.multiply(ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix));
basically, the implementation of the merge-algorithm which is crucial for the performance of the 
sparse matrix-matrix multiplication.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow.GetSize <a id="ilpsp.linsolvers.blockmsrmatrix.tempblockrow.getsize"></a>
**Summary:** The actually used number of bytes of this object in memory.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow.Serialize(System.IntPtr) <a id="ilpsp.linsolvers.blockmsrmatrix.tempblockrow.serialize(system.intptr)"></a>
**Summary:** Serializes this object into an unmanaged buffer, starting at address 'pBuffer';
the number of bytes is determined by [ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow.GetSize](#ilpsp.linsolvers.blockmsrmatrix.tempblockrow.getsize).


## Method: ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow.Deserialize(System.IntPtr) <a id="ilpsp.linsolvers.blockmsrmatrix.tempblockrow.deserialize(system.intptr)"></a>
**Summary:** De-serializes a block row from an unmanaged buffer, starting at address 'pBuffer';


## Method: ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow.Merge(ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow,ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow,ilPSP.LinSolvers.BlockMsrMatrix.TempBlockRow,System.Double*,System.Int32,System.Int32) <a id="ilpsp.linsolvers.blockmsrmatrix.tempblockrow.merge(ilpsp.linsolvers.blockmsrmatrix.tempblockrow,ilpsp.linsolvers.blockmsrmatrix.tempblockrow,ilpsp.linsolvers.blockmsrmatrix.tempblockrow,system.double*,system.int32,system.int32)"></a>
**Summary:** 'C' = '_AscaleM_left'*'A' + 'B'
**Parameter:** `C` - Output; the merge of 'A' and 'B'
**Parameter:** `A` - First Input.
**Parameter:** `B` - Second Input.
**Parameter:** `_AscaleM_left` - 
**Parameter:** `AscaleM_I` - 
**Parameter:** `AscaleM_J` - 


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Multiply(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix) <a id="ilpsp.linsolvers.blockmsrmatrix.multiply(ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix)"></a>
**Summary:** Sparse Matrix-Matrix multiplication.
**Parameter:** `C` - On exit, hopefully equal to 'A'*'B';
**Parameter:** `A` - Left operand.
**Parameter:** `B` - Right operand.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.__Multiply(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix) <a id="ilpsp.linsolvers.blockmsrmatrix.__multiply(ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix)"></a>
**Summary:** Sparse Matrix-Matrix multiplication.
**Parameter:** `C` - On exit, hopefully equal to 'A'*'B';
**Parameter:** `A` - Left operand.
**Parameter:** `B` - Right operand.


## Method: ilPSP.LinSolvers.BlockMsrMatrix.Multiply(ilPSP.LinSolvers.BlockMsrMatrix,ilPSP.LinSolvers.BlockMsrMatrix) <a id="ilpsp.linsolvers.blockmsrmatrix.multiply(ilpsp.linsolvers.blockmsrmatrix,ilpsp.linsolvers.blockmsrmatrix)"></a>
**Summary:** Sparse Matrix-Matrix multiplication.
**Parameter:** `A` - Left operand.
**Parameter:** `B` - Right operand.
**Returns:**
Hopefully equal to 'A'*'B';


## Method: ilPSP.LinSolvers.BlockMsrMatrix.InvertBlocks(System.Boolean,System.Boolean,System.Boolean,System.Boolean) <a id="ilpsp.linsolvers.blockmsrmatrix.invertblocks(system.boolean,system.boolean,system.boolean,system.boolean)"></a>
**Summary:** Returns a matrix with inverted blocks.
**Parameter:** `OnlyDiagonal` - If true, only diagonal blocks resp. sub-blocks are inverted.
**Parameter:** `Subblocks` -
Whether the blocks or sub-blocks should be inverted.
- false: inversion of (full) blocks, as defined by **ilPSP.IBlockPartitioning.GetBlockI0(System.Int64)** and **ilPSP.IBlockPartitioning.GetBlockLen(System.Int64)**.
- true: sub-block inversion, sub-blocks are defined by the **ilPSP.IBlockPartitioning**, 
see especially **ilPSP.IBlockPartitioning.GetBlockType(System.Int64)**, **ilPSP.IBlockPartitioning.GetSubblk_i0(System.Int32)** and **ilPSP.IBlockPartitioning.GetSubblkLen(System.Int32)**
**Parameter:** `ignoreEmptyBlocks` - 
**Parameter:** `SymmetricalInversion` - If true, symmetrical blocks are assumed, which are inverted by **ilPSP.IMatrixExtensions.InvertSymmetrical``1(``0)**.
**Returns:**




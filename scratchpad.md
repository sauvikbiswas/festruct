Working on a structure to represent FE entities.

## Three absolutes of the model.
1. Grid / Node
2. Element dfinitions
3. System definitions
Any model must be digested to yield at least these three entities. Note that Boundary Connditions and Loading are not part of this list. This is because a model may be subjected to various BCs and LCs. The meaning of the mesh remains the same.

## A generic data object - SET
A set can be a Grid or an Element set. The set has to be kept as close to Python native set as possible to take advantage of various operations. There has to be metadata associated with each set - What kind of set is it? Is the set used to define property of the elements?

There maybe other entities that will require a pointer to a set. For example, a surface definition, an edge definition, a BC definition or and LC definition.

## The idea of a GRID / NODE.
A grid is an entry in 3D. It can be represented by a vector.
However, most grids can have the definitions dependent on a different system. This could be something like a `*SYSTEM` on Abaqus or `CID` in Nastran.
The object as such must have a system object as reference.

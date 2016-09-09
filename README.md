# cache-zerocopy-tree

## Experiment to create multidimensional Caché ObjectScript array/tree with _zero-copy_ capabilties

The idea is simple - do not use `MERGE` when copying huge multi-dimensional trees (bee them local, PPG or global), 
but rather save the "pointer" to the right tree from the left node. This pointer will be hidden, and redirected 
upon subscription walk. For convenience, the external interface will use dynamic dispatch for multidimensional 
property, thus programmer will use the old good array syntax accessing such indirected subtrees.

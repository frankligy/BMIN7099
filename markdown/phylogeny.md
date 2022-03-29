# Phylogeny

Defining phylogeny is a branch of science in bioinformatics. Imagine we have a series of entities, we want to put them into a tree-structure, how shall we do that?

Three potential ways:

1. Based on Distance

If we can represent the relationship between entities using a distance matrix, we just need to transform the distance matrix to a tree. It is not always solvable because we have more constraints (equations) than the degree of freedom (unknowns). Methods like UPGMA can be used to heuristically contruct phylogenetic trees.

2. Based on Parsimony

The preferred evolutional tree is the one that requires minimum net amount of mutation. We basically count the number of mutation needed along the different topology and different ways to place the entity on the node, and find the most parsimous topology and placement. When the topology is known, this is called "small parsimony", when even topology is unknown, it becomes "big parsimony". If each branch have different weight, the problem becomes "weighted parsimony". Sankoff algorithm and Fitch's algorithm falls into this category.

3. maximum likelihood

Find the path along which the likehihood of observing the entities become the maximum.



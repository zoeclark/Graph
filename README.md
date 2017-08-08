# Graph
Uses Prim-Jarnik's algorithm and Kruskalls algorithm to find minimum spanning tree

There aren't that many opportunities for design choices in the graph class. I used an  instance variable to keep track of the maximum int I had assigned to a vertex. Whenever I deleted a vertex, I added its integer number to a deque. When adding a new vertex, if any numbers remained in that deque, i would pop them and use them for the new vertex. Otherwise, I would use the max number incremented by 1. 

Kruskal Klass:
I used two decorators, one which holds the "parent" of a given vertex. I used then when I ask a vertex for the root of the cloud it is in. During path compression, my helper method, getCloudRoot, passes up the parent number through recursion from the "lowest" to the "highest" cloud. This amortizes the run time to 0(1).   The other decorator I used held the "rank" of the vertex. Vertices only get ranks when they are the root of the cloud, and the rank roughly represents the clouds size. When merging two clouds, I merge the cloud with the lower rank into the smaller one. 

PrimJarik Class:
I also use two decorators for PrimJarnick. One, called "dists" that keeps track of the "distance" (sum of edge weights) to that node. The other decorator, called "pointers," points to vertex most recently visited so that we can follow the pointers back. The decorators create keys that form the k value for (k,v) pairs which get inserted into a dictionary. 



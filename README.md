# Algorithms
Programming and problem solving, with applications.
Algorithm : method for solving a problem
Data Structure : method to store information

Data Types - stack, queue, bag, union-find, priority  queue
Sorting - quicksort, mergesort, heapsort, radix sorts
Searching - BST, red-black BST, Hash Table
Graphs - BFS, DFS, Prim, Kruskal, Dijkstra
Strings - KMP, regular expressions, TST, Huffman, LZW
Advanced - BTree, Suffix Array, Maxflow

Why study algorithms?

Their impact is broad and far-reaching.
Internet - Web search, packet routing, distributed file sharing,...
Biology - Human genome project, protein folding,...
Computers - Circuit layout, file system, compilers,....
Computer graphics - Movies, Video Games, Virtual Reality,...
Security - Cell phones, e-commerce, voting machines,...
Multimedia - MP3, JPG, DivX, HDTV, Face recognition,....
Social Networks - recommendations, news feeds, advertisements,...
Physics - N-body simulation, particle collision simulation,....

ALGORITHMS + DATA STRUCTURES = PROGRAMS

Prerequisites
- Programming : loops, arrays, functions, objects, recursion
- Java : we use as expository language
- Mathematics : high-school algebra

Review of prerequisite material
- Quick : Sections 1.1 and 1.2 of Algorithms, 4th edition
- In-depth : An introduction to programming
 in java : An interdisciplinary approach by Sedgewick and Wayne (booksite and book).
 
Programming Environment 
 - Use your own eg. eclipse
 
Quick exercise : Write a java program

What is hypotheses???

Analyse memory usage of a program

How to solve connectivity problem?

- Modeling the connections

We assume "is connected to" is an equivalence relation:
- Reflexive : p is connected to p.
- Symmetric : if p is connected to q, then q is connected to p.
- Transitive : if p is connected to q and q is connected to r, then p is connected to r.

Connected components: Maximal set of objects that are mutually connected.

Implementing the operations

Find query : Check if two objects are in the same component.

Union Command : Replace components containing two objects with their union.

Union-find data type (API)

Goal : Design efficient data structure for union-find.
- Number of objects N can be huge.
- Number of operations M can be huge.
- Find queries and union commands may be intermixed.

Dynamic-connectivity client
- Read in number of objects N from standard input.
- Repeat:
1. read in pair of integers from standard input
2. if they are not yet connected, connect them and print out pair

Quick Find [eager approach]

Data Structure
- Integer array id[] of size N
- Interpretation: p and q are connected iff they have the same id.

Find : Check if p and q have the same id.
Union : To merge components containing p and q, change all entries whose id equals id[p] to id[q].

Quick-union [lazy approach]
- Data Structure
1. Integer array id[] of size N.
2. Interpretation : id[i] is parent of i.
3. Root of i is id[ id[ id[....id[i]....] ] ]

 Weighted quick-union : Java Implementation
 
 Data Structure. Same as quick-union, but maintain extra array sz[i] to count number of objects in the tree rooted at i.
 
 Find. identical to quick-union
 
    return root(p) == root(q);
    
Union. modify quick-union to:
- link root of smaller tree to root of larger tree
- update the sz[] array.

        int i = root(p);
        int j = root(q);
        if (i == j) return;
        if (sz[i] < sz[j]) { id[i] = j; sz[j] += sz[i]; }
        else { id[j] = i; sz[i] += sz[j]; }
    
Steps to developing a usable algorithm
- model the problem
- find an algorithm to solve it
- fast enough? fits in memory?
- if not, figure out why.
- find a way to address the problem
- iterate until satisfied


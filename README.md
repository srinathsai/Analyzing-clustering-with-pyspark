# Analyzing-clustering-with-pyspark
2 Famous algorithms called Kmeans and Kmeans++ are analyzed with pyspark without any libraries.

## introduction:-
Imagine you are a doctor and wanted a machine that would classify very precise patients into crictical state, emergency state and normal state . Or if you wanted to check plagiarism in the homework of students in your university. If you go on thinking scenarios, there will be millions of million cases where there would be need of grouping items based on similarities.
**Clustering** is one of the powerful methods that falls in this category of grouping of objects based on similarites. As clustering is one of the important techniques in today's world ,therefore this project explores two powerful clustering algorithms called kmeans and kmeans++ using pyspark without any inbuilt libraries.

## Methodolgy :-
1. First and foremost thing is finding k centroids. This is the only step in which kmeans and kmeans++ differ and it is as follows:-<br>

| k centroids in kmeans                   | k centeroids in kmeans++                                       |
| ----------------------------------------| ---------------------------------------------------------------|         
| all k centroids are initialised randomly| here only one point is initialised randomly.                   |
|                                         |  After one point next point will be farthest of all            |
|                                         |  indicating next centeroid, now next point will be **farthest**|
|                                         |  of midpoint of  centeroids found in previous iteration.       |
|                                         |  this process is **iteratively** repeated untill we get k-2    |
|                                         |  centeroids.                                                   |

2. After finding k centeroids , the point closest to any of the centeroid is considered to be one cluster. So mean of new point and closest centeroid will be new centeroid for next iteration.

3. Iteratively repeating 2nd step untill all points are clustered into k clusters.

## Metrics used in coding :-
  * no of iterations=20<br>
  * k=20( usually determined by elbow method).
  
## Observations :-
  * Cost of error function decereased per iteration implying increase in  correctness of clustering .
  * As in kmeans++ only one centeroid is randomised it performed better than normal K means and it can be observed in the kmeans++.py file with graph.
  
                                                                                                        

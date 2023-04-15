
+++
date = "2020-01-03"
lastmod = "2020-01-03"
draft = false
tags = ["R", "hyperSpec", "export"]
title = "Export matrix with PC or cluster number to csv"
summary = """
Data matrix export to txt file
"""
math = false
+++

Sometimes we need to export data matrix with the results of the analysis for further processing or visualization (for example in ImageJ).
Typically firstly we have to convert object to matrix with `matrix` function. Then we can use `write.table` function. Settings `col.names=F` and  `row.names=F` allows for exporting pure matrix.

```r
#PCA
#export map with PC1 values to csv
s1= scores [[,,1 ]]
pc1 = matrix(s1, nrow=y1, byrow =TRUE)
write.table (pc1, "pc1.txt", col.names=F, row.names=F )

#HCA
#export map with cluster number: variable test$clusters
cl = matrix(as.numeric (test$ clusters), nrow=y1, byrow =TRUE)
write.table (cl, "clusters.txt", col.names=F, row.names=F )
```




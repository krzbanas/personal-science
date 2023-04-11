+++
date = "2019-02-01"
lastmod = "2019-02-01"
draft = false
tags = ["R", "hyperSpec"]
title = "Hierarchical Cluster Analysis of Spectra in R"
summary = """
Hierarchical Cluster Analysis of Spectra in R
"""
math = false
+++

Example of hierarchical cluster analysis on spectra. First the distances are calculated for spectra matrix by `pearson.dist` function, then dendrogram is created with `hclust` function (here Ward's algorithm is selected as linkage method). 


```r

# dendrogram
dist <- pearson.dist(test [[]])
dendrogram <- hclust(dist , method = "ward")
test$clusters <- as.factor (cutree ( dendrogram, k=5 ))
# mean spectra for clusters
cluster.means <- aggregate ( test, test$clusters, mean)
cols <- c ("blue", "cyan","green" , "yellow" ,"red" )
plot(cluster.means, stacked = ".aggregate" , fill = ".aggregate", col = cols, wl.reverse= TRUE, xoffset=150,lines.args = list( lwd = 3, lty = 1 ), wl.range =c( 800~2250 ,2400 ~3800))
#clusters mapping
levels ( test$clusters ) <- c (1,2 ,3 , 4 ,5 )
plotmap(test,    z  =  test$clusters)
# dendrogram with colour bars
plot(dendrogram )
plot(dendrogram, labels = FALSE, hang=0 )
points ( seq_along (dendrogram $order) , rep (-3, length (dendrogram$order)), col= cols [test$ clusters [dendrogram $order]] , pch ="|")
# plus extra rectangles
rect.hclust(dendrogram, k =5, border ="red")
```

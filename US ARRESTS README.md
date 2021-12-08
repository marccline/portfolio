# US ARRESTS README

#### INTRODUCTION
The data set contains statistics, in arrests per 100,000 residents for assault, murder, and rape in each of the 50 US states in 1973. Also given is the percent of the population living in urban areas.

#### PRE-PROCESSING
The dataset has been cleaned beforehand. No missing values were found. 

PRE-PROCESSING DATA ANALYSIS: Assault has by far the highest mean of arrests/100 000 residents (170.76) with Rape far behind with 21,23 arrests/100 000. Furthermore, Assault has the highest Min value(45/100 000) and the highest max value (337/100 000).



Max value for Assault is 337.0, which is a much bigger value than the rest of the values. Scaling is required.

#### PCA-DATA ANALYSIS
(1) HEATMAP
Pre-PCA Implementation.

There is only 1 strong positive correlation, between Murder and Assault (0.8). The next highest positive correlation is between Assault and Rape (0.67), followed by Murder/Rape (0.56). The rest of the variables do not correlate strongly wth one another.

The strong positive correlation between Murder and Assault could be because murder can be thought of as a specific kind of assault-an assault that leads to death. Similar logic can be applied to Assault/Rape.

Regarding Assault/Rape, it could be that there is an under-reporting of rapes and the correlation between Assault/Rape could be stronger/higher value, closer to the positive correlation value between Assault/Murder. This could be because those cases reported as assaults-particularly cases reported by women-may actually be cases of rape, as women who have experienced the trauma of being raped may be reluctant to tell the authorities that they were raped. Instead, they report the incident as just a case of assault.

(2) BIPLOT & HEATMAP
A loading plot shows how strongly each characteristic influences a principal component.

Post-PCA Implementation, what stands out is the strong negative correlation between UrbanPop (percent of the population living in urban areas) and PC2, i.e. there higher percentage of people that live in urban areas, the less arrests. Also, there is a slight positive correlation between Assault and PC1, and similarly with Murder and Rape and PC1. On the other hand, there are weak correlations between UrbanPop and PC1, Asssault and PC2, and Rape and PC2.

In summary, Rape, Assault, Murder have moderate influence over PC1, while UrbanPop has a big influence over PC2. This last point, particularly that UrbanPop is strongly negatively correlated with PC2, hints that the higher the percentage of people living in urban areas, the lower the crime rate. Whether this could be attributed to more concentrated law enforcement in urban areas, the corollary that urban-dwellers are thus disuaded from commiting these crimes as they risk more likely being caught, needs further investigation.

(3) SCREE PLOT
A scree plot displays how much variation each principal component captures from the data.

The Scree plot shows that 2 components account for around 95% of the variance. So we can visualise the clusters by reducing the dimensions into 2 using PCA.

(4) EIGENVALUES
A good rule of thumb is that PCs with eigenvalues > 1 contributes greater variance and should be retained for further analysis.We see that PC1 and PC2 fit this criterion (at 2.53085875 1.00996444 respectively) and they should be retained.

(5) Primary Component Analysis
The cumulative variance shows that 95% of the variance is due to PC1, PC2, and PC3, with each accounting for around 62%, 25%, and 9% respectively.

From the heatmap, we see strong positive correlation between PC3 and Rape, as well as strong negative correlation between PC2 and UrbanPop, and PC4 and Assault.

#### CLUSTERING I-HIERARCHICAL CLUSTERING
Using complete linkage, the dendrogram shows that the clusters sizes are 10 (yellow), 21 (green), 11 (red), and 8 (purple). The complete linkage is appropriate as there is a good balance between the different coloured clusters. The shortest distance line-i.e. the most similar points-is between the numbers 24 and 28 in the yellow cluster, followed by 31 and 2 in the red cluster. Looking at the green and purple clusters, it appears that the threshold is 3, so we will set K = 3.

With K = 3 and linkage = complete, we see that the purple cluster is virtually disctinct and separate from the other clusters. However, the yellow and blue clusters are not as separated from one another, clearly demonstrated by the overlap between them at specific places. The Silhouette Score (0.369) confirms that the clusters are somewhat distinct but overlapping is still evident.

#### CLUSTERING II-K-MEANS
The K-means algorithm yielded worse results than the hierarchical/agglomerative clustering used above (Silhouette Score: 0.31 vs 0.369). While the topmost purple cluster is mostly distinct and separate from the other clusters, the blue and yellow clusters exhibit considerable overlap. The worse results could possibly be attributed to the limitations of k-means clustering (too much noise in the data, inability to deal with outliers, etc.) in addition to the data not being suitable for clustering.


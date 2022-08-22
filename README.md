# Farmers’ adoption of climate change mitigation measures
Link to our final report: https://docs.google.com/document/d/1IYOJ7ibMRlcDI27pSTVK6SU1vm0cm2v-p0rPMFW79GQ/edit?usp=sharing

## Introduction
Climate change has been accelerating over the past few decades, and it threatens us with food and water scarcity, extreme weathers and extermination of a species. In a recent study conducted in 2019, 105 farmers in a region in Switzerland were surveyed about the mitigation measures taken to combat climate change. Also, the survey also collected information about the farmers’ individual characteristics, risk attitudes and social influences.

With the data collected, we are interested in finding out how we can better leverage this information to help the farmers better adopt the mitigation measures. Also, it would be beneficial to generalize the analysis to promote the mitigation measures in other countries and regions.

## Contents in Github Repo
All dataset used in our study
Coding for each type of analyses including regression, clustering, network analysis, and recommender system. 

## Regression Analysis
Our regression analysis answers the question that what are the key factors impacting farmers’ adoption of climate change mitigations. 
If you were the policy makers, our findings could be of value to you. 



Key findings:
1.	Identified two influential factors (network size and feeling impact) that have an impact on farmer's adoption of climate change mitigation. This confirms our hypothesis 1 and 4.
2.	Reject hypothesis 2 and 3, which means farm size and level of importance attached to people in the network are not influential factors.
Our findings provide actionable insights to policymakers about how they can improve the adoption of climate change mitigation by farmers. 
First of all, we found that network size is an influential factor. Policy makers should probably organize more networking events such as conferences, seminars, and sharing sessions to create opportunities for farmers to expand their network. Also, as we identified feeling impact as an influential factor, all the networking events can be leveraged to promote awareness of how farming behaviors can impact climate change. The rejected hypothesis offers insights that it is not meaningful to target larger farms unless it is believed to be more efficient and economically viable given a single larger farm may have a more significant impact on overall climate change compared to a smaller one. Also, it is not necessary to care about a farmer's network quality (how a farm thinks the people in the network will impact their decision making). This is somewhat contradictory to common sense, but it may indicate that social comparison is a more implicit process that people may not be aware of. 
The limitations of our regression analysis are that we only have data of 105 farmers in Switzerland and therefore our research may not be generalizable to other regions and we may miss out other influential factors given our choice of model and feature shortlisting. A potential future study could be done to research more farmers across different regions and cultures, and test more machine learning models to find other potential influential factors.

## Clustering
Clustering is used to explore the grouping of farmers and its relationship with the adoption of greenhouse gas reduction measures. We found that a specific cluster of farmers care more about climate change and we will analyze the features of this group. We selected K-means clustering since this algorithm fits the analysis when there are unclear trends or tendencies.  The K-means algorithm is appropriate for the early stage analysis, where objects are irregular and inter-object relevance is unknown. As a result of analysis, the farmers in cluster 2 think climate change will have very negative consequences for agriculture in Switzerland. As a result of analysis, we made the model and visualized the result. The farmers in cluster 2 are likely to have livestock farms in the Flaachtal region or Thurtal region. Their age is 50.3 years old on average and their standard workforce units is 2.8 in average and their farm’s total agricultural land is 3085Ar on average. 

 

## Network Analysis
Applying the networkx library to create and draw the graph to visualize how farmers are connected in the network. Node importance measures, such as degree centrality, betweenness centrality, closeness centrality, etc, are used to check the importance level of farmers in the network. Based on the analysis result, the good side is that we can make use of farmers who have more influence in the network to share messages related to climate change mitigation. The negative side is that the sample size is limited and it’s kind of hard to generalize the impact to other groups. The conclusion will be more solid if more information about farmers’ profiles is provided. The hints we obtain from the existing data are simply about their relationship and communication frequency. If we can get more demographic information, it is more likely to sum up a regular pattern about which specific group of farmers normally has more impact on others. Then we can generalize our findings to other farmer groups.
 
 

## Recommender System
A recommender system to suggest mitigation strategies to the farmers in a systematic way. In our analysis, we implemented truncated singular value decomposition (SVD) model
 
Next we need to find the most meaningful r -- the number of features in the latent space. 
For evaluation strategies, we tried two most intuitive ways:
- maximize outcome:👍most desired outcome;👎model may always recommend every measures
- approximate based on current matrix:👍 works well for SVD; 👎can be stuck at local maxima
In the training, we mask the input data:
1. Fully mask the input data of a particular farmer, by replacing all columns with 0
2. Partially mask the input data, by random replacing columns with 0 to simulate we already know some measure the farmers have implemented
In addition, we also added some clustering model to group the farmers and farms by their properties (size, type of animals and product, etc.) to further improve the result. With partial masking and clustering, the distribution of r is the most meaningful with lowest error:
 

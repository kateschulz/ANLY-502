Katherine Schulz, ANLY 502 Project

# Introduction
In this project, I focused on the subreddits, scores, and bodies (comments). I first analyzed the ratings of each subreddit by averaging their scores across the entire dataset. Using comments from each subreddit, I then performed a k-means clustering on the top scoring 1,000 subreddits to assess how similar their contents were. Overall, most of the top 1,000 subreddits were in clusters close to each other; however, two distinct subreddits were the only points in clusters far from the rest. 


# Code
The code for this project is contained in three .ipynb notebooks:
* *qry_scores.ipynb*
* *qry_body.ipynb*
* *K-means.ipynb*

*qry_scores.ipynb* queried the full dataset and computed the average score for each subreddit. The results of this query are in *subreddit_score.csv*.

*qry_body.ipynb* queried the full dataset and took each distinct subreddit and the first comment associated with it. The results of this query are in *subreddit_bodies.csv*

*K-means.ipynb* used the results of the previous queries and joined them together. In this case, I chose K = 10 for clustering the top 1,000 subreddits. 

# Methodology

### Summary Statistics
I computed some summary statistic on the dataset in the *qry_scores.ipynb* notebook, in addition to performing the average scoring query. The full dataset had 476,259,744 rows. After querying, I found that the:

* Number of Distinct Subreddits = 233,505
* Highest Average Score = 103.3
* Lowest Average Score = -119.0

The chart below shows the average scores of the 10 highest subreddits:
![Image of Yaktocat](https://github.com/gu-anly502/spring2019-miniproject-kateschulz/blob/master/Top%2010%20Scores.png)


### Data Manipulation
After query the data in the *qry_scores.ipynb* and *qry_body.ipynb* notebooks, I joined the datasets in the *K-means.ipynb* notebook and removed any rows where the comment was "[removed]" or "[deleted]". I also subsetted for the 1,000 subreddits with the highest average scores to make the text processing of the comments quicker in the k-means clustering. During the k-means clustering, I also removed stop words from the comments to make the available text more meaningful for analysis. 

### K-means Clustering
I performed the k-means clustering in the *K-means.ipynb* notebook. I chose k = 10 arbitrarily, as I could not figure out how to do arithmetic with the sparse vector representations of the comments. In addition, I limited the number of features in the text hashing to three, so I could visualize the results with a 3D plot. 

# Results
On 10 groups, the k-means clusters classified most of the subreddits into two groups. The number of subreddits in each cluster are shown in the table below. Of the 1,000 subreddits analyzed, 725 are in groups 0 or 3.

 ![Image of Yaktocat](https://github.com/gu-anly502/spring2019-miniproject-kateschulz/blob/master/results.png)
 
 The 3D plot of the centers of the clusters shows that all but two of the groups, 2 and 5, are fairly close together:
 
  ![Image of Yaktocat](https://github.com/gu-anly502/spring2019-miniproject-kateschulz/blob/master/3D%20plot.png)

The top 10 subreddits pictured earlier with their average scores were clustered in groups 0 or 3: 

 ![Image of Yaktocat](https://github.com/gu-anly502/spring2019-miniproject-kateschulz/blob/master/top%2010%20groups.png)

The individual subreddit that belonged to group 5 was "LetterstoJNMIL", which has been made private, so I cannot determine what topics the subreddit covers 

http://github.com - automatic!
[GitHub](http://github.com)

# Future Work

For the text processing, I only chose the first body (i.e. comment) for each distinct subreddit and did not control for the authors of the comments or number of tokens vectorized for each subreddit in the k-means clustering. In  future work, creating a dictionary of all comments by all authors for each distinct subreddit and using the same number of tokens for each subreddit in the k-means clustering may improve the results. Currently, my analysis relies on writing samples of random lengths from random authors as proxies for the contents of the subreddits.  

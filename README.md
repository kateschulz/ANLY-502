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
## Data cleaning and Manipulating 

First two notebooks

K-means clustering, final notebook


# Results


# Future Work

For the text processing, I only chose the first body (i.e. comment) for each distinct subreddit and did not control for the authors of the comments or number of tokens vectorized for each subreddit in the k-means clustering. In  future work, creating a dictionary of all comments by all authors for each distinct subreddit and using the same number of tokens for each subreddit in the k-means clustering may improve the results. Currently, my analysis relies on writing samples of random lengths from random authors as proxies for the contents of the subreddits.  

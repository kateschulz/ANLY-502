Katherine Schulz, ANLY 502 Project

# Introduction
In this project, I focused on the subreddits, scores, and bodies (comments). I first analyzed the ratings of each subreddit by averaging their scores across the entire dataset. Using comments from each subreddit, I then performed a k-means clustering on the subreddits to assess how similar their contents were. 


# Code

# Methodology
Data cleaning and manipulating 

First two notebooks

K-means clustering, final notebook


# Results


# Future Work

For the text processing, I only chose the first body (i.e. comment) for each distinct subreddit and did not control for the authors of the comments or number of tokens vectorized for each subreddit in the k-means clustering. In  future work, creating a dictionary of all comments by all authors for each distinct subreddit and using the same number of tokens for each subreddit in the k-means clustering may improve the results. Currently, my analysis relies on writing samples of random lengths from random authors as proxies for the contents of the subreddits.  

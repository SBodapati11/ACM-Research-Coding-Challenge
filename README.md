# ACM Research Coding Challenge (Fall 2020)

* My answer and explanation are located at the bottom of the README *

## No Collaboration Policy

**You may not collaborate with anyone on this challenge.** You _are_ allowed to use Internet documentation. If you _do_ use existing code (either from Github, Stack Overflow, or other sources), **please cite your sources in the README**.

## Submission Procedure

Please follow the below instructions on how to submit your answers.

1. Create a **public** fork of this repo and name it `ACM-Research-Coding-Challenge`. To fork this repo, click the button on the top right and click the "Fork" button.
2. Clone the fork of the repo to your computer using . `git clone [the URL of your clone]`. You may need to install Git for this (Google it).
3. Complete the Challenge based on the instructions below.
4. Email the link of your repo to research@acmutd.co with the same email you used to submit your application. Be sure to include your name in the email.

## Question One

![Image of Cluster Plot](ClusterPlot.png)
<br/>
Given the following dataset in `ClusterPlot.csv`, determine the number of clusters by using any clustering algorithm. **You're allowed to use any Python library you want to implement this**, just document which ones you used in this README file. Try to complete this as soon as possible.

Regardless if you can or cannot answer the question, provide a short explanation of how you got your solution or how you think it can be solved in your README.md file.

**Answer/Explanation:**

**There are 2 clusters**

I know a little from learning over the summer, but I did some additional research to enhance my understanding of clustering algorithms. I used a Gaussian Mixture Model clustering algorithm. I chose this algorithm over the K-means model because of 2 advantages: 1) a GMM allows oval-shaped/stretched clusters instead of just circular clusters and 2) provides the probabilities that the data points point to a certain cluster. I used the sklearn (sci-kit learn) library, specifically sklearn.mixture.GaussianMixture. The GaussianMixture allows for a model to be created given the number of components and covariance type (I used 'full'). To determine the optimal number of clusters/components, I learned that this the value that has the lowest Akaike information criterion (AIC) or Bayesian information criterion (BIC). I was able to find these values for up to 15 clusters, determining that both 2 and 3 clusters can be reasonably found in the dataset. However, to choose one out of the two, I looked at the probabilities that each data point belongs in a cluster using gmm.predict_proba(dataset) and noticed that data points in 2 clusters were much more likely than in 3. Therefore, I concluded that there are 2 clusters in the dataset.

**Libraries I used: numpy, pandas, sklearn.mixture, matplotlib.pyplot**

I adapted my code from the following article: https://towardsdatascience.com/gaussian-mixture-models-d13a5e915c8e

MLA Citation of source: 
Maklin, Cory. “Gaussian Mixture Models Clustering Algorithm Explained.” Medium, Towards Data Science, 16 July 2019, towardsdatascience.com/gaussian-mixture-models-d13a5e915c8e.


# ACM Research Coding Challenge (Fall 2020)

  

## Question One

  

![Image of Cluster Plot](ClusterPlot.png)

<br/>

Given the following dataset in `ClusterPlot.csv`, determine the number of clusters by using any clustering algorithm. **You're allowed to use any Python library you want to implement this**, just document which ones you used in this README file. Try to complete this as soon as possible.

  

Regardless if you can or cannot answer the question, provide a short explanation of how you got your solution or how you think it can be solved in your README.md file.

  

## Solution

  tl;dr - The number of clusters is **two** with a few outliers. The clustering algorithm used for this problem is **DBSCAN**.

### Introduction

Data Science and Machine Learning is a completely new world for me, given I've dabbled mostly in Software Development. Only recently did I acquire some surface level ML knowledge when I was working on a GPT-2 text generator. However, this project was just implementing the GPT-2 library and just that. This Coding Challenge was my first time being introduced to data analysis, clustering algorithms and the math-side of it all. This morning, I spent quite some time researching and I can now say that I understand what clustering is, and different clustering algorithms. I was able to come up with a solution for the Coding Challenge which I will explain in detail below.

  

### Research

Since I had zero knowledge about the material, I had to start from the ground up. I find that I learn better from reading articles over watching videos. I stumbled upon the blog *'Towards Data Science'* which had the answer to almost every question I had. So, I started off with finding the answer to *"What is Clustering?"* The ELI5 of clustering is basically 'grouping datapoints which have similar properties into clusters.' Then, I learnt that there are a handful of different types of clustering algorithms and there is no one-size-fits-all algorithm for any dataset -- each algorithm has its pros and cons and should be implemented according to the dataset's properties. So now my task was to find the best algorithm which suits the dataset provided in the challenge.

  

### K-Means vs DBscan?

  

The big question for me was whether I should use **K-means or DBSCAN** algorithms for this (I chose these two algorithms because I read they are easiest for a beginner to implement and would get the job done without much complexities). This question was quickly answered when I found an article on Towards Data Science which compared the two algorithms.
<br/>
I decided that **DBSCAN would be the most optimal** algorithm for this purpose and here are the reasons why:
<br/>
1. The given clusters are not spherical and are irregularly shaped. K-means works best when the clusters are spherical and DBSCAN works best with irregularly shaped clusters.
<br/>
2. I observed that there are a handful of outliers in the given dataset. K-means does not work well with outliers but DBscan does.

  

### Implementation

  

Now that I had chosen the algorithm that fits the purpose, implementing it was quite straightforward.

<br/>

Here's the pseudocode for the DBSCAN algorithm:
<br/>
1. Decide the value of eps and minPts. [eps (epsilon): The maxi radius that forms the neighbourhood of one core point; minPts: Minimum number of points inside a neighbourhood that are needed to form a cluster.]
<br/>
2. For each point:
Calculate its distance from all other points. If the distance is less than or equal to eps then mark that point as a neighbor of x. If the point gets a neighboring count greater than or equal to minPts, then mark it as a core point or visited.
<br/>
3. For each core point, if it not already assigned to a cluster than create a new cluster. Recursively find all its neighboring points and assign them the same cluster as the core point.
<br/>
4. Continue these steps until all the unvisited points are covered.

<br/>


**Note**: I have used a combination of code from these tutorials in my Jupyter notebook to implement the DBSCAN algorithm and the algorithm to find Epsilon: <br/>

* https://www.geeksforgeeks.org/implementing-dbscan-algorithm-using-sklearn/ <br/>

* https://towardsdatascience.com/machine-learning-clustering-dbscan-determine-the-optimal-value-for-epsilon-eps-python-example-3100091cfbc <br/>

  
  
  

### Result

  

![Image of Result Plot](ResultPlot.png)

  
  

<br/>

The model spit out a scatter plot which had the data points marked in three colors. There were mainly **two clusters** (identified by yellow and pink) and **six outlier points** (marked by green). One way of verifying this result is by plain visual observation. The separation between the two clusters and the outliers is quite obvious.
<br/>

Thus, I'd conclude that the results of the algorithm is quite optimal and would satisfy the given problem.

### Takeaway

  

This whole challenge was super exciting and a breath of fresh air. I definitely seem to enjoy data science more than software engineering (at least as far as what I've delved into). I excitedly look forward to the results of my submission and getting selected into the research program. Regardless, I plan to pursue this field further on my own to see what it holds.

### Resources
https://towardsdatascience.com/understanding-dbscan-algorithm-and-implementation-from-scratch-c256289479c5

https://towardsdatascience.com/machine-learning-clustering-dbscan-determine-the-optimal-value-for-epsilon-eps-python-example-3100091cfbc

https://www.geeksforgeeks.org/implementing-dbscan-algorithm-using-sklearn/

https://towardsdatascience.com/k-means-vs-dbscan-clustering-49f8e627de27

*And several Indian YouTube Channels haha!*

---
layout: page
title: "Distributed and collaborative algorithms"
description: "Pervasive Applications course review - part 3"
---
{% include JB/setup %}

####	Distributed algorithms
* Problems solved: resource allocation, distributed search, cooperative scheduling, spanning tree generation
* Are typically executed **concurrently** with separate parts of the algo being run **simultaneously** on **independent** processors.
* Challenge: **coordinating** the behavior of the independent parts of the algo in the face of processor **failures** and unreliable communication links

**Collaboration Filtering (CF)**: Process of filtering for information or patterns using the know preferences of a group of users to make recommendations or predictions of the unknown preferences for others users.

**Common insight**: personal tastes are correlated

**Recommender systems** assist and augment the natural social process to help people to find the most interesting and valuable information for them. **Tapestry**, first recommender system (1992)

**CF fundamental assumption**: if users X and Y rate n items similarly, or have similar behaviors, and hence will rate or act on other items similarly.

<br/>

#### CF Challenges
* Provide fast and **accurate** recommendations to attract the interest of customers
* **Data Sparsity**: when very large product set, performance challenge
* **Cold start** problem: new user or item just entered the system, not enough info
* **Reduced coverage** problem: small number of user’s rating but large number or item 
* **Neighboor transitivity**: data sparsity -> users with similar tastes may not be identified as such if they have not both rated any of the same items
* **Scalability**: if users and items grow tremendously, CF algo will suffer
* **Synonymy**: same or very similar items have different names, need to construct a semantic space to associate terms and documents
* **Gray Sheep**: users whose opinions do not consistently  agree or disagree with any group of people
* **Shilling attacks**: tons of positive recommendation for their own materials and negative recommendation for their competitors.
* **Privacy**: people may not want their habit or views widely known
* **Increased noise**: another challenge as the user population becomes more diverse

**The Netfix Prize Challenge**: open competition for the best CF algo. Team “BellKor’s Pragmatic Chaos” 10.07% improvement of RMSE in 2009

<br/>

#### CF Techniques
* Memory-Based
* Model-Based
* Hybrid 

<br/>

#### Memory-Based CF algos:
* Generate prediction with entire or sample of the user-item database. Every user is part of a group of people with similar interests. Prediction produced with the neighbors of a new user. 
* **Neighborhood-based CF algo** is a prevalent memory based CF algo. It calculates the similarity or weight between two users or two items, produce prediction and generate Top-N recommendation.
* **Similarity computation** is a critical step, determines the similarity between two co-rated items or two users.
	- **Correlation-Based similarity** measured by computing a **Person correlation**
	- **Vector Cosine-Based similarity** 

<br/>

* **Prediction and recommendation computation** is the most important step in a CF system. In the neighborhood-based CF algo, a subset of nearest neighbor of the active user are chosen based on their similarity with him and a weighted aggregate of their rating is used to generate prediction for the active user.
	- **Weighted sum of others ratings**
	- **Simple weighted average** (for item-based prediction)

<br/>

* **Top-N recommendation** is to recommend a set of N top-ranked items that will be of interest to a certain user (analyze the user-item matrix to discover relations between different user or items and use them to compute the recommendation)
	- **User-based** Top-N recommendation algo
	- **Item-based** Top-N recommendation algo

<br/>

#### Model-Based CF Algos: 
* Model such as machine learning or data mining algo allow the system to learn to recognize complex patterns based on the training data and then make intelligent prediction for the collaborative filtering tasks. 
* Bayesian models, clustering models and dependency networks have been investigated to **solve the shortcoming of memory-based algo**.
* The goal is more to uncover latent factors rather than explain ratings. Most of the model are based on creating a classification or clustering technique (the number of paramaters can be reduced)
* **Advantages**: handle sparsity better than memory-based, helps with scalability for large data sets, improve the prediction performance, intuitive rationale for the recommendation.
* **Disadvantages**: expensive model building, tradeoff between prediction performance and scalability

<br/>

#### Hybrid CF Algo 
To combine the memory-based and the model-based algos, overcome the limitation of native CF approaches, improves the prediction performance, overcomes the CF problems such as sparsity and loss information. Disadvantage: increased complexity and expensive to implement.

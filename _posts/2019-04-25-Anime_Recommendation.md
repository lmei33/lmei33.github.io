---
layout: post
title:  "Anime Recommendation System"
date:   2019-03-20
excerpt: "Collaborative filtering recommendations based on Py-Surprise Framework "
project: true
tag:
- RecommendationSystem 
- CollaborativeFiltering
- Surprise
- SurpriseFramework
- Anime
- python
comments: true
---

CLICK HERE:
[Colab Notebook Version](https://github.com/lmei33/trial/blob/master/HW_7_Anime_Recommendations.ipynb)

CLICK HERE:
[Full PDF Version](https://github.com/lmei33/Miscellaneous/blob/master/Anime%20Recommendation.pdf)


      
## Overview
Anime Recommendation is a project that create collaborative filtering recommendation using SVD in Surprise framework. The recommendation is based on user preference data from 25,451 users on 12,294 animes.

The original data is from:
[Anime Recommendations Database](https://www.kaggle.com/CooperUnion/anime-recommendations-database/home)
![0](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/anime/animetitle.PNG)    

## Steps of Analysis  

### Data Preprocessing
Original dataset contains Anime.csv and Rating.csv, which is about the information of
animes and user rating. After data cleaning, we got table rating and anime_mapping:
![1](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/anime/anime1.PNG) 


From the barchart of the dataset, we can find that the rating is lower-rating-skewed. It seems that users are generous about their rating, with “8” as the most frequent rating score.
![2](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/anime/anime2.PNG) 


### Collaborative Filtering Recommendation 
I used singular value decomposition (SVD) — one of the Matrix Factorization models for identifying latent factors. With 3-fold cross-validation, we got the mean RMSE/MAE.

![3](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/anime/anime3.PNG) 

If we take user_id = 45 as an example, the above one is the animes with high ratings from the user, and the below one is what will be recommended based on collaborative filtering recommendation:

![4](https://raw.githubusercontent.com/lmei33/lmei33.github.io/master/assets/img/anime/anime4.PNG) 


## Conclusion
* Collaborative Filtering collects and analyzes past user behavior, and predicts what users like based on their similarity to other users. The accuracy can be improved with larger dataset on users/ items.
* From the example we can find that the recommendation offers various choices with only two anime that the user has already watched. Though the recommended animes have types that are largely different from the user’s preference(mainly “TV”), they are still from the genres that the user is interested in.
* With Collaborative Filtering we may discover the possible interests of users.


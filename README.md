# Recomendation System


## Index
1. Intro & Recommendation System Workflow
2. Measure Similarity & Content-based Recommendation System
3. Evaluation of Recommendation System
4. Collaborative Filtering
5. [Matrix Factorization : SVD & Funk SVD](notebooks/5-collaborativeFiltering_funkSvd.ipynb)
6. [Collaborative Filtering with Context & Factorization Machine](notebooks/6-contextAware_factorizationMachine.ipynb.ipynb)
7. [Recommendation System for Implicit Data & Logistic Matrix Factorization](notebooks/7-implicitData_logisticMatrixFactorization.ipynb)

**Alternating Least Squares**
We add regularization in purpose to make our model can avoid overfitting, adding Ridge Regularization is what we do here.

Final Objective Function as follow :

$$
\text{Objective}= \underset{x^*,y^*}{\min} \cfrac{1}{2}
\left [
\sum_{u \in U} \sum_{n \in I} c_{ui}(p_{ui} - x_u.y_i^T)^2
\right ] + \cfrac{\lambda}{2} \sum_{u \in U} \sum_{n \in I} \left[  ||x_u||^2 + ||y_i||^2 \right]
$$

- $c_{ui} = 1 + \alpha r_{ui}$


8. [Learning to Rank & Bayesian Personalized Ranking](notebooks/8-learningToRank_bayesianPersonalizedRanking.ipynb)


## Project Tree

```
├─ .gitignore
├─ README.md
├─ assets
│  ├─ Content-based-filtering-and-Collaborative-filtering-recommendation.png
│  ├─ applsci-10-05510-g001.webp
│  ├─ collaborative_filtering.png
│  ├─ cross_validation.png
│  ├─ model_training.png
│  ├─ svd_components.png
│  └─ utility_item.png
├─ data
│  ├─ artist_name.csv
│  ├─ movies.csv
│  ├─ sample_movie_rating.csv
│  ├─ sample_user_artist.csv
│  ├─ tripadvisor_travel.csv
│  └─ user_artist_play.csv
├─ notebooks
│  ├─ 5-collaborativeFiltering_funkSvd.ipynb
│  ├─ 6-contextAware_factorizationMachine.ipynb
│  ├─ 7-implicitData_logisticMatrixFactorization.ipynb
│  └─ 8-learningToRank_bayesianPersonalizedRanking.ipynb
└─ requirements.txt
```
# Recomendation System


## Index
### 1. Intro & Recommendation System Workflow
### 2. Measure Similarity & Content-based Recommendation System
### 3. Evaluation of Recommendation System
### 4. Collaborative Filtering
### 5. [Matrix Factorization : SVD & Funk SVD](notebooks/5-collaborativeFiltering_funkSvd.ipynb)
### 6. [Collaborative Filtering with Context & Factorization Machine](notebooks/6-contextAware_factorizationMachine.ipynb.ipynb)
### 7. [Recommendation System for Implicit Data & Logistic Matrix Factorization](notebooks/7-implicitData_logisticMatrixFactorization.ipynb)
#### Alternating Least Squares
<p> We add regularization in purpose to make our model can avoid overfitting, adding Ridge Regularization is what we do here. <p>
<p> Final Objective Function as follow : </p>

![alt text](assets/formula/equation_als_white.png)

where : 
- $x_u$ : User factor , matrix `<n_users x n_factor>`
- $y_i$ : Item factor , matrix `<n_items x n_factor>`

with : 
- $c_{ui} = 1 + \alpha r_{ui}$
- $c_{ui} = 1 + \alpha r_{ui}$ have similar size to utility matrix `<n_users,n_items>`
- $p_{ui} = \begin{cases} 1 & r_{ui} > 0 \\ 0 & r_{ui} < 0 \end{cases}$ have similar size to utility matrix `<n_users,n_items>`

- $r_{ui}$ : Implicit data feedback from user u to item i

#### Prediction Function
The pediction is generated from dot product between user and item factor :
- $\hat{p_{ui}} = x_u \cdot y_i^T$

#### Optimization

##### User Factor ($x_u$)
To find user factor we can solve analytically with Alternating Least Squares
$x_u = (Y^T.C^u.Y + \lambda I )^{-1} \cdot (Y^T.C^u.p(u))$

with :
- $Y^T$ : Item Factor (Constant) Transposed
- $Y$ : Item Factor (Constant)
- $\lambda I$ : Regularization Term multiply by identity matrix
- $C^u$ : Confidence from user u to all item , diagonal matrix, has shape of `<n_item x n_item>`
- $p(u)$ : preference from user u, contain binary value of preference (0/1) for all item

##### Item Factor ($y_i$)


To find user factor we can solve analytically with Alternating Least Squares
$yi = (X^T.C^i.X + \lambda I )^{-1} \cdot (X^T.C^i.p(i))$

with :
- $X^T$ : User Factor (Constant) Transposed
- $X$ : User Factor (Constant)
- $\lambda I$ : Regularization Term multiply by identity matrix
- $C^i$ : Confidence from item i to all user , diagonal matrix, has shape of `<n_user x n_user>`
- $p(i)$ : preference from item i contain binary value of preference (0/1) for all user






### 8. [Learning to Rank & Bayesian Personalized Ranking](notebooks/8-learningToRank_bayesianPersonalizedRanking.ipynb)


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
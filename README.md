# Product_Recommender_System_LLM_NLP
Personalized product recommendation system using Amazon Electronics data. Combines collaborative filtering, NLP, and LLM evaluation to optimize user experience. Includes model tuning, precision-recall evaluation, and real-world deployment insights.

# Amazon Electronics Product Recommendation System

This repository showcases a recommendation system project built using Natural Language Processing (NLP), Large Language Models (LLMs), and collaborative filtering techniques. The system provides personalized product recommendations based on historical user-product ratings from Amazon's electronics category.

## 🧠 Objective
The goal of this project is to design a data-driven recommendation engine that can effectively predict user preferences for unseen products using various collaborative filtering approaches. This work demonstrates proficiency in data preprocessing, exploratory data analysis (EDA), and building multiple recommendation models, including hyperparameter tuning and model evaluation using metrics like Precision@K, Recall@K, and F1-score.

## 📊 Dataset

- **Source:** Amazon Electronics Review Dataset  
- **Rows:** 7,824,482 → filtered to 65,290 after cleaning  
- **Attributes:**
  - `user_id`: Unique identifier for each user
  - `prod_id`: Unique identifier for each product
  - `rating`: User's rating of the product (1 to 5)
  - `timestamp`: Time of rating (excluded from modeling)

To enhance model performance and ensure computational feasibility, we filtered:
- Users with at least **50 ratings**
- Products with at least **5 ratings**

## 🔍 Steps Followed

1. **Data Loading & Preprocessing**
   - Removed sparse users/products
   - Dropped unused timestamp column

2. **Exploratory Data Analysis**
   - Visualized rating distributions
   - Analyzed user/product activity
   - Summary statistics and sparsity checks

3. **Baseline Models**
   - **Popularity-based Recommender** using average ratings

4. **Collaborative Filtering Approaches**
   - **User-User Similarity** using KNN with cosine distance
   - **Item-Item Similarity** using KNN
   - **Matrix Factorization** using SVD
   - **Co-Clustering Algorithm**

5. **Model Evaluation**
   - Precision@K, Recall@K, F1-Score
   - RMSE of predicted ratings
   - Predicted ratings for seen & unseen users/items
   - GridSearchCV for hyperparameter tuning

6. **Recommendation Functionality**
   - Custom function to recommend top-N items
   - Showcases personalized recommendations

## 🛠 Libraries & Tools

- Python
- Pandas, NumPy
- Matplotlib, Seaborn (for EDA)
- `scikit-surprise` (for recommendation models)
- Google Colab / Jupyter Notebook
- GridSearchCV (for tuning)

## ⚙️ Key Functions

- `top_n_products()`: Ranks products by average rating with interaction threshold
- `precision_recall_at_k()`: Evaluates model relevance performance
- `get_recommendations()`: Returns top-N personalized product suggestions
- `GridSearchCV()`: Finds optimal KNN parameters

## 📈 Model Performance

| Model Type           | RMSE   | Precision@10 | Recall@10 | F1@10  |
|----------------------|--------|--------------|-----------|--------|
| User-User KNN (base) | 1.02   | 0.848        | 0.857     | 0.852  |
| User-User (tuned)    | 0.969  | 0.846        | 0.897     | 0.871  |
| Item-Item (tuned)    | 0.974  | 0.830        | 0.852     | 0.841  |

## 🎯 Sample Predictions

- For user who rated product `1400501466`:
  - Predicted: 4.59 (Optimized), 4.73 (Baseline)
- For a new user on the same product:
  - Predicted: 4.30 (Optimized), 1.75 (Baseline)

## 📄 Project Notebook

You can find the full code and implementation details in:
- `Recommendation_Systems_Learner_Notebook_Full_Code.ipynb`
- `Recommendation_Systems_Learner_Notebook_Low_Code.ipynb`
- `MBaaoum_Project3.pdf` (detailed PDF report)

## 👤 Author

Mohammed Baaoum — [LinkedIn](https://www.linkedin.com/in/mbaaoum)

## 🏷️ Tags
`Recommender Systems`, `Collaborative Filtering`, `NLP`, `LLM`, `Surprise`, `Amazon Reviews`, `Python`, `Machine Learning`, `EDA`, `Evaluation Metrics`, `AI Projects`

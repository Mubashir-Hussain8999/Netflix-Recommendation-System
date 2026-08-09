# Netflix Movie Recommendation System

## Project Overview

This project develops a movie recommendation system using the Netflix movie ratings dataset.

The system analyzes user-movie ratings and uses a collaborative filtering approach to predict the ratings a specific user may give to movies. The recommendation model is built using **SVD (Singular Value Decomposition)** from the Surprise library.

The final system predicts estimated ratings for movies and recommends the **Top 5 movies** for a selected user.

## Objectives

- Analyze the Netflix movie ratings dataset
- Perform data cleaning and preprocessing
- Extract Movie IDs from the raw dataset
- Analyze customer and movie rating activity
- Filter less-rated movies and inactive customers
- Build a collaborative filtering recommendation model
- Use SVD for rating prediction
- Evaluate the model using RMSE
- Generate personalized movie recommendations for a specific user

## Dataset

The project uses the Netflix movie ratings dataset.

The main dataset contains:

- `Cust_Id` - Customer/User ID
- `Rating` - Rating given by the customer
- `Movie_Id` - Movie ID

A separate movie titles dataset is also used:

- `Movie_Id` - Movie ID
- `Year` - Movie release year
- `Name` - Movie name

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Surprise
- Jupyter Notebook

## Project Workflow

### 1. Data Loading

The Netflix ratings data and movie titles data are loaded using Pandas.

### 2. Data Exploration

The dataset is explored to understand:

- Number of movies
- Number of customers
- Total ratings
- Rating distribution
- Dataset structure
- Missing values

### 3. Data Preprocessing

Movie IDs are extracted from the raw dataset and added as a separate `Movie_Id` column.

Rows with missing ratings are removed and the `Cust_Id` column is converted to integer format.

### 4. Pre-filtering

To improve the recommendation process, the project filters:

- Movies with fewer ratings than the selected benchmark
- Customers with fewer ratings than the selected benchmark

The benchmarks are calculated using the 60th percentile of movie and customer rating counts.

### 5. Model Building

The **SVD (Singular Value Decomposition)** algorithm is used to build the recommendation model.

The model is implemented using the `Surprise` library.

For faster execution, the project uses the top 100,000 rows of the prepared dataset for model training.

### 6. Model Evaluation

The recommendation model is evaluated using:

**RMSE (Root Mean Squared Error)**

A **3-fold cross-validation** approach is used for evaluation.

### 7. Personalized Recommendation

A specific customer is selected and their previous ratings are analyzed.

The trained SVD model predicts estimated ratings for available movies.

Movies are sorted according to their estimated ratings and the **Top 5 movies** are recommended to the selected user.

## Recommendation Approach

The project follows a collaborative filtering approach.

```text
User Ratings
     ↓
Data Cleaning
     ↓
Movie & Customer Filtering
     ↓
SVD Recommendation Model
     ↓
Predicted Ratings
     ↓
Sort by Estimated Rating
     ↓
Top 5 Movie Recommendations

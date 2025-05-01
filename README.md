# Book_Ratings_Recommender
Books Rating Predtictor - Recommender Systems

Collaborative Filtering Book Recommendation System

👩‍💻 Author
Riya Disawal

📝 Overview

This project implements an Item-Item Collaborative Filtering algorithm to predict user ratings for books they have not yet rated. The model is evaluated using the Mean Absolute Difference (MAD) metric on a held-out test set.

The algorithm relies on the assumption that users tend to rate similar items similarly. Therefore, by computing item similarity using cosine similarity and leveraging the ratings a user has given to similar items, the system predicts unknown ratings.

💡 Algorithm & Implementation Details
Collaborative Filtering Approach: Item-Item (Book-Book)

Similarity Metric: Cosine Similarity

Prediction Strategy:
For a target book, find the k most similar books that the user has already rated.
Predict the rating using a weighted average of ratings, weighted by item similarity.

Data Preprocessing:
Ratings with value 0 are treated as missing and removed.
Users and books with very few ratings are filtered to reduce matrix sparsity.

Train-Test Split:
The dataset is split randomly by (User-ID, ISBN) pairs (not by user or book).
The test set only includes users and books that exist in the training set to ensure valid predictions.

Evaluation:
The model is evaluated using Mean Absolute Difference (MAD) between predicted and actual ratings.
MAD is calculated across different neighborhood sizes (k = 5, 10, 15, 20, 50, 100).
It is also evaluated across different train/test splits from 60% to 90% in 5% increments.

🚀 How to Run
Clone or download this repository.

Place the dataset files in the same directory:

Ratings.csv (Used in the code)

Users.csv (Available)

Books.csv (Available)

Run the main Python script:

python Collaborative_Filtering.py

Note: Ensure the dataset files are properly formatted with UTF-8 or Latin-1 encoding if needed.

📦 Dependencies

This project uses the following Python libraries:

pandas, numpy, scikit-learn, tqdm (for progress bars)

You can install all dependencies using:

pip install pandas numpy scikit-learn tqdm

📊 Example Output

k = 5, MAD = 1.2034

k = 10, MAD = 1.1891

k = 15, MAD = 1.1778
...




📁 File Structure

Collaborative_filtering.py         # Main collaborative filtering implementation

Ratings.csv              # Ratings data (User-ID, ISBN, Book-Rating)

Books.csv                # Book metadata

Users.csv                # User metadata

README.md                # This file

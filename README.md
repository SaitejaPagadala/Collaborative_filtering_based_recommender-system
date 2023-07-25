# Collaborative_filtering_based_recommender-system
This repo is for project on Collaborative filtering based recommender system

The dataset can be found at this link: https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset

# Creating a Book Recommender with Collaborative Filtering

Recommender systems are useful for discovering products and content that aligns with your interests. I recently built a simple book recommendation system using collaborative filtering in Python. In this post, I'll walk through the approach.

## The Data

I used 3 datasets:
- Books - containing book titles, authors, year published, etc
- Users - with user IDs and location 
- Ratings - detailing user IDs, book IDs, and ratings

After loading into Pandas, I did some exploration to understand the data better before diving into modeling.

## Building the Collaborative Filter

Collaborative filtering looks at patterns of ratings across users and items to make suggestions. The key steps:

1. Filtered datasets to only most active users and most rated books. This gives more robust data to find signals.

2. Created a user-book ratings matrix with book titles as columns and user IDs as rows. Filled any missing values with 0. 

3. Calculated the cosine similarity between each pair of books based on their user rating patterns. This identifies book pairs that tend to get similar ratings from users.

4. Wrote a function to retrieve the most similar books to a given book title. It uses the calculated cosine similarities to find books rated similarly by users.

## Results

Despite its simplicity, the collaborative filter was able to come up with decent book recommendations based on similar rating behavior. With more tuning and additional data, the quality could likely be improved further.

## Next Steps 

Some ideas for enhancing the recommender:
- Incorporate metadata like authors, genres, text descriptions
- Apply matrix factorization for lower-dimensional embeddings
- Evaluate models using precision, recall or RMSE

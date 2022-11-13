## Recommendation system with implicit data using collaborative recommendation model
### Libraries used
Pandas, scipy.sparse, numpy, random, sklearn.preprocessing and Implicit Library, a Fast Python Collaborative Filtering for Implicit Datasets is used for matrix factorization.
### Alternating Least Squares Recommender Model Fitting
Instead of representing an explicit rating, to represent a “confidence” in terms of how strong the interaction was, a read_strength was created by creating weights for time spent (reading_time * read_percent). Books with a larger number of read_strength by a person can carry more weight in our ratings matrix of read_strengh.
To get around “negative integer” warning, I will have to create numeric user_id and pratilipi_id columns
Created two matrices, one for fitting the model (pratilipi-user) and one for recommendations (user-pratilipi).
Initialized the Alternating Least Squares (ALS) recommendation model and Fit the model using the sparse content-person matrix, type of the matrix is set to double for the ALS function to run properly.
### Finding the Similar Articles
To find the top 10 most similar books for user_id = 450, The user and pratilipi vectors from trained model is used and calculated the vector norms and the similarity score.
### Recommend Articles to Persons
The recommend function will return the top 10 recommendations chosen based on the user/ pratilipi vectors for user never interacted with for any given user.
•	The interactions score from the sparse person content matrix is created.
•	Added 1 to everything, so that books with no interaction yet become equal to 1.
•	Make books already interacted zero.
•	Dot product of user vector and all pratilipi vectors is created.
•	Scaled the recommendation vector between 0 and 1.
•	pratilipi already interacted have their recommendation multiplied by zero.
•	Sort the indices of the content into order of best recommendations.
•	Start empty list to store titles and scores.
•	Append titles and scores to the list.
•	Get the trained user and pratilipi vectors. Converted them to csr matrices.
•	Create recommendations for person with id 50.


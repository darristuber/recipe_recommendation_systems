# recipe_recommendation_systems
Project 1 from Applied Data Science Course. Utilized content and collaborative based recommendation systems to provide new recipes based on previous recipe or user id respectively. 

Extended Project Description:

In this project, I focused on various related datasets on customer interaction and recipes. The data content is from Food.com, and was amassed by Maunder et al.. I retrieved the data content from Kaggle (https://www.kaggle.com/datasets/shuyangli94/food-com-recipes-and-user-interactions?select=ingr_map.pkl). Specifically I utilized the PP_recipes, PP_users, raw_rec, and raw_int datasets. 

To build a content recommender system, I first created a new dataset with meaningful tokens. Many cells of the database were lists formatted as strings, so I reformatted them as lists. I also separated the nutrition column into decipherable information, since nutritional content is important when comparing recipes. To better compare these factors, I added new columns to classify the calorie, fat, sugar, sodium, and protein content as low, medium, or high respective to the other recipes. I then merged additional columns from PP_recipes and raw_rec to allow more recipe factors to be identified with the ID and name. 

A combined_features column was then created to collect all the desired identity tokens for each recipe in a single column. A smaller sample was used due to computing limitations. A count vectorizer was used to make a vector for each row of the data frame based on combined features so that a cosine similarity matrix could be applied.

Next, I built a collaborative filter for the dataset. I created a new data frame with just the user ID, recipe ID and recipe rating information. Again, a smaller sample was used to speed up the time to run the code. I then created a user-item matrix with the new data frame. Ager running singular value decomposition, I reconstructed the predicted ratings. And got the specified number of recipe names from the top value ratings and IDs.


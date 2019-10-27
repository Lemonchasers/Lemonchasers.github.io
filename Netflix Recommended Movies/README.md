# DSC-680-Portfolio
# Recommendation Model

The code found in this folder is for a recommendation model that was created
in order to find a list of new movies for a customer based on how similar
they are to other netflix users. The data was provided from Kaggle.

### Summary
The recommendation model works by cleaning the data first and getting it into a workable state. Once this has been achieved, The PreProcess function takes a given customer id. Then it filters our dataset for the movies that customer rated. Then we get a list of just those movies and apply it back to the overall dataset. This way when we run a our model, the nearest neighbors aren't the ones with many 0's for ratings. From the PreProcessing function we receive a matrix to use with filtered values necessary for modeling.

The matrix_prep function takes the processed matrix and groups it so that we get a nxm matrix where n are the customers
and m are the movies they rated. If there is a movie a customer has not rated it gets a 0. The output is a sparse matrix 
with these results.

Finally, the Recommendation function takes the sparse matrix from the matrix_prep function, the customer id, 
and how many neighbors you want your model to have. The model is a nearestneighbor model that caluclates the 
cosine similarity between the provided customer and the other customers that rated the at least one of the
movies that the customer rated. 

Then we loop through the customers pulling out the similar customers and put this in a list. We then use this 
list to go back and filter for these customers movies that they rated a 4 or 5. Then we grab this list of movies
and this is the list returned.

### Links
[Jupyter Notebook](https://github.com/Lemonchasers/Lemonchasers.github.io/blob/master/IMDB%20Webscraper/DSC%20540%20Final%20Chase%20Lemons.ipynb)

[Back](/Lemonchasers.github.io/Index.md)

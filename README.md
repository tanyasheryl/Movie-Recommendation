## Movie-Recommendation

This project mainly uses four approaches to build a Recommendation model for the movies dataset. 

* Content-Based Filtering
* Collaborative Filtering
  - Memory Based Filtering 
  - Model-Based Filtering
* Hybrid Filtering

### Content based filtering 
Content based recommender systems use some kind of past browsing history of the user to recommend a new list. It uses item factors like overview, genres, cast, crew and tags to find the similarity between the movies and thereby generate an item matrix. Based on the user's previous preferences combined with the similarity of movies, it recommends a list of movies. Movie features like overview, genres etc. are text data and hence we need to convert this into the vector space to calculate the similarity. We use the Term Frequency- Inverse Document Frequency (TF-IDF) to convert the word to its vector form and thereby determine the importance of each feature. TF is the relative frequency of any word in the document and IDF is the inverse of document frequency which is the count of documents containing the words. Once we calculate the TF-IDF, we use the Vector Space Model to compute the proximity between different vectors. There are different parameters to calculate the similarity between two vectors: Cosine similarity, Dot Product and Euclidean Distance. Now, we can rank and sort the movies according to this similarity matrix.
### Collaborative Filtering
This method uses similarity between the items and users to recommend movies to the users. It analyses the neighbors of users to make recommendations. It is based on the approach that users who liked the same movies in the past would like the same in the future. This filtering takes user feedback into consideration and user feedback can be categorized into Implicit and Explicit. Implicit feedback assumes that if a person watches a movie, then he is interested.  Explicit feedback relies on user ratings to make decisions. In this project, I will use the Explicit feedback to make recommendations. There are two types of memory based collaborative methods- Item based CF and User-based CF.
### Model Based Collaborative - Matrix factorization: 
It decomposes the high dimensional user-item matrix to a product of lower dimensional matrices. In this model, let’s say we have a feedback matrix (A) where the rows show each user(U) and the columns represent the movies(V).  The feedback matrix can be represented as UVT. For an entry (i, j) the observed feedback matrix is (Ui, Vj) and the actual value would be Ai,j. The objective of this is to minimize the squared errors over all the entries in the matrix. One of the ways to do this is use Singular Value Decomposition (SVD). In this project, I will be using the matrix factorization to implement Collaborative filtering.
### Hybrid Recommenders:
Both Content based filtering and Collaborative filtering has its advantages and disadvantages and we can combine both these models to form a hybrid model. This can be achieved in multiple ways: either by building CF and CBF separately and then combining them or by doing them one after the other or incorporating one into the other.

## Dataset

In this project, I will be working on the Movies dataset from [Kaggle](https://www.kaggle.com/rounakbanik/the-movies-dataset). These files contain metadata for all 45,000 movies listed in the Full MovieLens Dataset. It contains 5 data files containing information regarding the movie metadata, credits, ratings, keywords and links. This dataset is an ensemble of data collected from GroupLens and TMDB. 



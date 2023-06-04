# Movie_Recommendation_System
The basic concept behind a movie recommendation system is quite simple. In particular, there are two main elements in every recommender system: users and items. The system generates movie predictions for its users, while items are the movies themselves.

The primary goal of movie recommendation systems is to filter and predict only those movies that a corresponding user is most likely to want to watch. The ML algorithms for these recommendation systems use the data about this user from the system’s database. This data is used to predict the future behavior of the user concerned based on the information from the past.

**How to Build a Movie Recommendation System?**

Once we’ve discussed the basics of film recommendation engines in machine learning, we can move on to building an actual movie recommendation system. So, we need to build an engine that learns and recognizes patterns in a user’s viewing history before using these patterns to generate new recommendations. What’s required for this?

Data. ML systems need data, so find and import the essential libraries with movie datasets that already have global ratings.
Analysis. Create generic recommendations of top-rated movies from the existing dataset.
Personalization. Get personalized ratings by providing your own movie scores.
Strategy. Implement content-based or collaborative filtering strategy.
Combination. Combine recommendation lists to get a reasonable estimate across the ratings. The combined dataset of movie ratings can now be used for either filtering model.
In a nutshell, all it takes to build a movie recommendation engine is to analyze the data, build the recommendation system, and get recommendations. 

A) Content-Based Movie Recommendation Systems
Content-based methods are based on the similarity of movie attributes. Using this type of recommender system, if a user watches one movie, similar movies are recommended. For example, if a user watches a comedy movie starring Adam Sandler, the system will recommend them movies in the same genre or starring the same actor, or both. With this in mind, the input for building a content-based recommender system is movie attributes.

B) Collaborative Filtering Movie Recommendation Systems
With collaborative filtering, the system is based on past interactions between users and movies. With this in mind, the input for a collaborative filtering system is made up of past data of user interactions with the movies they watch.

For example, if user A watches M1, M2, and M3, and user B watches M1, M3, M4, we recommend M1 and M3 to a similar user C. You can see how this looks in the figure below for clearer reference.



This data is stored in a matrix called the user-movie interactions matrix, where the rows are the users and the columns are the movies.

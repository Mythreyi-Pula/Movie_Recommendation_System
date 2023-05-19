# Movie_Recommendation_System
import numpy as np
import pandas as pd
import difflib
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.metrics.pairwise import cosine_similarity


movies_data = pd.read_csv('/content/movies.csv')

movies_data.head()

movies_data.shape

selected_features=['genres','keywords','tagline','cast','director']
print(selected_features)

for feature in selected_features:
  movies_data[feature]=movies_data[feature].fillna('')

combined_features=movies_data['genres']+''+movies_data['keywords']+''+movies_data['tagline']+''+movies_data['cast']+''+movies_data['director']
print(combined_features)

vectorizer=TfidfVectorizer()


feature_vectors=vectorizer.fit_transform(combined_features)

print(feature_vectors)

cosine similarity


cosine_sim=cosine_similarity(feature_vectors)

print(cosine_sim)

cosine_sim.shape

movie_name=input('enter your fav movie name:')


list_of_all_titles=movies_data['original_title'].tolist()
print(list_of_all_titles)

find_close_match = difflib.get_close_matches(movie_name , list_of_all_titles)
print(find_close_match)


close_match=find_close_match[0]
print(close_match)

index_of_the_movie=int(movies_data[movies_data.original_title == close_match]['index'].values[0])
print(index_of_the_movie)


similarity_score = list(enumerate(cosine_sim[index_of_the_movie]))
print(similarity_score)
len(similarity_score)

 sorted_similiar_movies=sorted(similarity_score,key=lambda x:x[1],reverse=True)
 print(sorted_similiar_movies)

print('movies suggested for you:\n')
i=1
for movie in sorted_similiar_movies:
  index=movie[0]
  title_from_index=movies_data[movies_data.index==index]['title'].values[0]
  if (i<20):
    print(i,'-',title_from_index)
    i+=1

movie_name=input('enter your fav movie name:')
list_of_all_titles=movies_data['original_title'].tolist()
find_close_match = difflib.get_close_matches(movie_name , list_of_all_titles)
close_match=find_close_match[0]
index_of_the_movie=int(movies_data[movies_data.original_title == close_match]['index'].values[0])
similarity_score = list(enumerate(cosine_sim[index_of_the_movie]))
sorted_similiar_movies=sorted(similarity_score,key=lambda x:x[1],reverse=True)
print('movies suggested for you:\n')
i=1
for movie in sorted_similiar_movies:
  index=movie[0]
  title_from_index=movies_data[movies_data.index==index]['title'].values[0]
  if (i<30):
    print(i,'-',title_from_index)
    i+=1

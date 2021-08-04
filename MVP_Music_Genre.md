# Interpreting Song Genres Using Lyrics and Music

## MVP

My original project proposal involved classification of song emotions, or the feelings people have while listening to them, based on lyrics and musical features. I found several music research datasets complete with lyric analysis using NLP. However, the target of feeling was not readily available. Previous research had used live test subjects to achieve this target, though that is not within the scope of this project. I used spotipy, a python API for Spotify, to download millions of songs from thousands of playlists with the target variable in the title: happy, sad, angry, or chill(relaxed). Despite the quantity of songs, after dropping duplicates 7M songs narrowed down to 158,000. Then merging on the research dataset yielded 10,800 matches. This would have worked if each match was unique. However, only 3,100 songs were labeled with just one feeling, while the rest were multi-labeled. The question of my project has now changed to genre classification using lyrics and musical features.

The project will use a dataset with >28,000 mostly recognizable songs categorized into 7 genres: pop, country, blues, jazz, rock, reggae, and hip-hop. The distribution is not perfect, and may require some resampling strategies.

![image.png](attachment:image.png)

Here are two key musical features, energy and valence, plotted by target. There are a lot of data points, but they appear to have some relevance to the genres.

![image.png](attachment:image.png)

Energy and valence correlation to genre is more clear in the following box plots.
![image.png](attachment:image.png)
![image-2.png](attachment:image-2.png)

Initial fit with all features on K Nearest Neighbors does not look good.

- The score for kNN is

- Training:  53.38%

- Test set:  32.16%

Here is K Nearest Neighbors using only energy and valence as features.

- The score for kNN is
- Training:  46.64%
- Test set:  23.40%

I also ran it through logistic regression just to see.

- The score for logistic regression is
- Training:  37.88%
- Test set:  37.20%

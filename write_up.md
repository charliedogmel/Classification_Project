# Interpreting Song Genres Through Lyrics and Music
Melissa Cooper

## Abstract
Music genre prediction is a big industry today with all the music streaming services available and the overall love of music by all people. This project explores the question of if it's possible to interpret genres accurately using a song's lyrics and audio metadata. I worked with data from a research paper (1) containing topic distributions of lyrics (using Natural Language Processing(NLP)) and audio metadata from songs over the last 7 decades (1950-2019). With seven genres to predict, modeling with random forest provided the best results.    

## Design

Genre classification can be done many ways. Whether or not it could be done using only lyric analysis and musical features posed an interesting question. Since we have not learned NLP yet, it was convenient that I found a dataset with the lyrics already analyzed by NLP using  Latent Dirichlet Allocation (LDA). This topic modelling shows what proportion of a song's lyrics fit into each topic or category. Topics range from sadness and feelings to obscene and violence. The musical features, or audio metadata, originate from Spotify and describe the musicality of each song as being danceable, acoustic, loud, etc. In particular, I anticipate energy and valence to be important features in the model results. Energy represents a measure of intensity and activity, and valence describes how positive a track sounds. It will also be interesting to observe the impact of the LDA topics.

## Data
There are over 28,000 unique songs in the dataset with 23 numerical features and 7 genre targets of pop, country, blues, rock, jazz, reggae, and hip hop. I analyzed the features extensively to determine feature importance using a boxplot for each feature/target and a correlation matrix. In the end, my own feature importance determination lined up well with the model's feature importance chart. 

## Algorithms

*Feature Engineering*
1. Correlation matrix to see relationships
2. Individual boxplots to view each feature/target importance
3. Analysis of LDA topics, many of which seemed odd or obscure

*Models*
  
Baseline models included k-Nearest Neighbors, logistic regression, Naive Bayes, and random forest classifiers. Random forest exhibited the strongest baseline score and was chosen as the model.

*Model Evaluation and Selection*
  
The data splitting structure was 60/20/20 for training/validating/testing the model. Many iterations were performed over many different feature combinations and hyperparameter tuning. The feature iterations included: the eight most important features being added one by one, only audio features plus release year, only LDA features plus release year, all features, and removed the least important features one by one. I also plotted the validation score of several hyperparameters in order to choose the best values. The test data was used only at the end after the model was finalized for a final estimate of generalization performance.

Accuracy was the chosen metric and improved throughout the process. Despite much hyperparameter tuning, there were only two that made the best improvement: class weights and a higher number of trees.The official metric for DrivenData was classification rate (accuracy); however, class weights were included to improve performance against F1 score and provide a more useful real-world application where classification of the minority class (functional needs repair) would be essential.

**Final random forest 10-fold cross-validation scores:**
- all features except one with class weights and 750 trees

       genre  precision    recall  f1-score   support

       blues       0.42      0.25      0.31       921
     country       0.47      0.58      0.52      1089
     hip hop       0.69      0.53      0.60       181
        jazz       0.53      0.45      0.49       769
         pop       0.43      0.59      0.50      1409
      reggae       0.53      0.49      0.51       499
        rock       0.51      0.36      0.42       807

Validation accuracy:  0.4704140969162996

**Test holdout**

       genre  precision    recall  f1-score   support

       blues       0.48      0.30      0.37       921
     country       0.47      0.60      0.53      1089
     hip hop       0.65      0.48      0.55       181
        jazz       0.55      0.41      0.47       769
         pop       0.40      0.56      0.46      1408
      reggae       0.52      0.48      0.50       500
        rock       0.46      0.32      0.38       807

Test accuracy:  0.4606167400881057

## Tools

- SQLite, Numpy, and Pandas for data manipulation
- Scikit-learn for modeling
- Mlxtend, Matplotlib, and Seaborn for plotting
- spotipy - python Spotify API used to find 7M songs for an initial classification project idea that did not work out

## Communication
Presentation, slides, and write-up

(1) Moura, Luan; Fontelles, Emanuel; Sampaio, Vinicius; França, Mardônio (2020), “Music Dataset: Lyrics and Metadata from 1950 to 2019”, Mendeley Data, V3, doi: 10.17632/3t9vbwxgr5.3
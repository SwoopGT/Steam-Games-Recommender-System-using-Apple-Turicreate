# Steam-Games-Recommender-System using Apple Turicreate

## 1.Introduction

Steam is a video game digital distribution service provided by Valve. It is the largest platform in the video game distribution genre by player base.[1]

Users of Steam can download games digitally into their profile library. Games can be purchased and gifted between users and these games stay until deleted by the user himself.

Kaggle completion involving datasets for steam users and the games in their libraries was used for the analysis. Further information provided was the number of hours a particular user has played the game. The aim of the analysis was to build a recommender system which could accurately suggest games to other users which they haven’t played yet.

</br>

## 2.Business Problem

The main question is- depending upon the number of games purchased by the users and the amount of time in hours spent in playing the games, what different games can be suggested to different users using a recommender system?
This report aims to put forward an analysis of building a recommender system to recommend games to users with similar interests.

</br>

## 3.People interested in the Project – Target Audience

The target audience in this scenario are the people – gamers, who would like to be recommended with similar games according to their interests.

</br>

## 4.Data required

The data required to build a model to predict customer satisfaction is as follows:
User Data: Data pertaining to the users and games played is provided by the Kaggle user for analysis.

</br>

## 5.Methodology

The following steps were employed to obtain the required results:
</br>

#### 5.1 Importing Necessary Libraries

The first step is to import the necessary libraries and packages.
Numpy – For numerical calculations
Pandas – Data manipulation
Turicreate – Machine Learning library for Recommender Systems

</br>

#### 5.2 Google Drive Pre - Requisites

This step involves the authentication steps taken in order to use the dataset stored in Google Drive which can be directly loaded into Google Colab.

</br>
 
#### 5.3 Pre-Processing

The following preprocessing steps were employed:
1. Checking the shape of the dataset
2. Checking the data types of the columns (features) present in the dataset
3. Removal of unwanted columns
4. Getting statistical information from the dataset
5. Displaying brief information on the dataset
6. Creating a new dataframe as per requirement by merging

</br>

#### 5.4 Ranking

The dataset provided is without a rating column for the games played by the user. The next step included creation of a ranking system depending upon the game hours played by a user.

This ranking system will be used as a rating system by grouping the dataset by users and games and then using the ( pd.cut ) command on it. This results in a rating of 10 for the top games played by the user and the remaining accordingly.

</br>

#### 5.5 Recommender Systems – User Recommendations

Using the Turicreate library provided by Apple, the following three recommender systems were built:
1. Factorization Recommender
2. Ranking Factorization
3. Item Similarity Recommender

</br>

##### 5.5.1 Creation of SFrame
The use of Turicreate library requires a SFrame which is created from the original dataframe.

</br>

##### 5.5.2 Building of Recommender Systems

1. Factorization Recommender – Observed ratings are modeled as a weighted combination of terms, where weights are learned from data.

2. Ranking Factorization Recommender – Recommends items that are both similar to items in a user’s dataset and if rating is given, which item would be rated highly by the user.

3. Item Similarity Recommender – Computes the similarity between each pair of items and recommends items to each user that are closest to items they have already used and liked.[2]

</br>

##### 5.5.3 Display the results
The recommendations for the top 5 users were obtained and compared in the Results section.

</br>

#### 5.6 Reduction of Dataset
The dataset is optimized by removal of all the users with less than 5 games in their steam library.

</br>

#### 5.7 Recommendation Systems – Testing and Evaluation
This step involves the following steps:

</br>

##### 5.7.1 Convert into SFrame
The optimized dataset is converted to a SFrame.

</br>

##### 5.7.2 Splitting the optimized dataset into Train and Test set
Obtained SFrame is split into a Training set and a Test set.

</br>

##### 5.7.3 Training and Evaluation
The model is trained on the training set for all the three recommender systems and then model performance is evaluated on the testing set using RMSE as a metric.

</br>

##### 5.7.4 Comparison of improvement in model performance
The results obtained from this step are presented in the result section where the performance of the models are compared.

</br>

#### 5.8. Metrics for Evaluation
The following metrics were used for evaluation: RMSE

</br>

## 6.Results

With the removal of users with very less amount of games played, the RMSE decreases considerably.

For the Factorization Recommender, the percentage decrease was 8.2 percent.
For the Ranking Factorization Recommender, the percentage decrease was 34.82 percent.
For the Item Similarity Recommender, the percentage decrease was 19.64 percent.

Thus the performance of Ranking Factorization Recommender increases considerably by the removal of redundant information.

</br>

## 7.Limitations

The model's performance could have been further improved if the actual ratings provided by users were available.

</br>

## 8.Conclusion

Using Google Collab, the dataset stored in Google Drive was loaded. Pre-processing steps were carried out and using the Turicreate library, 3 recommender systems were built. Dividing the data into the training set and testing set, the performance of these systems were compared.

The dataset was further optimized and the process was repeated. The evaluated model performances were compared for unoptimized and optimized models. The RMSE score improves with the removal of users with less than 5 games played.

</br>

## 9. References

Steam, “Steam (Service),” [Online]. Available at: https://en.wikipedia.org/wiki/Steam_(service)
Apple, “Turicreate,” [Online]. Available at: https://apple.github.io/turicreate/docs/userguide/recommender/choosing-a-model.html

</br>

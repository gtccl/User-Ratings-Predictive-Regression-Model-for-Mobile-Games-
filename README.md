## Predicting User Ratings of Mobile Games 

### Background
The mobile phone games industry has become increasingly popular over the years with the introduction of smart phones. As technology has advanced, smartphones and their gaming ability have turned into major sources of profits for companies. 

Whether it be on public transport, waiting for family and friends at meet-up locations or just taking the time at the end of the day to unwind, these platforms offer unlimited opportunies for people to escape into games.
Mobile games are also easy to download and can be played on the go without investing into any special equipment making it a valuable source of entertainment.

User reviews are just one factor among many that affect gaming sales. Game developers can leverage positive reviews to increase excitement and attract players. Game ratings can play a pivotal role in purchasing the game and gamers may have varying thresholds for ratings which affect their buying.

#### Business Problem - Predicting User Ratings of Mobile Strategy Games
Objective: To create a predictive multiple regression model to predict the user rating of a mobile strategy game.

Using this tool, game developers can create a mobile strategy game that capitalises on features that lead to increased user ratings. Mobile game ratings are a crucial metric for developers and companies to gauge the success of their games and overall revenue generation.

#### Data
This dataset, '17K Mobile Strategy Games' was downloaded from Kaggle. This can be accessed with the URL https://www.kaggle.com/datasets/tristan581/17k-apple-app-store-strategy-games?resource=download .The data was collected by the owner of the dataset by mostly using the iTunes API, App Store sitemap, along with some web scraping on 3rd of August 2019.

Column Names and Descriptions:
* URL - The URL for the mobile game
* ID - The assigned ID for the game
* Name - The name of the game
* Subtitle - The secondary text under the name.
* Icon URL - The URL for the game icon
* Average User Rating - Rounded to nearest 0.5, requires at least 5 ratings.
* User Rating Count - Number of ratings internationally, null means it is below 5
* Price - Price in USD
* In-app Purchases - Prices of available in-app purchases
* Description - Mobile Game App description
* Developer - App developer
* Age Rating - Either 4+, 9+, 12+ or 17+
* Languages - Language codes using ISO Language Codes
* Size - Size of the app in bytes
* Primary Genre - The main genre of the app
* Genres - Genres of the app
* Original Release Date - When it was released
* Current Version Release Date - When it was last updated

<img width="412" alt="Screenshot 2024-02-27 at 4 43 36 pm" src="https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/a3add1c5-f608-404e-8bb7-29575819ab8e">

We can see that this dataset contains 17000 entries and 18 columns. 
Majority of this dataset is in object type which will need to be transformed befor it can be used in a multiple regression model. 

#### Data Cleaning/Preparation
Dealing with missing values, outliers
Fix data values 
Transform data types 

After cleaning, we are left with 16635 entries and 12 columns. 

#### Data Understanding, Exploratory Analysis

Let's have a look at the target variable, **Average User Rating**: The average user rating of games are rated 4.0 <br>
![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/312bdd9e-8558-4e80-bfc1-c8f5a88f3d1b)

User Rating Count: The higher the number of user ratings, the higher the rating. <br>
![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/3b513996-29af-4c1a-b43c-e015f9833cd1)

Price and In-App Purchases: Most apps are free-to-play or cost less than $5 USD as an upfront fee to download and begin playing. These apps also have low-cost in-app purchases. <br>
![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/ef1adacf-86d0-4481-945a-6933b8bd3e6b)

Languages: The most popular language is English, followed by Chinese and then German. <br>
![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/6af14a8f-ce6b-433e-822b-ee9b02c499e4)

Genres: The most popular genre is Strategy, followed by Games and Entertainment. <br>
![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/b98a49e0-cfe3-46c3-852d-080a728cd108)

Size: Majority of these mobile app games are within 7500MB in size. <br>
![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/f52b58cb-e1b7-4d4f-afe5-c35db5d172ad)


We will also visualise relationship between predictor features and the target variable. <br>
![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/8bd4e394-c3b8-46bc-9d56-83dcc36005b8)
Overall, there does not appear to be any strong relationships between the feature variables and the user ratings. 

#### Preparing the Model 
![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/33a1b67d-cdc4-45d9-a2c0-5d741d0dd5db)
There are no variables that are highly correlated with each other.

* Encode the data
* Split the data
* Scale the data

### Final Model <br>
<img width="346" alt="Screenshot 2024-02-27 at 4 54 39 pm" src="https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/ce9e4385-5533-443a-95fc-5c7ff8620442">

R^2: 0.053
Adjusted R^2: 0.048
P-value (Prob(F-Statistic)) < 0, we can reject the null hypothesis.
Train Mean Squared Error: 0.2398071778731519
Test Mean Squared Error: 0.22223161203951125

![image](https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/05bea779-3486-4767-9270-241d85168c4f)

#### Conclusions <br>
<img width="286" alt="Screenshot 2024-02-27 at 4 56 28 pm" src="https://github.com/gtccl/User-Ratings-Predictive-Regression-Model-for-Mobile-Games-/assets/153160634/05e58a5a-c699-4a85-a3eb-4fc910838d0e">

Mobile game ratings are important to developers and companies for several reasons:
* Ratings provide direct feedback from plays about their experiences with the game.
* Games with positive ratings are more likely to be downloaded and played by users, increasing the game's active user base. Engaged users are more likely to spend time and money on in-app purchases which can contribute to the game's revenue.
* Games with higher ratings are more likely to be more visible in App Stores and improved visibility can lead to higher download numbers.
* Games with higher ratings are more likely to stand out from competitors. These ratings also contribute to the overall reputation of the developer.
* Higher-rated games are generally more successful in monetising their user base. Satisfied players are more likely to make in-app purchases leading to higher revenue generation.

##### In order to have a prediction for a mobile app's rating for strategy games, our top 5 most important features include the Current Version Year, Original Year, the User Rating Count and various Secondary Genre options.

This proposed prediction model for User Ratings will provide companies with practical recommendations and the probability of successful development of mobile games.
Knowing the priority features helps the developer understand the user's needs and trends which helps them then develop a successful application based on these needs and the potential to predict their app rating based on an assumption of Price, Age Rating, Genres and other features.

**Limitations**
There was a lot of missing values that had to be accounted for. I chose to keep as much missing values as possible however depending on the business requirement, this could change how the data was used.

Data had to be transformed in order to be suitable for machine learning. This means that that this same transformation needs to be applied to both training and testing dataset otherwise this could lead to inaccuracy of the model

For more information please see this repositorys:
* Original dataset
* Jupyter Notebook Code
* Non-technical Presentation

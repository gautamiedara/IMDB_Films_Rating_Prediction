# IMDB_Rating
IMDb is an online database of information related to films, television programs, home videos, video games, and streaming content online – including cast, production crew and personal biographies, plot summaries, trivia, ratings, and fan and critical reviews. Ratings reflect the quality of every aspect of the film and are becoming an increasingly important factor in the overall success of the film. Ideally, the higher the rating, the better the film. IMDb allows registered users to rate any movie on a scale of 1 to 10. Since the IMDb rating of a movie is important information for the viewer, it is important to make an accurate rating to represent the full range of the movie. Various factors contribute to the high and low IMDb ratings of movies. Some of these factors can be quantified or categorized to build a model for predicting IMDb ratings for movies. The purpose of this project is to build such a statistical model to predict the IMDb ratings of the unknown movies using R Language. The following report discusses the variable distributions and their relationships, the methodology used to build the model, and the results of the final model.
# Data Description
## Data Overview
The dataset used has information on 2953 movies from IMDb. It includes characteristics or variables such as movie names, IMDb score, budget, duration and genre, release time and year, the cast and crew, language, and production country.
## Data Cleaning
The columns such as "title", "imdb_id" and "imdb_url" are removed for the analysis as these variables are distinct for each data point. The variables like "genre_shortfilms" and "genre_realitytv" are also removed from the data analysis since all values in these columns are 0. Hence these will not have any effect on the model. The columns like "main_lang", "main_director_name", "main_actor1_name", "main_actor2_name", "main_actor3_name", "main_producer_name", "editor_name", "main_production_company","main_production_country” have different written scripts which are transformed to English for better interpretability and uniformity of the script during analysis.

~Finally, 46 columns and 2953 records are picked for the overall analysis of data and for the prediction of modeling.

## Predictors are selected after performing the following analysis -
  1. Correlation and Collinearity Analysis
  2. Heteroskedasticity Analysis
  3. Outliers Detection

## Model Building
Following steps were performed for model building
  1. Linear Regressions
  2. Non-Linearity Relationship Analysis and Splines
  3. Check for Interaction Terms

Once the significant predictors were identified, a statistical model was crafted with the aim of increasing its predictive power. To avoid overfitting the training data, K-fold Cross Validation was used in order to test its out-of-sample performance.

# Understanding model implications
Based on the final model's summary table following are the business insights for the impact of predictors on IMDb score.

● Based on the dataset provided, we have taken the frequency identical to each actor, producer and director name to their respective experiences within the scope of the dataset:
      
      ○ For choice of actors, keeping all the other predictors the same, we would prefer Johnny Depp and Tom Hanks over Bruce Willis in order to obtain a higher IMDb score. Similarly, the following would be the preference of actors in order of their impact on IMDb score: Tom Hanks, Johnny Depp, Bruce Willis, Denzel Washington, Robert de Niro, Nicolas Cage.
      
      ○ The following would be the preference of directors in order of their impact on IMDb score:Woody Allen, John Carpenter, Steven Spielberg, Robert Zemeckis, Martin Scorsese, Albert Hitchcock, Clint Eastwood, Brian De Palma.
      
      ○ The following would be the preference of producers in order of their impact on IMDb score: Scott Rudin, Tim Bevan, Jerry Bruckheimer, Joel Silver, Arnon Milchan, Brian Grazer.
      
● Compared to France, movies produced in Germany and the UK have a higher IMDB score, keeping all other predictors the same. Similarly, compared to France, movies produced in France have a higher IMDb score than those produced in the US and other countries.

● Movies released during the festive/winter season i.e. from Sep-Dec have a higher IMDb score compared to the rest of the months.

● Based on the coefficient values for the main actor’s gender, the IMDb score shows a positive trend if all the main actors are male i.e. a movie with a higher number of male main actors would have a higher IMDb score.

● Movies with two directors have a higher IMDb score as compared to movies directed by a single director by 0.329. Similarly, Movies with three or more directors have a lower IMDb score than movies directed with a single director by 0.098.

● Higher the number of languages in which a movie is released, the higher is its IMDb score.

● Keeping other predictors constant, the IMDb score decreases by 0.012 with every subsequent year.

● For Drama genre movies, the IMDb score decreases by 0.48 with a unit(hour) increase in the duration of the movie.

● For animation genre movies, if the movie also comes under the fantasy genre its IMDB score would be lesser than the one not in the fantasy genre by 0.386.

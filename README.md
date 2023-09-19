# Beer-Profiling-and-Rating
/
1. About the Data:

The Beer Profile and Ratings dataset from Kaggle was used for the project. The main data set (beer_profile_and_ratings.csv) contains the following columns: /
(General) /
•	Name: Beer name (label)
•	Style: Beer Style
•	Brewery: Brewery name
•	Beer Name: Complete beer name (Brewery + Brew Name)
•	Description: Notes on the beer if available
•	ABV: Alcohol content of beer (% by volume)
•	Min IBU: The minimum IBU value each beer can possess
•	Max IBU: The maximum IBU value each beer can possess
(Mouth feel)
•	Astringency
•	Body
•	Alcohol
(Taste)
•	Bitter
•	Sweet
•	Sour
•	Salty
(Flavor And Aroma)
•	Fruits
•	Hoppy
•	Spices
•	Malty
(Reviews)
•	review_aroma
•	review_appearance
•	review_palate
•	review_taste
•	review_overall
•	number_of_reviews
 
Fig. 1: Summary of the dataset and count of missing values

The data columns are a mix of both character and numeric types. As seen in the figure above, there are no missing values in the data.

A file was generated for this data containing a grouping of the different beer styles, and the average ratings for those styles. Another In this file just the broader styles were used, and not the specific varieties inside the styles. Another similar file was generated using the same grouping for the total number of reviews. These files were prepared outside R. It could have been done inside R as well but these were prepared in Excel just because it was a quicker way, and allowed us to work on plots for these groupings without having to see all of the original data.

 
Fig. 2: Styles and average scores

 
Fig. 3: Styles and number of reviews
________________________________________






2. Objectives and Motivation

The main objectives we hope to accomplish with this project are as follows:
•	Understand the influence of the profile parameters on the review parameters
•	Find the if there are any parameters that are more important than the others
•	Find the relationship between the profile parameters
•	Identify the most/least popular styles of beer

As a consumer, knowing what each beer feels like and what other people think about it would make one make better decisions while choosing a drink, or make it easier to explore new options.

As a manufacturer, knowing what the people prefer and what they are talking about the most would help produce better, more desirable products for the market.

Even though this is just a small example, the concepts used here can be used (and improved upon) to do real-world analysis on much larger data as well.
________________________________________

























3. Methodology

We start by tackling the question of style preference and relevance amongst the consumers. This is achieved in two ways – through the average review scores and through the total number of comments.

 
Fig.4: Average scores for different beer styles

 
Fig. 5: Number of reviews for different beer styles

From the above plots we see a few interesting things. Lesser reviews do not always mean bad review scores (Braggot has some of the fewest reviews but has high average scores). Similarly, more reviews do not guarantee high scores (Lager has the highest number of revies but below average review scores).

We then move to the next half of the objective – study the profile parameters and predictors, and find a relationship between them.
 
Fig. 6: The predictor variables

 
Fig. 7: The target variables

 
Fig. 8: Relationship between the target variables

The fig. 8 shows that all reviews have similar values. This implies that we can build a model to predict one variable’s behavior and the results obtained would be able to explain the behavior of the other target variables.

Let us look at the predictor variables by category.

 
Fig. 9: Overall review by mouth feel variables

The above plot has log(Body) and Astringency faceted by Alcohol. The color depicts the overall review scores. Similarly, we can plot faceted graphs for the taste and flavor category.

 
Fig. 10: Faceted plot for taste variables

 
Fig. 11: Faceted plot for flavor and aroma variables

The above plots show that no one set of categories does a good job at explaining the overall review score.

 
Fig. 12: Correlation matrix

The above plot shows a few things. Firstly, there is redundancy between the target variables. Next, we see that there are no variables that clearly influence the predictor.

PCA would be a good idea to capture the importance of all variables and reduce the number of dimensions at the same time.

 
Fig. 13: PCA on data

The next step is to build models. We build a regular linear model, and one built using principal components. 









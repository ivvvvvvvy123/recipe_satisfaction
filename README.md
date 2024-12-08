## introduction

To use effective study strategies or to make another ramen noodle pack.
A personal problem of mine at least(Felix) is finding the time to cook at home.
When you're doomscrolling and finding a good recipe thinking one day you'll make it
then you realize souffle probably isn't a weekend meal. Ergo we 


## Data Cleaning and Exploratory Data Analysis






insert code here?


Box plot of ‘minutes’ and ‘n_steps’ after cleanup the ‘minutes’ to a range of 1-120




you found the 2nd step in creating a github webpage
heres an example of entire website written in markdown

goal find normal distribution of number of steps and length of time for recipe
|   recipe_id |   rating |
|------------:|---------:|
|       40893 |        5 |
|       85009 |        5 |
|       85009 |        5 |
|      120345 |        0 |
|      120345 |        2 |






## Assessment of Missingness


Review: MAR: Since there are 57 missing review, and the mean value of the rating is 4.7(quite high), so we guess most people are satisfied with the recipe and they feel no need to elaborate on their positive experience.
Name: MAR; This is missed by accident because there is only one row over 234428 recipes, and it is possible the people just forget to put the name in.
Description: MAR; since other columns are already enough to get the detail of the recipe, so adding more description may be necessary


(see 12/4 notebook)

## Hypothesis Testing



Part 1 Step 4: 
1st hypothesis
- null : The distribution of minutes is not correlated with the number of steps
- alternative : The distribution of minutes is positively correlated with the number of steps
- columns : ["n_steps","minutes"]
- test statistic : absolute mean difference (comparing the recipe ratings with and without the tag)




(see 12/8 notebook)

## Framing a Prediction Prediction


## Baseline Model
only add a written part with scores (😭)

## Final Model


in the example final they used segments of the tags they had cleaneed

so 

## Fairness Analysis



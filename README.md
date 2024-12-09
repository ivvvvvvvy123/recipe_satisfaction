food_interim["review"],food_interim["description"],food_interim["n_steps"],

print(interactions_r[['recipe_id', 'rating']].head().to_markdown(index=False))



## introduction

To use effective study strategies or to make another ramen noodle pack.
A personal problem of mine at least(Felix) is finding the time to cook at home.
When you're doomscrolling and finding a good recipe thinking one day you'll make it
then you realize souffle probably isn't a weekend meal. Ergo we 


## Data Cleaning and Exploratory Data Analysis






conducted outlier removal on food[minutes] present in the dataset 




you found the 2nd step in creating a github webpage
heres an example of entire website written in markdown

goal find normal distribution of number of steps and length of time for recipe
|   recipe_id |   minutes |   n_steps |
|------------|----------|----------|
|      306785 |        40 |         4 |
|      310237 |        30 |         9 |
|      321038 |        22 |        14 |
|      321038 |        22 |        14 |
|      342209 |        40 |         7 |




## Univariate Analysis
Look at the distributions of relevant columns separately by using DataFrame operations and drawing at least two relevant plots.
Embed at least one plotly plot you created in your notebook that displays the distribution of a single column (see Part 2: Report for instructions). Include a 1-2 sentence explanation about your plot, making sure to describe and interpret any trends present. (Your notebook will likely have more visualizations than your website, and that’s fine. Feel free to embed more than one univariate visualization in your website if you’d like, but make sure that each embedded plot is accompanied by a description.)



## Assessment of Missingness


missingness columns : review, name, descripition


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
 
We plan to be able to predict the minutes the recipe would take and thus is regression problem due to continous numerical behavior present. Also due to finding variances in recipes when only conducting analysis on one variable for example n_steps and minutes vizualiation. Yet also recognizing abnormalbity in other plots thus suggesting that skill of reviewer may be coming into play. Therefore meaning implications of how the reviewer is viewing (food["descripition"]) can provide insight to what they are predisposed to believe of quality expected from the minutes from the recipe.

The score will use is accuracy due to the minutes produced by the model being the same units as the original dataset but standarized.

## Baseline Model





# random forest (reason : lots of rows to tree on ) decision tree regression 
# ( dependent minutes may need to do a mixed approach due to drive space?)


# TODO 
# columns(features) for model

    # one hot tags | done
    # stdscaler 
    #
        # n_steps    
        # n_ingredients
    # tags
    # description (std scaler the values from the log?)
    # steps?
# decision tree viz for minutes given the attributes

# present accuracy and precision
# get the random forest regressor to work
# train with entropy(cv) the decision tree regressor

# TODO on next meet
# fairness & final model 

# 







only add a written part with scores (😭)

## Final Model


# lists_eval = ["tags","description"]
Arriving at practical computation limits the only features that we're possible to add on any computer that I tried was tags and description. 
Ingredients, nutrition , and for some reason steps weren't able to work under the multilabelbinarizer which in practice was simply a binary matrix but optimized for entry values with lists of data ["60 minutes", "15 minutes" ] etc. Although the model was able to train the all the tags alll of them being included would be shortsighted to the implications of colinearity due our being to predict the minutes or in other words if have variable that classifies the time. **Random Forest** may be able to make use of this fact due to the intervals of time suggested by the tags allowing for prediction that may be better suited for further iterations of the model.

Description was also included due to the behavior we have witnessed earlier of the missingingness presented in the providing insight into the opinions of the participants who were reviewed. 

scores : 


in the example final they used segments of the tags they had cleaneed

so 

## Fairness Analysis



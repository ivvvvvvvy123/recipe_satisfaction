food_interim["review"],food_interim["description"],food_interim["n_steps"],

print(interactions_r[['recipe_id', 'rating']].head().to_markdown(index=False))



## introduction

Recipe and rating is an important reference when we making food, providing reliable indication of the food quality and taste, as well as the energy and complexity to finish cooking. Time, in nowadays, becomes more crutIal when people live in such a high speed life, so understanding what factors are correlate with it is one question we are interested in. In our project, we focus on how to predict the cooking time(minutes) utilizing different categorical, numerical, and textual features. Our model tries to use statistical analysis method, including permutation test, hypothesis tests and the missing data analysis to conduct the exploratory analysis. We also build decision tree regressor to predict the detailed relationship between them. Overall, this project aims to shine light on how to make people more efficient cooking food with viable time management.  

<table border="1" style="border-collapse: collapse; width: 100%; text-align: left;">
  <thead>
    <tr>
      <th>Column</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Name</td>
      <td>Name of recipe</td>
    </tr>
    <tr>
      <td>Id</td>
      <td>Recipe id</td>
    </tr>
    <tr>
      <td>Minutes</td>
      <td>Time to cook</td>
    </tr>
    <tr>
      <td>Contributor_id</td>
      <td>User id who uploaded the recipe</td>
    </tr>
    <tr>
      <td>Submitted</td>
      <td>Date recipe was uploaded</td>
    </tr>
    <tr>
      <td>Tags</td>
      <td>Food.com tags for recipe</td>
    </tr>
    <tr>
      <td>Nutrition</td>
      <td>Nutrition information (calories, total fat, sugar, sodium, protein, saturated fat, etc.)</td>
    </tr>
    <tr>
      <td>N-steps</td>
      <td>Number of steps to cook</td>
    </tr>
    <tr>
      <td>Steps</td>
      <td>Text for recipe steps in order</td>
    </tr>
    <tr>
      <td>Description</td>
      <td>User-provided description</td>
    </tr>
    <tr>
      <td>Ingredients</td>
      <td>Text for recipe ingredients</td>
    </tr>
    <tr>
      <td>N-ingredients</td>
      <td>Number of ingredients in recipe</td>
    </tr>
  </tbody>
</table>



## Data Cleaning and Exploratory Data Analysis







conducted outlier removal on food[minutes] present in the dataset 




you found the 2nd step in creating a github webpage
heres an example of entire website written in markdown

goal find normal distribution of number of steps and length of time for recipe


| recipe_id | minutes | n_steps |
|-----------|---------|---------|
| 306785    | 40      | 4       |
| 310237    | 30      | 9       |
| 321038    | 22      | 14      |
| 321038    | 22      | 14      |
| 342209    | 40      | 7       |




+----------+------+-----+-----+-----+------+-------+
| rating   |    0 |   1 |   2 |   3 |    4 |     5 |
+==========+======+=====+=====+=====+======+=======+
| rating   |    0 |   1 |   2 |   3 |    4 |     5 |
+----------+------+-----+-----+-----+------+-------+
| 1        |  123 |  22 |  18 |  65 |  416 |  1971 |
+----------+------+-----+-----+-----+------+-------+
| 2        |  319 |  54 |  39 | 172 | 1060 |  5321 |
+----------+------+-----+-----+-----+------+-------+
| 3        |  504 | 104 |  83 | 271 | 1663 |  8092 |
+----------+------+-----+-----+-----+------+-------+
| 4        |  679 | 136 |  88 | 353 | 2080 |  9999 |
+----------+------+-----+-----+-----+------+-------+
| 5        |  880 | 185 | 154 | 522 | 2736 | 11424 |
+----------+------+-----+-----+-----+------+-------+
| 6        |  952 | 201 | 158 | 549 | 2883 | 12555 |
+----------+------+-----+-----+-----+------+-------+
| 7        | 1099 | 182 | 178 | 578 | 3045 | 13430 |
+----------+------+-----+-----+-----+------+-------+
| 8        |  996 | 183 | 159 | 523 | 2972 | 12688 |
+----------+------+-----+-----+-----+------+-------+
| 9        | 1082 | 202 | 166 | 550 | 2761 | 12003 |
+----------+------+-----+-----+-----+------+-------+
| 10       |  947 | 189 | 185 | 492 | 2457 | 10558 |
+----------+------+-----+-----+-----+------+-------+
| 11       |  793 | 167 | 132 | 370 | 2012 |  9011 |
+----------+------+-----+-----+-----+------+-------+
| 12       |  750 | 146 | 126 | 312 | 1826 |  7980 |
+----------+------+-----+-----+-----+------+-------+
| 13       |  510 | 107 |  77 | 244 | 1470 |  6499 |
+----------+------+-----+-----+-----+------+-------+
| 14       |  436 | 110 |  79 | 254 | 1190 |  5626 |
+----------+------+-----+-----+-----+------+-------+
| 15       |  433 |  80 |  66 | 195 |  963 |  4529 |
+----------+------+-----+-----+-----+------+-------+
| 16       |  425 |  66 |  66 | 166 |  771 |  3959 |
+----------+------+-----+-----+-----+------+-------+
| 17       |  367 |  55 |  48 | 138 |  634 |  3304 |
+----------+------+-----+-----+-----+------+-------+
| 18       |  254 |  44 |  29 |  87 |  541 |  2331 |
+----------+------+-----+-----+-----+------+-------+
| 19       |  214 |  30 |  35 |  79 |  382 |  2080 |
+----------+------+-----+-----+-----+------+-------+
| 20       |  204 |  30 |  28 |  68 |  379 |  1952 |
+----------+------+-----+-----+-----+------+-------+
| 21       |  143 |  30 |  19 |  55 |  252 |  1395 |
+----------+------+-----+-----+-----+------+-------+
| 22       |   88 |  18 |  19 |  49 |  194 |  1051 |
+----------+------+-----+-----+-----+------+-------+
| 23       |  116 |  19 |   9 |  42 |  174 |  1045 |
+----------+------+-----+-----+-----+------+-------+
| 24       |   89 |  11 |   9 |  25 |  117 |   615 |
+----------+------+-----+-----+-----+------+-------+
| 25       |   78 |  16 |  18 |  28 |  108 |   594 |
+----------+------+-----+-----+-----+------+-------+
| 26       |   51 |  13 |   5 |  31 |   87 |   446 |
+----------+------+-----+-----+-----+------+-------+
| 27       |   57 |  11 |   7 |  20 |   73 |   347 |
+----------+------+-----+-----+-----+------+-------+
| 28       |   29 |   2 |   6 |   7 |   47 |   554 |
+----------+------+-----+-----+-----+------+-------+
| 29       |   25 |   3 |   2 |   3 |   45 |   251 |
+----------+------+-----+-----+-----+------+-------+
| 30       |   30 |   5 |   4 |   9 |   41 |   217 |
+----------+------+-----+-----+-----+------+-------+
| 31       |   26 |   7 |   4 |  11 |   33 |   188 |
+----------+------+-----+-----+-----+------+-------+
| 32       |   17 |   4 |   5 |   3 |   18 |   117 |
+----------+------+-----+-----+-----+------+-------+
| 33       |   10 |   1 |   2 |   3 |   15 |   127 |
+----------+------+-----+-----+-----+------+-------+
| 34       |   13 |   4 |   1 |   3 |   16 |   113 |
+----------+------+-----+-----+-----+------+-------+
| 35       |    6 | nan | nan |   1 |   15 |    52 |
+----------+------+-----+-----+-----+------+-------+
| 36       |    8 |   2 |   1 |   1 |   12 |    57 |
+----------+------+-----+-----+-----+------+-------+
| 37       |   11 |   1 |   3 |   2 |   13 |    54 |
+----------+------+-----+-----+-----+------+-------+
| 38       |   11 | nan |   1 | nan |    9 |    50 |
+----------+------+-----+-----+-----+------+-------+
| 39       |    1 | nan |   1 |   2 |    2 |    29 |
+----------+------+-----+-----+-----+------+-------+
| 40       |    4 | nan | nan |   1 |    6 |    37 |
+----------+------+-----+-----+-----+------+-------+
| 41       |    4 | nan |   1 | nan |    4 |    45 |
+----------+------+-----+-----+-----+------+-------+
| 42       |    3 |   2 | nan |   1 |    1 |    28 |
+----------+------+-----+-----+-----+------+-------+
| 43       |    3 | nan | nan | nan |  nan |    14 |
+----------+------+-----+-----+-----+------+-------+
| 44       |    4 |   1 |   1 | nan |  nan |    12 |
+----------+------+-----+-----+-----+------+-------+
| 45       |    8 |   2 |   1 |   3 |    4 |    60 |
+----------+------+-----+-----+-----+------+-------+
| 46       |    2 |   2 | nan | nan |    2 |     7 |
+----------+------+-----+-----+-----+------+-------+
| 47       |    3 | nan | nan | nan |    3 |    19 |
+----------+------+-----+-----+-----+------+-------+
| 48       |    4 | nan |   1 | nan |  nan |    23 |
+----------+------+-----+-----+-----+------+-------+
| 49       |    1 | nan | nan |   1 |  nan |     7 |
+----------+------+-----+-----+-----+------+-------+
| 50       |    4 | nan | nan | nan |    2 |    22 |
+----------+------+-----+-----+-----+------+-------+
| 51       |  nan | nan | nan | nan |    2 |     5 |
+----------+------+-----+-----+-----+------+-------+
| 52       |  nan | nan | nan |   1 |  nan |     1 |
+----------+------+-----+-----+-----+------+-------+
| 53       |    3 | nan | nan |   1 |  nan |     7 |
+----------+------+-----+-----+-----+------+-------+
| 54       |  nan | nan | nan | nan |  nan |    14 |
+----------+------+-----+-----+-----+------+-------+
| 55       |    2 |   1 | nan | nan |    1 |    11 |
+----------+------+-----+-----+-----+------+-------+
| 56       |    1 | nan | nan | nan |  nan |   nan |
+----------+------+-----+-----+-----+------+-------+
| 57       |    1 | nan | nan |   1 |  nan |     8 |
+----------+------+-----+-----+-----+------+-------+
| 58       |  nan | nan | nan | nan |  nan |     2 |
+----------+------+-----+-----+-----+------+-------+
| 59       |  nan | nan | nan | nan |  nan |     4 |
+----------+------+-----+-----+-----+------+-------+
| 60       |    1 | nan | nan | nan |  nan |     1 |
+----------+------+-----+-----+-----+------+-------+
| 61       |    1 | nan |   1 |   1 |    2 |    12 |
+----------+------+-----+-----+-----+------+-------+
| 62       |  nan | nan | nan | nan |    1 |   nan |
+----------+------+-----+-----+-----+------+-------+
| 63       |  nan | nan | nan | nan |  nan |     1 |
+----------+------+-----+-----+-----+------+-------+
| 65       |  nan | nan | nan | nan |  nan |     3 |
+----------+------+-----+-----+-----+------+-------+
| 66       |  nan | nan | nan | nan |  nan |     1 |
+----------+------+-----+-----+-----+------+-------+
| 67       |  nan | nan | nan | nan |  nan |     1 |
+----------+------+-----+-----+-----+------+-------+
| 68       |  nan | nan | nan | nan |    1 |     1 |
+----------+------+-----+-----+-----+------+-------+
| 70       |    4 | nan | nan | nan |  nan |     4 |
+----------+------+-----+-----+-----+------+-------+
| 73       |    1 | nan | nan | nan |  nan |   nan |
+----------+------+-----+-----+-----+------+-------+
| 76       |  nan | nan | nan | nan |  nan |     5 |
+----------+------+-----+-----+-----+------+-------+
| 77       |  nan | nan | nan | nan |  nan |     1 |
+----------+------+-----+-----+-----+------+-------+
| 80       |    2 | nan | nan | nan |    2 |    14 |
+----------+------+-----+-----+-----+------+-------+
| 86       |  nan | nan | nan | nan |  nan |     2 |
+----------+------+-----+-----+-----+------+-------+


## Univariate Analysis
Look at the distributions of relevant columns separately by using DataFrame operations and drawing at least two relevant plots.
Embed at least one plotly plot you created in your notebook that displays the distribution of a single column (see Part 2: Report for instructions). Include a 1-2 sentence explanation about your plot, making sure to describe and interpret any trends present. (Your notebook will likely have more visualizations than your website, and that’s fine. Feel free to embed more than one univariate visualization in your website if you’d like, but make sure that each embedded plot is accompanied by a description.)

<img src="assets/univariate_hist_minutes.png" alt="univar plot" />

## Bivariate Analysis

<img src="assets/plotly_bivariate_whisker.png" alt="univar plot" />



## Assessment of Missingness


missingness columns : review, name, descripition


Review: MAR: Since there are 57 missing reviews, and the mean value of the rating is 4.7(quite high), most people are satisfied with the recipe and feel no need to elaborate on their positive experience.
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


- Framing journey
Taking inspiration from the example for the same we arrived at that feature(defined as one column)
that the columns containing strings of lists in python syntax would prove to be most insightful
for arriving at thought provoking predictions. First foremost we would need conduct a tad bit more
of data cleaning before being able to add features in the same vain
 
	```python3
	
	
	import ast
	def clean_str_to_list(tags):
		# Convert the string representation of the list to an actual list
		return ast.literal_eval(tags)
	
	```

After doing so we choose to make arrived at the best model to use would be random forest regressor
due to the desired initutiive nature of interpreting how the features would be represented in our 
output due to our choosen encoding of MulitLabelBinarizer although the name suggests on the surface 
to be same aforementioned Binarizer as found in lecture. The documentation and actually application to
dataset has more in column with OneHotEncoder. Applying a OneHot encode to the what would be all the items
found in the list. At first not having specific input in mind to arrive at accurately predicting the number of
minutes for the recipe. Although the methodology for what feature to include for prediction may not have been
as deliberate as the study that originates the data we still learned a very practical approach of trial and 
error for the encode to even process of course there would've been ways to encode other features
similiar to "tags" we desired to not conduct any data truncation in the name of portablility. Also 
due to computationally limitations even explicit nested features being dropped such as what the orignal study
did with all the "indgredients" found not being included in their model.
	




random forest (reason: lots of rows to tree on ) decision tree regression 
( dependent minutes may need to do a mixed approach due to drive space?)


TODO 
columns(features) for model
    - one hot tags | done
    - stdscaler 
    
        - n_steps    
        - n_ingredients
    - tags
    - description (std scaler the values from the log?)
    - steps?
decision tree viz for minutes given the attributes
present accuracy and precision
get the random forest regressor to work
train with entropy(cv) the decision tree regressor

TODO on next meet
	fairness & final model 









only add a written part with scores (😭)

## Final Model

obvious short comings of decision tree regressor on display overfitting :(



lists_eval = ["tags","description"]
Arriving at practical computation limits the only features that we're possible to add on any computer that I tried was tags and description. 
Ingredients, nutrition , and for some reason steps weren't able to work under the multilabelbinarizer which in practice was simply a binary matrix but optimized for entry values with lists of data ["60 minutes", "15 minutes" ] etc. Although the model was able to train the all the tags alll of them being included would be shortsighted to the implications of colinearity due our being to predict the minutes or in other words if have variable that classifies the time. **Random Forest** may be able to make use of this fact due to the intervals of time suggested by the tags allowing for prediction that may be better suited for further iterations of the model.

Description was also included due to the behavior we have witnessed earlier of the missingingness presented in the providing insight into the opinions of the participants who were reviewed. 

scores : 


in the example final they used segments of the tags they had cleaneed

so 

y=food_cleaned
Standard normalized: n_steps, n_ingredients, number of tags, 
vectorized description
One_hot encoding: rating tags


## Fairness Analysis







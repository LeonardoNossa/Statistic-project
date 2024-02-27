# Statistic-project
Analysis about cardiovascular disease

Three other young people, mentioned in the project presentation, contributed to the project.

Our project is an investigation conducted on the possible existing correlations between several life-habits or biometric parameters and the occurrence of cardiovascular diseases. The chosen dataset contains 17 variables about 68k patients.
For each patient we know its sex, height, weight, age and if it smokes, drinks or does physical activity. We have some biometric parameters such as blood pressure measurements, cholesterol and glucose levels and whether or not it developed a cardiovascular disease. 
We first explored the parameters regarding blood composition such as cholesterol and glucose, represented by random variables assuming 3 values (1,2,3)
In figure A is shown the correlation between three different levels of cholesterol and the weight of patients. We see that the increase of the cholesterol level is associated with patients having a higher weight and the table on the right shows also the increase of ill patients among the three levels . 
We perform the same analysis for the glucose levels but we cannot see the same correlation between the weight as before. The percentage of patients affected still increases following the glucose levels.
During our exploration we decided to seek the relationship  between sex (a random variable that can assume two values (males and females)  and percentage of sick patients on different cholesterol levels. There is a curious inversion of our line plots at level three so we performed an hypothesis test; we can state that there is no significant difference since the typical alpha levels are lower than our p value → 0.114.
The same reasoning has been applied on glucose levels and we discovered an interesting behavior so we applied two unilateral hypothesis tests. We applies a test regarding the difference of two bernoulli populations on level 2 and level 3 of our graph: the results for level 3 showed a significant difference between the female population, compared to the male population (females > males), for level 2 our result depends on the chosen alpha level, since the p value is 0.0238
Then we moved to other variables. Figure N shows the positive relationship between the percentage of people affected by cardiovascular diseases and different range of age. We wanted to find out if this growth is also correlated to other variables. So we applied the same analysis to the variables about other life habits: smoke, alcohol and physical activity, each of them is represented by bernoullian random  variables. Unfortunately we weren’t able to see a clear difference... about the alcohol variable and the smoke variable.  
Because of that, we focused our study on the variable about physical activity. We can see a pattern from the age of 44 where the red line is always higher than the black one, who represent the sporty people. So we decided to perform one bilateral test where we compared the illness rate between sporty people and sedentary ones, about the “younger” patients and older ones: In the first case we obtained a p-value of 0.07199, so for significance level under 0,07199 we cannot find significant importance of sport in the development of cardiovascular disease. While for patients between 45 to 64 there is significant difference... between physical activity and percentage of ill people as shown in several articles of preventive medicine


The main topic of our investigation was to assess the factors determining the occurrence of a cardiovascular disease given different biometrical parameters. Since the variable describing the occurrence of the disease was a bernoullian rv, the regression model we decided to build is a logistic one, whose main difference is to have a response variable that can only assume 0 and 1 values. The model was constructed using 70% of the dataset as training, and the remaining 30% as a testing sample. With in mind the objective to build a reliable model describing a complex biological phenomenon we found that the best possible model regarding our data is built using a large number of different variables, as shown in the image (only the most significative ones have been kept). 
In order to assess the goodness of our model we used a pseudo R2 index (McFadden), since the real R2 is only applicable to linear regression model. On the internet, and on articles has been said that McFadden values > 0.20 represent an  excellent fitting model: our index is slightly > 0.19, so we thought it was good enough to be considered. 
We also tested to seek if  multicolinearity could affect our model and, as it is shown no value is severely affected by multicollinearity
We then used our logistic model to actually make predictions about the data in our test sample. By predicting the elements in the test sample (we are now converting the logit in an actual probability), we are obtaining a probability value, which will then be used against a threshold to classify. An optimized threshold to maximize accuracy has been obtained by hand, comparing different values. If the value is lower then the threshold then the sample is classified as NOT SICK (0), and the same otherwise (1).
Our results are then represented in a confusion matrix, showing different values, the most important are the accuracy (number of matches) compared to the NIR (best guess knowing nothing about our model)
Other important values are the sensitivity (true positive rate) and specificity (true negative rate), the K index, showing a moderate agreement between prediction and observation 
Everything seems to suggest that our model is pretty robust in describing the variability of the dataset we chose. 
Lastly, we decided to create two subsets of our dataset, containing the patients with the best and worst possible biometrical parameters and life habits in order to compare the rate of illness in the two groups
we used this subsets to plot a pie chart in order to be able to find a clear difference between ill patients form the two subset, in fact from the second subset the percentage of patients with a cardiovascular disease is higher
We couldn’t perform a statistical test, since the subset containing the worst patients contained (fortunately) only 8 rows, but the gap is clearly evident. We then took one patient for each subset, one from the best having these parameters… and one from the worst having these values… and fed it to our model in order to validate even further its predictive ability and, as expected, both patients have been correctly classified, not sick for patient A and sick for patient B with 73% of accuracy.

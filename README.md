# hr_attrition_analysis
DSC424 Milestone 5 Final Project: HR Attrition Data
Author: JITEN MISHRA, Team (Data Crew)
 
Milestone 3 Review:
Initial Hypothesis:
From the milestone 3 visual plots we inferred that Male person who is doing more overtime and is Single has more no of Attrition and probably has a low income. Which we need to analyze more in our final project. We do Also see a significant Attrition rate in young employees which is a sector to analyze more.
 
Aspect line of Analysis: Regression
 
Dataset Description: [NOTE: Initial Explanatory Graphs is submitted in milestone 3]
As mentioned in the previous milestone we did data cleaning, preprocessing converted variable to factors and created dummies. Variable involved for the analysis is as below. There are couple of categorical variables which will be explained in final report.

Our Response Variable is Attrition, with this line of aspect we want to measure the performance of different models used to predict the Attrition class where we conducted Regression to analyze our data using below technique.
 
• Logistic Regression, Regularized subset, Ridge Regression, Lasso Regression, Elasticnet Regression.
 
Since our class had data imbalance, we oversampled the data and verified the distribution is same. (Detail graphs in final report)

Bar Graph showing Before and after Oversampling
To prepare the data set we converted our variables to dummies and applied “Principal component analysis Technique” to reduce dimensionality and determine the number of factors and then performed a “Principal Factor analysis” and determined the factors to be used for regression. From our analysis it suggested us 16 factors, but we took 13 factors covering 58% of the variance. (Details in final report)
  
 
Logistic Regression
We performed a logistic regression dividing data into training and testing with manual variable selection and measured the performance. The model turned out good with selected variable being significant at p < 0.05 having a goodness of fit of chi square = 16.73 , p < 2.2e-16 ***.
log(p/(1-p)) = -0.08 - 0.42(RC6) -0.30(RC1) + 0.21(RC3) + 0.12(RC2) - 0.44(RC4) - 0.25(RC9)
               ​​​+ 0.35(RC8) - 0.11(RC13) - 0.13(RC12)
RegSubset Regression
We performed a Reg subset regression using “adjR2” and “bic” scale to measure the performance and found out the model with adjR2 did better after removing the non-significant variables and the performance was same as logistic.
 
   
(adjR2 Equation)    log(p/(1-p)) = -0.08 - 0.42(RC6) -0.30(RC1) + 0.21(RC3) + 0.12(RC2) - 0.44(RC4) - 0.25(RC9)
              ​​​​ + 0.35(RC8) - 0.11(RC13) - 0.13(RC12)
Ridge Regression
We then performed a ridge regression as another technique to verifed the performance, we select lambda.min for our lambda parameter as we want to have maximum confidence interval to capture most of the true positives.

Lasso Regression
We then performed a lasso regression to verify the performance again and it performed the almost similar.
 
  
Elastic net Regression
For elasticnet we ran a for loop with a range of alpha 0 to 1 with an increment of 0.01 and captured the performance which did better, and it reported that model at alpha =0.55 did better with performance which we see is same as the performance of lasso.
 
Performance Comparison of Models
From the Performance matrix we see Lasso is doing slightly better than all other model which is also reported in elastic net.
 
Model                 Sensitivity Accuracy  Precision Specificity 
LogisticTest         0.7342857   0.6954103  0.6710183   0.6585366
RegSubsetTest_adjr2  0.7342857   0.6954103  0.6710183  0.6585366
RegSubsetTest_bic    0.7342857   0.6912378 0.672043   0.6693767
RidgeTest            0.7285714   0.6884562 0.6640625  0.6504065
LassoTest            0.7371429   0.6954103  0.6701299  0.6558266
ElasticNetTest        0.7371429  0.6954103  0.6701299  0.6558266
 
Conclusion: So, if we look at the model equation, we have some of the highest coefficients for RC8 which is a factor of Overtime With research scientist, RC3 which is factor of Sales and marketing people,RC2 which is a factor of HR Profile, RC6 effecting negatively which is a factor of Manager Profile. These all factor has a significant influence on the attrition which is kind of supporting our initial hypothesis.
[NOTE: More details in the final Report]

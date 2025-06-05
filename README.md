JupiterNotebook: (https://github.com/NaglaJ/Berkeley-Projects/blob/NaglaJ-patch-1/Exercise_17_Practical_Application_III.ipynb)

The dataset used in this activity comes from the UCI Machine Learning repository link. The data is from a Portuguese banking institution and is a collection of the results of multiple marketing campaigns. 

In addition to the dataset, we were provided with the following article accompanying the dataset here for more information on the data and features.

Based on the article, this dataset was refined from 58 potential input values to this group of 17 inputs after several iterations through CRISP-DM.  SVC yielded the best results for this data, as stated in the pdf.  This was also proven out in the attached Jupiter Notebook that shows SVC with the best performance. 

To engineer the appropriate components, I applied PCA against two sets of data, one that included all features, and one that dropped social and economic features (socec).  For the LinearRegression model, I applied the model that dropped socec features.

Other options here would have been to identify the most important features, create fewer categories for some of the columns, apply polynomial regression to some of the numeric features, etc.  Since this exercise is focused on modeling, I stuck to only the PCA approach to identify differences in performance across the classifiers.

After analyzing the data, a baseline was created using Logistic Regression.  This model resulted in a training accuracy score of 90%. Test accuracy was slightly higher but also around 90%. This is the minimum score to beat. 

In addition to accuracy scores, I created Confusion Matrix Heat maps, which confirmed the accuracy as 90.5%.

The notebook shows code for 4 different classifiers, each with their own set of parameters to test.  The code runs through KNeighborsClassifier, LogisticRegression, SVC and DecisionTreeClassifier, each with a set of parameters to assess.

The result is output in a table that shows the classifier names, the performance for each one in terms of accuracy, the time required to generate results and the specific parameters that performed the best for each classifier.

It was clear that SVC performed quite well, but took too many cycles and too much time to result in a model that barely outperformed other models. 

Adding social and economic data as inputs did not improve the performance of the model.  A better model might apply linear or polynomial regression against the social and economic data before being fit into a SVC model.  Other future model improvements should seek to build upon non-campaign related data:
“In future work, we intend to collect more client based data, in order to check if high quality predictive models can be achieved without contact-based information. We also plan to apply the best DM models in a real setting, with a tighter interaction with marketing managers, in order to gain a valuable feedback.”

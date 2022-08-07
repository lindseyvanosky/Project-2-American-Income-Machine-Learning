# American Income - Census Data
## Will someone make >50K or <=50K?

**Author**: Lindsey Vanosky
**Project 2**: Coding Dojo

### Business problem: 
These models have several use cases in the world, such as: 
- Targeted Marketing: specifically of budget or premium products.
- Community Development: identifying the gaps in equity throughout a neighborhood. 
- Hiring Talent: identifying potential high-earners.  

### Data:
The data source is a csv file that originally had 15 columns and 32,561 entries.  

RangeIndex: 32561 entries, 0 to 32560
Data columns (total 15 columns):
 #   Column  Non-Null Count  Dtype 
---  ------  --------------  ----- 
1. age :                int64 
2. workclass :          object
3. fnlwgt  :            int64 
4. education :          object
5. education-num :      int64 
6. marital-status  :    object
7. occupation  :        object
8. relationship :       object
9. race  :              object
10. gender  :           object
11. capital-gain  :     int64
12. capital-loss :      int64 
13. hours-per-week   :  int64 
14. native country  :   object
15. outcome        :    object
 

## Methods
- For this project I utilized pandas to import, inspect and clean the data set. There was a small amount of duplicates that I dropped, and luckily this set did not have an NaN values. The data did not have a header, so I imported the data set's dictionary to rename the columns. Once I confirmed all of the values were consistent and there weren't any outliers, I was able to move to the next step of plotting visuals. 
- Using matplotlib, I plotted a histogram and heatmap to further explore the data. The data set was a bit unbalanced, we need more information for those making >50K. I was also able to determine that we didn't have any strong correlations in our numerical data set. 

## Results
- Now with a better understanding of the data set, I was able to create some explanatory visuals to tell a story. Primarily I was interested in how race and education played a part in someone's earning potential. I was able to plot the following visuals to begin investigating. 

#### Line Graph: Salaries by Race
![line graph - salaries by race](https://user-images.githubusercontent.com/105459145/183309520-bc872530-875a-4635-8458-4ffcf688412e.png)
> This line graph plots the count of salaries both over and under 50K by race. At first plot, it looked like there was a massive disparity of >50K by race. It looked as if salaries over 50K were disproprtionally awarded to white people. This isn't necessarily untrue, but I found it important to plot the line of total answers by race so we can see who this data actually represents. Adding this line did highlight that the majority of our data was from white people. Therefore my first recommendation - more data!

#### Bar Chart: Salaries by Education Level 
![bar chart - salaries by education](https://user-images.githubusercontent.com/105459145/183310369-7c01f603-d065-42aa-8231-69ac1cd04b20.png)
> This bar chart plots the number of salaries both over and under 50K by education level. Here we can see some interesting facts, for example, Prof school, Masters, and Doctorate, are the only columns where those earning >50k outnumber those making <=50K. Additionally, the fact that the total number of >50K is very similar between the HS grad and Bachelors columns, makes me think there could be opportunity to use this data set as a tool to decided whether to go to college or not base on finances. 

## Models
For this project, I built several machine learning models - both supervised and unsupervised. I started with a Decision Tree and used PCA feature engineering in an attempt to improve my results. However, on this model we saw almost no difference between the PCA and non PCA data. I then attamepted the same feat with a KNN model. We saw some minor improvements, but like the decision tree, it didn't move the needle. To round out the supervised models, I built a Random Forest Classifier. I used GridSearchCV to extract the best hyperparamaters to tune the model with. With this model I was able to improve the scores greatly, however it was at the cost of a low recall score on the >50K set. A false negative in this scenario would mean that it was predicted that someone would not make over 50K, and do. I would consider this extremely low risk. I chose this model for final production because of this reason, as well as the fact that I believe the low recall score can be rectified with more data in the >50K set. 

## Recommendations:
More data! The Random Forest Classifier worked really well with this data set, and with just a bit more data it would be a productive model. 

### For further information
For any additional questions, please contact **lindsey.vanosky@gmail.com**

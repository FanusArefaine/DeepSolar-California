# DeepSolar-California
A predictive analysis project to assist solar system retailer and policy regulators in the State of California.

## Motivation and Objective

In recent years, solar systems have been getting enormous attention due to the increase in the price of electric energy and decreasing cost of solar panels across the world. Moreover, governments have been supporting the public with incentives to install solar systems in their homes. The use of solar systems in homes plays a crucial part in protecting the universe by reducing the amount of harmful gasses released to generate electrical energy. Due to these environmental and economic benefits, the deployment of solar energy facilities has recently been growing across many parts of the world. However, in this project, I will analyze and illustrate solar systems deployment in the State of California. To better understand the distribution and relationships of solar systems deployment using the data, we will numerically and visually present the relationships between different parameters of solar system deployment.

Focusing on analyzing and formulating a predictive model for solar power deployment across the United States of America, this project will be a great help to solar panel retailers, regulatory agencies, power generating companies. This project will use the SolarDeep dataset to analyze the distribution of solar power systems installed in relation with the socioeconomic and environmental parameters. These analyses will help solar retailers and regulatory agencies and power system companies to comprehend the relationships and hence, expand their business. Moreover, I have built a predictive model that would help these companies and agencies in taking business decisions based on the projections of the data at different times and different locations. 


## System Design and Implementation Details

<img width="874" alt="Screen Shot 2020-06-29 at 6 42 11 PM" src="https://user-images.githubusercontent.com/56777455/86073272-43674e00-ba38-11ea-8544-62acfae57fe5.png">

For the State of California subset, I decided to look into the impact of socioeconomic and environmental parameters on the solar system count in each tract area. Hence, I split the DeepSolar dataset into four subsets of parameters. These subsets belong to different aspects of socioeconomic status of the State of California. Each subset is examined carefully for missing values and irregularities within each subset. After each subset is cleaned, they are merged and fed into a classifier. 

The tract areas are then classified into areas with solar systems and areas without solar systems using the classification algorithm. Finally, the tract areas’ subset is fed into a regression algorithm for a prediction. The regression algorithm gives the predictions of solar system count per thousand households across the tract areas within the State of California. 


## Architecture Related Decisions

After I decided to perform socioeconomic data analysis for the State of California, I chose to split the dataset into four subsets of socioeconomic parameters to handle them with their relevant parameters. These sets of parameters are cleaned and fed into the classifier to prune the tract areas without solar systems.  Hence, the regression algorithm will be able to only deal with tract areas with solar systems which makes the data smaller, more convenient for computation and more accurate. 


## Algorithms Considered/Used

I have made use of major algorithms in the classification and regression sections of the implementation. Although I have tried a couple of algorithms for comparison and regression, some of the algorithms shine over others. 

I compared three major classification algorithms for classification of the dataset. Logistic Regression, Support Vector Machine, and Ensemble Methods are the algorithms I compared for my dataset. These classification algorithms are perfect for smaller dataset and they have shown good results.  

I have also compared and tuned a couple of regression algorithms. Due to the non-linearity of the data, I did not use linear regression. Algorithms that support non-linear relationships that I used are Decision Tree Regressor, Random Forest Regressor, and Support Vector Machines. These algorithms have shown fairly good results on the dataset. 


## Technologies and Tools Used

In this analysis, I have used python libraries such as numpy, pandas, scikit-learn, matplotlib, seaborn and several other supporting components. I used these libraries because they are very powerful for data computation and visualization. 


# Dataset Used and Preprocessing 

The DeepSolar dataset provided by Stanford University is used for this analysis. The dataset has 72537 data records of tract areas across the United States of America and 169 features. The data is composed of numerical and categorical features. 

For this particular analysis, I used a subset of the dataset that represents only the State of California. The subset is divided into four sets of parameters as described above. Various preprocessing techniques are applied on the subsets as per their requirements. 

These subsets are first examined for missing values which could be inconvenient for computation and otherwise misleading to the predictive model. Moreover, the parameter values are normalized to eliminate in the range of values while keeping the distribution and information embedded in the data. Mapping of categorical values to representative numerical values is performed as part of cleaning.
Moreover, feature reduction is applied on the dataset. Since features with constant values doesn’t not contribute much to the classification algorithm, they are dropped before the data is fed into the classification algorithm. Feature creation is also used to make a meaningful label for the regression algorithm. 


## Methodology Followed

For optimal training and evaluating the classification and regression algorithms, the dataset is split into training, validation and testing subsets. The split proportion used is 60% training data, 20% validation data, 20% testing data. Moreover, I used GridSearchCV and RandomizedSearchCV for cross validation to optimally train algorithms with different parameters. I used 5-fold and 10-fold combinations to get best results from the algorithms. 


## Results

I have properly described the results in the notebook. 









# Data Analytics Bootcamp - Team 1 Final Poject

## Project Overview

Initially launched in 2012, the World Happiness Report reflects the results from an annual survey published by the United Nations' Sustainable Development Solutions Network (SDSN).  One of the main purposes of the report is to encourage world leaders to give more importance to happiness when measuring social and economic success as well as setting policies.  Since its inception, the most important data for the World Happiness Report has been the responses to the main life evaluation questions in the Gallup World Poll from respondents in more than 150 countries.  Therefore, for purposes of the report, happiness is measured based on six factors (GDP, social support, life expectancy, freedom to make life choices, generosity, and perceptions of corruption).  This approach helps to standardize how happiness is measured and compared across multiple geographies.

Our team chose to delve into this topic so we can better understand similarities, differences and key drivers of happiness across multiple geographies and years.  Some of the questions we will attempt to answer are:

- How does each country rank in terms of their happiness scores?
- How have happiness scores trended over multiple years?
- What are the factors that influence happiness the most?
- What are the factors that influence happiness the least?
- Can we predict the happiness scores for the following year?

Our analysis will be based on data from [Kaggle](https://www.kaggle.com/mathurinache/world-happiness-report) which is also available on the [World Happiness Report Website](https://worldhappiness.report/ed/2020/#appendices-and-data).  These are "csv" files with country names, survey year, numerical happiness scores and numerical values representing reponses to the six life evaluation questions from the Gallop World Poll (GDP, social support, life expectancy, freedom to make life choices, generosity, and perceptions of corruption).  We will also integrate information regarding 2020 COVID-19 cases from [Our World In Data](https://ourworldindata.org/covid-cases) to determine if there is a correlation between the number of cases and changes to the 2020 happiness score in specific countries.

Our final presentation is available on [Google Slides](https://docs.google.com/presentation/d/1LzUF1a--rYRFc8Gh1VT8G6T_l73ZLKaS8qHJjd3fUms/edit#slide=id.ged61554b6d_0_8) and our interactive dashboard is available on [Tableau Public](https://public.tableau.com/app/profile/stanley.isaacs/viz/WorldHappiness_16317461141940/HappinessFactors?publish=yes).

## Database Integration

* Created an Entity Relationship Diagram (ERD) 
* Loaded all the datasets in Jupyter Notebook
* Renamed the columns to create a sample dataset 
* Sample data was imported to a PostgreSQL database from Jupyter notebook using SQLAlchemy
* We will use UNION to concatenate our data and form the final dataset
* Created additional columns in the 2019 and 2018 data sets. "Dystopia_Residual" and "Year"
![](https://github.com/degitaccount/Team1_Project/blob/Adam_M_branch/Modified_Resources/Updated_Schema_pic.PNG)

* The images of the ERD and sample data in PostgreSQL can be found below

![](https://github.com/degitaccount/Team1_Project/blob/Adam_M_branch/Final_ERD.PNG)

* We were able to consolidate the ERD for the final dataset

![](https://github.com/degitaccount/Team1_Project/blob/Adam_M_branch/SQL_screenshot.png)

## Machine Learnings Aspects
For the machine learning portion, we will be taking a look at a two different models to ascertain relationships within the data. We will use Principal Component Analysis (PCA)/K-Means clustering to analyze regional similarities as well as multivariate linear regression to analyze the main driver(s) of overall happiness scores. The data that we have gathered contains country name and region, overall happiness score, and items related to overall score such as GDP per capita, social support, healthy life expectancy, freedom to make choices, generosity, perceptions of corruption, and dystopia/residual. All of these columns are important in terms of determining the overall score but we will work to analyze which columns specifically carry more statistical weight. Below is a screenshot of our inital PCA run which shows that the ideal cluster size would be of size 3. 

![image](https://user-images.githubusercontent.com/82548977/131260510-c239bec8-bf8d-4a3d-abbf-10469a6a3bc0.png)

We chose to use PCA, an unsupervised machine learning process used to determine principal components and subsequently use K-means clustering to find similarities in the dataset. The advantages of using this machine learning model is to reduce overfitting of the data by reducing the number of features, improve algorithm performance by removing variables that do not contribute to the decision making process, and is easy to compute. On the other hand, some disadvantages are that independent variables become less interpretable since principal components are linear combinations of the original features, the data needs to be standardized before performing PCA, and there is a trade-off between information loss and dimensionality reduction which is a necessary compromise when using this kind of model.  

One additional analysis we will perform is seeing if the total number of COVID-19 cases for a particular country in 2020 had any correlation with the happiness score from that year. Our prediction is that a country with higher total number of cases of COVID-19 will have seen some sort of decrease in their happiness score from 2019. To see whether this hypothesis is true, we would need to pull in a dataset that we found from an Oxford University source called Our World In Data that includes the total number of covid cases per country for different dates throughout 2020 (click [here](https://ourworldindata.org/covid-cases)) to access the data. We can then take the average of total cases per country/region, and place it in a linear regression as an independent variable against the percent change between happiness scores from 2019 and 2020 as a dependent variable. This analysis will be done using Excel, Jupyter Notebook, and the Python Pandas library.

## Summary of Analysis
After analyzing the happiness score data from 2015-2020 we concluded the following:

-	Finland, Denmark and Switzerland were the top three happiest countries in 2020
-	Afghanistan, South Sudan and Zimbabwe were the three least happy countries in 2020
-	Average happiness scores from 2015-2018 have been stable, however scores have continued to improve since 2019
-	Highest improvement in happiness was in 2020, which is counterintuitive considering the global COVID-19 pandemic and social unrest in various parts of the world
-	Family Support and Economy have consistently scored highest in determining individual happiness, whereas Trust in Government and Generosity scored lowest
-	While 2020 had the highest average score over the time-period we analyzed, Freedom to Make Choices was a bit more important in determining individual happiness than in 2019

![image](https://github.com/degitaccount/Team1_Project/blob/main/Images/ScoreTable.png)

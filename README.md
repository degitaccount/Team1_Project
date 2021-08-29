# Data Analytics Bootcamp - Team 1 Final Poject

## Project Overview

Initially launched in 2012, the World Happiness Report reflects the results from an annual survey published by the United Nations' Sustainable Development Solutions Network (SDSN).  One of the main purposes of the report is to encourage world leaders to give more importance to happiness when measuring social and economic success as well as setting policies.  Since its inception, the most important data for the World Happiness Report has been the responses to the main life evaluation questions in the Gallup World Poll from respondents in more than 150 countries.  Therefore, for purposes of the report, happiness is measured based on six factors (GDP, social support, life expectancy, freedom to make life choices, generosity, and perceptions of corruption).  This approach helps to standardize how happiness is measured and compared across multiple geographies.

Our team chose to delve into this topic so we can better understand similarities, differences and key drivers of happines across multiple geographies and years.  Some of the questions we will attempt to answer are:

- How does each country rank in terms of their happiness scores?
- How have happiness scores trended over multiple years?
- What are the factors that influence happiness the most?
- What are the factors that influence happiness the least?
- Can we predict the happiness scores for the following year?

Our analysis will be based on data from [Kaggle](https://https://www.kaggle.com/mathurinache/world-happiness-report) which is also available on the [World Happiness Report Website](https://worldhappiness.report/ed/2020/#appendices-and-data).  These are "csv" files with country names, survey year, numerical happiness scores and numerical values representing reponses to the six life evaluation questions from the Gallop World Poll (GDP, social support, life expectancy, freedom to make life choices, generosity, and perceptions of corruption).

For the duration of the project, this team intends to use Slack, WhatsApp, Zoom and Google Meet as the main communication tools.  We will leverage class time to discuss progress and plan for each week's deliverables and will meet on an ad-hoc basis whenever live collaboration is necessary.

## Database Integration

* Created an EDR of the data 
* Loaded all the datasets in jupyter notebook
* Renamed the column names to create a sample dataset 
* Sample data is imported to Postgres SQL database from Jupyter notebook using SQLAlchemy
* We will use UNION to concate our datasets and form the final dataset. 
* We will add the year column for each dataset to segregate the data in the final dataset by "year"
* The images of the EDR and sampledata in postgres can be found below.

![Picture1](https://user-images.githubusercontent.com/79213116/131256961-47f897c0-bbcb-48c0-9be5-a441791c06ad.png)

![Picture1](https://user-images.githubusercontent.com/79213116/131256940-7d11189d-6195-4be5-b860-81d6f3f984bc.png)

## Machine Learnings Aspects

One of the analyses that we will perform is seeing if the total number of COVID-19 cases for a particular country in 2020 had any correlation with the happiness score from that year. Our prediction is that a country with higher total number of cases of COVID-19 will have seen some sort of decrease in their happiness score from 2019. To see whether this hypothesis is true, we would need to pull in a dataset that we found from an Oxford University source called Our World In Data that includes the total number of covid cases per country for different dates throughout 2020 (click [here](https://ourworldindata.org/covid-cases)) to access the data. We can then take the average of total cases per country/region, and place it in a linear regression as an independent variable against the percent change between happiness scores from 2019 and 2020 as a dependent variable. This analysis will be done using Excel, Jupyter Notebook, and the Python Pandas library.

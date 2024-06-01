# Predicting Diabetes Rates using the Food Environment Atlas

We utilize the Food Environment Atlas dataset to predict diabetes rate given various food environment indicators such as poverty rate, access to SNAP benefits, access to food stores, and other community characteristics.

# Table of Contents
1. [Introduction](#Introduction)
2. [Dataset](#Dataset)
3. [Exploratory Data Analysis](#Exploratory-Data-Analysis)
4. [Modeling Approach](#Modeling-Approach)
5. [Conclusions and Future Directions](#Conclusions-and-Future-Directions)
6. [Description of Repository](#Description-of-Repository)

## Introduction

Diabetes is a major global health issue, affecting millions and incurring significant costs. In the United States alone, the financial burden reached $412.9 billion in 2022 (source: https://diabetes.org/about-diabetes/statistics/about-diabetes). Accurate predictions of diabetes incidence are crucial for effective governmental planning and intervention. In response, we have developed predictive regression and classification models to anticipate the diabetes rate in different regions of the United States, and to identify key contributing factors. 

## Dataset

We utilize the Food Environment Atlas (FEA) dataset (https://www.ers.usda.gov/data-products/food-environment-atlas),  which comprises 284 variables and is compiled by the USDA’s Economic Research Service (ERS). A part of the ERS mission is to foresee trends and issues arising in agriculture, food, and the environment and to conduct objective research with the goal of informing and enhancing public and private decision-making. The dataset contains food environment indicators such as access to food stores, quantity of food stores, and other community characteristics regarding food, health, nutrition, and socioeconomic status for each US county.

The dataset also provides diabetes prevalence data for each county in 2008 and 2013. We selected diabetese rate in 2013 as our target variable.

![newplot-2](https://github.com/db4014/food-atlas-2024/assets/111996974/79c2df69-52ca-46a5-b6b3-acf91bbfd020)


## Exploratory Data Analysis

We initially visualized the relationship between the target variable, diabetes rate in 2013, and the other variables in the dataset using 2D scatterplots. This was a cumbersome task as it is challenging working with so many variables. So, for our feature variables, we decided to select columns that are percentages because they are already normalized with respect to county population. This approach also prevented redundant information. Additionally, columns that were from a date after the target variable year (2013) were dropped, apart from poverty rate as there was no similar variable. We then computed the correlation matrix between these variables and dropped pairs where the absolute value of the correlation was above the threshold of 0.9. This left us with 49 feature variables. 

There are 3,143 counties in the US and the raw FEA dataset contains a row for each county. We created a new feature for modeling that placed each county into a region of the US, northeast, southeast, midwest, and west. We then separated the data into these regions. 

For the classification model, we defined a new feature named health which is either 0, 1, or 2 depending on whether the diabetes rate is low, medium or high, respectively. This threshold was determined using a violin plot.


## Modeling Approach


## Conclusions and Future Directions


## Description of Repository


All the notebooks are in the _notebooks_ folder

* [EDA.ipynb](link) - This is a Jupyter Notebook
* [Regression with Regions.ipynb](link) - This is a Jupyter Notebook 
* [Classification.ipynb](link) - This is a Jupyter Notebook 
  


Supervised Learning Final Project for CSCA 5622 Introduction to Machine Learning

Laptop Prices

The purpose of this machine leanring project is to create a linear regression model to help me decide what is the best laptop I am interested in buying based on my own personal criteria. My personal criteria is a laptop I can use to play games as well as develop software.

Data Source: 

- This data was downloaded directly from Kaggle, a public repository for learning data science and machine learning and included into this project locally as of 10/10/2024 in a .csv format.
- Laptop Prices - https://www.kaggle.com/datasets/owm4096/laptop-prices
- The features of the data includes several aspects and specifications for purchasing a laptop. Such as price, graphics, memory, processing power, etc. There are 1276 rows of information and 23 features for 26 kB of data. All for various types of laptop models and manufacturers.

Data Cleaning:

- Removed Apple products, Apple products have their place but is not supported for several types of online video games. I also believe Apple computers come at a premium cost.
- Removing the following features as it doesn't matter to me if they have these features or not:
    - TypeName (The laptop is characterized as a Notebook/Ultrabook/etc)
    - Touchscreen
    - IPSpanel (has an IPS screen)
    - RetinaDisplay (has Retina Display)

- Checking how many laptops actually have secondary data only 208 out of the 1,254 have secondary storage so I will be removing this and the SecondaryStorageType feature as well.

Inspecting the cleaned data, there are no missing values or garbage characters that need addressing.

EDA:


<u><b>Supervised Learning Final Project for CSCA 5622 Introduction to Machine Learning</b></u>

<b>Laptop Prices</b>

The purpose of this machine learning project is to create a linear regression model to help me decide what is the best laptop I am interested in buying based on my own personal criteria. My personal criteria is a laptop I can use to play games as well as develop software.

<u>Data Source:</u>

- This data was downloaded directly from Kaggle, a public repository for learning data science and machine learning and included into this project locally as of 10/10/2024 in a .csv format.
- Laptop Prices - https://www.kaggle.com/datasets/owm4096/laptop-prices
- The features of the data includes several aspects and specifications for purchasing a laptop. Such as price, graphics, memory, processing power, etc. There are 1276 rows of information and 23 features for 26 kB of data. All for various types of laptop models and manufacturers. There are 14 categorical features and 9 numerical features.

<u>Data Cleaning:</u>

- Removed Apple products, Apple products have their place but is not supported for several types of online video games. I also believe Apple computers come at a premium cost for their specifications.
- Removing the following features as it doesn't matter to me if they have these features or not:
    - TypeName (The laptop is characterized as a Notebook/Ultrabook/etc)
    - Touchscreen
    - IPSpanel (has an IPS screen)
    - RetinaDisplay (has Retina Display)
- Removed Intel as a GPU option. This is merely the default graphics card and nothing special. This will not do for gaming and is good for web browsing only.
- Removed Screen Width and Screen Height as those are closely coorelated with Inches

- Checking how many laptops actually have secondary data and very few have secondary storage so I will be removing this and the SecondaryStorageType feature as well.

Inspecting the cleaned data, there are no missing values or garbage characters that need addressing. There were no unforseen issues preprocessing this data set. The goal of this data cleaning was to remove as many unnecessary features to help streamline the future models.

<u>EDA:</u>

After cleaning the data and trimming away features I do not find relevant, we can start doing some preliminary inspections of our data set.
Looking at the coorelation matrix and pair plot it looks like the features that have the biggest influence on Price are the weight, RAM, inches, and CPU frequency.
We will use these 4 hyperparameters to tune our regression models.
Some outliers may be inches as the heatmap shows some instances of this becoming more of a factor. Surprisingly primary storage size does not seem to matter at all.
The screen size may be a misnomer as that is effected by the size of the laptop, which is dictated by the weight. The internal parts and size of storage do not have any affect on the laptop. For my prejudgement I would assume larger RAM and higher CPU frequency would yield to a pricier laptop. A higher CPU frequency is used for higher performance.
I would hypothesize that higher RAM, higher CPU frequency, and higher weight would lead to a laptop I am interested in.

<u>Models/Results/Analysis:</u>

- Simple Linear Regression: constructing a simple linear regression model against our best guess features has dictated (with the highest R-squared value) that RAM is the best guess predictor. This could be attributed to the fact that higher RAM in a laptop would be more prolific in laptops with higher end specifications.

- Multi Linear Regression:  with a multi-linear regression model we can see using our top 3 features provides a value of 0 for the p-values, so our features are significant. We then can plot the leverage vs the residual to clean up more outliers. After removing several outliers we can see that our R-squared doesn't really change a lot, meaning the data is all over the place with these combined features. This makes sense as there are several different versions of laptops all with a combination of different components. This shows that this dataset is collinear and coorelated, as the weight, RAM, and CPU frequency become larger, the price becomes larger.

- K-Fold Cross-Validation: we will divide the dataset into K (5) parts. Each time one part of the dataset is used as the test set while the remaining K-1 parts are used as the training set. We will use this model method not discussed in class to cross validate with our other regression models. Running the K-Fold cross validation on the data set broken into 5 subsets. We get an accuracy of roughly 42%. This checks out as the varying degree of data per each laptop averages out to being even.

<u>Conclusion</u>

I believe using a simple linear regression model is satisfactory for our goal of determining which laptop is best. The end results match our earlier hypothesis that larger numbers of RAM, weight, and CPU frequency leads to higher performing thus better for gaming laptops. Some ways I would improve this project would be to perhaps find a dataset of only gaming laptops to narrow down the search further.

Based on the regression plots the following specifications are ideal:
- 16 GB RAM
- Approximately 2.7gHz CPU Frequency
- Weight under 3 kilograms
- For approximately $2,000 (Euros in this case)
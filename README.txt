# Watch Classification System
John Canque

- [Data](#data)
- [EDA](#eda)
- [Model](#model)
- [Final Recommendation System](#sys)
- [Futher Steps](#steps)


## Project Goals
The goal of this project is to look at what features of watches most contribute to higher prices. 


## Data Collection <a name='data'></a>
I used selenium and beautiful soup to scrape all watches from discount watch dealer [WorldofWatches](https://www.worldofwatches.com/). I got the following information for each activity:
- Name
- Brand
- Price
- Band
- Case Diameter
- Color
- and more

## EDA <a name='eda'></a>
### Data Cleaning
Many of the variables were categorical data. In the case where there are more than 10 classes, we look at the top 25 and see if there are patters that we can get using REGEX. Finally, if there are classes that are very small, we bin these into 'Other' categories. 


### Data Exploration
The biggest surprise was the amount of categories within the predictors. Even though I had more than 14k watches, turning dataframe into a sparce matrix would have reduced the output of model, so I decided to just include the largest categories.



### Risk Predictions
As part of the EDA, I wanted to see if I can predict the risk (using Monthly Value at Risk) using the many features of each fund. I used Decision Trees, Random Forests, and Linear Regression to evaluate.


## Recommender Model <a name='model'></a>
'''
I used NLP on the top 25 holdings of each fund to focus on the holdings with the most important frequencies(tf-idf). Then I vectorized into a matrix and added the matrix to my dataframe with the fund features. Finally I used cosine similarity to build the similarity matrix.
'''
 

## Final Recommendation System <a name='sys'></a>
'''
For the final recommender, the user inputs a mutual fund and will get the 10 most similar funds. The user can also filter using any of the features on the fund, ie. can look for cheapest funds in the Healthcare space while focusing on the risk metrics.

I built a front-end using streamlit - here is a look at how it works:

'''

## Further Steps <a name='steps'></a>
- Put app live online
- Add functionality to take in descriptors as user input.
- Add business functionality:
  - Allow for fund families to create portfolios based on their funds based on user's specifications
  - Allow for clients to upload full portfolios to get recommendations

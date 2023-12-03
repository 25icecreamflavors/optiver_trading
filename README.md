# Link to the competition

https://www.kaggle.com/competitions/optiver-trading-at-the-close/overview

# Competition description

Each trading day on the Nasdaq Stock Exchange concludes with the Nasdaq Closing Cross auction. This process establishes the official closing prices for securities listed on the exchange. These closing prices serve as key indicators for investors, analysts and other market participants in evaluating the performance of individual securities and the market as a whole.

In the last ten minutes of the Nasdaq exchange trading session, market makers like Optiver merge traditional order book data with auction book data. This ability to consolidate information from both sources is critical for providing the best prices to all market participants.

In this competition, you are challenged to develop a model capable of predicting the closing price movements for hundreds of Nasdaq listed stocks using data from the order book and the closing auction of the stock. Information from the auction can be used to adjust prices, assess supply and demand dynamics, and identify trading opportunities.

# Target description

The 60 second future move in the wap of the stock, less the 60 second future move of the synthetic index. Only provided for the train set.
The synthetic index is a custom weighted index of Nasdaq-listed stocks constructed by Optiver for this competition.

The unit of the target is basis points, which is a common unit of measurement in financial markets. A 1 basis point price move is equivalent to a 0.01% price move.
Where t is the time at the current observation, we can define the target:

$Target = (\frac{StockWAP_{t+60}}{StockWAP_{t}} - \frac{IndexWAP_{t+60}}{IndexWAP_{t}}) * 10000$

So, as we see, we should predict how close was the Optiver prediction to the real stock price movement. 


# Done
- EDA on features and data
- Learn competition theory and create ideas for the solution
- Add folds
- Create a baseline solution (gradient boosting on basic features)

# Future Plan

- Create additional features
- Choose features by importance
- Try deep learning models (for sequences), for example, small transformers or LSTMs
- Try 2 step solution: firstly classify, if the target is negative or positive, which means that Optiver prediction was in the right direction or not; secondly, use seprate regressor model to predict the value. 

# Data Checks

This is a way to analysis for data errors in a following table

|Date	      | Signal	  | Open	      | High	      | Low	Close	  | Adj Close   | 
| --------- |:---------:|:---------:  |:---------:  |:---------:  |:---------:  |
|2017-02-17	| 16.635032	| 138.449997	| 139.160004	| 138.250000	| 139.110001	| 132.366592| 

We cover data type checks, a desription of the data with visual plots to see what is happening

One example is to use visual check to see what's going on. Below we see there is a strange Adj Close price.

df[['Close','Adj Close']].plot(figsize =(16,8))

![alt text](https://github.com/ah0101/vigilant-octo-eureka1/blob/main/download%20(1).png "Close Vs Adj Close")

Using describe we have the following
| Varible | Value            |
|------   | :---------------:| 
|count    |    1038.000000   |
|mean     |    5.499913      |
|std      |     9.748196     |
|min      |   -33.025085     |
|25%      |     3.777889     |
|50%      |     5.693078     |
|75%      |     6.516651     |
|max      |   308.837845     |

Now we can find the locations where values are 0 those odd ones.

df[df['Signal'] == 0.0].index

also we should recall the normal plots

df['Close'].hist(figsize=(12,6))

![alt text](https://github.com/ah0101/vigilant-octo-eureka1/blob/main/close%20image.png "Close hist")

then we can do the following code:

df[~(df['Close'] <= df['High'])] and df[~(df['Close'] >= df['Low'])]

where we notice some repeated values that we can investigate and ask what's going on.

After we cleansed the data then we can look at how the data looks like:

![alt text](https://github.com/ah0101/vigilant-octo-eureka1/blob/main/visual.png "visual")

we can do a regression on this to see how the test and train data is like.


#now we have Train a Simple Linear Regression and Evaluate Residual Plot

visualizer = ResidualsPlot(LinearRegression(),size=(1080, 720))

visualizer.fit(train_x_1.values.reshape(-1, 1), train_y_1.values.reshape(-1, 1))

visualizer.score(dev_x_1.values.reshape(-1, 1), dev_y_1.values.reshape(-1, 1))

visualizer.show()

![alt text](https://github.com/ah0101/vigilant-octo-eureka1/blob/main/test%20%26%20train.png "test&train")


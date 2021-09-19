# Data Checks

This is a way to analysis for data errors in a following table

|Date	      | Signal	  | Open	      | High	      | Low	Close	  | Adj Close   | 
| --------- |:---------:|:---------:  |:---------:  |:---------:  |:---------:  |
|2017-02-17	| 16.635032	| 138.449997	| 139.160004	| 138.250000	| 139.110001	| 132.366592| 

We cover data type checks, a desription of the data with visual plots to see what is happening

One example is to use visual check to see what's going on. Below we see there is a strange Adj Close price.

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

# playing-around-with-R
Contains code snippets that does mini experiments on datasets

1. Mispricing Analysis 

Description: 
Using a dataset which contains information on the carat value, clarity (or grade) and price for various types of diamonds, 
an R snippet determines whether there has been a mispricing for a category(or grade) of diamonds.

Method:
Analyze diamond price based on diamond clarity(or grade) using ggplot2 package. 
A scatterplot is gnerated using ggplot2 package, overriding the plot defaults using aesthetic specifications(aes(), geom_point()). This enables us to clearly analyze the carat v/s price data based on clarity. 
Only statistically significant data is analyzed by limiting data in the 'data' specification. 
Average values are analyzed as smoothed curves using geom_smooth() 

Insights:
The line at the top represents diamonds with highest clarity(IF), while the line at the bottom represents diamonds with lowest clarity (I1). The lines in between represent diamonds that fall within the intermediate clarity range. 
The principle behind deteccting mis-pricing is that, if the lines overlap, there is mis-pricing. 
It is observed that, at lower carat values, there is mispricing amongst almost all clarity types.
For IF clarity diamonds between calarity range 1.5 and 2.0, there is mis-pricing.
Lowest grade diamonds are clearly priced after carat value of 0.5

Files - diamond_mispricing_anlaysis.R, diamond-price-correl.csv, diamondRplot.jpeg
Info on diamond clarity: http://blog.longsjewelers.com/hs-fs/hub/323238/file-1856876318-jpg/DiamondClarity.jpg?t=1489087979876

2. Testing Law of Large Numbers

Description:
Normal distribution is certainly any OCD-lover's favorite. According to probability theory, 68% of the values in a standard normal distribution lie between -1 and 1.  In this test, we check whether the probability that all numbers obtained from a set of values which follow a normal distribution with mean=0, standard deviation =1 (standard normal distribution) approaches the value 68.2% as we increase the number of random numbers selected. 

Method:
rnorm(N) generates N randomly generated values that follow a normal distribution. 
N is supplied manually for various values. According to statistics, the 68% rule applies for data with N>30
A 'counter' variable records the number of values between -1 and 1
For loop is used to count each number between -1 and 1
IF statement within the FOR loop checks whether each of the numbers passed from the for loop is between -1 and 1
If value is between -1 and 1, increase counter by 1
Once the control exits the for loop, the counter value is divided by N.
The program is executed for various values of N and results are noted.

Observation:
For N=10, percentage =0.7
FOR N=30, percentage=0.73
For N=50000, percentage =68.1
As N approaches a very large number, most of the numbers fall between -1 and 1 with a probability of 68.2.


Files - LLN.R


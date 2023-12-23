# Assignment_2_Set_2
Assignment_2_Set_2
# Topics: Normal distribution, Functions of Random Variables

# 1.The time required for servicing transmissions is normally distributed with  = 45 minutes and  = 8 minutes. The service manager plans to have work begin on the transmission of a customer’s car 10 minutes after the car is dropped off and the customer is told that the car will be ready within 1 hour from drop-off. What is the probability that the service manager cannot meet his commitment? 

A.0.3875   
B.0.2676   
C.0.5   
D.0.6987 

Ans: 
Given:  = 45,  = 8  
P = probability that service manager can meet his commitment.
q = probability that service manager cannot meet his commitment

Car is dropped for 1 hr and work starts after 10 min. Thus time for  successful delivery of commitment is 60 -10 = 50min. Delivery after this time means they cannot meet the commitment 
So,      q = P(x>=50)
	=P((x - )/   >=  (50 - 45)/8)
	=P( Z >=  0.625 )
	=1 - P( Z <=  0.625 )      {as Z table and python gives less than type probability (<=) I.e left 
			            Hand side probability. So we convert >= into <= }

{python code : import scipy.stats as st   
st.norm.cdf(0.625) =   0.7340144709512995 }

	=1 - 0.7340144709512995 
	=0.26598552904870054
So option B is correct answer.



# 2.The current age (in years) of 400 clerical employees at an insurance claims processing center is normally distributed with mean  = 38 and Standard deviation  =6. For each statement below, please specify True/False. If false, briefly explain why.

A.More employees at the processing center are older than 44 than between 38 and 44.
B.A training program for employees under the age of 30 at the center would be expected to attract about 36 employees.

Ans: 
 = 38   =6.
Let x be the age of Employee.
P(X=x) =  probability of age
A: More employees at the processing center are older than 44 than between 38 and 44.
   Probability of employee that is  older than 44 = P(x >= 44)
	=P((x - )/   >=  (44- 38)/6)
	=P( Z >= 1 )
	=1 - P( Z <= 1 )
	=0.15865525393145707
So ,   P(x >= 44) = 0.15865525393145707
Probability of employee that is  older than 44 is 0.15865525393145707 or 15.87%

Probability of employee is  between 38 and 44. =P( 38 <= x <= 44)
	=P( 38 <= x <= 44)
	= P( x <=  44 )  -  P( x  <=  38  )
	=P(z <=  (44- 38)/6 )   -  P(z <=  (38- 38)/6 )
	=P( Z <= 1 ) -  P( Z <= 0) 
	=0.8413447460685429   - 0.5
	{python code 
st.norm.cdf(1)-st.norm.cdf(0) = 0.3413447460685429}
	=0.3413447460685429
So,  P( 38 <= x <= 44) =0.3413447460685429
Probability of employee is  between 38 and 44 is 0.3413447460685429 or 34.13%.

 As  P(x >= 44) < P( 38 <= x <= 44)
Which suggests that, the statement “More employees at the processing center are older than 44 than between 38 and 44.” Is false.

B : A training program for employees under the age of 30 at the center would be expected to attract about 36 employees.

Probability that  A training program for employees under the age of 30 is  P(x<=30).
P(x<=30)=P( Z <= (30- 38)/6 )
	 =P( Z <= (30- 38)/6 )
	 =P( Z <= -1.33 )
	=st.norm.cdf(-1.33)
	=0.09175913565028077 
So, P(x<=30) =0.09175913565028077  I.e. 9.17 %
To find total no of employee under 30 ,
We know n = 400
So, total no of employee under 30 
=0.09175913565028077 *400
=36.70365426011231

So employees under 30 are approximatly 36  .
The statement “A training program for employees under the age of 30 at the center would be expected to attract about 36 employees.” is True.


# 3.If X1 ~ N(μ, σ2) and X2 ~ N(μ, σ2) are iid normal random variables, then what is the difference between 2 X1 and X1 + X2? Discuss both their distributions and parameters.   

Ans: 
Given:
 If  X1 ~ N(μ, σ2) and X2 ~ N(μ, σ2)   and both are independently and identically  distributed.
Here parameters=> mean =2μ , variance =2^2*σ2 = 4σ2 
then 2 X1  ~  N(2μ, 4σ2)  ,
and  
For  X1 + X2 ,  parameters=> mean =μ + μ =2μ, variance =2^2*σ2 = σ2 +σ2  =2σ2
Then X1 + X2 ~ N(2μ , 2σ2)

# 4.Let X ~ N(100, 202). Find two values, a and b, symmetric about the mean, such that the probability of the random variable taking a value between them is 0.99. 

A.90.5, 105.9 
B.80.2, 119.8 
C.22, 78 
D.48.5, 151.5 
E.90.1, 109.9

Ans: 
Given: 
X ~ N(100, 202)  
μ= 100
σ2= 20
P= P(a<= x <=b)= 0.99
Q = 1  -  P =0.01    =>this will be the complimentary of our desired area(area at the 2 tails) 
Q/2 =0.005            => 1 tail 

Lets find Z score for 0.005 probability from python table.
Z score = -2.575 

To find a, b from both side, we have formula  z = (x  -  μ)/σ  ,here x = a,b
 (As we know, a positive Z-score indicates that the value is above the mean(right hand side of mean ), while a negative Z-score indicates that the value is below the mean.(left hand side of mean ))

Thus,
a = μ + (Z * σ) = 100 + (-2.575 * 20) = 48.5
b = μ - (Z * σ) = 100 -  (-2.575 * 20) = 151.5

a, b = (48.5 , 151.5)  option D.

# 5.Consider a company that has two different divisions. The annual profits from the two divisions are independent and have distributions Profit1 ~ N(5, 32) and Profit2 ~ N(7, 42) respectively. Both the profits are in $ Million. Answer the following questions about the total profit of the company in Rupees. Assume that $1 = Rs. 45

A.Specify a Rupee range (centered on the mean) such that it contains 95% probability for the annual profit of the company.
B.Specify the 5th percentile of profit (in Rupees) for the company
C.Which of the two divisions has a larger probability of making a loss in a given year? 

Ans: 
Given:

Profit1 ~ N(5, 32)    Profit2 ~ N(7, 42) 

A.Specify a Rupee range (centered on the mean) such that it contains 95% probability for the annual profit of the company.
To find the combine distribution 

MEAN = Mean1+ Mean2 = 5+7 =12*45(in rupees) = 540
STD DEV = sqrt(VARIANCE)= sqrt(32  +  42) =5* 45 = 225

95% probability which is just 95%  confidence interval and we know the critical values for this 
{Python program = 
st.norm.interval(0.95 ,540, 225) = (99.00810347848784, 980.9918965215122)}

Therefore,
Range is Rs (99.00810347848784, 980.9918965215122) in Millions


B.Specify the 5th percentile of profit (in Rupees) for the company

The 5th percentile corresponds to 1.65 standard deviations below the mean
So Z =  1.645
X =MEAN - (Z*STD DEV)
  =540 - 1.645 *225)
 X = 170.0 Millions







.C .Which of the two divisions has a larger probability of making a loss in a given year? 
 
Profit1 ~ N(5, 32)    Profit2 ~ N(7, 42) 

For Profit1:
Probability of making a loss for Profit1 = P(Profit1 < 0) = CDF(0, 5, 3)  [=cdf(0, mean , sd)]

{stats.norm.cdf(0,5,3)}
=0.040059156863817086
=4%

For Profit2:
Probability of making a loss for Profit2 = P(Profit2 < 0) = CDF(0, 7, 4)

{stats.norm.cdf(0,7,4)}
=0.0477903522728147
=4.7%

Thus , second division has larger probability of loss which is 4.7%.

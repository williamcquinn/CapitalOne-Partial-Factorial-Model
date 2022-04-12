# Partial-Factorial-Experimtental-Design

Predictive modeling to maximize profits from mailing through targeting mailings of 10+ different product offers to 700K+ prospects. 

**Background**

Offering the best product to different groups of people is an intricate task. Especially when it comes to credit cards, there are numerous factors that drive the success and failure of the product offered. Hence, a thorough analysis of the demography and the bankruptcy score is indispensable for reducing the risk and improving the profitability of the rollout. Faced with the task of offering the best of the 12 products to the three groups of customers who have Bankruptcy scores of 150, 200, 250 respectively, we began analyzing the past data to find insights about variables like APR, Fixed/Variable rates, and annual fee having the effects on response rates and LTV. 

**Design of Experiment**

We began the task by designing an experiment to choose the best product to offer to each group of customers. The variables like APR, Fixed/Variable rates, and annual fee with levels of 3, 2, and 2 respectively which led to the creation of 12 different products (3x2x2) were used to find the optimal design. We also included the bankruptcy score with 3 levels as one of the variables so that the number of available combinations is 36 (3x2x2x3). We identified that the design efficiency was 100% for a full factorial design of 36 and the most efficient partial factorial design was 18 trials with an efficiency of  96.5%. 

We chose a partial factorial design for the test as we feel that we can evaluate the response rates of the chosen 18 combinations and then predicting the other combinations using the predictive model rather than testing all the combinations which would cost us 72,000 additional customers in the test run thereby reducing the profitability of the rollout phase.

We decided to use 4,000 as our sample size for each of the 18 combinations we found from the DOE because we believed that it would give us a realistic prediction for the response rate without using up too many of our available customers to mail to. When testing the effects of the three different random seeds we found that the seeds 19 and 172110 gave us different results than with using seed 1234. With seeds 19 and 172110 there were 12 possible products to mail to customers while with seed 1234 there were 10. The additional two products which were included both had APRs of 19.8, so we reasoned that they would not be rational options to test on since they would not have a high response rate and so we decided to use the seed 1234.

**Test Run & Analysis**

Using the results from DOE, we mailed 18 combinations, 6 products per bankruptcy score group, and received the response rates, profits, and costs for the mailing. The total profitability of test run mailing was $ 6,727. Using the results, we built a predictive logit model, predicting the response rates for all 36 possibilities and estimated the profitability of a customer in a respective group for the offered product using the CLVs from exhibit 2. We then identified which top 2-3 product offers that would give us the highest profitability for each level of bankruptcy score by combining the results of the test run and predictive model and allocated a percentage of the 226,000 remaining customers to each product offered for the input of our rollout stage.

**Rollout:**

We began the rollout using the inputs from the predictive model and the test run and received the results of mailing in terms of cumulative profits and mailing costs. The response rates from the rollout were fairly consistent with the predictive model achieving a profit of  $ 618,932 and our cumulative profit being $625,659.

**Key Findings**

1. Customer Lifetime Value varies with BK score because people with higher scores tend to default and resulting in the loss to the organization and vice versa.
2. Customer Lifetime Value varies by the product because products that are more profitable to us will be more costly to the customer, defined by a high APR, variable rate, and carries an annual fee. These product attributes will generate more revenue, so the customers that buy these products will have a higher CLV. Contrarily, customers that buy the products with the attributes of low APR, fixed cost, and no annual fee will have a lower CLV.
3. Predictive models estimated on historical data, in this case, are useful. It is not practical to wait out the lifetime of a customer with a bank, so it makes sense to build models using historical data to classify customers and plan effective offers. Although the model on the past data may not explain the variability due to unexplained factors, it was fair enough to determine the expected response rates for the different products during the test run. Also, the predictive model with inputs from a test run, predicted the response rates of the rollout for the combinations that are not tried out in the test run successfully proving that predictive models estimated on historical data useful in this case
4. The “best product” for all customers would be the one that is least costly to them, given that we are assuming that our customers are rational and they would prefer to pay less for the credit card services, they will want a low APR, fixed-rate, and no annual fee. In our case that would be the combination of low apr, fixed-rate, and no annual fee. The most desirable combination is:

• APR: 14.9

• Fixed-rate

• 0 Annual fee

This fact is validated as the response rates are the highest for this product in all groups when compared to other products both in the predictive model and the rollout results.


# Market Basket Analysis and Product Sales Suggestions

## Research Question and Goal
By analysing purchase history of customers, can certain products be recommended given that other products have been purchased?

The main goal would then be to identify 3 top if then relationships between one product purchased and high likelihood of another.

The data set used is an itemized breakdown of technical product purchases for 7,501 telco customers, with each row considered as a history of transactions.

## Background
Proportions of single products can be calculated by summing up all instances of each then dividing by the total. This would indicate a probability of an item being purchased. The probability of 1 or more items being purchased is also known as a metric called Support. Furthermore, the conditional probability of purchasing one product given that another had been purchased can also be calculated. Another name for this metric is Confidence. A third useful number is called Lift, which indicates the degree of randomness in Confidence. (Datacamp)

Support(X) = freq(X) / N

Confidence(X, Y) = Support(X, Y) / Support(X)

Lift(X, Y) = Support(X, Y) / Support(X)Support(Y)

The essential idea behind Market Basket Analysis (MBA) is to use these 3 metrics to form Association Rules. These rules take an if then form of Antecedent => Consequent. In other words the 3 metrics above allow for the likelihood of a consequent product being purchased given that an antecedent was purchased. These rules can only be obtained from existing data, so they don't necessarily indicate causality. Nevertheless, history can be valuable in attempting to predict future patterns and the purchase history in this data set covers 2 years.

There are 20 unique items in this data set, and the number of combinations of products purchased increases astronomically as more items are considered. Thankfully, there is an implimentable algorithm that can be used to narrow down the number of combinations. According to Datacamp "The Apriori algorithm is structured around the idea that we should retain items that are frequent -- that is, exceed some minimal level of support. The Apriori principle states that subsets of frequent sets must also be frequent. The Apriori algorithm uses this principle to retain frequent sets and prune those that cannot be said to be frequent."

In general confidence, which ranges from 0 to 1, should be high. Also, a lift greater than 1 implies that 2 items in a transaction exceeds their random occurance together. Python also has an association_rules function that ranks association rules according to support, confidence and lift.

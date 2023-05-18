# Powerage
## Assessment of Missingness
### NMAR
The concept of Not Missing At Random (NMAR) implies that the probability of a value being missing is dependent on the actual missing value itself. In the context of this dataset, the column in question records the names of hurricanes responsible for specific power outages. However, it is important to note that not all power outages can be attributed to hurricanes. Some outages may result from facility maintenance or other natural disasters.
Consequently, if a particular power outage is not caused by a hurricane, it is reasonable for the corresponding cell in the hurricane column to be missing. Incorporating an additional column, such as one that records the amount of rainfall during the corresponding time period, could provide further context. For instance, if the rainfall amount is significantly higher than usual, it is more likely that a hurricane is responsible for the power outage, and thus, the hurricane name column would be shown as NaN. 

|   HURRICANE.NAMES |\n|------------------:|\n|               nan |\n|               nan |\n|               nan |\n|               nan |\n|               nan |

### Missingness Test 1
In this test, we try to find out if the missingness in 'CUSTOMERS.AFFECTED' column is depend on the the column 'CAUSE.CATEGORY' or not. The 'CUSTOMERS.AFFECTED' column represent the number of people who are affected by the each of power shortage, and 'CAUSE.CATEGORY' represent the the category that caused this power shortage. Before we get start, lets have a look at what we can observed from the ditribution of the missingness. 
<iframe src="assets/missing_observed_graph1.html" width=800 height=600 frameBorder=0></iframe>

From the graph, we can see that there are few categories of causes, such as 'sever weather', 'public appeal'. And it seems like thre are lot of power shoartage were caused by'intentional attack when the 'CUSTOMERS.AFFECTED' is missing and a lot of shortage were caused by 'severe weather' when the value is no missing. But in order to know if it is a MAR, we need to appeal to a total Variation Distance (TVD) test after the permutation of the 'CUSTOMERS.AFFECTED' column. We choose TVD because there are a few categories of cause and we want to figure out the difference between each category between missing and not missing group. We set cuting off p value to 0.01, and we run the test for 1000 times. Here is the result:

<iframe src="assets/missing_tvd_tested_graph1.html" width=800 height=600 frameBorder=0></iframe>

We get the P value of 0! , and from the graph we can see that the red line and the distribution of the test result are in the two different world, we can conclude that the missingness in colum ''CUSTOMERS.AFFECTED' is MAR since column 'CAUSE.CATEGORY' told us something about the likelyhood of the missingness. 
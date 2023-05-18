## Assessment of Missingness
### NMAR
The concept of Not Missing At Random (NMAR) implies that the probability of a value being missing is dependent on the actual missing value itself. In the context of this dataset, the column in question records the names of hurricanes responsible for specific power outages. However, it is important to note that not all power outages can be attributed to hurricanes. Some outages may result from facility maintenance or other natural disasters.
Consequently, if a particular power outage is not caused by a hurricane, it is reasonable for the corresponding cell in the hurricane column to be missing. Incorporating an additional column, such as one that records the amount of rainfall during the corresponding time period, could provide further context. For instance, if the rainfall amount is significantly higher than usual, it is more likely that a hurricane is responsible for the power outage, and thus, the hurricane name column would be shown as NaN. 


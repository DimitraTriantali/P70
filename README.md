## Data-driven approach for cost-effective last-mile delivery with transshipment nodes and occasional drivers.
- Dimitra G. Triantali (d.triantali@uoi.gr)
- Konstantinos E. Parsopoulos (kostasp@uoi.gr)
- Konstantina Skouri (kskouri@uoi.gr)

## Data

For the experimental analysis of the proposed model, a test suite consisting of 27 scenarios was produced by the combinations of the following values for the underlying parameters:

- Number of transshipment nodes: t &isin; \{1, 2, 3\}
- Total number of customers: c &isin; \{5, 10, 20\}
- Available occasional drivers: o &isin; \{5, 10, 20\}

The corresponding parameter values per scenario were also used as the naming convention: *`Tt_Cc_Oo`*. For example, the scenario with 2 transshipment nodes, 20 customers, and 5 occasional drivers is denoted as T2_C20_O5. The created scenarios are stored in the [scenarios](https://github.com/DimitraTriantali/P70/tree/fa9a7eae01c4f540c02efa999c567fcbf00a21c3/data/scenarios) folder. 

The first row of the dataset contains details about the *`permanent installations`* of the company. The "lat_or" and "lon_or" columns represent the depot's latitude and longitude, respectively, while the "lat_des" and "lon_des" columns indicate the latitude and longitude of the node where the company's permanent fleets finish their routes, respectively. 

The information of the *`transshipment nodes`* is listed in rows 1,2,…,t. For each transshipment node, the columns "lat_or" and "lon_or" indicate its latitude and longitude, respectively, while the "max_capacity" column denotes its maximum capacity. 

The information of *`customers`* is provided in the rows indexed by t+1,t+2,...,t+c. For each customer, the columns "lat_or" and "lon_or" indicate the latitude and longitude of his location, respectively. The "demand" column denotes the weight of his order.

The information on *`occasional drivers`* can be found in the rows indexed by t+c+1,t+c+2,...,t+c+o. For each occasional driver, the columns "lat_or" and "lon_or" represent the latitude and longitude of his starting point, respectively. On the other hand, the "lat_des" and "lon_des" columns show the latitude and longitude of his destination, respectively. The "max_capacity" column represents the maximum weight he can carry, the "max_distance" column indicates the maximum distance he is willing to travel to deliver the order, and the "fee" column includes the minimum compensation he wants to receive in order to make a delivery. 

Information about *`classical vehicles`* is provided in rows indexed by t+c+o+1,t+c+o+2,...,t+c+o+v. The "lat_or" and "lon_or" columns indicate the latitude and longitude of their origin, respectively, while the "lat_des" and "lon_des" columns show the latitude and longitude of their destination, respectively. The "max_capacity" column specifies the maximum weight they can carry and the "fee" column indicates their corresponding cost per unit of traveled distance. 

The last row provides information on the *`emergency vehicle`*. The "lat_or" and "lon_or" columns represent the latitude and longitude of its origin, respectively, while its destination coordinates are included in the "lat_des" and "lon_des" columns. The "max_capacity" column shows the maximum weight it can carry and the "fee" column includes its corresponding cost per unit of traveled distance. 

Additionally, the folder [distances](https://github.com/DimitraTriantali/P70/tree/fa9a7eae01c4f540c02efa999c567fcbf00a21c3/data/distances) contains the calculated distances between the nodes for each scenario. Moreover, in the [probabilities](https://github.com/DimitraTriantali/P70/tree/fa9a7eae01c4f540c02efa999c567fcbf00a21c3/data/probabilities) folder, you will find the predicted acceptance probabilities of the occasional drivers, along with the historical data used to train the machine learning models. 

## Licence

[MIT License](https://github.com/DimitraTriantali/P70/blob/fa9a7eae01c4f540c02efa999c567fcbf00a21c3/LICENSE)

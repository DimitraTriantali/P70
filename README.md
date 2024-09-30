## Data-driven approach for cost-optimized last-mile delivery with transshipment nodes and occasional drivers.
- Dimitra G. Triantali (d.triantali@uoi.gr)
- Konstantinos E. Parsopoulos (kostasp@uoi.gr)
- Konstantina Skouri (kskouri@uoi.gr)

### Data

For the experimental analysis of the proposed model, a test suite consisting of *27 scenarios* was generated by combining the following values for key parameters:

- *Number of transshipment nodes*: `t ∈ {1, 2, 3}`
- *Total number of customers*: `c ∈ {5, 10, 20}`
- *Available occasional drivers*: `o ∈ {5, 10, 20}`

The naming convention for each scenario is based on the corresponding parameter values: `Tt_Cc_Oo`. For example, the scenario with 2 transshipment nodes, 20 customers, and 5 occasional drivers is denoted as `T2_C20_O5`. All the generated scenarios are stored in the [scenarios](https://github.com/DimitraTriantali/P70/tree/fa9a7eae01c4f540c02efa999c567fcbf00a21c3/data/scenarios) folder.

Each dataset is structured as follows:

##### Permanent installations
The first row contains information about the company's *permanent installations*:
- *lat_or* and *lon_or*: The latitude and longitude of the depot.
- *lat_des* and *lon_des*: The latitude and longitude of the endpoint where the company’s vehicles complete their routes.

##### Transshipment nodes
Information about the *transshipment nodes* is found in rows `1, 2, ..., t`:
- *lat_or* and *lon_or*: The latitude and longitude of each transshipment node.
- *max_capacity*: The maximum capacity of each transshipment node.

##### Customers
The details of the *customers* are listed in rows `t+1, t+2, ..., t+c`:
- *lat_or* and *lon_or*: Latitude and longitude of the customer's location.
- *demand*: The weight of the customer's order.

##### Occasional drivers
Information about the *occasional drivers* is available in rows `t+c+1, t+c+2, ..., t+c+o`:
- *lat_or* and *lon_or*: The latitude and longitude of the driver’s starting point.
- *lat_des* and *lon_des*: The latitude and longitude of the driver’s destination.
- *max_capacity*: The maximum weight the driver can carry.
- *max_distance*: The maximum distance the driver is willing to travel to deliver the order.
- *fee*: The minimum compensation the driver requires for a delivery.

##### Permanent fleet
The details of the vehicles belonging to the *permanent fleet* are listed in rows `t+c+o+1, t+c+o+2, ..., t+c+o+v`:
- *lat_or* and *lon_or*: The latitude and longitude of the vehicle’s origin.
- *lat_des* and *lon_des*: The latitude and longitude of the vehicle’s destination.
- *max_capacity*: The maximum weight the vehicle can carry.
- *fee*: The cost per unit of distance traveled.

##### Emergency vehicle
The *emergency vehicle* information is provided in the last row:
- *lat_or* and *lon_or*: The latitude and longitude of its origin.
- *lat_des* and *lon_des*: The latitude and longitude of its destination.
- *max_capacity*: The maximum weight the vehicle can carry.
- *fee*: The cost per unit of distance traveled.

### Additional resources
- The folder [distances](https://github.com/DimitraTriantali/P70/tree/fa9a7eae01c4f540c02efa999c567fcbf00a21c3/data/distances) contains the pre-calculated distances between the nodes for each scenario.
- The folder [probabilities](https://github.com/DimitraTriantali/P70/tree/fa9a7eae01c4f540c02efa999c567fcbf00a21c3/data/probabilities) includes the predicted acceptance probabilities of the occasional drivers, along with the historical data used to train the machine learning models.

## Licence

[MIT License](https://github.com/DimitraTriantali/P70/blob/fa9a7eae01c4f540c02efa999c567fcbf00a21c3/LICENSE)

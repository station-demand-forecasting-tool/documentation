# Exogenous data
<!-- position: 5 -->

The trip end model will use resident population and working population data obtained from the census that was used to calibrate the trip end model (currently the 2011 Census). If significant additional housing or sources of employment have been provided since the census, or are planned in the future, they can be specified in the `exogenous.csv` file. Each should be assigned to an existing centroid, either a postcode or workplace zone (employment can be assigned to a postcode centroid if an appropriate workplace zone is not available).

Example `exogenous.csv` file:

```txt
type;number;centroid
population;1000;TR138JX
houses;150;TR13AS
jobs;400;E33048534
```

* `type` - the type of exogenous data; can be either 'population', 'houses' or 'jobs'.
* `number` - the number of the data type.
* `centroid` - a centroid to assign the data to. For 'population' or 'houses' this must be a full postcode (with no spaces) that existed at the time of the 2011 census. For 'jobs' you can provide either a workplace zone code or a full postcode.

*Note: you can provide multiple entries of the same type.*
# Frequency Groups
<!-- position: 4 -->

The `freqgroups.csv` file is optional.

The station choice model contains daily service frequency as one of the predictor variables. If a demand forecast is required for a new station on an existing line then the service frequency provided for that station should normally match an existing service pattern on that line (unless it is expected that the stopping pattern at this station will differ from existing stations). If a proposed new station was given a higher service frequency than existing stations then the probability of it being chosen would erroneously increase relative to existing stations. Service frequencies of existing stations used by the model are available in the [sdft-docker GitHub repository](https://github.com/station-demand-forecasting-tool/sdft-docker/blob/master/db/data/stations/stations.csv).

If a demand forecast is required based on an expected increase in the service frequency on a line, then the service frequency of existing stations must be adjusted before the model is run. The affected stations are specified using service frequency groups. A frequency group must contain a list of one or more `crscode:frequency` pairs separated by commas. Frequency groups that should be applied are specified in the `stations.csv` file.

*Note: When multiple stations are to be handled concurrently the same frequency group must be specified for every station.*

Here is an example file:

```txt

group_id;group_crs
grp1;CBN:50,HYL:40
grp2;CBN:60,HYL:50

```

In this example, frequency group 'grp1' would adjust the existing service frequency of Camborne station to 50, and Hayle station to 40; and 'grp2' would adjust the existing service frequency of Camborne station to 60, and Hayle station to 50.


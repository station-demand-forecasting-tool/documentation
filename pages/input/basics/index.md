# Model Input Basics
<!-- position: 1 -->

The model inputs are provided using the following CSV files:

* `config.csv` - provides job configuration information
* `stations.csv` - information about the proposed stations
* `freqgroups.csv` - used to adjust the service frequency of existing stations
* `exogenous.csv`- data on new housing, population and/or employment

These files should be placed in a folder named `input` located in the directory path provided to the `sdft_submit()` function via the `dirpath` parameter.

Example input files are provided with the **sdft** R package in the `inst` folder.

For details about each configuration file, see:

* [config](https://www.stationdemand.org.uk/input/config)
* [stations](https://www.stationdemand.org.uk/input/stations)
* [freqgroups](https://www.stationdemand.org.uk/input/freqgroups)
* [exogenous](https://www.stationdemand.org.uk/input/exogenous)
# Stations
<!-- position: 3 -->

Example of the `stations.csv` file with a single entry:

```txt

id;name;region;stn_east;stn_north;acc_east;acc_north;freq;freqgrp;carsp;ticketm;busint;cctv;terminal;electric;tcbound;category;abstract
HELST1;HELSTON;South West;166257;028051;166257;028051;20;;25;true;false;true;true;false;false;E;PNZ,SER

```

* `id` - a unique id for the proposed station (must not match the crscode of any existing station).
* `name` - the long name of the proposed station.
* `region` - the region where the new station is located. This is used to determine the level of uplift applied to a demand forecast to account for growth in rail demand since 2011. Valid regions are:
    * East
    * East Midlands
    * London
    * North East
    * North West
    * Scotland
    * South East
    * South West
    * Wales - Cymru
    * West Midlands
    * Yorkshire And The Humber
* `stn_east` and `stn_north` - the easting and northing of the station's location.
* `acc_east` and `acc_north` - the easting and northing of the nearest access point to the new station from the *existing* road network.
* `freq` - the expected number of arrivals and departures during a typical weekday. For an existing route, this would normally match other stations on the route with similar stopping patterns. This can be checked by consulting the [data on existing stations](https://github.com/station-demand-forecasting-tool/sdft-docker/blob/master/db/data/stations/stations.csv).
* `freqgrp` - the id of a frequency group defined in `freqgroups.csv` file. 
* `carsp` - the number of car parking spaces provided at the station.
* `ticketm` - whether or not a ticket machine will be provided at the station (must be 'true' or 'false').
* `busint` - whether nor not a bus interchange will be available at the station (must be 'true' or 'false').
* `cctv` - whether or not CCTV will be installed at the station (must be 'true' or 'false').
* `terminal` - whether the station is a terminal station on the line (must be 'true' or 'false').
* `electric` - whether or not the station will be served by electric services via overhead lines or a third rail (must be 'true' or 'false').
* `tcbound` - whether or not the station is the boundary station of a travelcard ticket (must be 'true' or 'false').
* `category` - the Network Rail category of the proposed station. This should be 'F' for unstaffed stations, and 'E' for stations that have full-time or part-time staff.
* `abstract` - a comma separated list of *up to three* crscodes of *existing* stations for which an abstraction analysis is required.

## Sensitivity analysis

*This applies to 'isolation' mode only.*

If sensitivity analysis is required for service frequency or car parking spaces then simply create a new station entry with these fields amended as appropriate. The ID must be unique, but if you use the same station name the processing will be faster as unnecessary duplicate analysis will be avoided. If two or more entries have an identical station name they can only differ in the values of the frequency, parking spaces and/or frequency group fields. Remember to define different frequency groups as appropriate for the additional entries. 
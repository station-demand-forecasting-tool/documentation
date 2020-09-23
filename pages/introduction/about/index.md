# About
<!-- position: 1 -->

*This documentation is a work in progress and not all sections currently have content*.

This site contains information about the Station Demand Forecasting Tool and how to install and use it. 

The Station Demand Forecasting Tool generates a demand forecast (predicted trips per year) for one or more proposed local railway stations (a local railway station is a Network Rail category E or F station). If required, the tool can also produce an analysis of potential abstraction of journeys from existing stations, enabling the net impact of a new station on rail use to be estimated. Forecasts for multiple stations can be accommodated as part of the same job. These can be treated independently (alternative station locations are to be assessed) or concurrently (the proposed stations will coexist).

The underlying model is based on research by the University of Southampton’s [Transportation Research Group](https://www.southampton.ac.uk/engineering/research/groups/transportation_group.page?). At its core is a trip end model which has been calibrated on the smaller stations in Great Britain. In such a model the number of trips is a function of the population in a station’s catchment and a range of other variables, such as service frequency and number of jobs nearby. A novel aspect of this model is that probability-based catchments are defined using a station choice model. Rather than assuming everyone will use their nearest station, this provides a more realistic representation of behaviour and allows competition to occur between stations.

Generating a demand forecast involves a series of data processing and spatial analysis steps with a high computational requirement. As the model has been coded to take advantage of parallelisation, the length of a model run will depend on the number of available processor cores.

The video below will give you a good introduction to how the tool works. However, note that the web interface shown in the video is not part of the open source project. Currently, [model inputs](https://www.stationdemand.org.uk/input/) are instead provided using several CSV files, and [model outputs](https://www.stationdemand.org.uk/output/) are provided as CSV and GeoJSON files.

[![Video of The Station Demand Forecasting Tool](http://img.youtube.com/vi/q0CmY5lilWg/0.jpg)](http://www.youtube.com/watch?v=q0CmY5lilWg "The Station Demand Forecasting Tool")
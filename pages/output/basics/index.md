# Model Output Basics
<!-- position: 1 -->

When a job is complete, several files are created in a subfolder of the `output` folder. The subfolder takes the name of the job as specified in the `config.csv` file. 

The files, for a job without an abstraction analysis, are as follows:
   
   * `station_forecast.csv` - contains the input data and the forecast for each station
   * `exogenous.csv` - contains a summary of the input exogenous data
   * `station_catchment.geojson` - one file is created for each station, with the word 'station' in the filename replaced by the station name. It contains the postcode centroids for the station's probabilistic catchment, with the probability of the station being chosen as an attribute of each centroid.
   * `sdr.log` contains information on the job run. The level of detail will depend on the `loglevel` set in the `config.csv` file.
   
If an abstraction analysis was requested, the following additional files will be generated:

* `abstraction_analysis.csv` - contains the results of the abstraction analysis. 
* `proposed_impacted_catchment_before.geojson` - contains the probabilistic catchment for the 'impacted' station *before* the 'proposed' station exists. One or more files of this type depending on job.
* `proposed_impacted_catchment_after.geojson` - contains the probabilistic catchment for the 'impacted' station *after* the 'proposed' station exists. One or more files of this type depending on job.
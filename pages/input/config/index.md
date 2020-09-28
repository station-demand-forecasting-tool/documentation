# Configuration
<!-- position: 2 -->

Example of the `config.csv` file:

```txt

job_id;method;testing;loglevel;cores
job004;isolation;true;DEBUG;6

```

* `job_id` - up to 20 characters (this is used as the database schema name so must be valid schema name for postgreSQL).
* `method` - either 'isolation' or 'concurrent' (see 'Handling multiple stations' below).
* `testing` - either 'true' or 'false'. If true then the job will run in testing mode. The testing mode only considers a very small catchment area for a proposed station to speed up processing. Any forecast produced in testing mode is not valid.
* `loglevel` - determines the level of logging in the output `sdr.log` file. Can be one of: DEBUG, INFO, WARN, ERROR, or FATAL.
* `cores` - the number of processing cores to allocate to the job. This must be at least 4. Two of these cores will be reserved for the operating system. 


## Handling multiple stations

The model can forecast demand for multiple stations. If a forecast is requested for more than one station, the stations can either be treated in isolation (the default) or concurrently. Concurrent handling assumes that all the requested stations will be present in the new situation (for example, a new line). Handling in isolation assumes that each station is separately present in the new situation (for example, when considering a set of potential alternative station locations). 

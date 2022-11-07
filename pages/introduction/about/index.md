# About
<!-- position: 1 -->

This site contains information about the open source railway Station Demand Forecasting Tool (SDFT) and how to install and use it. The SDFT is released under the [Affero GPL](https://www.gnu.org/licenses/agpl-3.0.txt). This licence allows you to use, copy and change the code of the software, but requires you to release your changes under the same terms and conditions if you distribute the software or you run a modified copy on a web server on the Internet. 

<h2 id="purpose">Purpose and Scope</h2>

The SDFT generates a rail demand forecast (predicted trips per year) for one or more proposed local railway stations (a local railway station is considered to be a Network Rail category E or F station). If required, the tool can also produce an analysis of potential abstraction of journeys from existing railway stations, enabling the net impact of a new station on rail demand to be estimated. Forecasts for multiple stations can be accommodated as part of the same job. These can be treated independently (alternative station locations are to be assessed) or concurrently (the proposed stations will coexist).

The underlying model is based on research by the University of Southampton’s [Transportation Research Group](https://www.southampton.ac.uk/research/groups/transportation-group). At its core is a national trip end model which has been calibrated on the smaller stations in Great Britain. In this type of model the number of trips is a function of the population in a station’s catchment and a range of other variables, such as service frequency and number of jobs nearby. A novel aspect of this model is that probability-based catchments are defined using a station choice model applied at the unit postcode level. Rather than assuming everyone will use their nearest station, this provides a more realistic representation of behaviour and allows competition to occur between stations.

The SDFT is well-suited to the rapid and inexpensive assessment of a number of potential station sites as part of an early sifting process. For example, the underlying model was used to [forecast rail demand at 12 potential new stations in Wales](https://gov.wales/station-demand-forecasts-wales) as part of the Welsh National Transport Plan. Even in cases where local or regional government or transport authorities decide to commission their own bespoke studies, the SDFT can be used as a sense-check tool. For example, if rail demand forecasts produced by the local model and the SDFT differ by an order of magnitude, this would be a clear warning that the local rail demand models may not be reliable. 

The SDFT also has the potential to democratise the planning process by opening up the ability to produce forecasts to a much wider range of stakeholders, empowering local campaign groups who can often feel powerless when arguing against official forecasts that they believe to be unduly pessimistic.

Generating a rail demand forecast using the SDFT involves a series of data processing and spatial analysis steps with a high computational requirement. As the model has been coded to take advantage of parallelisation, the length of a model run will depend on the number of available processor cores.

An article about the tool, setting it in context, appeared in [Issue 165 (October 2020)](https://www.railwatch.org.uk/backtrack.php?mag=rwm&issue=165) of Railwatch (the quarterly magazine published by Railfuture).

The video below gives a good overview of how the tool works. However, the web interface shown in the video is not part of the open source project. Currently, [model inputs](https://www.stationdemand.org.uk/input/) are instead provided via CSV files, and [model outputs](https://www.stationdemand.org.uk/output/) are generated as CSV and GeoJSON files.

[![Video of The Station Demand Forecasting Tool](https://img.youtube.com/vi/q0CmY5lilWg/0.jpg)](http://www.youtube.com/watch?v=q0CmY5lilWg "The Station Demand Forecasting Tool")

<h2 id="cite">How to Cite</h2>

To cite SDFT in publications, please use the following (amend for version number and obtain
the DOI for the specific version from: [https://zenodo.org/record/4066924](https://zenodo.org/record/4066924)):

  > Marcus Young and Simon Blainey (2020). sdft: The Station Demand Forecasting Tool. R package version 0.3.0. https://doi.org/10.5281/zenodo.4066924

A BibTeX entry for LaTeX users:
```txt
  @Manual{,
    author = {{Marcus Young} and {Simon Blainey}},
    title = {{sdft: The Station Demand Forecasting Tool}},
    year = {2020},
    note = {{R package version 0.3.0}},
    doi = {{https://doi.org/10.5281/zenodo.4066924}},
  }
  
```
<h2 id="team">The Team</h2>


| [Dr Simon Blainey](https://www.southampton.ac.uk/engineering/about/staff/spb1g09.page) (Principal Investigator) | [Dr Marcus Young](https://www.southampton.ac.uk/engineering/about/staff/may1y17.page) (Researcher & Lead Developer) |
|:----------:|:----------:|
| ![Marcus Young](https://stationdemand.blob.core.windows.net/images/2020/09/23/simon-small.png) | ![Marcus Young](https://stationdemand.blob.core.windows.net/images/2020/09/23/marcus_small.png) |


<h2 id="funding">Funding and Acknowledgements</h2>

The development of the underlying models formed part of a [PhD research project](https://eprints.soton.ac.uk/430041/) funded by the EPSRC. Development of the automated tool was supported through the University of Southampton’s Impact Acceleration Account (also funded by the EPSRC). The station choice model was calibrated using passenger survey data kindly provided by the Welsh Government and Transport Scotland.

<h2 id="limitations">Limitations</h2>

Users should be aware of the following potential limitations of the underlying trip end model:

* This type of model cannot take account of the destinations that are (or are not) served by the station. If the station will not provide access to a desired destination (i.e. one with jobs, retail and leisure opportunities etc.) then rail demand is likely to be over-estimated.     
* It does not explicitly take account of trip attraction resulting from tourism. This may not be a major concern for typical levels of tourism as many of the calibration stations will have an element of tourism and its trip generation potential will be reflected in the catchment population variable. However, if a station is expected to be used by a large number of tourists then the model is likely to under-estimate rail demand and a manual adjustment to the forecast will be necessary.
* If a proposed railway station is primarily a *destination* station, then the tool is unlikely to be appropriate. This will include, for example, stations that specifically serve a sports arena, concert venue or retail park.
* The model may under-estimate rail demand when an unusually high proportion of passengers access the railway station by bus, for example if the station is part of a transport interchange hub where bus services converge from a large surrounding area. 
* The model may over-estimate rail demand when there is strong competition from an alternative transit mode, in particular when a frequent, reliable and lower-priced bus service is available to the primary destination. 

<h2 id="liability">Liability</h2>

The SDFT is designed to support the decision-making process and it is assumed that users will have sufficient local knowledge to recognise situations, like those listed above, where it may not be appropriate or where adjustments to the forecasts may be required to take account of local factors. We cannot accept liability for any loss or damage caused by the use of the tool.


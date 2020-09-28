# Visualising catchments
<!-- position: 2 -->

## Using OS Code-Point with polygons

The [OS Code-Point with polygons](https://www.ordnancesurvey.co.uk/business-government/products/code-point-polygons) dataset shows the notional shape of every unit postcode in Great Britain. It can be used to visualise a station's probabilistic catchment. An example is shown below:

![Example polygon catchment](https://stationdemand.blob.core.windows.net/images/2020/09/28/catchment_polygons.jpg)

As OS Code-Point with polygons is not open data, the SDFT does not generate station catchments using it. However, if you have access to the dataset you could use a GIS to join the postcode centroids (with probability attribute) to the polygon layer. 


## Using IDW interpolation in QGIS

An alternative to using postcode polygons to visualise a station catchment, is to perform an IDW interpolation in a GIS. We have produced good results using the 'IDW Interpolation' algorithm in QGIS. First export the geoJSON layer to a shapefile (changing the projection to EPSG:27700 at the same time), and then run the 'IDW Interpolation' algorithm with the following settings:

* Distance coefficient: 25
* Extent: set to your catchment layer
* Output raster size: pixel size X: 10; pixel size Y: 10

An example, for the same catchment shown using postcode polygon above, is shown below (raster clipped to coastline):

![Example idw catchment](https://stationdemand.blob.core.windows.net/images/2020/09/28/catchment_idw.jpg)


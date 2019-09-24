# Hurricane evacuation zones

This is a compilation of evacuation zones begun in the middle of the 2019 season by GateHouse Media LLC. Contributions would be welcomed.

Please see also [Hurricane Tools](https://github.com/GateHouseMedia/hurricane-tools) and [Power Outages](https://github.com/GateHouseMedia/power-outages).


The KMLs are conversions from the original layers, and typically have modifications:

- Multiple entries for a particular hurricane zone are dissolved into solo versions.

- The CRS is frequently converted to EPSG 4326 / WGS84

- Lines may be modestly simplified, e.g., by 20 feet. One KML was shrunk about 95 percent this way. (Note: 0.00004 degrees in Florida may be pretty close to 15 feet.)

- Areas under a certain size, like 2000 square feet, can be dropped.

- Areas that are *not* in hurricane evacuation zones may be struck.

A sample embed code for Google Maps is available here:
https://pastebin.com/JaSNC1dM

Standardized color keys help considerably.

### fl-bay

Bay County, Fla.

Pulled: September 2019

Origin: Evacuation Zones dataset, http://data-baycountygis.opendata.arcgis.com/datasets/evacuation-zones

https://drive.google.com/open?id=1YtoldYnbQKLLZxIO8lou0-FpnM8ZWJDF&usp=sharing


### fl-duval

Duval County, Fla.

Pulled: September 2019.

Origin: Records request and money order.

https://www.google.com/maps/d/u/0/edit?mid=17uCI1TAbhGNI5XqZtpJlzy5FF4uxJ5yr&ll=30.108910654905152%2C-81.45540122359341&z=10


### fl-flagler

Flagler County, Fla.

Pulled: September 2019

Origin: Searching for "evac" at http://data-fcmaps.opendata.arcgis.com/

https://www.google.com/maps/d/u/0/edit?mid=1l2WqMQvmehrxcbSkqGah1hSNWIITyaHY&ll=29.158760341415245%2C-80.9948695021863&z=11


### fl-manatee

Manatee County, Fla.

Pulled: September 2019

Origin: Pulled from Evacuation Levels dataset, https://public-manateegis.opendata.arcgis.com/

https://www.google.com/maps/d/edit?mid=1Oh5pdmrvpIsZ8jsCHatAD9H7QNL3cEqB&ll=27.395186380366894%2C-82.53387658362345&z=11

### fl-palmbeach

Palm Beach County, Fla.

Pulled: September 2019

Origin: Pulled from Evacuation_Areas_2012 dataset, http://maps.co.palm-beach.fl.us/EGISdata_catalog/

https://www.google.com/maps/d/u/0/edit?mid=166Ew7mzl0s2Oi-2pfKE6q2RYmLmFcAbX&ll=26.645304193166602%2C-80.458508&z=10


### fl-sarasota

Sarasota County, Fla.

Pulled: September 2019

Origin: Downloaded from StormEvacuationLevel dataset, https://data-sarco.opendata.arcgis.com/search?tags=Environmental%2Csafety

https://www.google.com/maps/d/edit?mid=1Oh5pdmrvpIsZ8jsCHatAD9H7QNL3cEqB&ll=27.395186380366894%2C-82.53387658362345&z=11

Warning: This does not play nicely in several different ways. There are an extraordinary number of polygons, some of which represent like, 0 square feet. A straight KML conversion is runs something silly like 120mb; Google wants no more than 5mb. And the borders are just crazily complex. So the default CRS is feet; this relies on you having calculated the area for each poly:

```c:\osgeo4w\bin\ogr2ogr -f KML sarasotav5everything.kml sarasotav5.shp -simplify 35 -mapFieldType Integer64=Integer -dialect sqlite -sql "SELECT ST_Union(geometry), evacuation FROM sarasotav5 where area >= 200 GROUP BY evacuation" -t_srs EPSG:4326```


### fl-stjohns

St. Johns County, Fla.

Pulled: September 2019.

Origin: Email response to records request.

https://www.google.com/maps/d/u/0/edit?mid=17uCI1TAbhGNI5XqZtpJlzy5FF4uxJ5yr&ll=30.108910654905152%2C-81.45540122359341&z=10


### fl-volusia

Volusia County, Fla.

Pulled: September 2019

Origin: EvacZones dataset from http://maps.vcgov.org/gis/download/shapes.htm

https://www.google.com/maps/d/u/0/edit?mid=1l2WqMQvmehrxcbSkqGah1hSNWIITyaHY&ll=29.158760341415245%2C-80.9948695021863&z=11

### fl-walton

Walton County, Fla.

Pulled: September 2019

Origin: Records request (may go online later)

https://drive.google.com/open?id=1YtoldYnbQKLLZxIO8lou0-FpnM8ZWJDF&usp=sharing

### Counties without hurricane evacuation zones

Washington County, Fla. as of September 2019


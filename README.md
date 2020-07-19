The CSV files in this repository are daily exports of the
[`Florida_COVID_19_Deaths_by_Day`][tbl] table. The Florida Department of Health
appears to updated the table once a day around 10am-11am Eastern time.

[tbl]: https://fdoh.maps.arcgis.com/home/item.html?id=230270972343459a812a1ae8c28574a6

The [download](download) Python script automatically downloads the table, converts it from
JSON to CSV format, and saves it as `deathsbydateexport_YYYYMMDD.csv`.

If for whatever reason you want to download the table without using the script:

1. Browse [`Florida_COVID_19_Deaths_by_Day`][tbl]
1. Click on [View](https://services1.arcgis.com/CY1LXxl9zlJeBuRZ/arcgis/rest/services/Florida_COVID_19_Deaths_by_Day/FeatureServer)
1. Click on table [Florida_COVID_19_Deaths_by_Day](https://services1.arcgis.com/CY1LXxl9zlJeBuRZ/ArcGIS/rest/services/Florida_COVID_19_Deaths_by_Day/FeatureServer/0)
1. Click on [Query](https://services1.arcgis.com/CY1LXxl9zlJeBuRZ/ArcGIS/rest/services/Florida_COVID_19_Deaths_by_Day/FeatureServer/0/query)
1. Type:
```
Where: ObjectId>0
Result type: standard  (although seems to work with none too)
Out Fields: *
Format: JSON
```
1. Click [Query (GET)](https://services1.arcgis.com/CY1LXxl9zlJeBuRZ/ArcGIS/rest/services/Florida_COVID_19_Deaths_by_Day/FeatureServer/0/query?where=ObjectId%3E0&objectIds=&time=&resultType=none&outFields=*&returnIdsOnly=false&returnUniqueIdsOnly=false&returnCountOnly=false&returnDistinctValues=false&cacheHint=false&orderByFields=&groupByFieldsForStatistics=&outStatistics=&having=&resultOffset=&resultRecordCount=&sqlFormat=none&f=pjson&token=)
1. The above URL returns the data in JSON format

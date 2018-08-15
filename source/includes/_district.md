# Districts

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/districts.json?shifts=true
```

 > Response

```json
[
    {
        "id": 1,
        "name": "Beat 1",
        "created_at": "2015-09-22T11:45:45.000-07:00",
        "updated_at": "2015-10-16T11:46:24.000-07:00",
        "is_hidden": false,
        "box_size": 150,
        "lat_min": "37.7251167959645",
        "lat_max": "37.7397032208206",
        "lng_min": "-121.44552474922",
        "lng_max": "-121.40821298484",
        "map_center_lat": "37.73241000839255",
        "map_center_lng": "-121.42686886703",
        "years_of_data": 5,
        "land_area": null
        "shifts": [
            {
                "id": 1,
                "label": "DAY",
                "hour_start": 5,
                "hour_end": 15,
                "created_at": "2015-09-22T11:45:53.000-07:00",
                "updated_at": "2015-09-22T11:45:53.000-07:00",
                "num_boxes": 3
            },

            ...

        ]
    },

    ...

]
```


`GET <YOUR_SITE>.predpol.com/api/districts.json`

The list API is used to fetch all the districts. The response contains an array of district objects.

Districts can be filtered by passing some parameters (optional) in the request as listed below.

Parameter | Type | Description
--------- | ----- | -----------
hidden | Boolean | Some districts are hidden. Pass this parameter as 'true' to retrive hidden districts.
kml | Boolean | Each district has a KML associated with it. If this parameter is true, districts are retrieved along with their KML.
incident_types | Boolean | Each district has incident_types associated with it. If this parameter is true, districts are retrieved along with their incident_types.
shifts | Boolean | Each district has shifts associated with it. If this parameter is true, districts are retrieved along with their shifts.

Each district object in the response contains the following properties.

Property | Type | Description
--------- | -------- | -------
id | Integer | The unique id of the district.
name | String | The name of the district.
created_at | String | The date and time that the district was created.
updated_at | String | The date and time that the district was last updated.
is_hidden | Boolean | True if the district has been soft deleted.
box_size | Integer | The size in meteres of prediction boxes in this district.
lat_min | Float | The minimum latitude of the district in decimal degrees.
lat_max | Float | The maximum latitude of the district in decimal degrees.
lng_min | Float | The minimum longitude of the district in decimal degrees.
lng_max | Float | The maximum longitude of the district in decimal degrees.
map_center_lat | Float | The center of the district in decimal degrees latitude.
map_center_lng | Float | The center of the district in decimal degrees longitude.
years_of_data  | Integer | The number of years of data considered.
land_area | Float | The land area of the district in meters squared.
kml | String | The kml of the district.
incident_types | Array | An array of the incident types associated with the district.
shifts | Array | An array of the shifts associated with the district.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/districts/<ID>.json
```

> Response

```json
{
    "id": 1,
    "name": "Beat 1",
    "created_at": "2015-09-22T11:45:45.000-07:00",
    "updated_at": "2015-10-16T11:46:24.000-07:00",
    "is_hidden": false,
    "box_size": 150,
    "lat_min": "37.7251167959645",
    "lat_max": "37.7397032208206",
    "lng_min": "-121.44552474922",
    "lng_max": "-121.40821298484",
    "map_center_lat": "37.73241000839255",
    "map_center_lng": "-121.42686886703",
    "years_of_data": 5,
    "land_area": null
}
```

`GET <YOUR_SITE>.predpol.com/api/districts/<ID>.json`

The show API is used to fetch an individual district. The response contains the district object corresponding to the 'id' passed in the request.

Each district can be filtered by passing some parameters (optional) in the request as listed below.

Parameter | Type | Description
--------- | ----- | -----------
kml | Boolean | Each district has a KML associated with it. If this parameter is true, districts are retrieved along with their KML.
incident_types | Boolean | Each district has incident_types associated with it. If this parameter is true, districts are retrieved along with their incident_types.
shifts | Boolean | Each district has shifts associated with it. If this parameter is true, districts are retrieved along with their shifts.

The district object returned contains the following properties.

Property | Type | Description
--------- | -------- | -------
id | Integer | The unique id of the district.
name | String | The name of the district.
created_at | String | The date and time that the district was created.
updated_at | String | The date and time that the district was last updated.
is_hidden | Boolean | True if the district has been soft deleted.
box_size | Integer | The size in meteres of prediction boxes in this district.
lat_min | Float | The minimum latitude of the district in decimal degrees.
lat_max | Float | The maximum latitude of the district in decimal degrees.
lng_min | Float | The minimum longitude of the district in decimal degrees.
lng_max | Float | The maximum longitude of the district in decimal degrees.
map_center_lat | Float | The center of the district in decimal degrees latitude.
map_center_lng | Float | The center of the district in decimal degrees longitude.
years_of_data  | Integer | The number of years of data considered.
land_area | Float | The land area of the district in meters squared.
kml | String | The kml of the district.
incident_types | Array | An array of the incident types associated with the district.
shifts | Array | An array of the shifts associated with the district.


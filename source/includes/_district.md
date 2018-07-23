# District APIs

## Index

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'[
    {
        "id":1,
        "name":"Beat 1",
        "group_name":"Tracy Police",
        "rd":"1",
        "endpoint":null,
        "created_at":"2015-09-22T11:45:45.000-07:00",
        "updated_at":"2015-10-16T11:46:24.000-07:00",
        "dns_name":"beat_1",
        "parent_id":8,
        "is_hidden":false,
        "box_size":150,
        "kml_url":"https://pp-kml-files.s3.amazonaws.com/california/cities--places/tracy/tracy-beat1.kml",
        "lat_min":"37.7251167959645",
        "lat_max":"37.7397032208206",
        "lng_min":"-121.44552474922",
        "lng_max":"-121.40821298484",
        "initial_zoom":15,
        "map_center_lat":"37.73241000839255",
        "map_center_lng":"-121.42686886703",
        "years_of_crime":5,
        "locality":null,
        "district_type":null,
        "basic_cars":null,
        "display_order":210,
        "report_num_clusters":6,
        "land_area":null
    },
    {
        "id":2,
        "name":"Beat 2",
        "group_name":"Tracy Police",
        "rd":"2",
        "endpoint":null,
        "created_at":"2015-09-22T11:45:54.000-07:00",
        "updated_at":"2015-10-16T11:46:24.000-07:00",
        "dns_name":"beat_2",
        "parent_id":8,
        "is_hidden":false,
        "box_size":150,
        "kml_url":"https://pp-kml-files.s3-us-west-2.amazonaws.com/temporary/8576e66b-b2f4-49b9-9629-5a4333bea4ac.kml",
        "lat_min":"37.677336618694",
        "lat_max":"37.7296125145321",
        "lng_min":"-121.461072614548",
        "lng_max":"-121.397969524469",
        "initial_zoom":13,
        "map_center_lat":"37.70347456661305",
        "map_center_lng":"-121.4295210695085",
        "years_of_crime":5,
        "locality":null,
        "district_type":null,
        "basic_cars":null,
        "display_order":220,
        "report_num_clusters":6,
        "land_area":null
    }
]' https://<customer_name>.predpol.com/api/districts.json
```

`GET <customer_name>.predpol.com/api/districts.json`

The index API is used to fetch all the districts. The response contains an array of district objects.

Districts can be filtered by passing some parameters (optional) in the request as listed below.

Parameter | Value | Description
--------- | ----- | -----------
hidden | Boolean | Some districts are hidden. Pass this parameter as 'true' to retrive hidden districts.
kml | Boolean | Each district has a KML associated with it. If this parameter is true, districts are retrieved along with their KML.
crime_types | Boolean | Each district has crime_types associated with it. If this parameter is true, districts are retrieved along with their crime_types.
shifts | Boolean | Each district has shifts associated with it. If this parameter is true, districts are retrieved along with their shifts.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'{
        "id":1,
        "name":"Beat 1",
        "group_name":"Tracy Police",
        "rd":"1",
        "endpoint":null,
        "created_at":"2015-09-22T11:45:45.000-07:00",
        "updated_at":"2015-10-16T11:46:24.000-07:00",
        "dns_name":"beat_1",
        "parent_id":8,
        "is_hidden":false,
        "box_size":150,
        "kml_url":"https://pp-kml-files.s3.amazonaws.com/california/cities--places/tracy/tracy-beat1.kml",
        "lat_min":"37.7251167959645",
        "lat_max":"37.7397032208206",
        "lng_min":"-121.44552474922",
        "lng_max":"-121.40821298484",
        "initial_zoom":15,
        "map_center_lat":"37.73241000839255",
        "map_center_lng":"-121.42686886703",
        "years_of_crime":5,
        "locality":null,
        "district_type":null,
        "basic_cars":null,
        "display_order":210,
        "report_num_clusters":6,
        "land_area":null
}' https://<customer_name>.predpol.com/api/districts/<id>.json
```

`GET <customer_name>.predpol.com/api/districts/<id>.json`

The show API is used to fetch an individual district. The response contains a district object corresponding to the 'id' passed in the request.

Each districts can be filtered by passing some parameters (optional) in the request as listed below.

Parameter | Value | Description
--------- | ----- | -----------
kml | Boolean | Each district has a KML associated with it. If this parameter is true, districts are retrieved along with their KML.
crime_types | Boolean | Each district has crime_types associated with it. If this parameter is true, districts are retrieved along with their crime_types.
shifts | Boolean | Each district has shifts associated with it. If this parameter is true, districts are retrieved along with their shifts.

## Create

## Update

## Destroy

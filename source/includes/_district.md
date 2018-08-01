# District APIs

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'{
    "hidden": false,
    "kml": true,
    "crime_types": true,
    "shifts": true
}' https://<YOUR_SITE>.predpol.com/api/districts.json
```

`GET <YOUR_SITE>.predpol.com/api/districts.json`

The list API is used to fetch all the districts. The response contains an array of district objects.

Districts can be filtered by passing some parameters (optional) in the request as listed below.

Property | Type | Description
--------- | ----- | -----------
hidden | Boolean | Some districts are hidden. Pass this parameter as 'true' to retrive hidden districts.
kml | Boolean | Each district has a KML associated with it. If this parameter is true, districts are retrieved along with their KML.
crime_types | Boolean | Each district has crime_types associated with it. If this parameter is true, districts are retrieved along with their crime_types.
shifts | Boolean | Each district has shifts associated with it. If this parameter is true, districts are retrieved along with their shifts.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'{
    "kml": false,
    "crime_types": true,
    "shifts": true
}' https://<YOUR_SITE>.predpol.com/api/districts/<ID>.json
```

`GET <YOUR_SITE>.predpol.com/api/districts/<ID>.json`

The show API is used to fetch an individual district. The response contains the district object corresponding to the 'id' passed in the request.

Each districts can be filtered by passing some parameters (optional) in the request as listed below.

Property | Type | Description
--------- | ----- | -----------
kml | Boolean | Each district has a KML associated with it. If this parameter is true, districts are retrieved along with their KML.
crime_types | Boolean | Each district has crime_types associated with it. If this parameter is true, districts are retrieved along with their crime_types.
shifts | Boolean | Each district has shifts associated with it. If this parameter is true, districts are retrieved along with their shifts.

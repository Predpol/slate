# Crime Types

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/crime_types.json
```

`GET <YOUR_SITE>.predpol.com/api/crime_types.json`

The index API is used to fetch all the crime_types. The response contains an array of crime_types objects.

Crime_types can be filtered by passing a district_id.

Property | Value | Description
--------- | ----- | -----------
district_id | Integer | A district_id can be used to fetch crime_types associated with a given district.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/crime_types/<ID>.json
```

`GET <YOUR_SITE>.predpol.com/api/crime_types/<ID>.json`

The show API is used to fetch an individual crime_type. The response contains a crime_type object corresponding to the 'id' passed in the request.


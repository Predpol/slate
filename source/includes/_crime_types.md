# Crime_Types APIs

## Index

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'[
    {
        "id":1,
        "name":"residential_burglaries",
        "label":"Residential Burglary",
        "is_deleted":false,
        "created_at":"2015-09-22T11:45:54.000-07:00",
        "updated_at":"2015-09-22T11:45:54.000-07:00",
        "color":"#C0392B",
        "is_public":false
    },
    {
        "id":2,
        "name":"commercial_burglaries",
        "label":"Commercial Burglary",
        "is_deleted":false,
        "created_at":"2015-09-22T11:45:54.000-07:00",
        "updated_at":"2015-09-22T11:45:54.000-07:00",
        "color":"#1B52DA",
        "is_public":false
    }
]' https://<customer_name>.predpol.com/api/crime_types.json
```

`GET <customer_name>.predpol.com/api/crime_types.json`

The index API is used to fetch all the crime_types. The response contains an array of crime_types objects.

Crime_types can be filtered by passing some parameters (optional) in the request as listed below.

Parameter | Value | Description
--------- | ----- | -----------
district_id | Integer | A district_id can be used to fetch crime_types associated with a given district.
classifications | Boolean | Each crime_type has an array of classifications associated with it which help in futher classifying crime_types.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'{
        "id":1,
        "name":"residential_burglaries",
        "label":"Residential Burglary",
        "is_deleted":false,
        "created_at":"2015-09-22T11:45:54.000-07:00",
        "updated_at":"2015-09-22T11:45:54.000-07:00",
        "color":"#C0392B",
        "is_public":false
}' https://<customer_name>.predpol.com/api/crime_types/<id>.json
```

`GET <customer_name>.predpol.com/api/crime_types/<id>.json`

The show API is used to fetch an individual crime_type. The response contains a crime_type object corresponding to the 'id' passed in the request.

## Create

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X POST -d 
'{
        "name":"residential_burglaries",
        "label":"Residential Burglary",
        "is_deleted":false,
        "color":"#C0392B",
        "is_public":false
}' https://<customer_name>.predpol.com/api/crime_types/<id>.json
```

`POST <customer_name>.predpol.com/api/crime_types/<id>.json`

The create API is used to create a new crime_type. If the request is processed successfully, the new crime_type is added to all the districts and if classifications are passed as parameters, they are associated with the crime_types object. Then, the new crime_types object along with status 'created' is saved and rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'. The shell shows a sample POST request for create API.

A crime_types object has the following properties:

Property | Description
--------- | -----------
name | Name of the crime_type.
label | Display name of the crime_type.
is_deleted | Indicates whether a crime_type is deleted or not.
color | Color associated with the crime_type.
is_public | Specifies whether the crime_type is public or not.
classifications | Each crime_type has an array of classifications associated with it which help in futher classifying crime_types.

<aside class="notice">
Classifications are optional.
</aside>

## Update

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X PUT -d 
'{
        "name":"residential_burglaries",
        "label":"Residential Burglary",
        "is_deleted":false,
        "color":"#C0392B",
        "is_public":false
}' https://<customer_name>.predpol.com/api/crime_types/<id>.json
```

`PUT <customer_name>.predpol.com/api/crime_types/<id>.json`

The update API is used to update an existing crime_type on the basis of crime_types id. If the request is processed successfully, the updated crime_types object is rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'. The shell shows a sample PUT request for update API.

A crime_types object has the following properties:

Property | Description
--------- | -----------
name | Name of the crime_type.
label | Display name of the crime_type.
is_deleted | Indicates whether a crime_type is deleted or not.
color | Color associated with the crime_type.
is_public | Specifies whether the crime_type is public or not.
classifications | Each crime_type has an array of classifications associated with it which help in futher classifying crime_types.

<aside class="notice">
Properties associated with update API are optional.
</aside>

## Destroy

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X DELETE -d 
'{
        "id":1
}' https://<customer_name>.predpol.com/api/crime_types/<id>.json
```

`DELETE <customer_name>.predpol.com/api/crime_types/<id>.json`

The destroy API is used to delete an existing crime_type on the basis of crime_types id. The shell shows a sample DELETE request for destroy API.

## Is_Classifying

## Classify_Crimes

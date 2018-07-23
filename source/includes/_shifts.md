# Shifts APIs

## Index

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'[
    {
        "id":1,
        "label":"DAY",
        "hour_start":5,
        "hour_end":15,
        "created_at":"2015-09-22T11:45:53.000-07:00",
        "updated_at":"2015-09-22T11:45:53.000-07:00"
    },
    {
        "id":2,
        "label":"SWINGS",
        "hour_start":14,
        "hour_end":24,
        "created_at":"2015-09-22T11:45:53.000-07:00",
        "updated_at":"2015-09-22T11:45:53.000-07:00"
   }
]' https://<customer_name>.predpol.com/api/shifts.json
```

`GET <customer_name>.predpol.com/api/shifts.json`

The index API is used to fetch all the shifts. The response contains an array of shift objects.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'{
        "id":1,
        "label":"DAY",
        "hour_start":5,
        "hour_end":15,
        "created_at":"2015-09-22T11:45:53.000-07:00",
        "updated_at":"2015-09-22T11:45:53.000-07:00"
}' https://<customer_name>.predpol.com/api/shifts/<id>.json
```

`GET <customer_name>.predpol.com/api/shifts/<id>.json`

The show API is used to fetch an individual shift. The response contains a shift object corresponding to the 'id' passed in the request.

## Create

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X POST -d 
'{
        "label":"DAY",
        "hour_start":5,
        "hour_end":15
}' https://<customer_name>.predpol.com/api/shifts.json
```

`POST <customer_name>.predpol.com/api/shifts.json`

The show API is used to create a new shift. If the request is processed successfully, the new shift object along with status 'created' is rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'. The shell shows a sample POST request for Create API.

A shifts object has the following properties:

Property | Description
-------- | ----------
label | Label corresponds to the name of the shift.
hour_start | The hour at which shift started.
hour_end | The hour at which shift ended.

## Update

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X PUT -d 
'{
        "label":"DAY",
        "hour_start":5,
        "hour_end":15
}' https://<customer_name>.predpol.com/api/shifts/<id>.json
```

`PUT <customer_name>.predpol.com/api/shifts/<id>.json`

The show API is used to update an existing shift on the basis of shift id. If the request is processed successfully, the updated shift object is rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'. The shell shows a sample PUT request for Update API.

A shifts object has the following properties:

Property | Description
-------- | ----------
label | Label corresponds to the name of the shift.
hour_start | The hour at which shift started.
hour_end | The hour at which shift ended.

<aside class="notice">
Properties associated with Update API are optional.
</aside>

## Destroy

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X DELETE -d 
'{
        "id":1
}' https://<customer_name>.predpol.com/api/shifts/<id>.json
```

`DELETE <customer_name>.predpol.com/api/shifts/<id>.json`

The destroy API is used to delete an existing shift on the basis of shift id. The shell shows a sample DELETE request for Destroy API.

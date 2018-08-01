# Shifts APIs

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/shifts.json
```

`GET <YOUR_SITE>.predpol.com/api/shifts.json`

The index API is used to fetch all the shifts. The response contains an array of shift objects.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/shifts/<ID>.json
```

`GET <YOUR_SITE>.predpol.com/api/shifts/<ID>.json`

The show API is used to fetch an individual shift. The response contains a shift object corresponding to the 'id' passed in the request.

## Create

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X POST -d 
'{
        "label":"DAY",
        "hour_start":5,
        "hour_end":15
}' https://<YOUR_SITE>.predpol.com/api/shifts.json
```

`POST <YOUR_SITE>.predpol.com/api/shifts.json`

The create API is used to create a new shift. If the request is processed successfully, the new shift object is rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'. 

A shifts object has the following properties:

Property | Type | Description
-------- | -------- | ----------
label | String | Label corresponds to the name of the shift.
hour_start | Integer | The hour at which the shift starts.
hour_end | Integer | The hour at which the shift ends.

## Update

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X PUT -d 
'{
        "label":"DAY",
        "hour_start":5,
        "hour_end":15
}' https://<YOUR_SITE>.predpol.com/api/shifts/<ID>.json
```

`PUT <YOUR_SITE>.predpol.com/api/shifts/<ID>.json`

The update API is used to update an existing shift on the basis of shift id. If the request is processed successfully, the updated shift object is rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'.

A shifts object has the following properties:

Property | Type | Description
-------- | -------- | ----------
label | String | Label corresponds to the name of the shift.
hour_start | Integer | The hour at which the shift starts.
hour_end | Integer | The hour at which the shift ends.

<aside class="notice">
Properties associated with update API are optional.
</aside>



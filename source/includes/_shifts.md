# Shifts

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/shifts.json
```
> Response

```json
[
    {
        "id": 1,
        "label": "DAY",
        "hour_start": 5,
        "hour_end": 15,
        "created_at": "2015-09-22T11:45:53.000-07:00",
        "updated_at": "2015-09-22T11:45:53.000-07:00"
    },

    ...

]
```


`GET <YOUR_SITE>.predpol.com/api/shifts.json`

The index API is used to fetch all the shifts. It takes no parameters. The response contains an array of shift objects.

Each shift object contains the following properties.

Property | Type | Description
------- | ------- | ---------
id | Integer | The unique id of the shift.
label | String | The name of the shift.
hour_start | Integer | The hour that the shift begins.
hour_end | Integer | The hour that the shift ends.
created_at | String | The date and time that the shift was created.
updated_at | String | The date and time that the shift was last updated.


<aside class="notice">
All times are local. If a shift cross midnight the end_hour will be greater than 24.
</aside>

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/shifts/<ID>.json
```

> Response

```json
{
    "id": 1,
    "label": "DAY",
    "hour_start": 5,
    "hour_end": 15,
    "created_at": "2015-09-22T11:45:53.000-07:00",
    "updated_at": "2015-09-22T11:45:53.000-07:00"
}
```

`GET <YOUR_SITE>.predpol.com/api/shifts/<ID>.json`

The show API is used to fetch an individual shift. It takes no parameters. The response contains a shift object corresponding to the 'id' passed in the request.

The shift object contains the following properties.

Property | Type | Description
------- | ------- | ---------
id | Integer | The unique id of the shift.
label | String | The name of the shift.
hour_start | Integer | The hour that the shift begins.
hour_end | Integer | The hour that the shift ends.
created_at | String | The date and time that the shift was created.
updated_at | String | The date and time that the shift was last updated.


<aside class="notice">
All times are local. If a shift cross midnight the end_hour will be greater than 24.
</aside>

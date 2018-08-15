# Prediction Boxes

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/prediction_boxes?date='2018-06-14'&district_id=8
```

> Response

```json
[
    {
        "id": 5974029,
        "address": "80 W 7 Th St",
        "district_id": 1,
        "effective_date": "2018-07-29",
        "center_lng": -121.427717,
        "center_lat": 37.735062,
        "min_lat": 37.734399,
        "max_lat": 37.735725,
        "min_lng": -121.428565,
        "max_lng": -121.426869,
        "shift_id": 1,
        "mission_id": 8
    },

    ...

]
```


`GET <YOUR_SITE>.predpol.com/api/prediction_boxes`

The list API is used to fetch all the prediction boxes. The response contains an array of prediction box objects.

A GET request can have the following parameters:

Parameter | Type | Description
--------- | -------- | -----------
shift_id | Integer | Filter prediction boxes by shift.
district_id | Integer | Filter prediction boxes by district.
mission_id | Integer | Filter prediction boxes by mission.
date | String | Fetch prediction boxes for a particular date.

<aside class='notice'>
All parameters are optional. The most recent boxes are shown if no date is passed.
</aside>

Each prediction box has the following properties.

Property | Type | Description
------- | -------- | --------
id | Integer | The unique id of the prediction box
address | String | The approximate address of the prediction box.
district_id | Integer | The unique id of the district containing the prediction box.
effective_date | String | The effective date of the prediction box.
center_lat | Float | The latitude of the center of the prediction box.
center_lng | Float | The longitude of the center of the prediction box.
min_lat | Float | The minimum latitude of the prediction box.
max_lat | Float | The maximum latitude of the prediction box.
min_lng | Float | The minimum longitude of the prediction box.
max_lng | Float | The maximum longitude of the prediction box.
shift_id | Integer | The unique of the id of the shift of the prediction box.
mission_id | Integer | The unique id of the mission of the prediction box.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/prediction_boxes/<ID>
```
> Response

```json
{
    "id": 5974029,
    "address": "80 W 7 Th St",
    "district_id": 1,
    "effective_date": "2018-07-29",
    "center_lng": -121.427717,
    "center_lat": 37.735062,
    "min_lat": 37.734399,
    "max_lat": 37.735725,
    "min_lng": -121.428565,
    "max_lng": -121.426869,
    "shift_id": 1,
    "mission_id": 8
}
```
`GET <YOUR_SITE>.predpol.com/api/prediction_boxes/<ID>`

The show API is used to fetch an individual prediction box. The response contains a prediction box object corresponding to the 'id' passed in the request.

The prediction box will have the following properties.

Property | Type | Description
------- | -------- | --------
id | Integer | The unique id of the prediction box
address | String | The approximate address of the prediction box.
district_id | Integer | The unique id of the district containing the prediction box.
effective_date | String | The effective date of the prediction box.
center_lat | Float | The latitude of the center of the prediction box.
center_lng | Float | The longitude of the center of the prediction box.
min_lat | Float | The minimum latitude of the prediction box.
max_lat | Float | The maximum latitude of the prediction box.
min_lng | Float | The minimum longitude of the prediction box.
max_lng | Float | The maximum longitude of the prediction box.
shift_id | Integer | The unique of the id of the shift of the prediction box.
mission_id | Integer | The unique id of the mission of the prediction box.


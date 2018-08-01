# Prediction Boxes

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/prediction_boxes?date='2018-06-14'&district_id=8
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

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/prediction_boxes/<ID>
```

`GET <YOUR_SITE>.predpol.com/api/prediction_boxes/<ID>`

The show API is used to fetch an individual prediction box. The response contains a prediction box object corresponding to the 'id' passed in the request.


# Export APIs

## Crimes

### Index

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'{
    "crimes":
        [
            {
                "id":127759,
                "docket_number":"CR180000005020",
                "address":"Jaeger \u0026 Chukar , Tracy, CA",
                "begin_time":"2018-07-06T03:42:00.000-07:00",
                "is_excluded":true,
                "reason_excluded":"unclassified",
                "latitude":"37.7313399",
                "longitude":"-121.420292",
                "event_description":"TC PROP. DAM/MTR VEH",
                "districts":
                    [
                        {
                            "id":"1",
                            "name":"Beat 1"
                        },
                        {
                            "id":"8",
                            "name":"City-wide"
                        }
                    ],
                "crime_types":[],
                "violation_codes":
                    [
                        {
                            "id":"40",
                            "violation_code":"VC 22107:420901:"
                        }
                    ]
           },
           {
               "id":127760,
               "docket_number":"CR180000005018",
               "address":"1975 W 11Th St, Tracy, CA",
               "begin_time":"2018-07-06T00:10:00.000-07:00",
               "is_excluded":true,
               "reason_excluded":"unclassified",
               "latitude":"37.7410103",
               "longitude":"-121.4521132",
               "event_description":"MISC MISDEMEANORS   ",
               "districts":
                   [
                       {
                           "id":"3",
                           "name":"Beat 3"
                       },
                       {
                           "id":"8",
                           "name":"City-wide"
                       }
                   ],
               "crime_types":[],
               "violation_codes":
                   [
                       {
                           "id":"12396",
                           "violation_code":"VC 12500 (A):VC 23103 (B):VC 22651(P):261117:261117:510301:"
                       }
                   ]
           }
        ]
}' https://<customer_name>.predpol.com/api/crimes
```

`GET <customer_name>.predpol.com/api/crimes`

The index API is used to fetch all the crimes. The response contains an array of crime objects.

A GET request can have the following parameters:

Parameter | Description
---------| -----------
docket_number | A unique identifier of a crime. The docket number is required and is used to identify individual crimes so that they may be updated later. Docket numbers must never be reused.
start_date | The earliest date that the crimes must be looked up from.
end_date | The latest date that the crime must be looked up to.
limit | Limiting the number of crimes.
offset | Offset to fetch crimes from.
shift_id | Filtering crimes on the basis of shift.
district_id | Filtering crimes on the basis of district.
crime_type_ids | Array of crime_type_ids to filter crimes.
is_excluded | A boolean value to filter excluded crimes.
reason_excluded | Filtering crimes on the basis of exclusion reason.
address | The address where the crime occurred.
event_description | A brief description of the event.
violation_code | Violation code representing the crime.
sort_column | Column on which crimes should be sorted
sort_order | Order of sort.

## Prediction Boxes

### Index

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'[
    {
        "id":5849890,
        "address":"35 E 7 Th St",
        "district_id":1,
        "effective_date":"2018-07-08",
        "crime_type_id":3,
        "probability_today":0.004446713977397,
        "grid_cell_id":17455,
        "center_lng":-121.424325,
        "center_lat":37.736388,
        "type":"PredictionBox",
        "label":"A",
        "min_lat":37.735725,
        "max_lat":37.737051,
        "min_lng":-121.425173,
        "max_lng":-121.423477,
        "cell_score":0.003676701053570431,
        "shift_id":1,
        "mission_id":-1
    },
    {
        "id":5849907,
        "address":"824 W 11 Th St",
        "district_id":1,
        "effective_date":"2018-07-08",
        "crime_type_id":3,
        "probability_today":0.004322943639534,
        "grid_cell_id":17482,
        "center_lng":-121.437893,
        "center_lat":37.73904,
        "type":"PredictionBox",
        "label":"B",
        "min_lat":37.738377,
        "max_lat":37.739703,
        "min_lng":-121.438741,
        "max_lng":-121.437045,
        "cell_score":0.004203297310035259,
        "shift_id":1,
        "mission_id":-1
    }
]' https://<customer_name>.predpol.com/api/prediction_boxes
```

`GET <customer_name>.predpol.com/api/prediction_boxes`

The index API is used to fetch all the prediction boxes. The response contains an array of prediction box objects.

A GET request can have the following parameters:

Parameter | Description
---------| -----------
shift_id | Filtering prediction boxes on the basis of shift.
district_id | Filtering prediction boxes on the basis of district.
mission_id | Filtering prediction boxes on the basis of mission.
crime_type_ids | A comma-separated list of crime_type_ids to filter prediction boxes.
date | Fetching prediction boxes for a particular date.

### Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'{
        "id":5849845,
        "address":"315 Mt Oso Ave",
        "effective_date":"2018-07-08",
        "max_lat":"37.727769",
        "min_lat":"37.726443",
        "max_lng":"-121.430261",
        "min_lng":"-121.431957",
        "look_for":
            [
                "Auto Burglary",
                "Residential Burglary",
                "Auto Theft Report"
            ],
        "recent_crime_counts":{},
        "grid_cell_id":17364
}' https://<customer_name>.predpol.com/api/prediction_boxes/<id>
```

`GET <customer_name>.predpol.com/api/prediction_boxes/<id>`

The show API is used to fetch an individual prediction box. The response contains a prediction box object corresponding to the 'id' passed in the request.

A prediction box object has the following properties:

Property | Description
---------| -----------
id | A unique identifier of a prediction box.
address | Address corresponding to the prediction box.
effective_date | Indicates the date when the prediction box is effective.
max_lat | Maximum latitude coordinate for locating the prediction box.
min_lat | Minimun latitude coordinate for locating the prediction box.
max_lng | Maximum longitude coordinate for locating the prediction box.
min_lng | Minimum longitude coordinate for locating the prediction box.
look_for | Indicates an array of crimes to be aware of inside the corresponding prediction box.
recent_crime_counts | Indicates the number of crimes that recently occured within the prediction box.
grid_cell_id | Depicts a unique grid cell id that is associated with each prediction box.

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

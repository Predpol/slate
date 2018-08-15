# Incident Types

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/incident_types.json
```

>Response

```json
[
    {
        "id": 2,
        "label": "Battery",
        "is_deleted": false,
        "created_at": "2017-12-05T15:41:20.000-05:00",
        "updated_at": "2017-12-05T15:41:20.000-05:00",
        "color": "#1B52DA"
    },
    {
        "id": 3,
        "label": "Robbery",
        "is_deleted": false,
        "created_at": "2017-12-05T15:41:20.000-05:00",
        "updated_at": "2017-12-05T15:41:20.000-05:00",
        "color": "#EB9B22"
    }
]
```

`GET <YOUR_SITE>.predpol.com/api/incident_types.json`

The list API is used to fetch all the incident types. The response contains an array of incident_type objects.

Incident types can optionally be filtered by passing a district_id to show only the incident types associated with a specific district.

Property | Value | Description
--------- | ----- | -----------
district_id | Integer | A district_id can be used to fetch incident types associated with a given district.

Each incident_type object has the following properties:

Property | Value | Description
--------- | ----------- | ----------
id | Integer | A unique indentifier of the incident_type.
label | String | The name of the incident_type.
is_deleted | Boolean | True if this incident_type has been soft deleted.
created_at | String | The date and time that the incident_type was created.
updated_at | String | The date and time that the incident_type was last updated.
color | String | Hex representation of the color used for incidents of this type in the PredPol app.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/incident_types/<ID>.json
```

> Response

```json
{
    "id": 2,
    "label": "Battery",
    "is_deleted": false,
    "created_at": "2017-12-05T15:41:20.000-05:00",
    "updated_at": "2017-12-05T15:41:20.000-05:00",
    "color": "#1B52DA"
}
```


`GET <YOUR_SITE>.predpol.com/api/incident_types/<ID>.json`

The show API is used to fetch an individual incident_type. The response contains an incident_type object corresponding to the 'id' passed in the request.

The incident_type object has the following properties:

Property | Value | Description
--------- | ----------- | ----------
id | Integer | A unique indentifier of the incident_type.
label | String | The name of the incident_type.
is_deleted | Boolean | True if this incident_type has been soft deleted.
created_at | String | The date and time that the incident_type was created.
updated_at | String | The date and time that the incident_type was last updated.
color | String | Hex representation of the color used for incidents of this type in the PredPol app.

# Missions

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/missions.json
```
> Response

```json
[
    {
        "id": 1,
        "name": "Auto Theft/Auto Burg",
        "created_at": "2015-09-30T18:13:44.000-07:00",
        "updated_at": "2017-05-21T14:42:33.000-07:00",
        "is_deleted": false,
        "crime_types": [
            {
                "id": 3,
                "label": "Auto Burglary",
                "is_deleted": false,
                "created_at": "2015-09-22T11:45:54.000-07:00",
                "updated_at": "2015-09-22T11:45:54.000-07:00",
                "color": "#EB9B22",
            },
            {
                "id": 4,
                "label": "Auto Theft Report",
                "is_deleted": false,
                "created_at": "2015-09-22T11:45:54.000-07:00",
                "updated_at": "2015-09-22T11:45:54.000-07:00",
                "color": "#84568D",
            }
        ]
    }

    ...

]
```


`GET <YOUR_SITE>.predpol.com/api/missions.json`

The list API is used to fetch all the missions. The response contains an array of mission objects.

Each mission object has the following properties.

Property | Type | Description
--------- | ------- | ---------
id | Integer | A unique id of the mission
name | String | The name of the mission
created_at | String | The date and time that the mission was created.
updated_at | String | The date and time that the mission was last updated.
is_deleted | Boolean | Whether or not this mission has been soft deleted.
incident_types | Array | An array of the incident_types included in this mission.


## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/missions/<ID>.json
```
> Response

```json
{
    "id": 1,
    "name": "Auto Theft/Auto Burg",
    "created_at": "2015-09-30T18:13:44.000-07:00",
    "updated_at": "2017-05-21T14:42:33.000-07:00",
    "is_deleted": false,
    "incident_types": [
        {
            "id": 3,
            "label": "Auto Burglary",
            "is_deleted": false,
            "created_at": "2015-09-22T11:45:54.000-07:00",
            "updated_at": "2015-09-22T11:45:54.000-07:00",
            "color": "#EB9B22",
        },
        {
            "id": 4,
            "label": "Auto Theft Report",
            "is_deleted": false,
            "created_at": "2015-09-22T11:45:54.000-07:00",
            "updated_at": "2015-09-22T11:45:54.000-07:00",
            "color": "#84568D",
        }
    ]
}
```

`GET <YOUR_SITE>.predpol.com/api/missions/<ID>.json`

The show API is used to fetch an individual mission. The response contains a mission object corresponding to the 'id' passed in the request.

The mission object has the following properties.

Property | Type | Description
--------- | ------- | ---------
id | Integer | A unique id of the mission
name | String | The name of the mission
created_at | String | The date and time that the mission was created.
updated_at | String | The date and time that the mission was last updated.
is_deleted | Boolean | Whether or not this mission has been soft deleted.
incident_types | Array | An array of the incident_types included in this mission.

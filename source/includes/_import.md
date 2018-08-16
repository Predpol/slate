# Import Data

## Incidents

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X POST -d 
'[
    {
        "latitude": 42.0310442,
        "longitude": -88.2844599,
        "begin_time": "2017-03-14T17:45:13.000-05:00",
        "address": "204 S State St, Elgin, Illinois",
        "incident_id": "2017-00019676-public",
        "incident_codes": ["Robbery", "Assault"],
        "end_time": "2017-03-14T17:45:13.000-05:00",
        "description": "Theft > $1000, Injury"
    },
    {
        "latitude": 42.0351538,
        "longitude": -88.2563516,
        "begin_time": "2017-03-14T15:24:56.000-05:00",
        "address": "910 E Chicago St, Elgin, Illinois",
        "incident_id": "2017-00019654-public",
        "incident_codes": ["Auto Theft"],
        "end_time": "2017-03-14T15:24:56.000-05:00",
        "description": "Auto theft > $10,000"
    }
]' https://api.predpol.com/incidents.json
```
> Response

```json
{ success: "2 incidents uploaded successfully" }
```

`POST api.predpol.com/incidents.json`

The incidents import API is used to send incidents to the Predpol application.

An incident object has the following properties:

Property | Type | Description
--------- | ------- | -----------
incident_id | String | A unique identifier of the incident. The incident_id is required and is used to identify individual incidents so that they may be updated later. Incident IDs must never be reused.
begin_time | String | The earliest time that the incident may have occurred in [RFC3339](https://tools.ietf.org/html/rfc3339) format.
end_time | String | The latest time that the incident may have occurred in [RFC3339](https://tools.ietf.org/html/rfc3339) format.
latitude | Float | Latitude of the incident in decimal degrees.
longitude | Float | Longitude of the incident in decimal degrees.
address | String | The address where the incident occurred.
description | String |  A brief description of the event.
incident_codes | String array | Incident codes are used by Predpol to classify incidents into specific incident types. An incident may have multiple incident codes which can be passed at one time as an array.
incident_code | String | A single, string-valued incident code may be passed if the incident has only one incident code. (Ignored if incident_codes exists).

<aside class="notice">
Multiple incident codes may also be added to an incident by sending the same incident object repeatedly with different incident codes within an hour.
</aside>

PredPol will return one of the following properties:

Property | Type | Description
--------- | --------- | ----------
success | String | Success is set if the operation was successful.
error | String | An error message if the operation was not successful.


## Locations

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X POST -d 
'[
    {
        "latitude": 33.39377,
        "longitude": -111.85288,
        "device": "5C15",
        "time_stamp": "2017-03-18T23:59:56.000-07:00"
    },
    {
        "latitude": 33.41517,
        "longitude": -111.79739,
        "device": "5C54",
        "time_stamp": "2017-03-18T23:59:58.000-07:00"
    }
]' https://api.predpol.com/locations.json
```

> Response

```json
{ success: "2 locations uploaded successfully" }
```

`POST api.predpol.com/locations.json`

The locations API is used to send updates about device locations. Each request sends an array of location objects.

A location object has the following properties:

Property | Type | Description
-------- | ------- | ----------
latitude | Float | The latitude of the device in decimal degrees.
longitude | Float | The longitude of the device in decimal degrees.
device | String | A unique identifer of the device.
time_stamp | String | The time at which the location was recorded in [RFC3339](https://tools.ietf.org/html/rfc3339) format.


PredPol will return one of the following properties:

Property | Type | Description
--------- | --------- | ----------
success | String | Success is set if the operation was successful.
error | String | An error message if the operation was not successful.



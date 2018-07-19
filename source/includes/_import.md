# Import APIs

## Crimes

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X POST -d 
'[
    {
        "latitude": 42.0310442,
        "longitude": -88.2844599,
        "begin_time": "2017-03-14T17:45:13.000-05:00",
        "address": "204 S State St, Elgin, Illinois",
        "docket_number": "2017-00019676-public",
        "violation_codes": ["Robbery", "Assault"],
        "end_time": "2017-03-14T17:45:13.000-05:00",
        "description": "Theft > $1000, Injury"
    },
    {
        "latitude": 42.0351538,
        "longitude": -88.2563516,
        "begin_time": "2017-03-14T15:24:56.000-05:00",
        "address": "910 E Chicago St, Elgin, Illinois",
        "docket_number": "2017-00019654-public",
        "violation_codes": ["Auto Theft"],
        "end_time": "2017-03-14T15:24:56.000-05:00",
        "description": "Auto theft > $10,000"
    }
]' https://api.predpol.com/crimes.json
```

`POST api.predpol.com/crime.json`

`POST api.predpol.com/crimes.json`

The crimes import APIs are used to send crimes to the Predpol application. Crimes may be sent either as an individual
crime object (to crime.json) or as an array of crime objects (to crimes.json).

A crime object has the following properties:

Property | Description
---------| -----------
docket_number | A unique identifier of a crime. The docket number is required and is used to identify individual crimes so that they may be updated later. Docket numbers must never be reused.
begin_time | The earliest time that a crime may have occurred in [RFC3339](https://tools.ietf.org/html/rfc3339) format.
end_time | The latest time that a crime may have occurred in [RFC3339](https://tools.ietf.org/html/rfc3339) format.
latitude | Latitude of a crime in decimal degrees.
longitude | Longitude of a crime in decimal degrees.
address | The address where the crime occurred.
description | A brief description of the event.
violation_codes | Violation codes are used by Predpol to classify crimes into specific crime types. A crime may have multiple violation codes which can be passed at one time as an array.
violation_code | A single, string-valued violation code may be passed if the crime has only one violation code. (Ignored if violation_codes exists).

<aside class="notice">
Multiple violation codes may also be added to a crime by sending the same crime object repeatedly with different violation codes within an hour.
</aside>


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

`POST api.predpol.com/locations.json`

The locations API is used to send updates about officer locations. Each request sends an array of location objects.

A location object has the following properties:

Property | Description
-------- | ----------
latitude | The latitude of the officer in decimal degrees.
longitude | The longitude of the officer in decimal degrees.
device | A unique identifer of the vehicle.
time_stamp | The time at which the location was recorded in [RFC3339](https://tools.ietf.org/html/rfc3339) format.





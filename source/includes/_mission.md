# Missions APIs

## Index

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'[
    {
        "id":1,
        "name":"Auto Theft/Auto Burg",
        "created_at":"2015-09-30T18:13:44.000-07:00",
        "updated_at":"2017-05-21T14:42:33.000-07:00",
        "is_deleted":false,
        "crime_types":
            [
                {
                    "id":3,
                    "name":"auto_burglaries",
                    "label":"Auto Burglary",
                    "is_deleted":false,
                    "created_at":"2015-09-22T11:45:54.000-07:00",
                    "updated_at":"2015-09-22T11:45:54.000-07:00",
                    "color":"#EB9B22",
                    "is_public":false
                },
                {
                    "id":4,
                    "name":"auto_theft_reports",
                    "label":"Auto Theft Report",
                    "is_deleted":false,
                    "created_at":"2015-09-22T11:45:54.000-07:00",
                    "updated_at":"2015-09-22T11:45:54.000-07:00",
                    "color":"#84568D",
                    "is_public":false
                }
            ]
    },
    {
        "id":2,
        "name":"Auto Theft Recovery",
        "created_at":"2015-09-30T18:13:45.000-07:00",
        "updated_at":"2015-09-30T18:13:45.000-07:00",
        "is_deleted":false,
        "crime_types":
            [
                {
                    "id":5,
                    "name":"auto_theft_recoveries",
                    "label":"Auto Theft Recovery",
                    "is_deleted":false,
                    "created_at":"2015-09-22T11:45:54.000-07:00",
                    "updated_at":"2015-09-22T11:45:54.000-07:00",
                    "color":"#4ECD54",
                    "is_public":false
                },
                {
                    "id":4,
                    "name":"auto_theft_reports",
                    "label":"Auto Theft Report",
                    "is_deleted":false,
                    "created_at":"2015-09-22T11:45:54.000-07:00",
                    "updated_at":"2015-09-22T11:45:54.000-07:00",
                    "color":"#84568D",
                    "is_public":false
                }
            ]
    }
]' https://<customer_name>.predpol.com/api/missions.json
```

`GET <customer_name>.predpol.com/api/missions.json`

The index API is used to fetch all the missions. The response contains an array of mission objects.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X GET -d 
'{
        "id":1,
        "name":"Auto Theft/Auto Burg",
        "created_at":"2015-09-30T18:13:44.000-07:00",
        "updated_at":"2017-05-21T14:42:33.000-07:00",
        "is_deleted":false,
        "crime_types":
            [
                {
                    "id":3,
                    "name":"auto_burglaries",
                    "label":"Auto Burglary",
                    "is_deleted":false,
                    "created_at":"2015-09-22T11:45:54.000-07:00",
                    "updated_at":"2015-09-22T11:45:54.000-07:00",
                    "color":"#EB9B22",
                    "is_public":false
                },
                {
                    "id":4,
                    "name":"auto_theft_reports",
                    "label":"Auto Theft Report",
                    "is_deleted":false,
                    "created_at":"2015-09-22T11:45:54.000-07:00",
                    "updated_at":"2015-09-22T11:45:54.000-07:00",
                    "color":"#84568D",
                    "is_public":false
                }
            ]
}' https://<customer_name>.predpol.com/api/missions/<id>.json
```

`GET <customer_name>.predpol.com/api/missions/<id>.json`

The show API is used to fetch an individual mission. The response contains a mission object corresponding to the 'id' passed in the request.

## Create

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X POST -d 
'{
        "name":"Auto Theft/Auto Burg",
        "is_deleted":false,
        "crime_types":
            [
                {
                    "name":"auto_burglaries",
                    "label":"Auto Burglary",
                    "is_deleted":false,
                    "color":"#EB9B22",
                    "is_public":false
                },
                {
                    "name":"auto_theft_reports",
                    "label":"Auto Theft Report",
                    "is_deleted":false,
                    "color":"#84568D",
                    "is_public":false
                }
            ]
}' https://<customer_name>.predpol.com/api/missions.json
```

`POST <customer_name>.predpol.com/api/missions.json`

The create API is used to create a new mission. If the request is processed successfully, the new mission object along with status 'created' is saved and rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'. The shell shows a sample POST request for create API.

A mission object has the following properties:

Property | Description
-------- | ----------
name | Name of the mission.
is_deleted | Indicates whether a mission is deleted or not.
crime_types | Specifies the crime_types associated with the mission.

<aside class="notice">
The parameter crime_types is optional.
</aside>

## Update

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X PUT -d 
'{
        "name":"Auto Theft/Auto Burg",
        "is_deleted":false,
        "crime_types":
            [
                {
                    "name":"auto_burglaries",
                    "label":"Auto Burglary",
                    "is_deleted":false,
                    "color":"#EB9B22",
                    "is_public":false
                }
            ]
}' https://<customer_name>.predpol.com/api/missions/<id>.json
```

`PUT <customer_name>.predpol.com/api/missions/<id>.json`

The update API is used to update an existing mission on the basis of mission id. If the request is processed successfully, the updated mission object is saved and rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'. The shell shows a sample PUT request for update API.

A mission object has the following properties:

Property | Description
-------- | ----------
name | Name of the mission.
is_deleted | Indicates whether a mission is deleted or not.
crime_types | Specifies the crime_types associated with the mission.

<aside class="notice">
Properties associated with update API are optional. Also, if crime_types of a mission is changed, the mission is deleted and a new mission is created.
</aside>

## Destroy

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X DELETE -d 
'{
        "id":1
}' https://<customer_name>.predpol.com/api/missions/<id>.json
```

`DELETE <customer_name>.predpol.com/api/missions/<id>.json`

The destroy API is used to delete an existing mission on the basis of mission id. The shell shows a sample DELETE request for destroy API.

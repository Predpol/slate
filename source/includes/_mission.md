# Missions APIs

## List

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/missions.json
```

`GET <YOUR_SITE>.predpol.com/api/missions.json`

The list API is used to fetch all the missions. The response contains an array of mission objects.

## Show

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY"\
    https://<YOUR_SITE>.predpol.com/api/missions/<id>.json
```

`GET <YOUR_SITE>.predpol.com/api/missions/<ID>.json`

The show API is used to fetch an individual mission. The response contains a mission object corresponding to the 'id' passed in the request.

## Create

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X POST -d 
'{
        "name":"Auto Theft/Auto Burg",
        "crime_type_ids": [1, 3]
}' https://<YOUR_SITE>.predpol.com/api/missions.json
```

`POST <YOUR_SITE>.predpol.com/api/missions.json`

The create API is used to create a new mission. If the request is processed successfully, the new mission object is rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'.

A mission object has the following properties:

Property | Type | Description
-------- | ------ | ----------
name | String | Name of the mission.
crime_type_ids | Integer array | Specifies the crime_types associated with the mission.

## Update

```shell
curl -H "Content-Type: application/json" -H "X-Predpol-Key: YOUR_API_KEY" -X PUT -d 
'{
        "name":"New Auto Theft/Auto Burg",
        "crime_type_ids": [4, 5, 6]
}' https://<YOUR_SITE>.predpol.com/api/missions/<ID>.json
```

`PUT <YOUR_SITE>.predpol.com/api/missions/<ID>.json`

The update API is used to update an existing mission. If the request is processed successfully, the updated mission object is saved and rendered as json. Otherwise, an appropriate error is thrown with status 'unprocessable_entity'. 

A mission object has the following properties:

Property | Type | Description
-------- | ------- | ----------
name | String | Name of the mission.
is_deleted | Boolean | Indicates whether a mission is deleted or not.
crime_type_ids | Integer array | Specifies the crime_types associated with the mission.

<aside class="warning">
If crime_types of a mission are changed, the mission is deleted and a new mission is created.
</aside>

<aside class="notice">
Properties associated with update API are optional. 
</aside>



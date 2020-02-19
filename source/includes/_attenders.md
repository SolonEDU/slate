# Attenders

## Attender Model

> Attenders are stored in a model structured like this:

```json
{
    "aid": 31,
    "eid": 30,
    "uid": 1
}
```

### Fields
Field | Description
----- | -----------
aid | ID of the attender
eid | ID of the event that is being attended
uid | ID of the user that is attending

## Get All Attenders

> This endpoint returns a JSON structured like this

```json
{
    "message": "All attenders were fetched",
    "attenders": [
        {
            "aid": 31,
            "eid": 30,
            "uid": 1
        },
        {
            "aid": 33,
            "eid": 29,
            "uid": 1
        }
    ]
}
```

This endpoint retrieves all attenders.

### HTTP Request

`GET https://api.solonedu.com/attenders`

## Get A Specific Attender

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Attender for eventID 30 by userID 1 was fetched",
    "attender": {
        "aid": 31,
        "eid": 30,
        "uid": 1
    }
}
```

This endpoint retrieves a specific vote.

### HTTP Request

`GET https://api.solonedu.com/attenders/<eventID>/<userID>`

### URL Parameters

Parameter | Description
--------- | -----------
eventID | ID of the proposal that is being attended
userID | ID of the user that is attending

## Create an Attender

> This endpoint requires a body like this:

```json
{
	"eid": 30,
	"uid": 5
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Attender was created",
    "attender": {
        "aid": 34,
        "eid": 30,
        "uid": 5
    }
}
```

This endpoint creates an attender.

### HTTP Request

`POST https://api.solonedu.com/attenders`

## Delete a Specific Attender

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Attender for eventID 30 by userID 5 was deleted"
}
```

This endpoint deletes a specific vote.

### HTTP Request

`DELETE https://api.solonedu.com/attenders/<eventID>/<userID>`

### URL Parameters

Parameter | Description
--------- | -----------
eventID | ID of the proposal that is being attended
userID | ID of the user that is attending
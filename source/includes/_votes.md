# Votes

## Vote Model

> Votes are stored in a model structured like this:

```json
{
    "vid": 71,
    "pid": 250,
    "uid": 4,
    "value": 1
}
```

### Fields
Field | Description
----- | -----------
vid | ID of the vote
pid | ID of the proposal that was voted on
uid | ID of the user that voted
value | value of the vote, 0 meaning no and 1 meaning yes

## Get All Votes

> This endpoint returns a JSON structured like this

```json
{
    "message": "All votes were fetched",
    "votes": [
        {
            "vid": 72,
            "pid": 256,
            "uid": 1,
            "value": 1
        },
        {
            "vid": 73,
            "pid": 250,
            "uid": 1,
            "value": 1
        }
    ]
}
```

This endpoint retrieves all votes.

### HTTP Request

`GET https://api.solonedu.com/votes`

## Get A Specific Vote

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Vote for proposalID 250 by userID 4 was fetched",
    "vote": {
        "vid": 71,
        "pid": 250,
        "uid": 4,
        "value": 1
    }
}
```

This endpoint retrieves a specific vote.

### HTTP Request

`GET https://api.solonedu.com/<proposalID>/<userID>`

### URL Parameters

Parameter | Description
--------- | -----------
proposalID | ID of the proposal that was voted on
userID | ID of the user that voted

## Create a Vote

> This endpoint requires a body like this:

```json
{
	"pid": 257,
	"uid": 5,
	"value": 1
}
```

> This endpoint returns a JSON structured like this:
```json
{
    "message": "Vote was created",
    "vote": {
        "vid": 74,
        "pid": 257,
        "uid": 5,
        "value": 1
    }
}
```

This endpoint creates a vote.

### HTTP Request

`POST http://example.com/votes`

### Change a Vote

> This endpoint requires a body like this:
```json
{
	"pid": 257,
	"uid": 5,
	"value": 0
}
```

> This endpoint returns a JSON structured like this:
```json
{
    "message": "Vote for proposalID 257 by userID 5 was updated",
    "value": 0
}
```

This endpoint changes a vote.

### HTTP Request
`PATCH https://api.solonedu.com/votes`

## Delete a Specific Vote

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Vote with voteID 257 was deleted"
}
```

This endpoint deletes a specific vote.

### HTTP Request

`DELETE https://api.solonedu.com/vote/<voteID>`

### URL Parameters

Parameter | Description
--------- | -----------
voteID | ID of the vote to delete
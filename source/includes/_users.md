# Users

## Users Model

> Users are stored in a model structured like this:

```json
{
    "uid": 7,
    "firstname": "Eric",
    "lastname": "Lau",
    "email": "elau00@stuy.edu",
    "password": "$2b$10$/hUVZMHcN79p7iR2eNgFIOjwdUQx3d2QQflBH4sCz1WnTXX.WnRZm",
    "lang": "zhcn"
}
```

### Fields

Field | Description
----- | -----------
uid | ID of the user
firstname | first name of the user
lastname | last name of the user
email | email address of the user
password | hashed password of the user
lang | language code of the preferred language of the user

## Get All Users

> This endpoint returns a JSON srtuctured like this:

```json
{
    "message": "All users were fetched",
    "users": [
        {
            "uid": 7,
            "firstname": "Eric",
            "lastname": "Lau",
            "email": "elau00@stuy.edu",
            "password": "$2b$10$/hUVZMHcN79p7iR2eNgFIOjwdUQx3d2QQflBH4sCz1WnTXX.WnRZm",
            "lang": "zhcn"
        },
        {
            "uid": 33,
            "firstname": "Jamal",
            "lastname": "Crawford",
            "email": "jcrawford00@gmail.com",
            "password": "$2b$10$BI36zuUIjqShINVnozUujet1nCvQHtevD1JREMw2IPWgN7WfgBYP.",
            "lang": "ko"
        }
    ]
}
```

This endpoint retrieves all users

### HTTP Request

`GET https://api.solonedu.com/users`

## Get a Specific User

> This endpoint returns a JSON structured like this:

```json
{
    "message": "User with userID 33 was fetched",
    "user": {
        "uid": 33,
        "firstname": "Jamal",
        "lastname": "Crawford",
        "email": "jcrawford00@gmail.com",
        "lang": "ko"
    }
}
```

This endpoint retrieves a specific user.

### HTTP Request

`GET https://api.solonedu.com/users/<userID>`

### URL Parameters

Parameter | Description
--------- | -----------
userID | ID of the user to retrieve

## Login a User

> This endpoint requires a body like this:

```json
{
	"email": "jcrawford00@gmail.com",
	"password": "password" 
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "User was successfully logged in",
    "uid": 33
}
```

This endpoint attempts to authenticate a user upon login.

### HTTP Request

`POST https://api.solonedu.com/users/login`

## Register a User

> This endpoint requires a body like this:

```json
{
	"email": "email@gmail.com",
	"password": "password",
	"firstname": "Frist",
	"lastname": "Lsat",
	"lang": "en"
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "User with email email@gmail.com was registered"
}
```

This endpoint attempts to register a user.

### HTTP Request

`POST https://api.solonedu.com/users/register`

## Change Language of a Specific User

> This endpoint requires a body like this:

```json
{
	"uid": 34,
	"lang": "bn"
}
```

> This endpoint returns a JSON srtuctured like this:

```json
{
    "message": "Language for user with userID 34 was updated",
    "lang": "bn"
}
```

This endpoint changes the language of a specific user.

### HTTP Request

`PATCH https://api.solonedu.com/users/language`

## Delete a Specific User

> This endpoint returns a JSON structured like this:

```json
{
    "message": "User with userID 34 was deleted"
}
```

This endpoint deletes a specific user.

### HTTP Request

`DELETE https://api.solonedu.com/users/<userID>`

### URL Parameters

Parameter | Description
--------- | -----------
userID | ID of the user to delete
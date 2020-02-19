# Admins

## Admins Model

> Admins are stored in a model structured like this:

```json
{
    "adminid": 1,
    "username": "admin",
    "password": "$2b$10$YzC1owZJxajF9NzmLW.8CucPz4xRaCGOJjKEbemMNZQEbBMh5PrjS"
}
```

### Fields

Field | Description
----- | -----------
adminid | ID of the admin
username | username of the admin
password | hashed password of the admin

## Get A Specific Admin

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Admin with adminID 1 was fetched",
    "admin": {
        "adminid": 1,
        "username": "admin",
        "password": "$2b$10$YzC1owZJxajF9NzmLW.8CucPz4xRaCGOJjKEbemMNZQEbBMh5PrjS"
    }
}
```

This endpoint retrieves a specific admin.

### HTTP Request

`GET https://api.solonedu.com/admins/<adminID>`

### URL Parameters

Parameter | Description
--------- | -----------
adminID | ID of the admin to retrieve

## Login an Admin

> This endpoint requires a body like this:

```json
{
	"username": "username",
	"password": "password" 
}
```

> This endpoint returns a JSON structured like this:

```json
{
	"username": "admin",
	"password": "password"
}
```

This endpoint attempts to authenticate an admin upon login.

### HTTP Request

`POST https://api.solonedu.com/admins/login`

## Register an Admin

> This endpoint requires a body like this:

```json
{
	"username": "username",
	"password": "password"
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Admin with username username was registered"
}
```

This endpoint attempts to register an admin.

### HTTP Request

`POST https://api.solonedu.com/admins/register`

## Delete a Specific Admin

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Admin with adminID 2 was deleted"
}
```

This endpoint deletes a specific admin.

### HTTP Request

`DELETE https://api.solonedu.com/admins/<adminID>`

### URL Parameters

Parameter | Description
--------- | -----------
adminID | ID of the admin to delete
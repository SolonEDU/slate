# Comments

## Comment Model

> Comments are stored in a model structured like this:

```json
{
    "cid": 107,
    "fid": 69,
    "content": "{\"en\":\"hey\",\"zhcn\":\"嘿\",\"zhtw\":\"嘿\",\"bn\":\"অঁ্যা\",\"ko\":\"야\",\"ru\":\"Привет\",\"ja\":\"ねえ\",\"uk\":\"гей\"}",
    "timestamp": "2020-02-17T14:00:35.431Z",
    "uid": 4
}
```

### Fields

Field | Description
----- | -----------
cid | ID of the comment
fid | ID of the forum post the comment was created on
content | JSON with language code as key and translated content as value
timestamp | timestamp for creation of the comment
uid | user ID of the user that created the comment

## Get All Comments

> This endpoint returns a JSON structured like this:

```json
{
    "message": "All comments were fetched",
    "comments": [
        {
            "cid": 107,
            "fid": 69,
            "content": "{\"en\":\"hey\",\"zhcn\":\"嘿\",\"zhtw\":\"嘿\",\"bn\":\"অঁ্যা\",\"ko\":\"야\",\"ru\":\"Привет\",\"ja\":\"ねえ\",\"uk\":\"гей\"}",
            "timestamp": "2020-02-17T14:00:35.431Z",
            "uid": 4
        },
        {
            "cid": 108,
            "fid": 69,
            "content": "{\"en\":\"what's up\",\"zhcn\":\"这是怎么回事\",\"zhtw\":\"這是怎麼回事\",\"bn\":\"কি খবর\",\"ko\":\"뭐야\",\"ru\":\"что происходит\",\"ja\":\"調子はどう\",\"uk\":\"як справи\"}",
            "timestamp": "2020-02-18T22:18:20.828Z",
            "uid": 1
        }
    ]
}
```

This endpoint retrieves all comments.

### HTTP Request

`GET https://api.solonedu.com/comments`

## Get a Specific Comment

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Comment with commentID 107 was fetched",
    "comment": {
        "cid": 107,
        "fid": 69,
        "content": "{\"en\":\"hey\",\"zhcn\":\"嘿\",\"zhtw\":\"嘿\",\"bn\":\"অঁ্যা\",\"ko\":\"야\",\"ru\":\"Привет\",\"ja\":\"ねえ\",\"uk\":\"гей\"}",
        "timestamp": "2020-02-17T14:00:35.431Z",
        "uid": 4
    }
}
```

This endpoint retrieves a specific comment.

### HTTP Request

`GET https://api.solonedu.com/comment/<commentID>`

### URL Parameters

Parameter | Description
--------- | -----------
commentID | ID of the comment to retrieve

## Get All Comments for a Specific Forum Post

> This endpoint returns a JSON structured like this:

```json
{
    "message": "All comments for forum post with forumpostID 69 were fetched",
    "comments": [
        {
            "cid": 108,
            "fid": 69,
            "content": "{\"en\":\"what's up\",\"zhcn\":\"这是怎么回事\",\"zhtw\":\"這是怎麼回事\",\"bn\":\"কি খবর\",\"ko\":\"뭐야\",\"ru\":\"что происходит\",\"ja\":\"調子はどう\",\"uk\":\"як справи\"}",
            "timestamp": "2020-02-18T22:18:20.828Z",
            "uid": 1
        },
        {
            "cid": 107,
            "fid": 69,
            "content": "{\"en\":\"hey\",\"zhcn\":\"嘿\",\"zhtw\":\"嘿\",\"bn\":\"অঁ্যা\",\"ko\":\"야\",\"ru\":\"Привет\",\"ja\":\"ねえ\",\"uk\":\"гей\"}",
            "timestamp": "2020-02-17T14:00:35.431Z",
            "uid": 4
        }
    ]
}
```

This endpoint retrieves all comments for a specific forum post.

### HTTP Request

`GET https://api.solonedu.com/comments/forumpost/<forumpostID>`

### URL Parameters

Parameter | Description
--------- | -----------
forumpostID | ID of the forumpost which has the comments to retrieve

## Create a Comment

> This endpoint requires a body like this:

```json
{
	"fid": 69,
	"content": "this is the content",
	"timestamp": "2020-07-28T19:23:51Z",
	"uid": 5
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Comment was created",
    "comment": {
        "cid": 109,
        "fid": 69,
        "content": "{\"en\":\"this is the content\",\"zhcn\":\"这是内容\",\"zhtw\":\"這是內容\",\"bn\":\"এই বিষয়বস্তু\",\"ko\":\"이것은 내용입니다\",\"ru\":\"это содержание\",\"ja\":\"これはコンテンツです\",\"uk\":\"це зміст\"}",
        "timestamp": "2020-07-28T19:23:51.000Z",
        "uid": 5
    }
}
```

This endpoint creates a comment.

### HTTP Request

`POST https://api.solonedu.com/comments`

## Delete a Specific Comment

> This endpoint requires a body like this:

```json
{
	"fid": 69
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Comment with commentID 109 was deleted"
}
```

This endpoint deletes a specific comment.

### HTTP Request

`DELETE https://api.solonedu.com/comments/<commentID>`

### URL Parameters

Parameter | Description
--------- | -----------
commentID | ID of the comment to delete
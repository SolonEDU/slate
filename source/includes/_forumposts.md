# Forum Posts

## Forum Post Model

> Forum posts are stored in a model structured like this:

```json
{
    "fid": 70,
    "title": "{\"en\":\"hello\",\"zhcn\":\"你好\",\"zhtw\":\"你好\",\"bn\":\"হ্যালো\",\"ko\":\"여보세요\",\"ru\":\"Здравствуйте\",\"ja\":\"こんにちは\",\"uk\":\"Здравствуйте\"}",
    "description": "{\"en\":\"WorLd\",\"zhcn\":\"世界\",\"zhtw\":\"世界\",\"bn\":\"দুনিয়া\",\"ko\":\"세계\",\"ru\":\"Мир\",\"ja\":\"世界\",\"uk\":\"WorLd\"}",
    "numcomments": 0,
    "timestamp": "2020-02-15T16:02:53.351Z",
    "uid": 1,
    "entitle": "hello",
    "endescription": "WorLd"
}
```

### Fields

Field | Description
----- | -----------
fid | ID of the forum post
title | JSON with language code as key and translated title as value
description | JSON with language code as key and translated description as value
numcomments | number of votes on the forum post
timestamp | timestamp for creation of the forum post
uid | user ID of the user that created the forum post
entitle | English string of the forum post title
endescription | English string of the forum post description

## Get All Forum Posts

> This endpoint returns a JSON structured like this:

```json
{
    "message": "All forumposts were fetched in order of timestamp ascending",
    "forumposts": [
        {
            "fid": 69,
            "title": "{\"en\":\"ff\",\"zhcn\":\"ff\",\"zhtw\":\"ff\",\"bn\":\"FF\",\"ko\":\"ff\",\"ru\":\"Ф.Ф.\",\"ja\":\"ff\",\"uk\":\"ff\"}",
            "description": "{\"en\":\"ffdfffffffff\",\"zhcn\":\"d\",\"zhtw\":\"d\",\"bn\":\"ffdfffffffff\",\"ko\":\"ffdfffffffff\",\"ru\":\"ffdfffffffff\",\"ja\":\"ffdfffffffff\",\"uk\":\"ffdfffffffff\"}",
            "numcomments": 1,
            "timestamp": "2020-02-15T15:58:33.266Z",
            "uid": 1,
            "entitle": "ff",
            "endescription": "ffdfffffffff"
        },
        {
            "fid": 70,
            "title": "{\"en\":\"hello\",\"zhcn\":\"你好\",\"zhtw\":\"你好\",\"bn\":\"হ্যালো\",\"ko\":\"여보세요\",\"ru\":\"Здравствуйте\",\"ja\":\"こんにちは\",\"uk\":\"Здравствуйте\"}",
            "description": "{\"en\":\"WorLd\",\"zhcn\":\"世界\",\"zhtw\":\"世界\",\"bn\":\"দুনিয়া\",\"ko\":\"세계\",\"ru\":\"Мир\",\"ja\":\"世界\",\"uk\":\"WorLd\"}",
            "numcomments": 0,
            "timestamp": "2020-02-15T16:02:53.351Z",
            "uid": 1,
            "entitle": "hello",
            "endescription": "WorLd"
        }
    ]
}
```

This endpoint retrieves all forum posts.

### HTTP Request

`GET https://api.solonedu.com/forumposts?sort_by=<sort.order>`

### sort_by Query Parameter

Parameter | Description
--------- | -----------
numcomments.asc | sorted by least to greatest number of comments
numcomments.desc | sorted by greatest to least number of comments
timestamp.asc | sorted by oldest to newest time of forum post creation
timestamp.desc | sorted by newest to oldest time of forum post creation

## Search for a Forum Post

> This endpoint returns a JSON structured like this:

```json
{
    "message": "All forumposts with search query in title or description were fetched",
    "forumposts": [
        {
            "fid": 70,
            "title": "{\"en\":\"hello\",\"zhcn\":\"你好\",\"zhtw\":\"你好\",\"bn\":\"হ্যালো\",\"ko\":\"여보세요\",\"ru\":\"Здравствуйте\",\"ja\":\"こんにちは\",\"uk\":\"Здравствуйте\"}",
            "description": "{\"en\":\"WorLd\",\"zhcn\":\"世界\",\"zhtw\":\"世界\",\"bn\":\"দুনিয়া\",\"ko\":\"세계\",\"ru\":\"Мир\",\"ja\":\"世界\",\"uk\":\"WorLd\"}",
            "numcomments": 0,
            "timestamp": "2020-02-15T16:02:53.351Z",
            "uid": 1,
            "entitle": "hello",
            "endescription": "WorLd"
        }
    ]
}
```

This endpoint retrieves all forum posts with the search query in its title or description.

### HTTP Request

`GET https://api.solonedu.com/forumposts?q=<query>`

## Get a Specific Forum Post

> This endpoint returns a JSON structured like this:

```json
{
    "message": "forumpost with forumpostID 70 was fetched",
    "forumpost": {
        "fid": 70,
        "title": "{\"en\":\"hello\",\"zhcn\":\"你好\",\"zhtw\":\"你好\",\"bn\":\"হ্যালো\",\"ko\":\"여보세요\",\"ru\":\"Здравствуйте\",\"ja\":\"こんにちは\",\"uk\":\"Здравствуйте\"}",
        "description": "{\"en\":\"WorLd\",\"zhcn\":\"世界\",\"zhtw\":\"世界\",\"bn\":\"দুনিয়া\",\"ko\":\"세계\",\"ru\":\"Мир\",\"ja\":\"世界\",\"uk\":\"WorLd\"}",
        "numcomments": 0,
        "timestamp": "2020-02-15T16:02:53.351Z",
        "uid": 1,
        "entitle": "hello",
        "endescription": "WorLd"
    }
}
```

This endpoint retrieves a specific forum post.

### HTTP Request

`GET https://api.solonedu.com/forumposts/<forumpostID>`

### URL Parameters

Parameter | Description
--------- | -----------
forumpostID | ID of the forum post to retrieve

## Create a Forum Post

> This endpoint requires a body like this:

```json
{
	"title": "this is a title",
	"description": "this is a description",
	"timestamp": "2020-07-14T19:23:51Z",
	"uid": 5
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Forumpost was created",
    "forumpost": {
        "fid": 71,
        "title": "{\"en\":\"this is a title\",\"zhcn\":\"这是一个标题\",\"zhtw\":\"這是一個標題\",\"bn\":\"এটি একটি শিরোনাম\",\"ko\":\"이것은 제목입니다\",\"ru\":\"это название\",\"ja\":\"これはタイトルです\",\"uk\":\"це заголовок\"}",
        "description": "{\"en\":\"this is a description\",\"zhcn\":\"这是一个描述\",\"zhtw\":\"這是一個描述\",\"bn\":\"এটি একটি বিবরণ\",\"ko\":\"이것은 설명입니다\",\"ru\":\"это описание\",\"ja\":\"これは説明です\",\"uk\":\"це опис\"}",
        "numcomments": 0,
        "timestamp": "2020-07-14T19:23:51.000Z",
        "uid": 5,
        "entitle": "this is a title",
        "endescription": "this is a description"
    }
}
```

This endpoint creates a forum post.

### HTTP Request

`POST https://api.solonedu.com/forumposts`

## Delete a Specific Forum Post

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Forumpost with forumpostID 71 was deleted"
}
```

This endpoint deletes a specific forum post.

### HTTP Request

`DELETE https://api.solonedu.com/forumposts/<forumpostID>`

### URL Parameters

Parameter | Description
--------- | -----------
forumpostID | ID of the forum post to delete
# Forum Posts

## Proposal Model

> Proposals are stored in a model structured like this:

```json
{
    "pid": 257,
    "title": "{\"en\":\"This is a title\",\"zhcn\":\"这是一个标题\",\"zhtw\":\"這是一個標題\",\"bn\":\"এটি একটি শিরোনাম\",\"ko\":\"제목입니다\",\"ru\":\"Это название\",\"ja\":\"これはタイトルです\",\"uk\":\"Це заголовок\"}",
    "description": "{\"en\":\"This is a description\",\"zhcn\":\"这是一个描述\",\"zhtw\":\"這是一個描述\",\"bn\":\"এটি একটি বিবরণ\",\"ko\":\"이것은 설명입니다\",\"ru\":\"Это описание\",\"ja\":\"これは説明です\",\"uk\":\"Це опис\"}",
    "starttime": "2020-07-14T19:23:51.000Z",
    "endtime": "2020-07-28T19:23:51.000Z",
    "uid": 5,
    "numyes": 0,
    "numno": 0,
    "numvotes": 0,
    "entitle": "faf",
    "endescription": "faf"
}
```

### Fields

Field | Description
----- | -----------
pid | ID of the proposal
title | JSON with language code as key and translated title as value
description | JSON with language code as key and translated description as value
starttime | timestamp for creation of the proposal
endtime | timestamp for end of the proposal
uid | user ID of the user that created the proposal
numyes | number of yes votes on the proposal
numno | number of no votes on the proposal
numvotes | number of votes on the proposal
entitle | English string of the proposal title
endescription | English string of the proposal description

## Get All Proposals

> This endpoint returns a JSON structured like this:

```json
{
    "message": "All proposals were fetched in order of numvotes ascending",
    "proposals": [
        {
            "pid": 249,
            "title": "{\"en\":\"faf\",\"zhcn\":\"FAF\",\"zhtw\":\"FAF\",\"bn\":\"ফাফ\",\"ko\":\"FAF\",\"ru\":\"FAF\",\"ja\":\"FAF\",\"uk\":\"FAF\"}",
            "description": "{\"en\":\"faf\",\"zhcn\":\"FAF\",\"zhtw\":\"FAF\",\"bn\":\"ফাফ\",\"ko\":\"FAF\",\"ru\":\"FAF\",\"ja\":\"FAF\",\"uk\":\"FAF\"}",
            "starttime": "2020-02-14T16:02:42.788Z",
            "endtime": "2020-02-21T16:02:42.788Z",
            "uid": 0,
            "numyes": 0,
            "numno": 0,
            "numvotes": 0,
            "entitle": "faf",
            "endescription": "faf"
        },
        {
            "pid": 251,
            "title": "{\"en\":\"vg\",\"zhcn\":\"vg\",\"zhtw\":\"vg\",\"bn\":\"VG\",\"ko\":\"vg\",\"ru\":\"В.Г.\",\"ja\":\"vg\",\"uk\":\"vg\"}",
            "description": "{\"en\":\"vff\",\"zhcn\":\"VFF\",\"zhtw\":\"VFF\",\"bn\":\"vff\",\"ko\":\"VFF\",\"ru\":\"ВФФ\",\"ja\":\"VFF\",\"uk\":\"ВФФ\"}",
            "starttime": "2020-02-14T16:52:15.540Z",
            "endtime": "2020-02-21T16:52:15.540Z",
            "uid": 0,
            "numyes": 0,
            "numno": 0,
            "numvotes": 0,
            "entitle": "vg",
            "endescription": "vff"
        }
    ]
}
```

This endpoint retrieves all proposals.

### HTTP Request

`GET https://api.solonedu.com/proposals?sort_by=<sort.order>`

### sort_by Query Parameter

Parameter | Description
--------- | -----------
numvotes.asc | sorted by least to greatest number of votes
numvotes.desc | sorted by greatest to least number of votes
starttime.asc | sorted by oldest to newest time of proposal creation
starttime.desc | sorted by newest to oldest time of proposal creation
endtime.asc | sorted by oldest to newest time of proposal expiration
endtime.desc | sorted by newest to oldest time of proposal expiration

## Search for a Proposal

> This endpoint returns a JSON structured like this:

```json
{
    "message": "All proposals with search query in title or description were fetched",
    "proposals": [
        {
            "pid": 251,
            "title": "{\"en\":\"vg\",\"zhcn\":\"vg\",\"zhtw\":\"vg\",\"bn\":\"VG\",\"ko\":\"vg\",\"ru\":\"В.Г.\",\"ja\":\"vg\",\"uk\":\"vg\"}",
            "description": "{\"en\":\"vff\",\"zhcn\":\"VFF\",\"zhtw\":\"VFF\",\"bn\":\"vff\",\"ko\":\"VFF\",\"ru\":\"ВФФ\",\"ja\":\"VFF\",\"uk\":\"ВФФ\"}",
            "starttime": "2020-02-14T16:52:15.540Z",
            "endtime": "2020-02-21T16:52:15.540Z",
            "uid": 0,
            "numyes": 0,
            "numno": 0,
            "numvotes": 0,
            "entitle": "vg",
            "endescription": "vff"
        }
    ]
}
```

This endpoint retrieves all proposals with the search query in its title or description.

### HTTP Request

`GET https://api.solonedu.com/proposals?q=<query>`

## Get a Specific Proposal

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Proposal with proposalID 256 was fetched",
    "proposal": {
        "pid": 256,
        "title": "{\"en\":\"ff\",\"zhcn\":\"ff\",\"zhtw\":\"ff\",\"bn\":\"FF\",\"ko\":\"ff\",\"ru\":\"Ф.Ф.\",\"ja\":\"ff\",\"uk\":\"ff\"}",
        "description": "{\"en\":\"ffdfffffffff\",\"zhcn\":\"d\",\"zhtw\":\"d\",\"bn\":\"ffdfffffffff\",\"ko\":\"ffdfffffffff\",\"ru\":\"ffdfffffffff\",\"ja\":\"ffdfffffffff\",\"uk\":\"ffdfffffffff\"}",
        "starttime": "2020-02-14T21:06:28.318Z",
        "endtime": "2020-02-21T21:06:28.318Z",
        "uid": 0,
        "numyes": 1,
        "numno": 0,
        "numvotes": 1,
        "entitle": "ff",
        "endescription": "ffdfffffffff"
    }
}
```

This endpoint retrieves a specific proposal.

### HTTP Request

`GET https://api.solonedu.com/proposals/<proposalID>`

### URL Parameters

Parameter | Description
--------- | -----------
proposalID | ID of the proposal to retrieve

## Create a Proposal

> This endpoint requires a body like this:

```json
{
	"title": "This is a title",
	"description": "This is a description",
	"starttime": "2020-07-14T19:23:51Z",
	"endtime": "2020-07-28T19:23:51Z",
	"uid": 5
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Proposal was created",
    "proposal": {
        "numyes": 0,
        "numno": 0,
        "numvotes": 0,
        "pid": 257,
        "title": "{\"en\":\"This is a title\",\"zhcn\":\"这是一个标题\",\"zhtw\":\"這是一個標題\",\"bn\":\"এটি একটি শিরোনাম\",\"ko\":\"제목입니다\",\"ru\":\"Это название\",\"ja\":\"これはタイトルです\",\"uk\":\"Це заголовок\"}",
        "description": "{\"en\":\"This is a description\",\"zhcn\":\"这是一个描述\",\"zhtw\":\"這是一個描述\",\"bn\":\"এটি একটি বিবরণ\",\"ko\":\"이것은 설명입니다\",\"ru\":\"Это описание\",\"ja\":\"これは説明です\",\"uk\":\"Це опис\"}",
        "starttime": "2020-07-14T19:23:51.000Z",
        "endtime": "2020-07-28T19:23:51.000Z",
        "uid": 5,
        "entitle": "This is a title",
        "endescription": "This is a description"
    }
}
```

This endpoint creates a proposal.

### HTTP Request

`POST https://api.solonedu.com/proposals`

## Delete a Specific Proposal

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Proposal with proposalID 256 was deleted"
}
```

This endpoint deletes a specific proposal.

### HTTP Request

`DELETE https://api.solonedu.com/proposals/<proposalID>`

### URL Parameters

Parameter | Description
--------- | -----------
proposalID | ID of the proposal to delete
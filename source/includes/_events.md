# Events

## Event Model

> Events are stored in a model structured like this:

```json
{
    "eid": 28,
    "title": "{\"en\":\"event 1\",\"zhcn\":\"事件1\",\"zhtw\":\"事件1\",\"bn\":\"ইভেন্ট 1\",\"ko\":\"이벤트 1\",\"ru\":\"событие 1\",\"ja\":\"イベント1\",\"uk\":\"подія 1\"}",
    "description": "{\"en\":\"this is an event\",\"zhcn\":\"这是一个事件\",\"zhtw\":\"這是一個事件\",\"bn\":\"এটি একটি ইভেন্ট\",\"ko\":\"이것은 이벤트입니다\",\"ru\":\"это событие\",\"ja\":\"これはイベントです\",\"uk\":\"це подія\"}",
    "date": "2020-02-12T00:00:00.000Z",
    "datecreated": "2020-02-14T21:37:41.550Z",
    "numattenders": 0,
    "entitle": "event 1",
    "endescription": "this is an event"
}
```

### Fields

Field | Description
----- | -----------
eid | ID of the event
title | JSON with language code as key and translated title as value
description | JSON with language code as key and translated description as value
date | timestamp for event
datecreated | timestamp for creation of the event
numattenders | number of attenders for the event
entitle | English string of the event title
endescription | English string of the event description

## Get All Events

> This endpoint returns a JSON structured like this:

```json
{
    "message": "All events were fetched in order of date ascending",
    "events": [
        {
            "eid": 28,
            "title": "{\"en\":\"event 1\",\"zhcn\":\"事件1\",\"zhtw\":\"事件1\",\"bn\":\"ইভেন্ট 1\",\"ko\":\"이벤트 1\",\"ru\":\"событие 1\",\"ja\":\"イベント1\",\"uk\":\"подія 1\"}",
            "description": "{\"en\":\"this is an event\",\"zhcn\":\"这是一个事件\",\"zhtw\":\"這是一個事件\",\"bn\":\"এটি একটি ইভেন্ট\",\"ko\":\"이것은 이벤트입니다\",\"ru\":\"это событие\",\"ja\":\"これはイベントです\",\"uk\":\"це подія\"}",
            "date": "2020-02-12T00:00:00.000Z",
            "datecreated": "2020-02-14T21:37:41.550Z",
            "numattenders": 0,
            "entitle": "event 1",
            "endescription": "this is an event"
        },
        {
            "eid": 29,
            "title": "{\"en\":\"might be\",\"zhcn\":\"可能\",\"zhtw\":\"可能\",\"bn\":\"হতে পারে\",\"ko\":\"아마도\",\"ru\":\"возможно\",\"ja\":\"かもしれない\",\"uk\":\"може бути\"}",
            "description": "{\"en\":\"a thing\",\"zhcn\":\"一个东西\",\"zhtw\":\"一個東西\",\"bn\":\"একটি জিনিস\",\"ko\":\"물건\",\"ru\":\"вещь\",\"ja\":\"事\",\"uk\":\"річ\"}",
            "date": "2020-02-29T00:00:00.000Z",
            "datecreated": "2020-02-14T21:38:07.090Z",
            "numattenders": 1,
            "entitle": "might be",
            "endescription": "a thing"
        }
    ]
}
```

This endpoint retrieves all events.

### HTTP Request

`GET https://api.solonedu.com/events?sort_by=<sort.order>`

### sort_by Query Parameter

Parameter | Description
--------- | -----------
numattenders.asc | sorted by least to greatest number of attenders
numattenders.desc | sorted by greatest to least number of attenders
date.asc | sorted by oldest to newest date
date.desc | sorted by newest to oldest date

## Search for an Event

> This endpoint returns a JSON structured like this:

```json
{
    "message": "All events with search query in title or description were fetched",
    "events": [
        {
            "eid": 29,
            "title": "{\"en\":\"might be\",\"zhcn\":\"可能\",\"zhtw\":\"可能\",\"bn\":\"হতে পারে\",\"ko\":\"아마도\",\"ru\":\"возможно\",\"ja\":\"かもしれない\",\"uk\":\"може бути\"}",
            "description": "{\"en\":\"a thing\",\"zhcn\":\"一个东西\",\"zhtw\":\"一個東西\",\"bn\":\"একটি জিনিস\",\"ko\":\"물건\",\"ru\":\"вещь\",\"ja\":\"事\",\"uk\":\"річ\"}",
            "date": "2020-02-29T00:00:00.000Z",
            "datecreated": "2020-02-14T21:38:07.090Z",
            "numattenders": 1,
            "entitle": "might be",
            "endescription": "a thing"
        }
    ]
}
```

This endpoint retrieves all events with the search query in its title or description.

### HTTP Request

`GET https://api.solonedu.com/events?q=<query>`

## Get a Specific Event

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Event with eventID 29 was fetched",
    "event": {
        "eid": 29,
        "title": "{\"en\":\"might be\",\"zhcn\":\"可能\",\"zhtw\":\"可能\",\"bn\":\"হতে পারে\",\"ko\":\"아마도\",\"ru\":\"возможно\",\"ja\":\"かもしれない\",\"uk\":\"може бути\"}",
        "description": "{\"en\":\"a thing\",\"zhcn\":\"一个东西\",\"zhtw\":\"一個東西\",\"bn\":\"একটি জিনিস\",\"ko\":\"물건\",\"ru\":\"вещь\",\"ja\":\"事\",\"uk\":\"річ\"}",
        "date": "2020-02-29T00:00:00.000Z",
        "datecreated": "2020-02-14T21:38:07.090Z",
        "numattenders": 1,
        "entitle": "might be",
        "endescription": "a thing"
    }
}
```

This endpoint retrieves a specific event.

### HTTP Request

`GET https://api.solonedu.com/events/<eventID>`

### URL Parameters

Parameter | Description
--------- | -----------
eventID | ID of the event to retrieve

## Create an Event

> This endpoint requires a body like this:

```json
{
	"title": "this is a title",
	"description": "this is a description",
	"date": "2020-07-28T19:23:51Z"
}
```

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Event was created",
    "createdEvent": {
        "datecreated": "2020-02-19T00:22:27.236Z",
        "numattenders": 0,
        "eid": 31,
        "title": "{\"en\":\"this is a title\",\"zhcn\":\"这是一个标题\",\"zhtw\":\"這是一個標題\",\"bn\":\"এটি একটি শিরোনাম\",\"ko\":\"이것은 제목입니다\",\"ru\":\"это название\",\"ja\":\"これはタイトルです\",\"uk\":\"це заголовок\"}",
        "description": "{\"en\":\"this is a description\",\"zhcn\":\"这是一个描述\",\"zhtw\":\"這是一個描述\",\"bn\":\"এটি একটি বিবরণ\",\"ko\":\"이것은 설명입니다\",\"ru\":\"это описание\",\"ja\":\"これは説明です\",\"uk\":\"це опис\"}",
        "date": "2020-07-28T19:23:51.000Z",
        "entitle": "this is a title",
        "endescription": "this is a description"
    }
}
```

This endpoint creates an event.

### HTTP Request

`POST https://api.solonedu.com/events`

## Delete a Specific Event

> This endpoint returns a JSON structured like this:

```json
{
    "message": "Event with eventID 31 was deleted"
}
```

This endpoint deletes a specific event.

### HTTP Request

`DELETE https://api.solonedu.com/events/<eventID>`

### URL Parameters

Parameter | Description
--------- | -----------
eventID | ID of the event to delete
## Introduction
REST, **Re**presentational **S**tate **T**ransfer, is a methodology of making an API. It has several key ingredients:

 * Everything that is fetched, modified, or has a URI is considered a "noun"
 * The HTTP request method sent (GET/POST/etc.), determines the "verb" that is applied to the resource
 
 
 
## Verbage
HTTP standards define request methods to perform a variety of tasks. Here are the main ones we support:


### GET

Responds with a resource or a list of resources.

```
> GET /api/path/playground/balls/1
-----
< 200: {"size": "big", "color": "red", "material": "rubber" }
```

#### Response codes:

| Status Code | Status | Body Data | Description |
| :---------: | :----: | :-------- | :---------- |
| **200** | Ok | Requested resource | Everything worked |
| **404** | Not Found | Empty | Could not find noun for path |


### POST

Creates a new resource.

```
> POST /api/path/crayons { "color": "green" }
-----
< 201

> GET /api/path/crayons
-----
< 200: [{ "color": "green" }, { "color": "gold" }]
```

#### Response codes:

| Status Code | Status | Body Data | Description |
| :---------: | :----: | :-------- | :---------- |
| **201** | Created | Empty | Everything worked |
| **404** | Not Found | Empty | Could not find noun collection for path |
| **409** | Conflict | Empty | There was a conflict with a unique field constraint |

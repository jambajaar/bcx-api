Projects
========

> Operations keeps the lights on, strategy provides a light at the end of the tunnel, 
> but project management is the train engine that moves the organization forward - Joy Gumz

Get projects
------------

* `GET /projects.json` will return all active projects.
* `GET /projects/archived.json` will return all archived projects.

```json
[
  {
    "id": 605816632,
    "name": "BCX",
    "description": "The Next Generation",
    "updated_at": "2012-03-23T13:55:43-05:00",
    "url": "https://basecamp.com/735644780/api/v1/projects/605816632-bcx.json"
  },
  {
    "id": 684146117,
    "name": "Nothing here!",
    "description": null,
    "updated_at": "2012-03-22T16:56:51-05:00",
    "url": "https://basecamp.com/735644780/api/v1/projects/684146117-nothing-here.json"
  }
]
```

`GET /projects/1.json`

```json
{
  "id": 605816632,
  "name": "BCX",
  "description": "The Next Generation",
  "created_at": "2012-03-22T16:56:51-05:00",
  "updated_at": "2012-03-23T13:55:43-05:00",
  "creator": {
    "id": 149087659,
    "name": "Jason Fried"
  },
  "accesses": {
    "count": 5,
    "updated_at": "2012-03-23T13:55:43-05:00",
    "url": "http://bcx.dev/735644780/api/v1/projects/605816632-bcx/accesses.json"
  },
  "attachments": {
    "count": 0,
    "updated_at": null,
    "url": "http://bcx.dev/735644780/api/v1/projects/605816632-bcx/attachments.json"
  },
  "calendar_events": {
    "count": 3,
    "updated_at": "2012-03-22T17:35:50-05:00",
    "url": "http://bcx.dev/735644780/api/v1/projects/605816632-bcx/calendar_events.json"
  },
  "documents": {
    "count": 1,
    "updated_at": null,
    "url": "http://bcx.dev/735644780/api/v1/projects/605816632-bcx/documents.json"
  },
  "topics": {
    "count": 2,
    "updated_at": "2012-03-22T17:35:50-05:00",
    "url": "http://bcx.dev/735644780/api/v1/projects/605816632-bcx/topics.json"
  },
  "todolists": {
    "remaining_count": 4,
    "completed_count": 0,
    "updated_at": "2012-03-23T12:59:23-05:00",
    "url": "http://bcx.dev/735644780/api/v1/projects/605816632-bcx/todolists.json"
  }
}
```

Create project
--------------

`POST /projects.json`

```json
{
  "name": "This is my new project!",
  "description": "It's going to run real smooth"
}
```

This will return `200 OK` with the location of the new project in the `Location` header, if the creation was a success. If the user does not have access to create new projects or the account has reached the project limit, you'll see `403 Forbidden`.
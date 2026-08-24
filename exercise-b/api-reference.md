EXERCISE B

Create a New Task

Endpoint

HTTP Method: POST

Endpoint: /projects/{project\_id}/tasks

Description

Creates a new task in a specified project.

The authenticated user must provide a task title, an assignee, a due date, and a priority level. A description can also be included but is optional.

Authentication

This endpoint requires authentication using a Bearer access token.

Request Headers

Header

Type

Required

Description

Authorization

String

Yes

Contains the user's access token in the format Bearer <token>.

Content-Type

String

Yes

Specifies that the request body is JSON. The value must be application/json.



Path Parameters

Parameter

Data Type

Required

Description

project\_id

Integer

Yes

The unique ID of the project where the new task will be created.



Request Body Parameters

Parameter

Data Type

Required

Description

title

String

Yes

The name or title of the task.

description

String

No

Additional information about the task.

assignee\_id

Integer

Yes

The unique ID of the user who will be assigned the task.

due\_date

String

Yes

The date by which the task should be completed. Uses the YYYY-MM-DD format.

priority

String

Yes

The priority of the task. Allowed values are low, medium, or high.



Example Request

POST /projects/42/tasks

Authorization: Bearer eyJhbGciOiJIUzI1NiIs...

Content-Type: application/json



{

&#x20; "title": "Prepare project documentation",

&#x20; "description": "Complete the user manual and API documentation.",

&#x20; "assignee\_id": 17,

&#x20; "due\_date": "2026-09-15",

&#x20; "priority": "high"

}



Response Codes

HTTP Status Code

Description

201 Created

The task was successfully created.

400 Bad Request

The request contains invalid or incorrectly formatted data.

401 Unauthorized

The authentication token is missing, invalid, or expired.

403 Forbidden

The authenticated user does not have permission to create a task in the specified project.

404 Not Found

The specified project or assignee could not be found.

409 Conflict

The task could not be created because it conflicts with the current state of the project.

422 Unprocessable Entity

The request is correctly formatted, but one or more supplied values fail validation.

429 Too Many Requests

The client has exceeded the API request rate limit.

500 Internal Server Error

The server encountered an unexpected problem while processing the request.



Successful Response

A successful request returns 201 Created.

{

&#x20; "id": 1058,

&#x20; "project\_id": 42,

&#x20; "title": "Prepare project documentation",

&#x20; "description": "Complete the user manual and API documentation.",

&#x20; "assignee\_id": 17,

&#x20; "due\_date": "2026-09-15",

&#x20; "priority": "high",

&#x20; "status": "open",

&#x20; "created\_at": "2026-08-24T11:30:00Z"

}



Response Field Descriptions

Field

Data Type

Description

id

Integer

Unique ID assigned to the newly created task.

project\_id

Integer

ID of the project containing the task.

title

String

Name of the task.

description

String

Additional information about the task.

assignee\_id

Integer

ID of the user assigned to the task.

due\_date

String

Task deadline in YYYY-MM-DD format.

priority

String

Task priority: low, medium, or high.

status

String

Current task status. A newly created task starts with open.

created\_at

String

Date and time when the task was created, using ISO 8601 format.








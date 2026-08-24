
Exercise A — User Manual Procedure

EXERCISE A

Creating and Using a Python Virtual Environment

Prerequisites

Before starting, make sure you have:

A Windows computer.

Python installed on the computer.

Windows PowerShell.

An internet connection.

Basic knowledge of opening and using a command-line terminal.

Procedure

Step 1 — Open PowerShell

Action: Open Windows PowerShell.

Expected result: A PowerShell window opens and displays a command prompt.

Step 2 — Create the project folder

Action: Enter the following command:

mkdir python\_project



Expected result: A folder named python\_project is created in the current location.

Step 3 — Open the project folder

Action: Enter the following command:

cd python\_project



Expected result: The PowerShell prompt shows that you are inside the python\_project folder.

Step 4 — Create the virtual environment

Action: Enter the following command:

python -m venv venv



Expected result: A folder named venv is created inside the project folder.

Step 5 — Activate the virtual environment

Action: Enter the following command:

.\\venv\\Scripts\\Activate.ps1



Expected result: (venv) appears at the beginning of the PowerShell prompt, showing that the virtual environment is active.

Step 6 — Install the requests package

Action: Enter the following command:

python -m pip install requests



Expected result: PowerShell reports that the requests package and its dependencies have been successfully installed.

Step 7 — Verify the installation

Action: Enter the following command:

python -c "import requests; print(requests.\_\_version\_\_)"



Expected result: PowerShell displays the installed version number of the requests package.

Step 8 — Deactivate the virtual environment

Action: Enter the following command:

deactivate



Expected result: The (venv) label disappears from the PowerShell prompt.



Screenshot Description

The screenshot shows a Windows PowerShell terminal documenting the successful creation and use of a Python virtual environment.

The screenshot shows the following:

The python\_project folder being created.

The terminal entering the python\_project folder.

The venv virtual environment being created using python -m venv venv.

The virtual environment being activated, shown by (venv) appearing in the PowerShell prompt.

The requests package being installed successfully using python -m pip install requests.

The message Successfully installed confirms that requests and its required dependencies were installed.

The installed requests version is verified as 2.34.2.

The virtual environment is deactivated, shown by (venv) disappearing from the PowerShell prompt.

This screenshot demonstrates that the procedure was completed successfully from creating the project environment through installing and verifying the package.

Troubleshooting

PowerShell says that running scripts is disabled

If PowerShell displays an error stating that Activate.ps1 cannot be loaded because running scripts is disabled, temporarily allow scripts for the current PowerShell session.

Action: Enter:

Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass



Expected result: PowerShell allows scripts to run for the current session.

Action: Enter:

.\\venv\\Scripts\\Activate.ps1



Expected result: (venv) appears at the beginning of the PowerShell prompt, indicating that the virtual environment is active.



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


Exercise C — Technical Report Executive Summary



&#x20;Executive Summary



This evaluation assessed MySQL, PostgreSQL, and MongoDB as potential database platforms for a new university student records management system. The four-week evaluation focused on the system's ability to manage structured student information, including personal details, enrolment records, and grades; support up to 200 concurrent staff users; maintain ACID compliance for data integrity; and remain manageable by a small IT team with limited database expertise.



Based on these requirements, we recommend \*\*PostgreSQL\*\* as the preferred database platform. PostgreSQL provides strong ACID compliance and reliable support for structured relational data, making it well suited to maintaining accurate student records and relationships between enrolment and grade information. It can also support the expected level of concurrent access without requiring a large specialist administration team.



The two most important factors driving this recommendation were \*\*data integrity\*\* and \*\*maintainability\*\*. PostgreSQL provides the transactional reliability required for sensitive academic records while offering a mature, well-documented platform that can be managed by a small IT team. Although MySQL is also a suitable relational option, PostgreSQL provides the strongest overall fit for the university's requirements.







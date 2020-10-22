= Zoho Samples

== Setup

Create the following gov keys:

* conf:app/zoho/zoho_client_id => ZoHo API client_id
* conf:app/zoho/zoho_client_secret => ZoHo API client_secret
* Modify the "zoho_project" url to reflect your portal/project IDs


== Create Task

Endpoint: http://<wso2 host>:8280/zoho/tasks

Supported operations:

* GET List tasks 
* POST create a new task with attachment

Using curl:



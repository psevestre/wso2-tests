# Zoho Samples

## Setup

Create the following gov keys:

* conf:app/zoho/zoho_client_id => ZoHo API client_id
* conf:app/zoho/zoho_client_secret => ZoHo API client_secret
* Modify the "zoho_project" url to reflect your portal/project IDs
* mvn clean install
* Deploy the generated "car" artifact under zoho_tasksCompositeApplication/target to WSO2

## Create Task

Using multipart/form-data with WSO2 (sort of... WSO2 fights really well against it)

Endpoint: http://<wso2 host>:8280/zoho/tasks

Supported operations:

* GET List tasks 
* POST create a new task with attachment


Using curl:

* List tasks: curl http://<wso2 host>:8280/zoho/tasks
* Create task: curl -X POST   -F "name=task18" -F 'uploaddoc=@/path/to/some/file.png'   http://localhost:8280/zoho/tasks
  
Notes:

* Just the task name is supported and attachment are supported
* Original filename and content-type are lost for now. I'm still ivestigating why those properties ere lost.
* The very much undocumented property DECODE_MULTIPART_DATA is *crucial* to avoid send a base64 encoded of the original file
* Very, very memory intensive as the attachment ends up being fully loaded in memory.






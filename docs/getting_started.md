---
title: "Getting started"
nav_order: 4
---

# HTTP SERVER

## Installing API
1. First, you need to extract the _PSR-API.zip_ file on your device.
2. Next, in order to run the HTTP server application, the following steps must be specified in the _PSRHttpApi.exe.config_ file.

## Starting Server
1. Before running the API, it’s necessary to put all the basic cases inside the cases folder aforementioned.
2. After that, run the _PSRHttpApi.exe_ file as administrator.
3. From now on, all communication with the server can be done using GET requests.

## Formatting the GET Requests

* It's important to know that this the standard format of GET request:

http://server:port/functionallity?parameter1=value1&parameter2=value2&etc


* Here is some comments about this format:
  * `server`: if _localhost_ is set as server, only the local machine connections will be accepted.
  * `port`: if _8080_ is set as port, only the connections to the port 8080 will be accepted.
  * `functionallity`: here is set the name of the desired method (see more in Overview Tab)
  * `parameter`: each functionallity has a set of parameters (see more in Overview Tab)
  * `value`: here is the value associated to each parameter (casename = Brazil_base_case)
  * `&`: The character _&_ is used to separate the parameters of each method.

## Examples

### Web Browser
Here are some examples of how to call the existing API requests through the `web browser`.
It's worth to mention that, in these examples, only the local machine connections to the port 8080 will be accepted.

* Running a case: `http://localhost:8080/run?casename=folder_name&model=sddp`

* Running a case and Updating some attributes: `http://localhost:8080/run?casename=folder_name&model=sddp&updatefilename=json_file_name.json`

* Getting Results: `http://localhost:8080/getresults?run_id=folder_id`

* Taking the _Status_ of a Run: `http://localhost:8080/status?run_id=folder_id`


### Python
Here are some examples of how to call the existing API requests through `Python` code.
It's worth to mention that, in these examples, only the local machine connections to the port 8080 will be accepted.

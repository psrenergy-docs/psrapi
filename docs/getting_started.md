---
title: "Getting started"
nav_order: 4
---

# HTTP SERVER

## Installing API
1. First, you need to extract the _PSR-API.zip_ file on your device.
2. Next, in order to run the HTTP server application, the following steps must be specified in the _PSRHttpApi.exe.config_ file.

```html
<appSettings>
  <add key="prefixes"        value="<address>"/>
  <add key="rootpath"        value="<root path>"/>
  <add key="sddppath"        value="<sddp path>"/>
  <add key="ncppath"         value="<ncp path>"/>
  <add key="mcpath"          value="<master converter path>"/>
  <add key="csvcnv"          value="<version>"/>
  <add key="updatefilepath"  value="<update file path>"/>
  <add key="secret"          value="<secret id>"/>
</appSettings>
```

* `address`:<br>
Network address mask that must be used to accept the incoming connection. It also defines the port.

* `rootpath`:<br>
Root directory for all data and generated results. When it specified, API will automatically create the cases folder and runs folder, inside the given rootpath. Otherwise, these folders will be created inside this new folder path “C:\psrhttpfiles\”.

* `sddppath`:<br>
SDDP installation directory (obligatory).

* `ncppath`:<br>
NCP installation directory (obligatory).

* `mcpath`:<br>
MasterConverter application directory. MasterConverter is a console application that incorporates the low/mid level C++ API and processes the case update.

* `csvcnv`:<br>
Version of SDDP/csv to be applied.

* `updatefilepath`:<br>
When specified, it determines the absolute directory of the JSON update files. If not, the JSON update file must be in the case's original folder.

* `secret`:<br>
Secret id that must be passed in the request header (HTTP header).


## Starting Server
1. Before running the API, it’s necessary to put all the basic cases inside the cases folder aforementioned.
2. After that, run the _PSRHttpApi.exe_ file as administrator.
3. From now on, all communication with the server can be done using GET requests.


## Formatting the GET Requests

* It's important to know that this the standard format of GET request:<br>
http://server:port/functionallity?parameter1=value1&parameter2=value2&etc

* Here is some comments about this format:
  * `server`: if _localhost_ is set as server, only the local machine connections will be accepted.
  * `port`: if _8080_ is set as port, only the connections to the port 8080 will be accepted.
  * `functionallity`: here is set the name of the desired method (_see more in Overview Tab_)
  * `parameter`: each functionallity has a set of parameters (_see more in Overview Tab_)
  * `value`: here is the value associated to each parameter (_casename = Brazil_base_case_)
  * `&`: The character _&_ is used to separate the parameters of each method.


## Examples

### Web Browser
Here are some examples of how to call the existing API requests through the `web browser`.<br>
It's worth to mention that, in these examples, only the local machine connections to the port 8080 will be accepted.

* Running a case:<br>
http://localhost:8080/run?casename=folder_name&model=sddp

* Running a case and Updating some attributes:<br>
http://localhost:8080/run?casename=folder_name&model=sddp&updatefilename=json_file_name.json

* Getting Results:<br>
http://localhost:8080/getresults?run_id=folder_id

* Taking the _Status_ of a Run:<br>
http://localhost:8080/status?run_id=folder_id


### Python
Here are some examples of how to call the existing API requests through `Python` code.<br>
It's worth to mention that, in these examples, only the local machine connections to the port 8080 will be accepted.

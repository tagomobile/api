Folders
==========


Listing Folders
----

<br />

* `GET /folders` return list of all folders.
* `GET /folders?skip={skip}&$top={top}` return custom range of folders.


Data type: [Folder](folder.md)

**Example**

* http://testv2.tago.ca/api/folders
* http://testv2.tago.ca/api/folders?skip=0&top=10

```
Status: 200 OK
```

```json
[
  {

    "id": 2232,
    "name": "Default", 
    "createdOn": "2012-03-24T11:00:39-05:00",
    "createdBy": "",
    "barcodesCount": 21,
    "totalScans": 214
  }
]
```

<br/>

Getting Folders
----
* `GET /folders/{id}` return folder by id.
* `GET /folders?folderName={name}` return folder by name.
<br />

Data type: [Folder](folder.md)

**Example**

* http://testv2.tago.ca/api/folders/16771?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
* http://testv2.tago.ca/api/folders?folderName=Default?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c


```
Status: 200 OK
```

```json
{

    "id": 2232,
    "name": "Default", 
    "createdOn": "2012-03-24T11:00:39-05:00",
    "createdBy": "",
    "barcodesCount": 21,
    "totalScans": 214
}
```

Creating Folders
----
* `POST /folders` add folder.

Data type: [Folder](folder.md)

Request JSON data:

```json
{

    "name": "New Folder", 
}

```
Response:

```
Status: 201 Created
```

```json
{
    "id": 2232,
    "name": "New Folder", 
    "createdOn": "2012-03-24T11:00:39-05:00",
    "createdBy": "",
    "barcodesCount": 0,
    "totalScans": 0
}
```

Updating Folders
----
* `PUT /folders/{id}` change folder name.
<br />

Data type: [Folder](folder.md)

Request JSON data:

```json
{

    "name": "Changed Name", 
}
```

Response:

```
Status: 200 OK
```

```json
{
    "id": 2232,
    "name": "Changed Name", 
    "createdOn": "2012-03-24T11:00:39-05:00",
    "createdBy": "",
    "barcodesCount": 0,
    "totalScans": 0
}
```

Deleting folders
----
* `DELETE /folders/{id}` delete folder by id.
* `DELETE /folders?folderName={name}` delete folder by name.

Will delete the folder by it id or name and return `200 OK` if that was successful. If the user does not have access to delete the folder, you'll see `403 Forbidden`.
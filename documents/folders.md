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

Creating Barocdes
----
* `POST /barcodes` add barcode.

Data type: [Barcode](barcode.md)

Request JSON data:

```json
{
    "type": "url", 
    "folderName": "Default",
    "isTrackable": true, 
    "Url": 
        { 
            "Url": "http://google.com"
        } 
}

```
Response:

```
Status: 201 Created
```

```json
{
    "shortLink": "http://tago.ca/MYj",
    "label": "",
    "folderId": 16771,
    "id": 24906,
    "isTrackable": true,
    "type": "url"
}
```

Updating Barcodes
----
* `PUT /barcodes/{id}` update barcode content.
<br />

Data type: [Barcode](barcode.md)

Request JSON data:

```json
{
    "type": "text", 
    "Text": 
        { 
            "Text": "New text goes here..."
        } 
}

```

Response:

```
Status: 200 OK
```



Deleting barocdes
----
* `DELETE /barcodes/{id}` delete barcode.

Will delete the barcode by it id and return `200 OK` if that was successful. If the user does not have access to delete the barcode, you'll see `403 Forbidden`.
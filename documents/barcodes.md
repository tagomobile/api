Barcodes
==========

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


QR Code Image Generating
----
Please note, that barcode firts should be created and than QR Code image can be donloaded via separate call

* `GET /barcodes/{id}/Image` return QR Code image by barcode id. Image size - M, Error Correction Level - M, format - png
* `GET /barcodes/{id}/Image?format=eps&size=M&errorCorrection=M` return QR Code image by barcode id with custom image settigns.
<br />

```http
HTTP/1.1 200 OK
Cache-Control: no-cache
Pragma: no-cache
Content-Type: image/png
Expires: -1
Server: Microsoft-IIS/7.5
X-AspNet-Version: 4.0.30319
X-Powered-By: ASP.NET
Date: Mon, 18 Jun 2012 04:46:50 GMT
Content-Length: 3329

"\211PNG\r\n\032\n\000\000\000\rIHDR\000\000\000\313\000\000\..."
```

Getting Barcodes
----
* `GET /barcodes/{id}` return barcode content by it id.
<br />

Data type: [Barcode](barcode.md)

```
Status: 200 OK
```

```json
{
  "folderId": 16771,
  "id": 24906,
  "isTrackable": true,
  "type": "url",
  "label": "Magazine",
  "geoEnabled": false,
  "createdDate": "24/03/2012",
  "Url": {
    "Url": "http://www.yandex.ru"
  }
}
```

Listing Barcodes
----

#### Get list with general barcodes information

* `GET /barcodes` return list of all barcodes.
* `GET /barcodes?folderId={id}` return all barcodes from specific folder by folder id.
* `GET /barcodes?folderName={name}` return all barcodes from speicif folder by folder name.
* `GET /barcodes$skip={skip}&$top={top}` return custom range of barcodes.

Data type: [BarcodeInfo](barcodeInfo.md)

**Sample**

* http://testv2.tago.ca/api/barcodes?folderId=16771&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c


#### Get list with full barcodes information

* `GET /barcodes/full` return list of all barcodes.
* `GET /barcodes/full?folderId={id}` return all barcodes from specific folder by folder id.
* `GET /barcodes/full?folderName={name}` return all barcodes from speicif folder by folder name.
* `GET /barcodes/full$skip={skip}&$top={top}` return custom range of barcodes.

Data type: [Barcode](barcode.md)

**Sample**

* http://testv2.tago.ca/api/barcodes/full?folderId=16771&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c

<br />


`GET /barcodes` return general information for all barcodes. To get barcode type specific data, you need to use `GET /barcodes/{id}` method. Or you can use `GET /barcodes/full` method, which behave the same, but return list of [Barcode](barcode.md) objects, which conatins barcode type specific information.
Depends on numbert of barcodes in your account, `GET /barcodes` generally perform faster than `GET /barcodes/full`.


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

Will delete the barcode by it id and return `204 No Content` if that was successful. If the user does not have access to delete the barcode, you'll see `403 Forbidden`.
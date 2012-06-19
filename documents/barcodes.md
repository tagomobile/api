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

* `GET /barcodes` return list of all barcodes.
* `GET /barcodes?folderId={id}` return all barcodes from specific folder by folder id.
* `GET /barcodes?folderName={name}` return all barcodes from speicif folder by folder name.
* `GET /barcodes$skip={skip}&$top={top}` return custom range of barcodes.
<br />

Data type: [BarcodeInfo](barcodeInfo.md)

```json
[
  {
    "shortLink": "http://tago.ca/EUd",
    "label": "",
    "folderId": 16771,
    "url": "",
    "id": 24798,
    "isTrackable": true,
    "type": "text"
    "createdDate": "14/12/2012"
  },
  {
    "shortLink": "http://tago.ca/zSZ",
    "label": "",
    "folderId": 16771,
    "url": "http://google.com",
    "id": 24849,
    "isTrackable": true,
    "type": "url"
    "createdDate": "14/12/2012"
  }
]
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

Will delete the barcode by it id and return `204 No Content` if that was successful. If the user does not have access to delete the barcode, you'll see `403 Forbidden`.
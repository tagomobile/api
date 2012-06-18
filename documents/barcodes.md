Barcodes
==========

Creating Barocdes
----
* `POST /barcodes` add barcode.

Request data:

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
* `GET /barcodes/{id}/Image?forat=eps&size=M&errorCorrection=M` return QR Code image by barcode id with custom image settigns.
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

Listing Barcodes
----

* `GET /barcodes` return list of all barcodes.
* `GET /barcodes?folder={id}` return all barcodes from specific folder by folder id.
* `GET /barcodes?folderName={id}` return all barcodes from speicif folder by folder name.
* `GET /barcodes$skip={skip}&$top={top}` return custom range of barcodes.
<br />

Updating Barcodes
----
* `PUT /barcodes/{id}` update barcode content.
<br />

Deleting barocdes
----
* `DELETE /barcodes/{id}` delete barcode.
Generate
=======

### Generate Embeddede Text code using GET request

This method will generate url or text code using single API call and without adding the barcode into the account. Currently URL and Text QR Code generation is supported using this method. Please email us at support@tago.ca if missing particular QR Code type support.

* `GET /generate/{type}.{image format}?type={type}&{type}=My%20text` generate barcode without adding it to the account
* `GET /generate/{type}.{image format}?type={type}&{type}=http://google.com&format=png&size=M&errorCorrection=M` generate barcode with custom image settigns. Barcode will not be added to the account
<br />

{type}: url | text <br/>
{image format}: png | gif | jpg | bmp | exif | tiff | icon


**Examples**

* http://tagomobile.com/api/v1/generate.png?type=url&url=http://google.com&format=png&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
* http://tagomobile.com/api/v1/generate.jpg?type=text&text=Hello%20World!&format=png&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c

*Note: Provided API Key is for testing purposes only, do not use in production environment.

Response:

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

<br />

### Generate Trackable\Non-Trackable code using POST request

This method will generate Trackable or Non-Trackable code using single API call.

Trackable code will be added into the account automatically.

For Non-Trackable you could optioanlly specify if code needed to be added it into the account or not. If not specified, code will be added by default. Currently Non-Trackable barcodes of following types could be generated: URL, Text and Contact Info. Please email us at support@tago.ca if missing particular QR Code type support.

* `POST /generate.{image format}?add={bool}&format={format}&size={size}&errorCorrection={level}` generate barcode. 'add' parameter is 'true' by default.

Data type: [Barcode](barcode.md)

{image format}: png | gif | jpg | bmp | exif | tiff | icon

Request:

    POST /generate?add=true&format=png

```json
{
    "type": "url", 
    "folderName": "Default",
    "isTrackable": true, 
    "url": 
        { 
            "url": "http://google.com"
        } 
}

```

Response:

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
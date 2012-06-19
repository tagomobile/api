Generate
=======

### Generate Embeddede Text code using GET request

This method will generate url or text code using single API call and without adding the barcode into the account.

* `GET /generate?type=text&text=My%20text` generate barcode without adding it to the account
* `GET /generate/?type=text&text=My%20text&format=png&size=M&errorCorrection=M` generate barcode with custom image settigns. Barcode will not be added to the account
<br />

**Examples**

* <a>http://www.tagomobile.com/api/v1/generate?type=url&url=http://google.com&format=png&apiKey='303kfd0-2223334w3-3243434-224324"</a>
* <a>http://www.tagomobile.com/api/v1/generate?type=text&text=Hello%20World!&format=png&apiKey='303kfd0-2223334w3-3243434-224324"</a>

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

This method will generate Trackable or Non-Trackable code using single API call and.

Trackable code will be added into the account automatically.

For Non-Trackable you could specify if code needed to be added it into the account, once generated, or not.

* `POST /generate?add={bool}` generate barcode.

Data type: [Barcode](barcode.md)

Request:

    POST /generate?add=true

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
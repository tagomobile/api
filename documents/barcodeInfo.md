BarcodeInfo Type
========

Barcodes are represented as JSON or XML objects with specific keys.

**Examples**

```json
{
    "id": "2232",
    "type": "url", 
    "folderId": "12321",
    "isTrackable": true,
    "geoEnabled": false,
    "shortLink": "http://tago.ca/abc",
    "label": "magazine",
    "targetUrl": "http://google.com",
    "createdDate" : "23/07/2012"
}
```

Refference
----


Barcode general:

<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Read-only</th>
      <th>Required</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>type</td>
        <td>enum</td>
        <td>no</td>
        <td>yes</td>
        <td>Type of barcode. Values: url, text, contact</td>
    </tr>
    <tr>
        <td>isTrackable</td>
        <td>bool</td>
        <td>no</td>
        <td>yes</td>
        <td>Specify if should be created trackable or non-tackable(Embedded) barcode.</td>
    </tr>
    <tr>
        <td>id</td>
        <td>long</td>
        <td>yes</td>
        <td>no</td>
        <td>Unique barcode id. Signed 64-bit integers</td>
    </tr>
    <tr>
        <td>targetUrl</td>
        <td>string</td>
        <td>yes</td>
        <td>no</td>
        <td>If barcode type is 'url', than this field will conatin target url. Otherwise empty</td>
    </tr>
    <tr>
        <td>shortLink</td>
        <td>string</td>
        <td>yes</td>
        <td>no</td>
        <td>If barcode is trackable, than this field will contain it short url. Otherwise empty</td>
    </tr>
    <tr>
        <td>createdDate</td>
        <td>date</td>
        <td>yes</td>
        <td>no</td>
        <td>The time the barcode was created</td>
    </tr>
    <tr>
        <td>folderId</td>
        <td>int</td>
        <td>no</td>
        <td>no</td>
        <td>Folder id where to add barcode</td>
    </tr>
    <tr>
        <td>label</td>
        <td>string</td>
        <td>no</td>
        <td>no</td>
        <td>Optionally set barcode lable</td>
    </tr>
    <tr>
        <td>geoEnabled</td>
        <td>bool</td>
        <td>no</td>
        <td>no</td>
        <td>Specify if geo-location should be requested from user, once he scan QR Code. Default: false</td>
    </tr>
</table>
<br />




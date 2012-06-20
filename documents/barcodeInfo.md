BarcodeInfo Type
========

BarcodeInfo data structure is represented as JSON or XML objects with specific keys. 

BarcodeInfo structure is used only in Listing Barcodes `GET /barcodes` method.
It contains general information about barcode. Also, it has additional parameter `targetUrl` specific only for URL type of barcode and presented in this structure only for convinience of API use. Hence, to get URL spcecific information from data returned by Listing Barcodes method, you don't need to do any additional calls. 

For all other types of barcodes, you need to do separate code for each barcode to get barcode specifi information. Or use `GET /barcodes/full` method to extract the most full data for all barcodes. Depends on number of codes in your account, `GET /barcodes/full` method is generally perform slower than `GET /barcoes`.

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
        <td>id</td>
        <td>long</td>
        <td>yes</td>
        <td>no</td>
        <td>Unique barcode id. Signed 64-bit integers</td>
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




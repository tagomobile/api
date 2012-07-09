Barcode Type
========

Barcodes are represented as JSON or XML objects with specific keys.
When your requesting\creating or updating  specific type of QR Code (Url, Text Note or Contact Info) you
need to you read\write Barcode general paramets (which are the same for all types of barcodes) and in correspondent
field (Url, Text, Contact) read\write specific JSON object, representing this particular type.

**Please note:** Currenty we support Creating\Updating only **URL**, **Text Note** and **Contact Info** barcode types. Please email us at support@tago.ca if you missing particular QR Code type support.

**Examples**

URL Barcode:

```json
{
    "type": "url", 
    "id": "2232",
    "createdOn" : "2012-03-24T11:00:39-05:00",
    "shortLink": "http://tago.ca/abc",
    "targetUrl": "http://google.com",
    "folderName": "Default",
    "isTrackable": true, 
    "Url": 
        { 
            "Url": "http://google.com"
        } 
}
```

Text Barcode:


```json
{
    "type": "text", 
    "folderName": "Default",
    "isTrackable": true, 
    "Text": 
        { 
            "Text": "Your text goes here..."
        } 
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
        <td>Type of barcode. Values: url, text, contact, entry. Entry type is a <a href="#content">compound</a> type for all other types of barcodes</td>
    </tr>
    <tr>
        <td>isTrackable</td>
        <td>bool</td>
        <td>no</td>
        <td>yes</td>
        <td>Specify if should be created trackable or non-tackable(Embedded) barcode.</td>
    </tr>
    <tr>
        <td>shortLink</td>
        <td>string</td>
        <td>yes</td>
        <td>no</td>
        <td>If barcode is trackable, than this field will contain it short url. Otherwise empty</td>
    </tr>
    <tr>
        <td>createdOn</td>
        <td>date</td>
        <td>yes</td>
        <td>no</td>
        <td>The time the barcode was created. Format: 2012-03-24T11:00:39-05:00</td>
    </tr>
    <tr>
        <td>createdBy</td>
        <td>string</td>
        <td>yes</td>
        <td>no</td>
        <td>Will conain sub-account name created the barcode, in case if current account has sub-accounts.</td>
    </tr>
    <tr>
        <td>folderId</td>
        <td>int</td>
        <td>no</td>
        <td>no</td>
        <td>Folder id where to add barcode</td>
    </tr>
    <tr>
        <td>folderName</td>
        <td>string</td>
        <td>no</td>
        <td>no</td>
        <td>Folder name where to add barcode, if folder id not specified</td>
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
    <tr>
        <td>url</td>
        <td>object</td>
        <td>no</td>
        <td>no</td>
        <td>Object with URL barcode specific parameters. See <a href="#url">URL Barcode</a> specification below</td>
    </tr>
    <tr>
        <td>text</td>
        <td>object</td>
        <td>no</td>
        <td>no</td>
        <td>Object with Text barcode specific parameters. See <a href="#text">Text Barcode</a> specification below</td>
    </tr>
    <tr>
        <td>сontact</td>
        <td>object</td>
        <td>no</td>
        <td>no</td>
        <td>Object with Contact Info barcode specific parameters. See <a href="#contact">Contact Info Barcode</a> specification below</td>
    </tr>
    <tr>
        <td>content</td>
        <td>object</td>
        <td>yes</td>
        <td>no</td>
        <td>Currently API supports only 3 major types of barcodes: URL, Text and Contact Info. If type of barocode is different from this major types, than will be retured <a href="#content">Content</a> data oject, which contains short description of barcode content</td>
    </tr>
</table>
<br />

<a name="url"></a>
URL barcode:

<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Read-only</th>
      <th>Required</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>url</td>
        <td>string</td>
        <td>no</td>
        <td>yes</td>
        <td>URL of resource where QR Code should be pointed to</td>
    </tr>
</table>
<br />

<a name="text"></a>
Text barcode:

<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Required</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>text</td>
        <td>string</td>
        <td>yes</td>
        <td>Text which will be displayed to user</td>
    </tr>
</table>
<br />

<a name="contact"></a>
Contact Info barcode:

<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Required</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>firstName</td>
        <td>string</td>
        <td>yes</td>
        <td>First Name</td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>string</td>
        <td>no</td>
        <td>Last Name</td>
    </tr>
    <tr>
        <td>organization</td>
        <td>string</td>
        <td>no</td>
        <td>Organization of company name</td>
    </tr>
    <tr>
        <td>title</td>
        <td>string</td>
        <td>no</td>
        <td>Job title</td>
    </tr>
    <tr>
        <td>photoUrl</td>
        <td>string</td>
        <td>no</td>
        <td>Link to photo</td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>string</td>
        <td>no</td>
        <td>Mobile phone number</td>
    </tr>
    <tr>
        <td>workPhone</td>
        <td>string</td>
        <td>no</td>
        <td>Work phone number</td>
    </tr>
    <tr>
        <td>email</td>
        <td>string</td>
        <td>no</td>
        <td>Email Address</td>
    </tr>
    <tr>
        <td>website</td>
        <td>string</td>
        <td>no</td>
        <td>Website Address</td>
    </tr>
    <tr>
        <td>facebookLink</td>
        <td>string</td>
        <td>no</td>
        <td>Link to facebook page</td>
    </tr>
    <tr>
        <td>twitterLink</td>
        <td>string</td>
        <td>no</td>
        <td>Link to twitter profile</td>
    </tr>
        <tr>
        <td>linkedInLink</td>
        <td>string</td>
        <td>no</td>
        <td>Link to linkedin profile</td>
    </tr>
    
</table>

<br/>

<a name="content"></a>
Сontent (for all other types of barcodes):

<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Read-only</th>
      <th>Required</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>data</td>
        <td>string</td>
        <td>yes</td>
        <td>no</td>
        <td>Short description of barcode content</td>
    </tr>
</table>
<br />







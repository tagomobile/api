Barcode Model
========

Barcodes are represented as JSON or XML objects with specific keys.
When your requesting\creating or updating  specific type of QR Code (Url, Text Note or Contact Info) you
need to you read\write Barcode general paramets (which are the same for all types of barcodes) and in correspondent
field (Url, Text, Contact) read\write specific JSON object, representing this particular type.

Example

URL Barcode:

```json
{
    type: url, 
    FolderName: Default,
    isTrackable: true, 
    Url: 
        { 
            Url: url
        } 
}
```

Text Barcode


```json
{
    type: url, 
    FolderName: Default,
    isTrackable: true, 
    Text: 
        { 
            Text: Enter your text here...
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
      <th>Required</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>type</td>
        <td>enum</td>
        <td>yes</td>
        <td>Type of barcode. Values: url, text, contact</td>
    </tr>
    <tr>
        <td>isTrackable</td>
        <td>bool</td>
        <td>yes</td>
        <td>Specify if should be created trackable or non-tackable(Embedded) barcode.</td>
    </tr>
    <tr>
        <td>folderId</td>
        <td>int</td>
        <td>no</td>
        <td>Folder id where to add barcode</td>
    </tr>
    <tr>
        <td>folderName</td>
        <td>string</td>
        <td>no</td>
        <td>Folder name where to add barcode, if folder id not specified</td>
    </tr>
    <tr>
        <td>label</td>
        <td>string</td>
        <td>no</td>
        <td>Optionally set barcode lable</td>
    </tr>
    <tr>
        <td>geoEnabled</td>
        <td>bool</td>
        <td>no</td>
        <td>Specify if geo-location should be requested from user, once he scan QR Code. Default: false</td>
    </tr>
</table>
<br />

URL barcode:


<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Required</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>url</td>
        <td>string</td>
        <td>yes</td>
        <td>URL of resource where QR Code should be pointed to</td>
    </tr>
</table>
<br />

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
        <td>lstName</td>
        <td>string</td>
        <td>no</td>
        <td>Last Name</td>
    </tr>
    <tr>
        <td>organization</td>
        <td>string</td>
        <td>no</td>
        <td>Oganization of company name</td>
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







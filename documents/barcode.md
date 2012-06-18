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

URL barcode specific parameters

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

Text barcode specific parameters

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

Contact Info barcode specific parameters

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







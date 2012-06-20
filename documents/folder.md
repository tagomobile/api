Folder Type
========

<br />
                
**Example**

```json
{

    "id": 2232,
    "name": "Default", 
    "createdOn": "2012-03-24T11:00:39-05:00",
    "createdBy": "",
    "barcodesCount": 21,
    "totalScans": 214
}
```

<br />

Refference
----
<br />

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
        <td>Unique folder id. Signed 64-bit integers</td>
    </tr>
    <tr>
        <td>name</td>
        <td>string</td>
        <td>no</td>
        <td>yes</td>
        <td>Folder name</td>
    </tr>
    <tr>
        <td>createdOn</td>
        <td>date</td>
        <td>yes</td>
        <td>no</td>
        <td>Date and time folder was created. Format: 2012-03-24T11:00:39-05:00</td>
    </tr>
    <tr>
        <td>createdBy</td>
        <td>string</td>
        <td>yes</td>
        <td>no</td>
        <td>Will conain sub-account name created the barcode, in case if current account has sub-accounts</td>
    </tr>
    <tr>
        <td>barcodesCount</td>
        <td>int</td>
        <td>yes</td>
        <td>no</td>
        <td>Total number of barcodes in folder</td>
    </tr>
    <tr>
        <td>totalScans</td>
        <td>int</td>
        <td>yes</td>
        <td>no</td>
        <td>Number of total scans for all barcodes in folder</td>
    </tr>
</table>
<br />




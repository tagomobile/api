Scans Type
-----------

<br/>

**Example**

```json
{
    "uniqueScans": 723,
    "totalScans": 689
  }
```

### Refference

<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>uniqueScans</td>
        <td>int</td>
        <td>Number of unique QR Code scans</td>
    </tr>
    <tr>
        <td>totalScans</td>
        <td>int</td>
        <td>Number of total QR Code scans</td>
    </tr>
</table>
<br />

DayScans Type
---

<br/>

**Example**

```json
{
    "date": "2012-03-24T11:00:39-05:00",
    "uniqueScans": 723,
    "totalScans": 689
}
```

### Refference

<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>date</td>
        <td>date</td>
        <td>Statistics date. Format: 2012-03-24T11:00:39-05:00. In case if enquire statistics for single day, than hours of day will be returned via this field. Format: 3 PM </td>
    </tr>
    <tr>
        <td>uniqueScans</td>
        <td>int</td>
        <td>Number of unique QR Code scans</td>
    </tr>
    <tr>
        <td>totalScans</td>
        <td>int</td>
        <td>Number of total QR Code scans</td>
    </tr>
</table>

<br />

ScanDetails Type
---

<br/>

**Example**

```json
{
    "barcodeId": 2032,
    "barcodeType": "url",
    "barcodeLabel": "magazine",
    "barcodeContent": "http://google.com",
    "folderName": "Default",
    "scanDateTime": "2012-03-24T11:00:39-05:00",
    "city": "San Francisco",
    "country": "USA",
    "device": "iPhone",
    "ipAddress": "168.124.123.100",
    "provider": "ProviderInc."
  }
```

### Refference

<table>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Comment</th>
    </tr>
    <tr>
        <td>barcodeId</td>
        <td>int</td>
        <td>Date and time QR Code was scanned</td>
    </tr>
    <tr>
        <td>barcodeType</td>
        <td>string</td>
        <td>Type of barcode. Values: url, text, contact</td>
    </tr>
    <tr>
        <td>barcodeLabel</td>
        <td>string</td>
        <td>Optional barcode label</td>
    </tr>
    <tr>
        <td>barcodeContent</td>
        <td>string</td>
        <td>Short description of barcode content</td>
    </tr>
    <tr>
        <td>folderName</td>
        <td>string</td>
        <td>Barcode folder name</td>
    </tr>
    <tr>
        <td>scanDateTime</td>
        <td>dateTime</td>
        <td>Date and time QR Code was scanned</td>
    </tr>
    <tr>
        <td>city</td>
        <td>string</td>
        <td>Name of city where QR Code was scanned</td>
    </tr>
    <tr>
        <td>country</td>
        <td>string</td>
        <td>Name of country where QR Code was scanned</td>
    </tr>
    <tr>
        <td>device</td>
        <td>string</td>
        <td>Name of device used to scan QR Code</td>
    </tr>
    <tr>
        <td>ipAddress</td>
        <td>string</td>
        <td>IpAddress of device which scanned QR Code</td>
    </tr>
    <tr>
        <td>provider</td>
        <td>string</td>
        <td>Device internet provicer name</td>
    </tr>
</table>

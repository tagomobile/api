Scans Type
-----------

<br/>

**Examples**

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

**Examples**

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
        <td>Statistics date</td>
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

**Examples**

```json
{
    barcodeId: 2032,
    barcodeType: "url",
    barcodeLabel: "magazine",
    barcodeContent: "http://google.com",
    folderName: "Default",
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

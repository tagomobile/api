Analytics
====

<br/>

General Statistics
------

For all barcodes:
* `GET /analytics` return scans statistics for all barcodes for all time
* `GET /analytics?fromDate={date}&toDate={date}` return scans statistics for all barcodes for selected date period

For specific barcode:
* `GET /analytics/{id}` return scans statistics for specific barcode by it id for all time
* `GET /analytics/{id}?fromDate={date}&toDate={date}` return scans statistics for specific barcode by it id for selected date period

For specific folder:
* `GET /analytics?folderId={id}` return scans statistics for specific folder by it id for all time
* `GET /analytics?folderId={id}?fromDate={date}&toDate={date}` return scans statistics for specific folder by it id for selected date period

Request optional parameters:

`fromDate` - Start date. Format: "YYYY-MM-DD" <br/>
`toDate` - End date. Format: "YYYY-MM-DD"

Response data type: [Scans](scans.md)

<br/>

**Statistics Examples**

For all barcodes:
  * http://testv2.tago.ca/api/analytics?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
  * http://testv2.tago.ca/api/analytics?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c&fromDate=2012-04-10&toDate=2012-10-01

For specific barcode: 
  * http://testv2.tago.ca/api/analytics/25043?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
  * http://testv2.tago.ca/api/analytics/25043?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c&fromDate=2012-04-10&toDate=2012-10-01

For specific folder: 
  * http://testv2.tago.ca/api/analytics?folderId=16771&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
  * http://testv2.tago.ca/api/analytics?folderId=16771&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c&fromDate=2012-04-10&toDate=2012-10-01

Response:

```
Status: 200 OK
```

```json
{
  "uniqueScans": 131,
  "totalScans": 858
}
```

<br/>

Daily Statistics
------

For all barcodes:
* `GET /analytics/daily?barcodeId={id}` return all scans statistics for specific barocde detailed by days.
* `GET /analytics?daily?barcodeId={id}fromDate={date}&toDate={date}` return scans statistics for all barcodes for selected date period

For specific barcode:
* `GET /analytics/{id}` return scans statistics for specific barcode by it id for all time
* `GET /analytics/{id}?fromDate={date}&toDate={date}` return scans statistics for specific barcode by it id for selected date period

For specific folder:
* `GET /analytics?folderId={id}` return scans statistics for specific folder by it id for all time
* `GET /analytics?folderId={id}?fromDate={date}&toDate={date}` return scans statistics for specific folder by it id for selected date period

**Statistics Examples**

* http://testv2.tago.ca/api/analytics/daily?barcodeId=31840&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c

Request optional parameters:

`fromDate` - Start date. Format: "YYYY-MM-DD" <br/>
`toDate` - End date. Format: "YYYY-MM-DD"

Response data type: [Scans](scans.md)

Response:

```
Status: 200 OK
```

```json
{
    "date": "2012-03-24T11:00:39-05:00",
    "uniqueScans": 723,
    "totalScans": 689
  }
```

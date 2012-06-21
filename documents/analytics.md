Analytics
====

<br/>

General Statistics
------

By all barcodes:
* `GET /analytics` return scans statistics for all barcodes for all time
* `GET /analytics?fromDate={date}&toDate={date}` return scans statistics for all barcodes for selected date period

By specific barcode:
* `GET /analytics/{id}` return scans statistics for specific barcode by it id for all time
* `GET /analytics/{id}?fromDate={date}&toDate={date}` return scans statistics for specific barcode by it id for selected date period

By specific folder:
* `GET /analytics?folderId={id}` return scans statistics for specific folder by it id for all time
* `GET /analytics?folderId={id}?fromDate={date}&toDate={date}` return scans statistics for specific folder by it id for selected date period

Request optional parameters:

`fromDate` - Start date. Format: "YYYY-MM-DD" <br/>
`toDate` - End date. Format: "YYYY-MM-DD"

Response data type: [Scans](scans.md)

**Example**

By all barcodes:
  * http://testv2.tago.ca/api/analytics?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
  * http://testv2.tago.ca/api/analytics?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c&fromDate=2012-04-10&toDate=2012-10-01

By specific barcode: 
  * http://testv2.tago.ca/api/analytics/25043?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
  * http://testv2.tago.ca/api/analytics/25043?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c&fromDate=2012-04-10&toDate=2012-10-01

By specific folder: 
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

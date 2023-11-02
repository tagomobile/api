Analytics
====

<br/>

General Statistics
------

For all barcodes:
* `GET /analytics/GetAllBarcodesStatistics?` return scans statistics for all barcodes for all time
* `GET /analytics/GetAllBarcodesStatistics?fromDate={date}toDate{date}` return scans statistics for all barcodes for selected date period

For specific barcode:
* `GET /analytics/GetBarcodeStatistics?id={id}` return scans statistics for specific barcode by it id for all time
* `GET /analytics/GetBarcodeStatistics?id={id}?fromDate={date}&toDate={date}` return scans statistics for specific barcode by it id for selected date period

For specific folder:
* `GET /analytics/GetFolderStatistics?folderId={id}` return scans statistics for specific folder by it id for all time
* `GET /analytics/GetFolderStatistics?folderId={id}?fromDate={date}&toDate={date}` return scans statistics for specific folder by it id for selected date period

Request optional parameters:

`fromDate` - Start date. Format: "YYYY-MM-DD" <br/>
`toDate` - End date. Format: "YYYY-MM-DD"

Response data type: [Scans](scans.md)

<br/>

**Statistics Examples**

For all barcodes:
  * http://tagomobile.com/api/v1/analytics/GetAllBarcodesStatistics?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
  * http://tagomobile.com/api/v1/analytics/GetAllBarcodesStatistics?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c&fromDate=2020-04-10&toDate=2020-10-01

For specific barcode: 
  * http://tagomobile.com/api/v1/analytics/GetBarcodeStatistics?id=25043&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
  * http://tagomobile.com/api/v1/analytics/25043?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c&fromDate=2020-04-10&toDate=2020-10-01

For specific folder: 
  * http://tagomobile.com/api/v1/analytics/GetFolderStatistics?folderId=16771&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
  * http://tagomobile.com/api/v1/analytics/GetFolderStatistics?folderId=16771&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c&fromDate=2020-04-10&toDate=2020-10-01

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

For specific barcode:

* `GET /analytics/daily/{id}` return all scans statistics detailed by days for specific barcode.
* `GET /analytics/daily/{id}?fromDate={date}&toDate={date}` return scans statistics detailed by days for specific barcode for selected date range. If selected single day (fromDate equals to toDate), than statistics by hours will be returned.

For specific folder:

* `GET /analytics/daily?folderId={id}` return all scans statistics detailed by days for specific folder.
* `GET /analytics/daily?folderId={id}&fromDate={date}&toDate={date}` return scans statistics detailed by days for specific folder for selected date range. If selected single day (fromDate equals to toDate), than statistics by hours will be returned.

**Statistics Examples**

For specific barcode:

* http://tagomobile.com/api/v1/analytics/daily/31840?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
* http://tagomobile.com/api/v1/analytics/daily/31840?fromDate=2020-04-17&toDate=2020-04-18&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c

For specific folder:
* http://tagomobile.com/api/v1/analytics/daily?folderId=29367&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
* http://tagomobile.com/api/v1/analytics/daily?folderId=29367&fromDate=2020-04-17&toDate=2020-04-18&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c


Request optional parameters:

`fromDate` - Start date. Format: "YYYY-MM-DD" <br/>
`toDate` - End date. Format: "YYYY-MM-DD"

Response data type: [DayScans](scans.md#dayScans)

Response:

```
Status: 200 OK
```

```json
[
 {
    "date": "2012-03-24T00:00:00-05:00",
    "uniqueScans": 723,
    "totalScans": 689
 }
]
```
<br />

Detailed Statistics
------

For specific barcode:

* `GET /analytics/scans/{id}` return list of all scans for specific barcode.
* `GET /analytics/scans/{id}?fromDate={date}&toDate={date}` return list of scans for specific barcode for selected date range.

For specific folder:

* `GET /analytics/scans?folderId={id}` return list of all scans for specific folder.
* `GET /analytics/scans?folderId={id}&fromDate={date}&toDate={date}` return list of scans for specific folder for selected date range.

**Statistics Examples**

For specific barcode:

* http://tagomobile.com/api/v1/analytics/scans/31840?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
* http://tagomobile.com/api/v1/analytics/scans/31840?fromDate=2020-04-17&toDate=2020-04-18&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c

For specific folder:
* http://tagomobile.com/api/v1/analytics/scans?folderId=29367&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c
* http://tagomobile.com/api/v1/analytics/scans?folderId=29367&fromDate=2020-04-17&toDate=2020-04-18&ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c


Request optional parameters:

`fromDate` - Start date. Format: "YYYY-MM-DD" <br/>
`toDate` - End date. Format: "YYYY-MM-DD"

Response data type: [ScanDetails](scans.md#scanDetails)

Response:

```
Status: 200 OK
```

```json
[
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
    "provider": "ProviderInc.",
 }
]
```



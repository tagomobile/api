Analytics
====

<br/>

General Analytics
------

* `GET /analytics` return scans statistics for all barcodes in account for all time

Data type: [Scans](scans.md)

**Example**

  * http://testv2.tago.ca/api/analytics?ApiKey=df2c3de1-bdbd-45c2-803e-84b52d335d9c

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

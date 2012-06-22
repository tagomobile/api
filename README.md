Tagomobile API
====================

This is the API for TAGO (tagomobile.com). 
Tago API is a RESTful style API that uses JSON for serialization and authentication token for authentication.

Additionally our API enpoint is fully supporting [OData](http://odata.org) protocol. OData is an extensiton for RESTful API protocol, which adds a lot of useful functionality to it. One of the main feature is that OData allows RPC-style operations to be made from major programing languages. You can read more about OData stanart at http://odata.org. Some of the libraries supports OData client-side code generation is .NET, PHP, Ruby, Objective C, Android and more.

Full list of clients supported OData clients:
http://www.odata.org/libraries


Authentication
----------------

In order to access our API, you need to have TAGO account. From your account you will be able to get API key that you will use with every request to the Tagomobile API. To obtain API key you need to login to TAGO account, go to Account page, click button "Generate API Key" and copy generated key.

You can sign up for TAGO account by following link: [http://tagomobile.com/signup](http://tagomobile.com/pricing)

All API requests require authentication. You can pass API key via query arguments: 

`GET /barcodes?apiKey=apiKey`

Also you can pass API key via X-Auth or Authorization HTTP headers. 
Read the [Authentication Guide](https://github.com/tagomobile/api/blob/master/documents/authentication.md) for more info.


Data formats
----------------

Tagomobile API media type determines how API serializes and deserializes the HTTP message body. We support XML (`application/xml`), JSON (`application/json`), and form-urlencoded data (`application/x-www-form-urlencoded`). You must supply `Content-Type` and `Accept` header on all requests.

If query to API does not specify media type, we treat data as **JSON by default**.


Making a request
----------------

All URLs start with `http://api.tagomobile.com/v1/` The path is prefixed with the API version. If we change the API in backward-incompatible ways, we will increase the version marker and maintain stable support for the old URLs.

To make a request for all barcodes on your account, you need to append the barcodes index path to the base url to form URL lool like https://api.tagomobile.com/v1/barcodes. In curl, that looks like:

```shell
curl http://api.tagomobile.com/v1/barcodes
  -H 'X-ApiKey: ApiKey=apiKey'
  -d '{"type": "url", "folderName": "Default","isTrackable": true, "Url": {"Url": "http://google.com"}}'
  -X POST
```

Check out this tutorial to see how make calls to our RESTfull API from Javascript, C#, PHP, Ryby, Python and Java:

[How to make API calls from different programming languages]()

Response example
-------------------

`GET /barcodes` will return all barcodes.

```shell
Status: 200 OK
Location: http://api.tagomobile.com/v1/barcodes
```

```json
[
  {
    "id": 124542,
    "type": "URL",
    "folder_id": "231",
    "trackable": "true",
    "short_link": "http://tago.ca/abc",
    "label": "magazine"
    "url": "http://www.youtube.com/watch?v=HkSDN1TXjvk"
  }
]
```

API reference
-----------------
General
* [Authentication](https://github.com/tagomobile/api/blob/master/documents/authentication.md)

Methods
* [Generate](api/blob/master/documents/generate.md)
* [Barcodes](api/blob/master/documents/barcodes.md)
* [Folders](api/blob/master/documents/folders.md)
* [Analytics](api/blob/master/documents/analytics.md)

Data structures
* [Barcode](api/blob/master/documents/barcode.md)
* [BarcodeInfo](api/blob/master/documents/barcodeInfo.md)
* [Folder] (api/blob/master/documents/folder.md)
* [Scans] (api/blob/master/documents/scans.md)
* [DayScans] (api/blob/master/documents/scans.md#dayScans)
* [ScansDetails] (api/blob/master/documents/scans.md#scanDetails)

Handling errors
---------------

If TAGO is having trouble, you might see a 5xx error. `500` means that the app is entirely down, but you might also see `502 Bad Gateway`, `503 Service Unavailable`, or `504 Gateway Timeout`. It's your responsibility in all of these cases to retry your request later. 
In case if particular API method failed, you will receive response with error status together with additional descriptin of the error.


OData Queries
---------------

Because Tagomobile API is supported OData protocol, you can take full advantage of some usefull OData features to query data from API. For example, you can apply following operations to collections of data, returned from API: pagination, filtering, sorting, top records and other.

Below is example of OData parameters applied to URL requests to do some useful operations.

* Pagination. Get 20 barcodes begingin from 41:
```GET /barcodes?$skip=40&$top=20```

* Sorting. Get barcodes sorted by created date:
```GET /barcodes?$orderby=created_date```

* Filtering. Get onlty trackable barcodes:
```GET /barcodes?$filter=trackable eq 'true'```

* Filtering. Get all URL barcodes pointed to twitter.com domain:
```GET /barcodes?$filter=substringof('twitter.com', url)```


More information on URI conventions can be found here: [OData: URI Conventions](http://www.odata.org/documentation/uri-conventions)

Change Policy
----------------

We reserves the right to add new attributes and resources to the API without advance notice. Breaking changes such as removing or renaming an attribute, may happen on an existing version of the API with two weeks notice. Major structural changes will only happen within the context of a version update.


Help us make it better
----------------------

Please tell us how we can make the API better. If you have a specific feature request or if you found a bug, please email us at [support@tago.ca](mailto:support@tago.ca).

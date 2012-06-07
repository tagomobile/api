Tagomobile API
====================

This is the API for TAGO (tagomobile.com). 
Tago API is a REST-style API that uses JSON for serialization and authentication token for authentication.

Additionally our API enpoint is fully supporting [OData](http://odata.org) protocol. OData is a RESTful API protocol, which adds a lot of useful functionality on top of it. One of the main feature is that OData allows RPC-style operations to be made from major programing languages. You can read more about OData stanart at http://odata.org. Some of the libraries supports OData client-side code generation is .NET, PHP, Ruby, Objective C, Android and more.

Full list of clients supported OData clients:
http://www.odata.org/libraries


Change Policy
----------------

We reserves the right to add new attributes and resources to the API without advance notice. Breaking changes such as removing or renaming an attribute, may happen on an existing version of the API with two weeks notice. Major structural changes will only happen within the context of a version update.


Authentication
----------------

Tagomobile API support authorisationg using API key. This key can be found in your TAGO account under Account page.

Read the [authentication guide](#) to get started.


Data formats
----------------

Tagomobile API media type determines how API serializes and deserializes the HTTP message body. We support XML (`application/xml`), JSON (`application/json`), and form-urlencoded data (`application/x-www-form-urlencoded`).  You must supply Content-Type and Accept header on all requests.

If query to API does not specify media type, we tread data as **JSON by default**.


Making a request
----------------

All URLs start with `http://api.tagomobile.com/v1/` The path is prefixed with the API version. If we change the API in backward-incompatible ways, we will increase the version marker and maintain stable support for the old URLs.

To make a request for all barcodes on your account, you need to append the barcodes index path to the base url to form URL lool like https://api.tagomobile.com/v1/barcodes. In curl, that looks like:

```shell
curl http://api.tagomobile.com/v1/barcodes
  -H 'Authorize: ApiKey=vbs76t8sdv'
  -H 'Accept: application/json'
```

Response example
-------------------

`GET /barcodes` will return all barcodes.

```shell
Status: 201 Created
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


Handling errors
---------------

If TAGO is having trouble, you might see a 5xx error. `500` means that the app is entirely down, but you might also see `502 Bad Gateway`, `503 Service Unavailable`, or `504 Gateway Timeout`. It's your responsibility in all of these cases to retry your request later. 
In case if particular API method failed, you will receive response with error status together with additional descriptin of the error.


OData Queries
---------------

Because Tagomobile API is supported OData protocol, you can take full advantage of some usefull OData features to query data from API. For example, you can apply following operations to collections of data, returned from API: pagination, filtering, sorting, top records and other.

Below is example of OData parameters applied to URL requests to do some useful operations.

Pagination. Get 10 barcodes begingin from 41:

```GET /barcodes?$skip=40&$top=20```


More information on URI conventions can be found here: [OData: URI Conventions](http://www.odata.org/documentation/uri-conventions)

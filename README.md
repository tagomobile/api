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


Making a request
----------------

All URLs start with `http://api.tagomobile.com/v1/` The path is prefixed with the API version. If we change the API in backward-incompatible ways, we will increase the version marker and maintain stable support for the old URLs.

To make a request for all barcodes on your account, you need to append the barcodes index path to the base url to form URL lool like https://api.tagomobile.com/v1/barcodes. In curl, that looks like:

```shell
curl https://api.tagomobile.com/v1/barcodes \
-H 'Authorize: ApiKey=vbs76t8sdv' \
-H 'Accept: application/json' \
```

Tagomobile API media type determines how API serializes and deserializes the HTTP message body. We support XML, JSON, and form-urlencoded data.

JSON `-H 'Accept: application/json'`
XML `'Accept: application/xml'`
form-urlencoded data `'Accept: application/x-www-form-urlencoded'`

If query to API does not specify media type, we tread data serialized as **JSON by default**.

Response format
----------------
If query to API doesn not contain Accept or Content-Type headers it is JSON by default.
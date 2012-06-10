Authentication Guide
====================

In order to access our API, you need to have TAGO account. Tagomobile support authenticatino via API key. 
From your account you will be able to get your API key that you will use with every request to the Tagomobile API. To obtain API key you need to login to TAGO account, go to Account page, click button "Generate API Key" and copy generated key.

You can sign up for TAGO account by following link: [http://tagomobile.com/signup](http://tagomobile.com/pricing)

All API requests require authentication. 
There is three options you can pass API key with the reuest.

Query arguments (default)
----------------

`GET /barcodes?apiKey=apiKey`


'Authorization ' HTTP header
----------------

```shell
curl http://api.tagomobile.com/v1/barcodes
  -H 'Authorize: ApiKey=apiKey'
```


'X-ApiKey ' HTTP header
----------------

```shell
curl http://api.tagomobile.com/v1/barcodes
  -H 'X-ApiKey: ApiKey=apiKey'
```
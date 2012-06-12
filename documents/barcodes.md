Barcodes
==========

List of methods
-----------------

Fetching  

* `GET /barcodes` return list of all barcodes.
* `GET /barcodes?folder={id}` return all barcodes from speicif folder by folder id.
* `GET /barcodes?folderName={id}` return all barcodes from speicif folder by folder name.
* `GET /barcodes$skip={skip}&$top={top}` return custom range of barcodes.
* `GET /barcodes/{id}` return specific barcode content.

Management
* `PUT /barcodes/{id}` update barcode content.
* `DELETE /barcodes/{id}` delete barcode.

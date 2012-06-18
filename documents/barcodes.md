Barcodes
==========

Creating Barocdes
----
* `POST /barcodes?type={type}&...` add barcode.
<br />

QR Code Image Generating
----
Please note, that barcode firts should be created and than QR Code image can be donloaded via separate call

* `GET /barcodes/{id}/Image` return QR Code image by barcode id. Image size - M, Error Correction Level - M, format - png
* `GET /barcodes/{id}/Image?forat=eps&size=M&errorCorrection=M` return QR Code image by barcode id with custom image settigns.
<br />

Getting Barcodes
----
* `GET /barcodes/{id}` return barcode content by it id.
<br />

Listing Barcodes
----

* `GET /barcodes` return list of all barcodes.
* `GET /barcodes?folder={id}` return all barcodes from specific folder by folder id.
* `GET /barcodes?folderName={id}` return all barcodes from speicif folder by folder name.
* `GET /barcodes$skip={skip}&$top={top}` return custom range of barcodes.
<br />

Updating Barcodes
----
* `PUT /barcodes/{id}` update barcode content.
<br />

Deleting barocdes
----
* `DELETE /barcodes/{id}` delete barcode.
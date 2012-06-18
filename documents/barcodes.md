Barcodes
==========


Listing Barcodes

* `GET /barcodes` return list of all barcodes.
* `GET /barcodes?folder={id}` return all barcodes from specific folder by folder id.
* `GET /barcodes?folderName={id}` return all barcodes from speicif folder by folder name.
* `GET /barcodes$skip={skip}&$top={top}` return custom range of barcodes.

QR Code Image Generating
* `GET /barcodes/{id}/Image` return QR Code image by barcode id. Image size - M, Error Correction Level - M, format - png
* `GET /barcodes/{id}/Image?forat=eps&size=M&errorCorrection=M` return QR Code image by barcode id with custom image settigns.


Getting Barcodes
* `GET /barcodes/{id}` return barcode content by it id.


Creating Barocdes
* `POST /barcodes?type={type}&...` add barcode.

Updating Barcodes
* `PUT /barcodes/{id}` update barcode content.

Deleting barocdes
* `DELETE /barcodes/{id}` delete barcode.


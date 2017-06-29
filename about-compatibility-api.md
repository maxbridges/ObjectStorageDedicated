---
copyright:
  years: 2017
lastupdated: "2017-02-23"
---
# About the Compatibility API

# API Reference

The IBM Cloud Object Storage implementation of the S3 API supports the most commonly used subset of Amazon S3 API operations. A complete list of supported operations can be found in the [API overview](docs/services/ObjectStorageDedicated/about-compatibility-api.html).

This reference documentation is being continously improved. If you have technical questions about using the API in your application, please post them on StackOverflow using both `ibm-bluemix` and `object-storage` tags and we will do our best to answer promptly, and then improve this documentation thanks to your feedback.

The following tables describe the complete set of supported operations when using the S3 API to access IBM Cloud Object Storage.  For details on using the operations, including examples, see [the API reference page](docs/services/ObjectStorageDedicated/api-reference.html).

## Operations on the account

The only operation that is performed directly at the account level is to get a list of buckets owned by that account. Accounts are limited to 100 buckets.

| Account operation | Note |
|:----|:---|
| `GET` account | Used to retrieve a list of all buckets belonging to an account. |
{:.opstable}

## Operations on buckets

These operations create, destroy, get information about, and control behavior of buckets.

| Bucket operation | Note |
|:----|:---|
| `DELETE` Bucket | Deletes an empty bucket.   |
| `DELETE` Bucket CORS | Deletes any cross-origin resource sharing configuration set on a bucket. |
| `GET` Bucket | Lists objects contained in a bucket.  Limited to listing 1,000 objects at once. |
| `GET` Bucket ACL |Retrieves the access control list for a bucket.|
| `GET` Bucket CORS |Retrieves any cross-origin resource sharing configuration set on a bucket.|
| `HEAD` Bucket | Retrieves a bucket's headers. |
| `GET` multipart uploads | Lists multipart uploads that have not completed or been canceled. |
| `PUT` Bucket | Buckets have naming restrictions. Accounts are limited to 100 buckets. |
| `PUT` Bucket ACL | Creates an access control list for a bucket. |
| `PUT` Bucket CORS | Creates a cross-origin resource sharing configuration for a bucket.|

Note that the 'version 2' method of listing objects within a bucket is not supported, and the 'version 1' syntax is needed.

## Operations on objects

These operations create, destroy, get information about, and control behavior of objects.

| Object operation | Note |
| :---------------| :------|
| `DELETE` Object | Deletes an object from a bucket.
| `DELETE` Multiple Objects  | Deletes multiple objects from a bucket.
| `GET` Object | Retrieves an object from a bucket.
| `GET` Object ACL | Retrieves an object's access control list.
| `HEAD` Object | Retrieves an object's headers.
| `OPTIONS` Object | Checks CORS configuration to see if a specific request can be sent.
| `POST` Object | Adds an object to a bucket using HTML forms.
| `PUT` Object | Adds an object to a bucket.
| `PUT` Object ACL | Creates an access control list for an object. 
| `PUT` Object (Copy) | Creates a copy of an object. |
| Initiate Multipart Upload | Creates an upload ID for a given set of parts to be uploaded.
| Upload Part | Uploads a part of an object associated with an upload ID.
| Upload Part (Copy) | Uploads a part of an existing object associated with an upload ID.
| Complete Multipart Upload | Assembles an object from parts associated with an upload ID.
| Abort Multipart Upload | Aborts upload and deletes outstanding parts associated with an upload ID.
| List Parts | Returns a list of parts associated with an upload ID


Some additional operations, such as tagging and versioning, are supported in private cloud implementations of IBM COS, but not in public or dedicated clouds at this time. More information custom object storage solutions can be found at [ibm.com](https://www.ibm.com/cloud-computing/products/storage/object-storage/cloud/).


---

copyright:
  years: 2017
lastupdated: "2017-02-23"

---

# FAQ

## API Questions

**Are COS bucket names case sensitive?**

Bucket names are required to be DNS addressable, and thus not case sensitive.

**What is the maximum number of characters that can be used in an Object name?**

1024

## Offering Questions


**Is there a 100-bucket limit to an account?  What happens if we need more?**

Yes, 100 is the current bucket limit.  Generally, prefixes are a better way to group together objects in a bucket, unless the data needs to be in a different region or storage class.  For example, to group patient records, you would use one prefix per patient. If this is not a workable solution, contact customer support.


## Performance Questions

**Does data consistency in COS come with a performance impact?**

Consistency with any distributed system comes with a cost, but the efficiency of the IBM COS dispersed storage system is higher, and overhead is lower compared to systems with multiple synchronous copies.  

**Aren't there performance implications if my application needs to manipulate large objects?**

For performance optimization, objects can be uploaded and downloaded in multiple parts, in parallel. 

 
## Encryption Questions

**Does IBM COS provide encryption at rest and in motion?**

Yes.  Data at rest is encrypted with automatic provider side Advanced Encryption Standard (AES) 256-bit encryption and Secure Hash Algorithm (SHA)-256 hash. Data in motion is secured by using built-in carrier grade Transport Layer Security/Secure Sockets Layer (TLS/SSL) or SNMPv3 with AES encryption.

**What is the typical encryption overhead if a customer wants to encrypt their data?**

Server side encryption is always on for customer data.  Compared to the hashing required in S3 authentication and the erasure coding, encryption is not a big part of the processing cost of COS.

**Does IBM COS encrypt all data?**  

Yes, IBM COS encrypts all data.  

**Does IBM COS have FIPS 140-2 compliance for the encryption algorithms?**

The algorithms are FIPS 140-2 ready but testing / certification is still pending.

**Will client-key encryption be supported?**

Yes, client-key encryption will be supported in 2017.  

## General questions

**How many objects can fit in a single bucket?**

There is no practical limit to the number of objects in a single bucket.

**Can I nest buckets inside one another?**

No, buckets can not be nested.  If a greater level of organization is required within a bucket, the use of prefixes is supported: `{endpoint}/{bucket-name}/{object-prefix}/{object-name}`.  Note that the object's key remains the combination `{object-prefix}/{object-name}`.


**What is the best way to structure your data using Object storage such that you can 'look' at it and find what you are looking for?  Without a directory structure, having 1000s of files at one level seems hard to view.**

You can use metadata associated with each object to find the objects you are looking for. The biggest advantage of object storage is the metadata associated with each object. Each object can have up to 4 MB of metadata in IBM COS.  When offloaded to a database, metadata provides excellent search capabilities.  A large number of (key, value) pairs can be stored in 4 MB.  You can also use Prefix searching to find what you are looking for. For example, if you use buckets to separate each customer data, you can use prefixes within buckets for organization. For example:  /bucket1/folder/object where 'folder/' is the prefix.

**Can you confirm that IBM COS is ‘immediately consistent’, as opposed to ‘eventually consistent’?** 

COS is ‘immediately consistent’ for data and ‘eventually consistent’ for usage accounting.


**Can IBM COS partition the data automatically for me like HDFS, so I can read the partitions in parallel, e.g. with Spark?**

IBM COS supports a ranged GET on the object, so an application can do a distributed striped read type operation.  Doing the striping would be on the application to manage.  


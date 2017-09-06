---

copyright:
  years: 2017
lastupdated: "2017-02-23"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# About

{{site.data.keyword.cosdimshort}} provides you a fully provisioned account, based on an implementation of the S3 API, to manage your data.
{: shortdesc}


## How the service works

With {{site.data.keyword.cosdimshort}}, your data is stored in an isolated, single-tenant cloud environment hosted in {{site.data.keyword.BluSoftlayer}}. Provider side encryption is provided. Your data is secured at rest and in flight.


Both admins and developers can store and access objects as shown in the following diagram:

<dl>
  <dt> {{site.data.keyword.Bluemix_notm}} app </dt>
    <dd> You can bind the {{site.data.keyword.cosdimshort}} service to a {{site.data.keyword.Bluemix_notm}} app.  </dd>
  <dt> S3 API </dt>
    <dd> The service uses an implementation of the S3 API to manage your storage.  </dd>
  <dt> Accesser appliance </dt>
    <dd> To maintain data integrity and availability, data is sliced, balanced and then dispersed to storage nodes.  </dd>
  <dt> Slicestor appliances </dt>
    <dd> The service provides limitless data storage across multiple regions. By separating your data, you never lose access. Even if an entire site goes down, data can be retrieved from a subset of slices. </dd>
</dl>


![How {{site.data.keyword.objectstorageshort}} works as written above, shown in a diagram.](/images/OS_dedicated_howitworks.png)
<caption> Figure 1. How {{site.data.keyword.Bluemix_notm}} Dedicated {{site.data.keyword.objectstorageshort}} works </caption>

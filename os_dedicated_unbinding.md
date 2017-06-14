---

copyright:
  years: 2017
lastupdated: "2017-02-23"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Unbinding and deprovisioning {: #dedicated-unbinding}

You can unbind or deprovision an instance of  {{site.data.keyword.cosdimshort}} that you no longer need.
{: shortdesc}


## Unbinding your instance

If you no longer have a need for {{site.data.keyword.cosdimshort}} in your Cloud Foundry app, but you want to maintain your saved data, you can unbind your instance of the service from your app.

**Attention:** If you unbind an {{site.data.keyword.cosdimshort}} instance from a {{site.data.keyword.Bluemix_notm}} application, or delete the service key, all of your credentials for that instance are deleted and cannot be restored.

1. To see the services bound to your app, click the connections tab in your Cloud Foundry application.
2. Locate the service you that you want to unbind and click the menu button on the service tile.
3. Select **Unbind service**.
4. Clear the **Delete service instance** box and click **OK**.
5. Click **Restage** for your change to take effect.



## Deprovisioning your instance

If you no longer have a need for {{site.data.keyword.cosdimshort}} you can deprovision your service instance.

1. From your service instance, delete all buckets and objects. You can use the multi-delete option.
2. Select the **Delete service** option and click **Delete** when prompted to verify.

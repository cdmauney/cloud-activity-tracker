---

copyright:
  years: 2016, 2018

lastupdated: "2018-07-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}


# CF events
{: #cf}

Use the {{site.data.keyword.cloudaccesstrailfull}} service to track interaction with core platform services in the {{site.data.keyword.Bluemix}}. 
{:shortdesc}


The following list outlines the different core platform tasks that send events to the {{site.data.keyword.cloudaccesstrailshort}} service: 

* Provisioning a service, removing a service, and changing the name of a service.
* Granting, updating, and revoking Cloud Foundry roles to users in the account.
* Creating a platform API key, renaming a platform key, and deleting a platform key.


## Events generated when interacting with Catalog services
{: #catalog}

When you provision a service, remove a service, and change the name of a service, an event is generated and sent to the space domain in {{site.data.keyword.cloudaccesstrailshort}} that is associated with the Cloud Foundry (CF) space where the service is available in the account. 

For example, you provision service A in space B in the us-south region. An event is generated. To see the event, you must provision the {{site.data.keyword.cloudaccesstrailshort}} service in us-south, in the same space where you have provisioned the service. Then, you can see the event through the the {{site.data.keyword.cloudaccesstrailshort}} service UI.

The following table lists the catalog actions that generate events:

<table>
  <caption>Catalog actions</caption>
  <tr>
    <th>Action</th>
	  <th>Description</th>
  <tr>
  <tr>
    <td>`audit.service_instance.create`</td>
	<td>An event is created when you provision a service in a CF space.</td>
  </tr>
  <tr>
    <td>`audit.service_instance.update`</td>
	<td>An event is created when you change the name of a service that is available in a CF space.</td>
  </tr>
  <tr>
    <td>`audit.service_instance.delete`</td>
	<td>An event is created when you remove a service from a CF space in the account.</td>
  </tr>
</table>


 	

## Events generated when managing CF roles in the account
{: #cfroles} 

When you grant or revoke (delete) a CF role to a user in the account, an event is generated and sent to the space domain in {{site.data.keyword.cloudaccesstrailshort}} that is associated with the CF space where the role is either granted or revoked. 

For example, you grant user A in space B in the us-south region a *manager* role. An event is generated. To see the event, you must provision the {{site.data.keyword.cloudaccesstrailshort}} service in us-south, in the same space where you are managing the user's CF permissions. Then, you can see the event through the {{site.data.keyword.cloudaccesstrailshort}} service UI.


The following table lists the actions that generate {{site.data.keyword.cloudaccesstrailshort}} events when you manage a user's CF roles:

<table>
  <caption>Actions managing CF roles</caption>
  <tr>
    <th>Action</th>
	<th>Description</th>
  <tr>
  <tr>
    <td>`audit.user.space_manager_add`</td>
	<td>Grant a user the *manager* role in a CF space.</td>
  </tr>
  <tr>
    <td>`audit.user.space_developer_add`</td>
	<td>Grant a user the *developer* role in a CF space.</td>
  </tr>
  <tr>
    <td>`audit.user.space_auditor_add`</td>
	<td>Grant a user the *audit* role in a CF space.</td>
  </tr>
  <tr>
    <td>`audit.user.space_manager_remove`</td>
	<td>Delete the user's *manager* role in a CF space.</td>
  </tr>
  <tr>
    <td>`audit.user.space_developer_remove`</td>
	<td>Delete the user's *developer* role in a CF space.</td>
  </tr>
  <tr>
    <td>`audit.user.space_auditor_remove`</td>
	<td>Delete the user's *audit* role in a CF space.</td>
  </tr>
</table>






	
 	
 	
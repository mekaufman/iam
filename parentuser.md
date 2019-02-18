---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Updating a user's parent user
{: #update-parent}

If you have the correct access, you can update the parent for a user. Updating the parent user affects how a user sees other users in the account when the user list visibility setting is set to restricted. Users see only other users for which they are a parent and any other users invited by those descendants of the parent user.
{:shortdesc}

See [user list visibility setting](/docs/iam?topic=iam-userlistview#userlistview) for more details about the setting. 

If you have the following access, you can update the parent for another user:

* An IAM policy with Editor or higher role on the User management service.
* You are an ancestor in the classic infrastructure hierarchy for the user and you have the Manage user classic infrastructure permission assigned


To update a user's parent, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.  
2. Select a user name from the list.
3. From the User details page, select a new parent user from the **Parent** menu.
4. Click **Apply**.

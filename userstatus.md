---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# User status
{: #user_status}

When a user is invited to the account, depending on the type of user they are and their status of accepting the invite, they are assigned a status that is displayed on the **User details** page for a particular user. 
{:shortdesc}

| User State | Description |
|:-----------|:------------|
| Active | The user accepted the invitation and has the assigned access to work within the account. | 
| Disabled classic infrastructure | The account owner or a user with sufficient permissions can set another user as disabled so that the user can no longer access classic infrastructure resources. The user can continue to log in to the console and access platform resources. |
| VPN-only | A user that is created in the account, but is restricted to VPN access only for devices. This type of user doesn't have access to log in to the console.| 
| Processing | A rarely viewed state in which the user is added to an invite, but the invite has not been sent and the system has created the first instance of the user. |
| Pending | A state in which a user has been invited but has not accepted the invitation or joined the account by creating an {{site.data.keyword.Bluemix_notm}} account. |
{: caption="Table 1. User status" caption-side="top"} 

For information about changing a user's status, see [Updating a user's status](/docs/iam?topic=iam-status#status).


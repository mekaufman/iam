---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: IBM Cloud IAM, user identities, service ID, policies, access management, roles, actions

subcollection: iam


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IAM concepts
{: #iamconcepts}

## Identity
{: #identity}

The identity concept in {{site.data.keyword.Bluemix_notm}} IAM consists of the following components:

<dl>
<dt>User identities</dt>
<dd>All users are identified by their IBMid.</dd>
<dt>Service and app identities</dt>
<dd>Service IDs are the Cloud IAM feature that is used to provide a separate identity for services and applications. You can create a service ID to be used by an application that needs access to your {{site.data.keyword.Bluemix_notm}} services so that individual user credentials do not have to be used.</dd>
<dt>API keys</dt>
<dd>{{site.data.keyword.cloud_notm}} API keys are available through Cloud IAM for you to use to authenticate by using API or CLI as a user or service ID. These API keys are provided through Cloud IAM and therefore cannot be used generally to authenticate with IBMid outside of IBM Cloud. A user can also have a single classic infrastructure API key that can be used to access classic infrastructure APIs; however, this is not required as you can use {{site.data.keyword.cloud_notm}} API keys to access the same APIs. </dd>
<dt>Resources</dt>
<dd>{{site.data.keyword.Bluemix_notm}} resources are identified by their cloud resource names (CRN). For more information, see [Cloud Resource Names](/docs/overview?topic=overview-crn#crn).</dd>
</dl>

## Access management
{: #am}

The concept of access management in {{site.data.keyword.Bluemix_notm}} consists of a few interrelated components, including users, resources, policies, roles, actions, and the Cloud IAM control system, which allow users to take actions on resources within an account.

You can review the following list to learn more about these Cloud IAM components:

<dl>
<dt>Users</dt>
<dd>All users within an account are identified by their IBMids. Users can be invited to the account and given access to resources. Access can be assigned to individual resources, down to the instance level, or to a set of resources that are organized in an account resource group.</dd>
<dt>Access group</dt>
<dd>A group of users and service IDs can be created by the account owner so that the same access can be assigned to all entities within the group with a single policy.</dd>
<dt>Resources</dt>
<dd>Account resources are the provisioned service offerings that are selected from the catalog or finer-grained resources within a service instance.</dd>
<dt>Policies</dt>
<dd>Policies are how users, service IDs, and access groups in the account are given permission to access account resources. Policies include a subject, target, and role. The subject is the user, service ID, or access group that you are providing access. The target of the policy is the resource to which you want to provide access. And, the roles are the way to define the level of access or allowed actions on the target of the policy. There are different types of policies that allow access to account resources: a resource group policy, a resource instance policy, an account-wide policy for access to all Identity and Access enabled services, and a policy on all or one account management services. Depending on your selections, custom configuration options such as defining access down to resources in a specific region or defining access to the granular level of a service-specific resource within an instance might be available.</dd>
<dt>Roles</dt>
<dd>Cloud IAM access roles allow a user to complete specific tasks on the resource that is defined in the policy. There are two types of access roles: platform management and service access. Platform management roles define allowable actions for managing resources at the platform level such as user access and creation of service instances, for example. Platform roles also apply to actions that can be taken within the context of account management services such as inviting and removing users, managing access groups, managing service IDs, and private catalog offerings. And, service access roles define allowable actions within the context of using the service such as calling service APIs. These roles are customized based on the service that is selected within the policy.</dd>
<dt>Actions</dt>
<dd>Actions are mapped to the Cloud IAM roles to enable users to perform only specific tasks when they are assigned the different roles. Allowable actions for each role might change based on the service that is being accessed because each service defines how that role maps to the use of the service. </dd>
<dt>Access management system</dt>
<dd>The Cloud IAM control system allows or denies actions by users within the context of a service based on the assigned policy. When a user tries to complete a specific action, the control system uses the attributes that are defined in the policy to determine whether the user has permission to perform that task.</dd>
</dl>

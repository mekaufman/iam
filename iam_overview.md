---

copyright:

  years: 2017, 2019

lastupdated: "2019-07-25"

keywords: user identities, service ID, policies, access management, roles, actions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:external: target="_blank" .external}

# IAM concepts
{: #iamconcepts}

Two major concepts stand out when you want to learn about {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM): identity and access management. Additionally, you can learn about access groups, resource groups, users, roles, access policies, and more.
{: shortdesc}

## Identity
{: #identity}

The identity concept in {{site.data.keyword.Bluemix_notm}} IAM consists of user identities, service and app identities, API keys, and resources. Users are identified by their IBMid or SoftLayer account ID. Service IDs are a second type of identity that is used in an account. Service IDs are the Cloud IAM feature that is used to provide a separate identity for services and applications. You can create a service ID to be used by an application that needs access to your {{site.data.keyword.Bluemix_notm}} services so that individual user credentials do not have to be used.

To authenticate with an API or CLI as a user or service ID, {{site.data.keyword.cloud_notm}} API keys can be used. These API keys are provided through Cloud IAM and therefore cannot be used generally to authenticate with IBMid outside of IBM Cloud. A user can also have a single classic infrastructure API key that can be used to access classic infrastructure APIs; however, this is not required as you can use {{site.data.keyword.cloud_notm}} API keys to access the same APIs.

The final piece of the identity concept in IAM is {{site.data.keyword.Bluemix_notm}} resources, which are identified by their cloud resource names (CRN). For more information, see [Cloud Resource Names](/docs/overview?topic=overview-crn#crn).

## Access management
{: #am}

The concept of access management in {{site.data.keyword.Bluemix_notm}} consists of a few interrelated components, including users, resources, policies, roles, actions, and the {{site.data.keyword.Bluemix_notm}} IAM control system, which allow users to take actions on resources within an account.

{{site.data.keyword.Bluemix_notm}} IAM follows an [eventually consistent](https://en.wikipedia.org/wiki/Eventual_consistency){: external} pattern that is common to many cloud-native services, which allows IAM to remain highly available and performant across multiple global regions. Changes that are made to IAM access policies, authorizations, service IDs, API keys, access groups, resource groups, users, or any other access controls are recorded and propagated across all IAM components and IAM-enabled services worldwide. Access changes might not take effect until the propagation process is complete.

### Users
{: #iam-users}

All users within an account are identified by their IBMids of their SoftLayer account IDs. Users can be invited to the account and given access to resources. Access policies start with the subject that is often a user in your account. Access can be assigned to account management services, individual resources down to the instance level, or to a set of resources that are organized in an account resource group.


### Access groups
{: #access-groups-iam}

A group of users and service IDs can be created by so that the same access can be assigned to all entities within the group with one or more policies. By using access groups, you can streamline the access assignment process so that you can manage a smaller amount of policies and reduce the number of policies in an account, which increases performance. After your groups are set up, you can start assigning policies by selecting an access group as the subject of the policy. For more information, see [Setting up access groups](/docs/iam?topic=iam-groups).

### Resources
{: #resources-access-management}

Account resources are the provisioned service offerings that are selected from the catalog or finer-grained resources within a service instance. These resources are added to a resource group when they are created from the catalog. IAM access management enables fine-grained access, which means that a policy can be set on a wider scale, to all resources in a resource group, for example, or to a specific resource type like a {{site.data.keyword.cos_full_notm}} bucket within a specific instance.


### Access policies
{: #access-policies-concept}

Access policies are how users, service IDs, and access groups in the account are given permission to access account resources. Policies include a subject, target, and role. The subject is the user, service ID, or access group that you are providing access. The target of the policy is the resource to which you want to provide access. And, the roles are the way to define the level of access or allowed actions on the target of the policy. There are different types of policies that allow access to account resources: a resource group policy, a resource instance policy, an account-wide policy for access to all Identity and Access enabled services, and a policy on all or one account management services. Depending on your selections, custom configuration options such as defining access down to resources in a specific region or defining access to the granular level of a service-specific resource within an instance might be available.

### Roles
{: #iam-roles-concept}

Cloud IAM access roles allow a user to complete specific tasks on the resource that is defined in the policy. There are two types of access roles: platform management and service access. 

Platform management roles define allowable actions for managing resources at the platform level such as user access and creation of service instances. Platform roles also apply to actions that can be taken within the context of account management services such as inviting and removing users, managing access groups, managing service IDs, and private catalog offerings. 

Service access roles define allowable actions within the context of using the service such as calling service APIs. These roles are customized based on the service that is selected within the policy.

### Actions
{: #iam-roles-actions}

Actions are mapped to the Cloud IAM roles to enable users to perform only specific tasks when they are assigned the different roles. Allowable actions for each role might change based on the service that is being accessed because each service defines how that role maps to the use of the service.

### Access management system
{: #access-management-system}

The Cloud IAM control system allows or denies actions by users within the context of a service based on the assigned policy. When a user tries to complete a specific action, the control system uses the attributes that are defined in the policy to determine whether the user has permission to perform that task.

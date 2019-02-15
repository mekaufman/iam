---

copyright:

  years: 2019

lastupdated: "2019-02-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Assigning access to account management services
{: #account-services}

As the account owner or the administrator of an account management service, you can use account management services to grant users in the account access to invite users to the account, track billing and usage, and work with support cases. Users with access can also manage service IDs, access policies, catalog entries, and access groups.

## Creating policies for account management service access
{: #account-management-access}

To assign access to one or all account management services, complete the following steps: 

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and then select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu, and then click **Assign access**.
3. Select to assign access to **Account Management Services**.
4. Select **All Account Management Services** or select a specific account management service.
5. Select any combination of roles to assign the wanted access.

To grant another user full access to the account for the purposes of managing user access and all account resources, you must assign two policies. One policy that gives the user access to all resources in the account by selecting **All Identity and Access enabled services** with the **Administrator** role assigned. And, one policy that gives the user access to all account management services in the account by selecting **All account management services** with the **Administrator** role assigned.
{: tip}

## Action to role mappings for account management services
{: #account-management-actions-roles}

The following tables outline the actions that users can take when they are assigned a specific role for each account management service. Review the information to ensure that you are assigning the correct level of access to your users. 

| Roles | Actions |
|:-------|----------|
| Viewer |   View access groups and members     |
| Operator | Not applicable    |
| Editor |  View, create, edit, and delete groups <br><br> Add or remove users from groups     |
| Administrator |  View, create, edit, and delete groups <br><br> Add or remove users <br><br> Assign access to a group <br><br> Manage access for working with access groups   |
{: caption="Table 1. Roles and example actions for the Access groups service" caption-side="top"}

| Roles | Actions |
|:-------|----------|
| Viewer |  View users in the account <br><br> View user profile settings     |
| Operator | View users in the account <br><br> View user profile settings  |
| Editor |  View, invite, remove, and update users from the account <br><br> View and update user profile settings    |
| Administrator | View, invite, remove, and update users from the account <br><br> View and update user profile settings    |
{: caption="Table 2. Roles and example actions for the User Management service" caption-side="top"}

| Roles | Actions |
|:-------|----------|
| Viewer |  View cases <br><br> Search cases      |
| Operator |  Not applicable    |
| Editor |  View cases <br><br> Search cases <br><br> Update cases <br><br> Create cases     |
| Administrator |  View cases <br><br> Search cases <br><br> Update cases <br><br> Create cases    |
{: caption="Table 3. Roles and example actions for the Support Center service" caption-side="top"}

| Roles | Actions |
|:-------|----------|
| Viewer | View account feature settings <br><br> View subscriptions in account <br><br> View account name <br><br> View resource groups   |
| Operator | View account feature settings <br><br> View subscriptions in account <br><br> View and change account name <br><br> View and update resource groups    |
| Editor |  View and update account feature settings <br><br> View subscriptions in account <br><br> View offers in account <br><br> View and apply feature codes <br><br> View and change account name <br><br> View and update spending limits <br><br> View, create, and update resource groups    |
| Administrator |  View and update account feature settings <br><br> View subscriptions in account <br><br> View offers in account <br><br> View and apply feature codes <br><br> View and change account name <br><br> View and update spending limits <br><br> View subscription balances and track usage <br><br> View, create, update, and assign access to manage resource groups  |
{: caption="Table 4. Roles and example actions for the Billing service" caption-side="top"}

| Roles | Actions |
|:-------|----------|
| Viewer |   View IDs     |
| Operator | Create and delete IDs and API keys   |
| Editor |  Create, update, and delete IDs and API keys  |
| Administrator |  Create, update, and delete IDs and API keys <br><br> Assign access policies to IDs  |
{: caption="Table 5. Roles and example actions for the IAM Identity service" caption-side="top"}

For the IAM Identity Service, these actions apply to service IDs within the account that the user didn't create. All users can create service IDs. They're the administrator for those IDs, and they can create the associated API key and access policies. However, this account management service applies to the ability to view, delete, and assign access to service IDs in the account created by other users.
{: note}

| Roles | Actions |
|:-------|----------|
| Viewer |   View private services    |
| Operator | Not applicable    |
| Editor |   Change object metadata but can't change visibility for private services     |
| Administrator |  Change object metadata or visibility for private services, and restrict visibility of a public service   |
{: caption="Table 6. Roles and example actions for the Global Catalog service" caption-side="top"}

| Roles | Actions |
|:-------|----------|
| Viewer |  All viewer role actions for the account management services     |
| Operator |  All operator role actions for the account management services     |
| Editor |  All editor role actions for the account management services     |
| Administrator |  All administrator role actions for the account management services   |
{: caption="Table 7. Roles and example actions for a policy on all identity and access services" caption-side="top"}



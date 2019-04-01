---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 启用对资源的公共访问权
{: #public}

通过对资源的公共访问权，所有用户和服务标识都能够访问您帐户中的特定资源。例如，这意味着用户或服务标识无需向 {{site.data.keyword.Bluemix}} 认证，就可访问 {{site.data.keyword.cos_full_notm}} 存储区中的信息。只有某些服务支持提供对服务特定资源类型的公共访问权的能力。因此，您仅限于为支持此功能的服务创建策略。
{:shortdesc}

要启用对资源的公共访问权，您必须使用帐户中为您提供的**公共访问权**访问组。缺省情况下，此访问组包含所有用户和服务标识。您无法删除该组或更改该组的成员资格，但可以添加、编辑和删除该组的访问策略。

## 为公共访问组创建策略
{: #public_policy}

完成以下步骤以将策略分配给公共访问组。以下任务以 Cloud Object Storage 服务为例，说明了如何分配对名为 `mybucket123` 的存储区的公共访问权。

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**访问组**。
2. 选择**公共访问权**组。
3. 单击**分配访问权**。
4. 从服务列表中选择 **Cloud Object Storage**。
5. 对于资源类型，输入 `bucket`。
6. 对于资源标识，输入 `mybucket123`。
7. 单击**分配**。
8. 单击**是**以确认要分配对资源的公共访问策略，然后单击**分配**。

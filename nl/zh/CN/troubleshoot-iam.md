---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-23"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# 有关 IAM 的故障诊断
{: #troubleshoot_iam}

使用 IAM 时会遇到的一般问题可能包括需要对资源或帐户的访问权才能执行任务，或者确定要分配给帐户中的用户以执行特定任务的正确访问权类型。在许多情况下，只需执行几个简单的步骤即可解决这些问题。
{:shortdesc}

## 我如何知道自己分配的访问权是什么？
{: #troubleshoot-myaccess}
{: troubleshoot}

如果您无权完成特定任务（例如创建服务实例并将其添加到资源组，或邀请其他用户加入帐户），那么可能需要检查为您分配的访问权。

我不确定自己分配有什么级别的访问权以在所属的帐户中完成操作。
{: tsSymptoms}
   
您可能未分配有正确的访问权。
{: tsCauses}

要检查您有权访问的内容以及具有的访问级别，请完成以下步骤。如果您需要请求访问权，请联系帐户所有者。

转至**管理** &gt; **访问权 (IAM)**，然后在**用户**页面中选择您的名称。接着，根据您查找的访问权，选择不同的选项卡：
{: tsResolve}

* 要确定您通过分配的访问组所具有的访问权，请选择**访问组**。
* 要查看分配给您的 IAM 访问策略，请选择**访问策略**。
* 要查看您对所有组织和空间的 Cloud Foundry 访问权，请选择 **Cloud Foundry 访问权**。


## 如何获取邀请用户加入帐户的访问权？ 
{: #troubleshoot-invite}
{: troubleshoot}

如果您不是帐户所有者且未分配有正确的访问权，那么无法邀请用户加入帐户。 

我无法邀请用户加入帐户。
{: tsSymptoms}
   
您可能未分配有正确的访问权。
{: tsCauses}

要邀请用户并管理待处理邀请，您必须是帐户所有者、组织管理者或者具有对用户管理帐户管理服务的编辑者或更高角色的 IAM 访问策略的用户，或者您必须具有添加用户的经典基础架构许可权。
{: tsResolve}


## 如何查看其他用户的经典基础架构许可权？
{: #troubleshoot-classicinfra}
{: troubleshoot}

帐户所有者对帐户具有完全访问权，因此他们看不到自己的许可权。单个用户无法编辑自己的许可权，因此在其经典基础架构页面上可以查看许可权，但无法进行编辑。您必须具有特定的访问权才能查看和编辑帐户中其他用户的许可权。

您看到一条消息，表明您无法查看其他用户的经典基础架构许可权。
{: tsSymptoms}
   
您可能未分配有正确的访问权。
{: tsCauses}

您必须要求帐户所有者为您分配**管理用户**经典基础架构许可权，但您还必须在经典基础架构用户层次结构中是该用户的祖代，才能查看和管理该用户的许可权。
{: tsResolve}

## 如何在 IBM Cloud 中管理迁移的计费和支持案例许可权？
{: #troubleshoot-migrated-permissions}
{: troubleshoot}

将用户以及管理计费和支持案例的许可权从 SoftLayer 帐户初始迁移到链接的 {{site.data.keyword.Bluemix_notm}} 帐户时，一些用户可能会缺少这些许可权。但是，现在会为所有迁移的许可权访问组分配正确的 IAM 访问策略，确保为所有用户分配先前拥有的正确访问权。

用户在 {{site.data.keyword.Bluemix_notm}} 控制台中拥有的管理计费和支持案例许可权似乎与先前在 SoftLayer 帐户中为其分配的不同。
{: tsSymptoms}
   
初始迁移用户时，可能尚未为迁移的许可权访问组分配正确的访问策略。
{: tsCauses}

从 2019 年 5 月 20 日开始，所有[迁移的许可权访问组](/docs/iam?topic=iam-migrated_permissions)都会分配有用于管理计费信息和支持案例的正确策略。如果您在此日期之前尝试使用了这些组，那么缺少相应 IAM 访问策略的访问组可能导致了 SoftLayer 许可权中分配的访问权与 IAM 访问权之间的不匹配。此问题现已解决。您可以转至**管理** > **访问权 (IAM)**，然后选择**访问组**来查看分配给每个访问组的用户和策略。
{: tsResolve}


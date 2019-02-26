---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-30"

keywords: maximum limits, IBM Cloud IAM, limits, maximum policies

subcollection: iam

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} IAM limits
{: #iam_limits}

The following table lists the maximum limits for {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) resources. These limits apply to any user who can create {{site.data.keyword.Bluemix_notm}} IAM resources, and if a limit is exceeded you will receive an exception and not be allowed to create any new resources beyond that limit.

| Resource | Max |
|----------|---------|
| Access groups per account | 500 |
| Access groups per user | 50 |
| Service IDs per account | 2000 |
| API Keys per identity | 20 |
{:caption="Table 1. IAM Account Limits" caption-side="top"}

A maximum of 1,000 policies and service to service authorizations within one account is recommended to ensure optimal performance within your account.
{: tip}

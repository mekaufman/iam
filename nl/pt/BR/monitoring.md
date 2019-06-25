---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: event tracking, IAM events, monitoring

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Rastreamento de eventos do IAM
{: #tracking}

Como um responsável pela segurança, auditor ou gerenciador, é possível usar o serviço {{site.data.keyword.at_full}} para controlar como os usuários e aplicativos interagem com o {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM).
{:shortdesc}

A partir de 9 de maio de 2019, o serviço {{site.data.keyword.cloudaccesstraillong}} foi descontinuado. Deve-se criar uma instância do {{site.data.keyword.at_short}} em sua conta para continuar rastreando os eventos do IAM. Para obter mais informações, consulte [Descontinuação do serviço IBM Cloud Activity Tracker](https://www.ibm.com/blogs/cloud-archive/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window}![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo").
{: deprecated}

É possível controlar os eventos a seguir:

* Gerenciando grupos de acesso criando e excluindo grupos ou incluindo e removendo usuários
* Criando, atualizando ou excluindo IDs de serviço
* Criando, atualizando ou excluindo chaves API
* Criando, atualizando ou excluindo políticas de acesso
* Efetuando login no {{site.data.keyword.Bluemix_notm}} usando uma chave API, código de autorização, senha ou uma chave API associada a um ID do serviço

Para começar a monitorar as ações do usuário, veja [{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). Para obter mais informações sobre cada uma das áreas de eventos que podem ser controladas, veja [Eventos do IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam).

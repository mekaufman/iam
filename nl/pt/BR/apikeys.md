---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Entendendo as chaves de API
{: #manapikey}

Uma chave de interface de programação de aplicativos (chave de API) é um código exclusivo passado para uma API para identificar o aplicativo de chamada ou o usuário. As chaves API são usadas para rastrear e controlar como a API está sendo usada, por exemplo, para evitar uso malicioso ou abuso da API. A chave de API geralmente age como um identificador exclusivo e um token secreto para autenticação e geralmente tem um conjunto de acesso que é específico para a identidade associada a ele.
{:shortdesc}

Para visualizar suas chaves de API, acesse **Gerenciar** > **Acesso (IAM)** e selecione **Usuários**. Em seguida, selecione um usuário para navegar para a seção de chaves de API que está incluída na página Detalhes do usuário. 

## {{site.data.keyword.cloud_notm}}Chaves API
{: #ibm-cloud-api-keys}

As chaves de API do {{site.data.keyword.cloud}} são criadas por meio da página Detalhes do usuário no console do {{site.data.keyword.cloud_notm}} para um usuário e associadas à identidade do usuário. Somente o usuário para o qual a chave de API é associada pode criá-la e excluí-la. É possível usar as chaves de API do {{site.data.keyword.cloud_notm}} na interface da linha de comandos (CLI) ou como parte da automação para efetuar login como sua identidade do usuário. Também é possível usar as chave de API do {{site.data.keyword.cloud_notm}} para acessar APIs de infraestrutura clássica. Para obter mais informações sobre como usar uma chave API associada à sua identidade de usuário, veja [Gerenciando chaves API do usuário](/docs/iam?topic=iam-userapikey#userapikey).

Também é possível usar as chaves API associadas aos IDs de serviço criados. Os IDs de serviço são usados para conectar um aplicativo dentro ou fora do {{site.data.keyword.Bluemix_notm}} a um serviço {{site.data.keyword.Bluemix_notm}}. Para obter mais informações sobre como criar chaves API associadas a um ID de serviço, veja [Gerenciando chaves API do ID de serviço](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Outros tipos de chaves de API
{: #othertypes}

Além de suas chaves de API do {{site.data.keyword.cloud_notm}}, um par de outros tipos de chaves de API que você pode usar está disponível:

* Chaves de API de infraestrutura clássica
* Chaves API específicas do serviço

As chaves de API de infraestrutura clássica são usadas para chamar as APIs para serviços de infraestrutura clássica. É possível criar somente uma chave de API de infraestrutura clássica por vez. É possível criar uma chave de API de infraestrutura clássica para um usuário na página Detalhes do usuário.

As chaves de API do {{site.data.keyword.cloud_notm}} também podem ser usadas para acessar APIs de infraestrutura clássica.
{: tip}

Alguns serviços no {{site.data.keyword.Bluemix_notm}} também podem fornecer uma chave de API para você usar ao trabalhar com o serviço. Por exemplo, se você estiver visualizando os detalhes da oferta de um serviço do Watson por meio de sua lista de recursos, será possível criar uma credencial, que inclui uma chave de API e um segredo que é específico apenas para esse serviço na página Credenciais de serviço.



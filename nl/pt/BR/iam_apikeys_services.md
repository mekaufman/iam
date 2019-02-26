---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Chamando APIs de serviço do {{site.data.keyword.cloud_notm}}
{: #iamapikeysforservices}

Para chamar um serviço do {{site.data.keyword.Bluemix}} por meio de uma API, passe as suas credenciais para a API do serviço para autenticar a sua identidade do usuário e o seu acesso para executar ações dentro do contexto do serviço. 
{:shortdesc}

É possível identificar o responsável pela chamada de uma das maneiras a seguir: 

* Chave de API do {{site.data.keyword.Bluemix_notm}} ou chave de API de ID do serviço
* Token do {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM)

[Chaves de API do {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#userapikey), [Chaves de API do ID de serviço](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys) e tokens do IAM identificam exclusivamente a identidade do responsável pela chamada. A identidade do responsável pela chamada é um usuário do {{site.data.keyword.Bluemix_notm}} ou um ID do serviço que foi criado em uma conta do {{site.data.keyword.Bluemix_notm}}. 

As chaves de API são credenciais que consistem em uma longa série de caracteres ou números aleatórios. Uma identidade do {{site.data.keyword.Bluemix_notm}} pode ter múltiplas chaves de API. Cada uma dessas chaves de API pode ser gerenciada independentemente, o que significa que se essa chave de API for usada somente por seu serviço, será possível excluir a chave de API sem interromper algum outro componente.

É possível usar chaves de API para [efetuar login na interface da linha de comandos (CLI) do {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_login#ibmcloud_login) ou para [gerar tokens do IAM](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey). Embora não seja recomendado para uso de produção, também é possível enviar chaves de API para serviços do {{site.data.keyword.Bluemix_notm}}.

## Passando uma chave de API do {{site.data.keyword.Bluemix_notm}} para autenticar com uma API de serviço
{: #apikey_auth}

Os clientes da API podem passar diretamente uma API do {{site.data.keyword.Bluemix_notm}} para a API do serviço de destino. Para fazer isso, envie a palavra-chave `apikey` como o nome do usuário e a chave de API do {{site.data.keyword.Bluemix_notm}} como a senha usando o cabeçalho de HTTP de autorização básica para o serviço de destino.

A API do serviço de destino deve fazer a introspecção da chave de API do {{site.data.keyword.Bluemix_notm}} usando o serviço {{site.data.keyword.Bluemix_notm}} IAM. O gráfico a seguir mostra três interações de API. A chave de API do {{site.data.keyword.Bluemix_notm}} é passada para cada API do serviço de destino, portanto, cada serviço de destino deve consultar os detalhes da chave de API do {{site.data.keyword.Bluemix_notm}} chamando o {{site.data.keyword.Bluemix_notm}} IAM.

![Autenticando com uma API de serviço usando uma chave de API](images/APIkeyauth.svg "Passando chaves de API para serviços de destino que, então, passam a chave de API para o IAM para validar credenciais")

Usar uma chave de API do {{site.data.keyword.Bluemix_notm}} é conveniente e torna mais fácil descobrir novas APIs e experimentar protótipos rapidamente. Esse método requer que você envie a chave de API do {{site.data.keyword.Bluemix_notm}} para a API do serviço de destino em um formato legível, que compromete desnecessariamente a chave de API. Além disso, como a API do serviço de destino deve sempre examinar a chave de API, esse método é menos desempenhável e, portanto, não é recomendado para cargas de trabalho de produção.

Para autenticar com a API de um serviço usando uma chave de API, conclua as etapas a seguir: 

  1. Primeiramente, [crie uma chave de API do {{site.data.keyword.Bluemix_notm}} ](/docs/iam?topic=iam-userapikey#creating-an-api-key), se ainda não tiver feito isso.
  2. Envie a chave de API do {{site.data.keyword.Bluemix_notm}} conforme definido em [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") como o cabeçalho de HTTP “Authorization”. Use `apikey` como o nome do usuário e o valor da chave de API como a senha.

Como um exemplo, as etapas a seguir presumem que a chave de API é 0a1A2b3B4c5C6d7D8e9E:

  1.	Concatene o `apikey` do nome do usuário e a chave de API separados por dois-pontos: `apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	Codifique em Base64 a sequência: `base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	Configure a Autorização de cabeçalho de HTTP com o esquema Basic, por exemplo, `Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`. Ao usar o comando curl, é possível passá-lo com o parâmetro -u:

    ```
    curl -u "apikey:<IBM Cloud API key value>"
    ```

  Se você usar outras ferramentas, talvez seja necessário especificar essas credenciais de forma diferente.
  {: tip}

## Passando um token do {{site.data.keyword.Bluemix_notm}} IAM para autenticar com a API de um serviço
{: #token_auth}

Para recuperar um token de acesso do IAM, o cliente da API deve primeiro chamar uma API do {{site.data.keyword.Bluemix_notm}} IAM para autenticar e recuperar esse token. A maneira preferencial para os clientes da API de serviço do {{site.data.keyword.Bluemix_notm}} é usar uma chave de API do IAM para obter um token de acesso do IAM. O token de acesso do IAM pode ser usado para múltiplas chamadas de serviços do {{site.data.keyword.Bluemix_notm}} que aceitam tokens de acesso do IAM como um método de autenticação. Como os tokens de acesso do IAM são assinados digitalmente com chaves assimétricas, os serviços do {{site.data.keyword.Bluemix_notm}} podem validar um token de acesso do IAM sem chamar qualquer serviço externo. Isso melhora dramaticamente o desempenho da chamada de uma API.

![Autenticando com uma API de serviço usando um token de acesso ](images/tokenauth.svg "Recuperando um token do IAM usando uma chave de API e passando o token de acesso para os serviços de destino para validar as credenciais")

Para autenticar com a API de um serviço usando um token de acesso, conclua as etapas a seguir:

  1. Primeiramente, [crie uma chave de API do {{site.data.keyword.Bluemix_notm}} ](/docs/iam?topic=iam-userapikey#creating-an-api-key), se ainda não tiver feito isso. 
  2. A próxima etapa para o cliente da API é a recuperação de um token de acesso do IAM, conforme descrito em [Obtendo um token do IAM de uma chave de API](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey).
  3. Da resposta, extraia a propriedade `access_token` para obter o token de acesso do IAM. `expires_in` indica os segundos até que o token de acesso do IAM `access_token` expire. Use esse valor relativo ou o registro de data e hora absoluto `expiration` com base no [horário do UNIX](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo"). 
  4. Envie o token de acesso do IAM conforme descrito em [RFC 6750, seção 2.1. Campo de cabeçalho da solicitação de autorização](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo"):
   
Revise o exemplo a seguir:

  1.	Use a Autorização do cabeçalho de HTTP
  2.	Prefixe o token de acesso do IAM com o literal `Bearer: Bearer eyJhbGciOiJSUzI1Ng...`
  3.	Inclua o token de acesso do IAM prefixado no cabeçalho de HTTP: `Authorization: Bearer eyJhbGciOiJSUzI1Ng...`. Quando você usa o comando curl, é possível passá-lo com o parâmetro -H:

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```
        
  Use o mesmo token de acesso do IAM para chamadas API subsequentes do serviço IBM Cloud para obter o melhor desempenho e escalabilidade.
  {: tip}




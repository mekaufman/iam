---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Permitindo endereços IP específicos para um usuário
{: #ips}

Por padrão, todos os endereços IP podem ser usados para efetuar login no console do {{site.data.keyword.cloud}} e acessar as APIs de infraestrutura clássica. É possível especificar quais endereços IP têm acesso e somente os endereços especificados que forem permitidos poderão ser usados e todos os outros serão restritos.
{:shortdesc}

Não será possível acessar páginas de infraestrutura clássica em [https://cloud.ibm.com](https://cloud.ibm.com){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") se você tiver endereços IP restritos. Deve-se acessar [https://control.softlayer.com](https://control.softlayer.com){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo").
{: important}

Se você tiver o acesso designado a seguir, será possível atualizar os endereços IP restritos para outro usuário:

  * Uma política do IAM com a função de Editor ou superior no serviço de gerenciamento de usuários.
  * Você é um antecessor na hierarquia de infraestrutura clássica para o usuário e tem a permissão Gerenciar a infraestrutura clássica de usuários designada
  
Será possível gerenciar essa configuração para si mesmo se você tiver a configuração Login gerenciado pelo usuário ativada na página Detalhes do usuário.
{: tip}

Para restringir um usuário para usar somente endereços IP específicos, conclua as etapas a seguir: 

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**. 
2. Selecione um usuário da lista.
3. Na página Detalhes do usuário, acesse a seção **Restrições de endereço IP**. 
4. Para **Plataforma de nuvem**, insira os endereços IP. Os endereços IP listados são os únicos por meio dos quais esse usuário pode efetuar login no {{site.data.keyword.Bluemix}}.
5. Para **Infraestrutura clássica**, insira os endereços IP. Os endereços IP listados são os únicos por meio dos quais o usuário pode chamar uma API de infraestrutura clássica. 
  
  Para inserir um endereço IP de infraestrutura clássica, o usuário já deve ter uma chave de API de infraestrutura clássica criada.
  {: note}
 



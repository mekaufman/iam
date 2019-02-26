---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-28"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}

# Atualizando o status de um usuário
{: #status}

O status designado de um usuário depende se o usuário aceitou seu convite para se associar à conta, se é um usuário somente VPN ou se o administrador de usuários configurou o usuário como um de uma infraestrutura clássica desativado.
{:shortdesc}

Se você tiver o acesso a seguir, será possível atualizar o status de outro usuário:

  * Uma política do IAM com a função de Editor ou superior no serviço de gerenciamento de usuários.
  * Você é um antecessor na hierarquia de infraestrutura clássica para o usuário e tem a permissão Gerenciar a infraestrutura clássica de usuários designada

Para obter mais informações sobre os tipos de status do usuário, veja [Estados do usuário](/docs/iam?topic=iam-user_status#user_status).

## Opções para mudar o status de um usuário
{: #status_options}

É possível escolher entre as opções a seguir para atualizar o estado de um usuário:

<dl>
<dt>Ativo</dt>
<dd>O usuário tem acesso total ao console do {{site.data.keyword.cloud_notm}} com base em suas políticas de acesso designado e nas permissões de infraestrutura clássica.</dd>
<dt>Infraestrutura clássica desativada</dt>
<dd>O usuário não pode mais acessar recursos de infraestrutura clássica, mas pode continuar a efetuar login no console e acessar recursos da plataforma.</dd>
<dt>VPN-apenas</dt>
<dd>O usuário não pode efetuar login no console, mas ele tem acesso a quaisquer dispositivos e sub-redes VPN que você designa para a infraestrutura clássica, efetuando login diretamente no dispositivo.</dd>
</dl>

Quando você atualiza um usuário do status Somente VPN para o status Ativo, o usuário deve saber a senha para efetuar login no console. Na maioria dos casos, essa é a senha do ID do SoftLayer, que pode precisar ser reconfigurada para ser usada. Em casos raros em que o usuário já tem um IBMid, ele deve efetuar login com o IBMid e a senha.
{: note}

## Atualizando o status de um usuário
{: #update_user_status}

Para mudar o status de um usuário, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Usuários**. 
2. Selecione um usuário da lista.
3. Na página Detalhes do usuário, selecione uma opção no menu **Status do usuário**.  
4. Clique em **Aplicar**.



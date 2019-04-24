---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

keywords: MFA, multifactor authentication, IBMid MFA, two-factor authentication, account MFA, time-based one-time passcode, TOTP

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Requerendo a MFA para os usuários em sua conta
{: #enablemfa}

Como um proprietário da conta do {{site.data.keyword.Bluemix}}, é possível escolher requerer a autenticação de diversos fatores (MFA) para cada usuário em sua conta. Todos os usuários com um IBMid usam um método de MFA com senha descartável baseada em tempo (TOTP) e quaisquer usuários com um tipo diferente de ID devem ser ativados para usar a TOTP, as perguntas de segurança ou o método de autenticação externa separado.  
{:shortdesc}

## Antes de começar
{: #considerations}

Revise as considerações a seguir antes de ativar a MFA do IBMid para sua conta a fim de assegurar que você saiba como ela afeta todos os usuários em sua conta:

* Ao ativar a MFA para sua conta, todos os usuários que forem incluídos em sua conta deverão concluir o processo de MFA na próxima vez em que efetuarem login.
* As chaves de API para usuários e IDs de serviço continuam a funcionar após a MFA ser ativada.
* Se você requer o uso de login de CLI ou UI do CF nativo no Cloud Foundry, deve-se usar as chaves API ou a conexão única (SSO) após a MFA ser ativada para a conta.
* A MFA para sua conta se aplica ao login de um usuário, mas não se aplica a chamadas API. Se um usuário tem permissão para fazer chamadas API para recursos em sua conta, o usuário pode fazer isso sem concluir a MFA. Se o usuário pertence a outras contas, o usuário pode fazer chamadas API para recursos em sua conta usando uma chave de API por meio de uma conta que não requereu a MFA.
* Se você é um usuário federado, a MFA não é suportada.
* Se você requer MFA para sua conta e tem usuários em sua conta que não têm um IBMid, deve-se ativar uma das outras opções de MFA para esse usuário na página Detalhes do usuário no console do {{site.data.keyword.Bluemix_notm}}. Para obter mais informações, veja [Tipos de autenticação de diversos fatores](/docs/iam?topic=iam-types#types).
* Planeje uma estratégia de comunicação e suporte para usuários em sua conta:
  * Escolha uma data e hora que você planeja ativar a MFA que resulte no menor impacto para seus negócios.
  * Notifique seus usuários da conta depois de ativar a MFA com informações sobre como [configurar](/docs/iam?topic=iam-enablemfa#setupapp).

Quando a configuração da conta de autenticação de diversos fatores estiver ativada, a autenticação de MFA do IBMid será solicitada a todos os usuários de IBMid em sua conta após o login. Se você tiver outros métodos de MFA configurados para quaisquer usuários de IBMid em sua conta, esses métodos de MFA não serão mais solicitados a eles.
{: tip}

## Ativando a MFA para todos os usuários em sua conta
{: #enabling}

Para ativar a MFA, deve-se ser o proprietário da conta. A ativação da MFA não afeta usuários que já estão com login efetuado, pois o cumprimento de MFA na conta entra em vigor somente em novos logins. Certifique-se de notificar seus usuários da conta de que a MFA está ativada e descreva o impacto para os usuários em seu próximo login.

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e, em seguida, selecione **Configurações**.
2. Selecione **Autenticação de diversos fatores**.
3. Na janela de confirmação, clique em **Sim, tenho certeza**.

## Configurando seu TOTP
{: #setupapp}

Depois de ativar a MFA para sua conta, deve-se configurar a senha descartável com um aplicativo autenticador no próxima login. Todos os usuários em sua conta também devem configurar a senha descartável em seu próximo login.

Conclua as etapas a seguir para configurar sua senha descartável com um aplicativo autenticador pela primeira vez:

1. Efetue login com seu IBMid e senha.

  Pode levar até 5 minutos para ser capaz de efetuar login novamente com a MFA.
  {: note}

2. Selecione **Verificar** na tela **Verificação é necessária** para configurar a MFA com um aplicativo autenticador.
3. Selecione **Configurar seu aplicativo autenticador** para ter um código descartável enviado para seu e-mail para continuar a configurar o aplicativo autenticador.
4. Selecione **Verificar**.
5. Varra o código de barras com seu app ou clique em **Não é possível varrer o código de barras?** para inserir uma chave fornecida.
6. Clique em **Continuar** para inserir seu código.
7. Insira seu código e selecione **Verificar**.

Se encontrar uma mensagem de erro que declara que você já configurou a autenticação, mas seu código de verificação não está funcionando ou você não tem seu código de verificação para inserir, deve-se entrar em contato com o [Help desk](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") para reconfigurar sua inscrição de MFA.
{: note}
{: #mfahelp}

## Desativando a MFA necessária para todos os usuários em sua conta
{: #disablemfa}

Para desativar a MFA, deve-se ser o proprietário da conta. Desativar a MFA não afeta usuários que já estão com login efetuado e a ação entra em vigor em todos os novos logins.

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e, em seguida, selecione **Configurações**.
2. Selecione **Padrão**.
3. Na janela de confirmação, clique em **Sim, tenho certeza**.

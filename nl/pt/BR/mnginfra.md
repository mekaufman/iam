---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Gerenciando o acesso à infraestrutura clássica
{: #mngclassicinfra}

É possível atualizar permissões para serviços de infraestrutura clássica ou incluir acesso de dispositivo e de sub-rede VPN para um usuário a qualquer momento. Para acessar as permissões de infraestrutura clássica, acesse **Gerenciar** &gt; **Acesso (IAM)**, selecione **Usuários**. Em seguida, selecione o nome do usuário para o qual você deseja atualizar o acesso e clique em **Infraestrutura clássica**.
{:shortdesc}

Deve-se estar designado à permissão Gerenciar a infraestrutura clássica de usuários e um antecessor do usuário dentro da hierarquia do usuário da infraestrutura clássica. Os proprietários da conta têm acesso total à conta, portanto, eles não veem as permissões na página. Os usuários individuais não podem editar suas próprias permissões e também não veem permissões na página.
{: note}

  1. Selecione **Permissões** para atualizar as permissões do usuário. É possível selecionar entre quatro tipos de permissões: conta, dispositivos, rede e serviços. Selecione individualmente as permissões de cada categoria ou use uma opção de conjunto de permissões para designar permissões em massa.
  
    As permissões de gerenciamento de conta e de suporte que você designou anteriormente para os usuários em sua conta agora são migradas de permissões de infraestrutura clássica para grupos de acesso do IAM migrados. Para obter mais informações, veja [Permissões de infraestrutura clássica migradas](/docs/iam?topic=iam-predefined#predefined).
    {: tip}
    
  2. Para conceder a um usuário acesso ao dispositivo, selecione **Dispositivos** e designe o acesso a dispositivos específicos e tipos de dispositivos, conforme necessário.
  
    O acesso a dispositivos é designado após o usuário ser convidado para a conta. As permissões de dispositivo se aplicam aos dispositivos específicos que estão designados para o usuário. É possível selecionar dispositivos específicos na lista ou é possível designar acesso por tipo de dispositivo. Se você designar acesso por tipo de dispositivo, talvez deseje usar as opções **Ativar acesso futuro** para assegurar que cada vez que novos dispositivos de um tipo específico forem incluídos, o usuário obtenha automaticamente o acesso designado a esses dispositivos.

  3. Para atualizar o acesso de um usuário a sub-redes VPN, selecione **Sub-redes VPN**. 
  
    Use a opção **Designar automaticamente** para configurar como o usuário obtém acesso às sub-redes VPN com base em seu acesso ao dispositivo. Se essa opção estiver configurada como ativada, o usuário terá o acesso designado automaticamente a todas as sub-redes para os dispositivos aos quais eles já têm acesso. É possível configurar essa opção como desativada para selecionar sub-redes manualmente na lista.
    {: tip}
  
    Para fornecer acesso a sub-redes VPN, o usuário deve já ter acesso designado a um ou mais dispositivos. Se o usuário não tiver acesso a nenhum dispositivo, nenhuma sub-rede estará disponível para seleção. É possível definir o tipo de sub-redes VPN às quais o usuário tem acesso usando a opção **Tipo de VPN**. Se você selecionar **Nenhum**, nenhum acesso à VPN poderá ser designado. 
    
    A opção PPTP foi descontinuada, portanto, se você tiver essa opção e limpá-la, ela não estará mais disponível.
    {: deprecated}















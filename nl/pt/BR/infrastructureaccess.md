---

copyright:

  years: 2017, 2018

lastupdated: "2018-11-30"

keywords: SoftLayer permissions, classic infrastructure access, classic infrastructure permission, migrated SoftLayer permissions, migrated permission access group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}

# Permissões de infraestrutura clássica
{: #infrapermission}

Quando você convida um usuário para sua conta, é possível selecionar entre três conjuntos de permissões de infraestrutura clássica que designam acesso em massa: Somente visualização, Usuário básico, Superusuário.
{:shortdesc}

É possível configurar permissões extras após o usuário aceitar o convite. Por exemplo, o conjunto de permissões inicial designado no convite não concede acesso a dispositivos. Portanto, deve-se conceder acesso ao dispositivo após o usuário aceitar o convite. Para obter mais informações, veja [Gerenciando o acesso de infraestrutura clássica](/docs/iam/mnginfra.html#mngclassicinfra).

Quando você convida alguém para a conta, somente você, o proprietário da conta ou um usuário com a permissão Gerenciar a infraestrutura clássica de usuários pode ajustar as permissões para o usuário. Se você estiver designando as permissões e não for o proprietário da conta, será possível designar somente o nível de permissões ou um subconjunto das permissões às quais já está designado. Um proprietário da conta pode atualizar as permissões de qualquer pessoa na conta para ter qualquer nível de acesso.


## Permissões de infraestrutura clássica migradas
{: #predefined}

Um conjunto de permissões de infraestrutura clássica para visualizar e gerenciar informações de faturamento e trabalhar com casos de suporte é agora migrado para grupos de acesso. Os usuários em sua conta que foram designados anteriormente a essas permissões agora são designados ao respectivo grupo de acesso de permissão migrado. Como resultado, as permissões de infraestrutura clássica podem ser gerenciadas diretamente usando as políticas de acesso do IAM.

Esses grupos de acesso especiais incluem todas as políticas apropriadas do IAM para preservar o comportamento original das permissões de infraestrutura clássica. Por exemplo, para que um usuário continue a ver todas as atualizações de todos os usuários em um caso de suporte, os grupos de acesso de permissão migrados para as permissões de infraestrutura clássica de chamados incluem uma política extra do IAM no serviço de gerenciamento de usuários com a função de Visualizador designada. Para obter mais informações, consulte [Designando acesso de usuário para trabalhar com casos de suporte](/docs/get-support/support_access.html#access).

É possível continuar a gerenciar essas permissões de infraestrutura clássica migradas para usuários diretamente por meio do IAM, incluindo e removendo-as dos grupos de acesso de permissão migrados. As políticas que esses grupos de acesso têm são bloqueadas para preservar o comportamento de acesso para seus membros. Para manter a facilidade de uso para os mais novos usuários do IAM, evite excluir esses grupos de acesso.

Depois que suas permissões de infraestrutura clássica são migradas, deve-se descontinuar seu uso. Consulte a tabela a seguir para obter todas as permissões de infraestrutura clássica migradas que agora fazem parte dos grupos de acesso do IAM.
{: important}

| Nome do grupo de acesso de permissão migrado | Ações permitidas |
|----------|---------|
| Visualizar resumo da conta | Visualizar a página de resumo da conta e as faturas e os pagamentos |
| Obter relatório de conformidade | Solicitar relatórios de conformidade |
| Editar perfil da empresa | Editar as informações do perfil da empresa |
| Pagamentos únicos | Fazer pagamentos únicos na conta do usuário |
| Atualizar detalhes do pagamento | Atualizar as informações de pagamento mensal recorrentes |
| Limitar restrição de caso da UE | Ativar ou desativar a opção Suportado pela UE que restringe os dados do caso de suporte para a União Europeia  |
| Incluir casos e visualizar ordens | Criar casos de suporte e ver todas as ordens.  |
| Editar casos | Editar qualquer caso de suporte |
| Procurar casos | Procurar todos os casos de suporte desde que a permissão de visualização de casos também seja designada |
| Visualizar casos | Visualizar todos os casos de suporte |
{: caption="Tabela 1. Grupos de acesso predefinidos" caption-side="top"}

É possível continuar gerenciando usuários para os grupos de acesso. No entanto, você pode achar útil criar novos grupos de acesso que incluam uma combinação de políticas de acesso para os [serviços de gerenciamento de conta do IAM](/docs/iam?topic=iam-account-services#account-services) para tornar mais fácil designar acesso para tarefas de gerenciamento de conta e trabalhar com casos de suporte.

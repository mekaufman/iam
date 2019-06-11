---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# Gerenciando permissões de conta SoftLayer migradas
{: #migrated_permissions}

Os grupos de acesso agora incluem um conjunto migrado de permissões de conta SoftLayer para visualizar e gerenciar informações de faturamento e trabalhar com casos de suporte. Os usuários em sua conta que foram designados anteriormente a essas permissões agora são designados ao respectivo grupo de acesso de permissão migrado. Como resultado, as permissões podem ser diretamente gerenciadas usando grupos de acesso do IAM.
{:shortdesc}

Esses grupos de acesso especiais incluem todas as políticas do IAM apropriadas para preservar o comportamento original das permissões de conta do SoftLayer. Por exemplo, para que um usuário continue a ver todas as atualizações de todos os usuários em um caso de suporte, os grupos de acesso de permissão migrados para as permissões de conta do SoftLayer de abertura de chamados incluem uma política do IAM no serviço de gerenciamento do usuário com a função Visualizador designada. Para obter mais informações, consulte [Designando acesso de usuário para trabalhar com casos de suporte](/docs/get-support?topic=get-support-access#access).

É possível continuar a gerenciar essas permissões de infraestrutura clássica migradas para usuários diretamente por meio do IAM, incluindo e removendo-as dos grupos de acesso de permissão migrados. As políticas que esses grupos de acesso têm são bloqueadas para preservar o comportamento de acesso para seus membros. Para manter a facilidade de uso para os mais novos usuários do IAM, evite excluir esses grupos de acesso.

Depois que suas permissões de infraestrutura clássica são migradas, deve-se descontinuar seu uso. Consulte a tabela a seguir para obter todas as permissões de infraestrutura clássica migradas que agora fazem parte dos grupos de acesso do IAM.
{: important}

| Nome do grupo de acesso de permissão migrado | Ações permitidas |
|----------|---------|
| Visualizar resumo da conta | Visualizar a página de resumo de conta, faturas e pagamentos. |
| Obter relatório de conformidade | Solicitar relatórios de conformidade. |
| Editar perfil da empresa | Editar as informações de perfil da empresa. |
| Pagamentos únicos | Fazer pagamentos únicos na conta do usuário. |
| Atualizar detalhes do pagamento | Atualize as informações de pagamento mensais recorrentes. |
| Limitar restrição de caso da UE | Ativar ou desativar a opção Suportado pela UE, a qual restringe os dados de caso de suporte para a União Europeia. |
| Incluir casos e visualizar ordens | Criar casos de suporte e ver todas as ordens.  |
| Editar casos | Editar qualquer caso de suporte. |
| Procurar casos | Procurar todos os casos de suporte se a permissão de visualização de casos também estiver designada. |
| Visualizar casos | Visualizar todos os casos de suporte. |
{: caption="Tabela 1. Grupos de acesso predefinidos" caption-side="top"}


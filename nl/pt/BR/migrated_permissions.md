---

copyright:

  years: 2019

lastupdated: "2019-06-24"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}
{:note: .note}


# Gerenciando permissões de conta SoftLayer migradas
{: #migrated_permissions}

É possível usar grupos de acesso de permissão migrados para gerenciar um conjunto de permissões de infraestrutura clássica (SoftLayer) para gerenciar informações de faturamento e trabalhar com casos de suporte. Os grupos de acesso contêm um conjunto de usuários e IDs de serviço que têm o mesmo acesso. Os usuários em sua conta da SoftLayer que foram designados anteriormente com permissões de conta e suporte agora são designados para o respectivo grupo de acesso de permissão migrado. Como resultado, as permissões podem ser diretamente gerenciadas usando grupos de acesso do IAM.
{:shortdesc}

Esses grupos de acesso especiais incluem todas as políticas apropriadas do IAM para preservar o comportamento original das permissões de conta da SoftLayer. Por exemplo, para que um usuário continue a visualizar todas as atualizações de todos os usuários em um caso de suporte, os grupos de acesso de permissão migrados para as permissões de conta da SoftLayer de chamados incluirão uma política extra do IAM no serviço de Gerenciamento de usuários com a função de visualizador designada. Para obter mais informações, consulte [Designando acesso de usuário para trabalhar com casos de suporte](/docs/get-support?topic=get-support-access#access).

Após as suas permissões de infraestrutura clássica serem migradas, deve-se descontinuar o uso dessas permissões e parar de usar a CLI da SoftLayer ou a API para gerenciá-las. Consulte a tabela a seguir para obter as permissões de infraestrutura clássica migradas que agora fazem parte de grupos de acesso do IAM. Os grupos de acesso são criados somente para as permissões que já estão designadas aos usuários; portanto, você pode observar um subconjunto dos grupos de acesso que estão em sua conta listada na tabela a seguir.
{: note}

É possível continuar a gerenciar essas permissões de infraestrutura clássica migradas para usuários diretamente por meio do IAM, incluindo e removendo usuários dos grupos de acesso. As políticas do grupo de acesso são bloqueadas para preservar o comportamento de acesso para os seus membros. No entanto, você pode achar útil criar novos grupos de acesso que incluam uma combinação de políticas de acesso para os [serviços de gerenciamento de conta](/docs/iam?topic=iam-account-services#account-services). A tabela a seguir esboça os detalhes de uma política de acesso do IAM que inclui a permissão do grupo de acesso de permissão migrado, para que você possa recriar e até combinar essas permissões com outras pessoas em um novo grupo de acesso.

| Nome do grupo de acesso de permissão migrado | Descrição | Serviço de gerenciamento de conta | Função do IAM |
|-----------------------------------|-------------|-----------------------------------------|----------|
| Visualizar resumo da conta | Visualizar a página de resumo de conta, faturas e pagamentos.  |  Faturamento |  Visualizador    |
| Obter relatórios de conformidade | Solicitar relatórios de conformidade. | Faturamento |    Visualizador |
| Editar perfil da empresa | Editar as informações de perfil da empresa. | Faturamento  | Operador |
| Atualizar detalhes do pagamento | Atualize as informações de pagamento mensais recorrentes. | Faturamento   | Operador |
| Limitar restrição de caso da UE | Ativar ou desativar a opção Suportado pela UE para restringir dados de caso de suporte para a União Europeia.  |   Faturamento |   Operador   |
| Incluir casos e visualizar ordens | Criar casos de suporte e ver todos os pedidos. | Centro de suporte |   Aplicativos   |
| Editar casos | Editar qualquer caso de suporte. | Centro de suporte |   Aplicativos |
| Procurar casos | Procurar todos os casos de suporte se a permissão de visualização de casos também estiver designada. | Centro de suporte |  Visualizador |
| Visualizar casos | Visualizar todos os casos de suporte. | Centro de suporte e Gerenciamento de usuários | Visualizador, Visualizador |
{: caption="Tabela 1. Permissões de infraestrutura migradas que são mapeadas para funções do IAM" caption-side="top"}

Para os casos de visualização de acesso, crie duas políticas separadas com a função de visualizador para os serviços de Centro de suporte e Gerenciamento de usuários. A política no serviço de Gerenciamento de usuários assegura que o usuário visualiza todos os casos na conta, independentemente de quem os abriu. Sem a política no serviço de Gerenciamento de usuários, se o proprietário da conta tiver a capacidade dos usuários restritos para visualizar outros usuários na conta, a visualização do usuário de casos poderá ser limitada a apenas aqueles que ele mesmo abriu.
{: note}

## Designando novas políticas de acesso do IAM para permissões migradas
{: #migrated-permissions-iam}

Para recriar as permissões migradas que estão disponíveis em cada grupo de acesso, é possível designar políticas para usuários individuais ou criar novos grupos de acesso em sua conta. O benefício da criação de um novo grupo de acesso é que você pode optar por combinar um conjunto de permissões para um grupo de acesso em vez de gerenciar um conjunto de grupos de acesso com um escopo granular de acesso configurado para cada um. Para este exemplo, as etapas explicam como criar um novo grupo de acesso e designar uma política de acesso equivalente para visualizar o resumo da conta e visualizar todos os casos de suporte.

A recriação dessas permissões designando novas políticas de acesso do IAM para os serviços de gerenciamento de conta pode incluir permissões além da permissão única que está disponível no grupo de acesso de permissão migrado. Por exemplo, se você designar a um usuário a função de visualizador no serviço de Faturamento, esse usuário poderá fazer mais do que visualizar o resumo da conta. Para obter uma lista integral das ações que são permitidas para cada função, consulte [Designando acesso a serviços de gerenciamento de conta](/docs/iam?topic=iam-account-services#account-services).
{: important}

Para criar um grupo de acesso, conclua as etapas a seguir:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Clique em **Criar**.
3. Insira um nome e uma descrição opcional para o seu grupo e clique em **Criar**.
4. Clique em **Incluir usuários** na guia **Usuários**.
3. Selecione os usuários que deseja incluir na lista e clique em **Incluir no grupo**. Será possível concluir a mesma ação por meio da guia **IDs de serviço** se você desejar incluir qualquer ID de serviço no grupo.

Após você configurar o seu grupo com usuários e IDs de serviço, designe acesso ao grupo. Lembre-se, qualquer política que você configurar para o grupo se aplicará a todos os membros do grupo.

1. Clique na guia **Políticas de acesso**.
2. Clique em **Designar acesso**.
3. Selecione a opção **Designar acesso a serviços de gerenciamento de conta**.
4. Selecione o serviço **Faturamento**.
5. Selecione a função  ** Visualizador ** .
6. Clique em **Designar**.
7. Clique em **Designar acesso** para designar uma segunda política de acesso para a capacidade de visualizar casos de suporte.
8. Escolha **Designar acesso a serviços de gerenciamento de conta**.
9. Selecione o serviço **Centro de suporte**.
10. Selecione a função  ** Visualizador ** .
11. Clique em **Designar**.
12. Clique em **Designar acesso** para designar uma terceira política de acesso para a capacidade de visualizar todos os casos de suporte, independentemente de como o proprietário da conta definiu a configuração de visibilidade do usuário da conta.
13. Selecione a opção **Designar acesso a serviços de gerenciamento de conta**.
14. Selecione o serviço **Gerenciamento de usuários**.
15. Selecione a função  ** Visualizador ** .
16. Clique em **Designar**.

Três políticas são agora designadas para o seu grupo:

* Uma política para visualizar o resumo da conta e todas as outras ações que estão associadas à função de visualizador no serviço de Faturamento.
* Uma política para visualizar e procurar casos de suporte na conta.
* Uma política para visualizar todos os usuários na conta e todas as outras ações que estão associadas à função de visualizador no serviço de Gerenciamento de usuários.


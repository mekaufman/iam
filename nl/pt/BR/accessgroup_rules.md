---

copyright:

  years: 2018, 2019

lastupdated: "2019-06-17"

keywords: dynamic rules, access groups, specific identity attributes

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Criando regras dinâmicas para grupos de acesso
{: #rules}

É possível criar regras dinâmicas para incluir automaticamente usuários federados nos grupos de acesso com base em atributos de identidade específicos. Quando seus usuários efetuam login com um ID federado, os dados do provedor de identidade mapeiam dinamicamente seus usuários para um grupo de acesso com base nas regras que você configurou.
{:shortdesc}

Os usuários já têm informações de identificação específicas dentro do domínio de sua empresa e, quando efetuam login com um ID federado, esses dados podem ser passados por meio do uso de asserções SAML. As asserções SAML ou instruções do atributo que são configuradas no provedor de identidade fornecem os dados que são usados para criar cada regra. Por exemplo, é possível que você tenha uma instrução do atributo true ou false que defina usuários como um gerenciador. Essas informações podem ser usadas para incluir todos os usuários que são gerenciadores em um grupo de acesso específico para gerenciadores que você criou em sua conta do {{site.data.keyword.Bluemix_notm}}. Para obter mais informações, consulte a [Regra de exemplo](/docs/iam?topic=iam-rules#example).

Somente usuários que já foram convidados para a conta podem ser mapeados para grupos de acesso usando regras dinâmicas.
{: note}

## Configurando regras
{: #setup_rules}

As regras dinâmicas são criadas configurando condições que devem ser correspondidas pelos dados que são configurados no provedor de identidade e passados com o ID federado de um usuário durante o login. É possível incluir mais de uma condição para uma regra. Todas as condições configuradas na regra devem ser atendidas para que um usuário seja incluído em um grupo de acesso. 

Para criar uma regra, siga estas etapas:

1. Na barra de menus, clique em **Gerenciar** &gt; **Acesso (IAM)** e selecione **Grupos de acesso**.
2. Selecione o nome do grupo de acesso para o qual você deseja criar uma regra para abrir a página de detalhes do grupo.
3. Selecione a guia  ** Regras Dinâmicas ** .
4. Clique em  ** Incluir regra **.
5. Insira as informações do seu provedor de identidade que são fornecidas dinamicamente para você na página Incluir regra. A lista a seguir fornece detalhes para cada campo obrigatório.

É possível pensar na regra como um par chave/valor, em que a chave é o que você inclui no campo `Incluir usuários quando` e o valor é o que você insere no campo `Valor`, que especifica com o que a regra deve ser comparada com base no comparador selecionado.
{: tip}

<dl>
<dt>Nome</dt>
<dd>Insira um nome customizado para a sua regra que ajude você a se lembrar do tipo de usuários que está incluindo em um grupo de acesso.</dd>
<dt>Provedor de identidade</dt>
<dd>Insira o URI para seu provedor de identidade. Esse é o campo SAML "entityId", que às vezes é referido como o ID do emissor, para o provedor de identidade como parte da configuração de federação para migração com IBMid.</dd>
<dt>Expiração (em horas)</dt>
<dd>É possível usar essa opção para fornecer segurança extra, configurando um limite de tempo para o acesso designado. Cada usuário deve efetuar login a cada 24 horas para atualizar seu acesso, mas é possível configurar o acesso para expirar em apenas uma hora. A associação ao grupo é revogada após a expiração desse período.</dd>
<dt>Incluir usuários quando</dt>
<dd>O nome da instrução do atributo deve ser inserido nesse campo. Esse valor é específico para o seu provedor de identidade.</dd>
<dt>Comparador</dt>
<dd>É possível escolher entre Equals, Not Equals, Equals Ignore Case, Not Equals Ignore Case, In e Contains. Use a opção Contains quando a instrução do atributo tiver um tipo de matriz. Além disso, é possível inserir mais de um valor para ser correspondido usando a opção In.</dd>
<dt>Valor</dt>
<dd>Insira o valor de atributo para a instrução do atributo com relação à qual a regra está comparando.</dd>
</dl>

Os usuários incluídos nos grupos de acesso usando regras dinâmicas não são exibidos como membros do grupo na lista de usuários para o grupo de acesso. Para verificar a participação de um usuário específico em um grupo de acesso, é possível selecionar o nome desse usuário na página **Usuários** da conta e, em seguida, clicar em **Grupos de acesso**.
{: note}

## Regra de exemplo
{: #example}

O exemplo a seguir inclui valores para cada um dos campos na página **Incluir regra**. Nessa regra, os usuários que são identificados como gerenciadores dentro do provedor de identidade federado são mapeados para um grupo de acesso do {{site.data.keyword.Bluemix_notm}} que tem acesso específico configurado somente para gerenciadores.

| Campo | Valor |
|----------|---------|
| Nome | Regra do grupo de gerenciador |
| Provedor de identidade | `https://idp.example.org/SAML2` |
| Expiração (em horas) | 12 |
| Incluir usuários quando (nome do atributo) | isManager |
| Comparador | Igual a  |
| Valor |  verdadeiro |
{: caption="Tabela 1. Exemplo de regra dinâmica para grupos de acesso" caption-side="top"}

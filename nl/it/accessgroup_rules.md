---

copyright:

  years: 2018, 2019

lastupdated: "2019-04-10"

keywords: dynamic rules, access groups, specific identity attributes

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Creazione di regole dinamiche per i gruppi di accesso
{: #rules}

Puoi creare delle regole dinamiche per aggiungere automaticamente gli utenti federati ai gruppi di accesso in base a specifici attributi di identità. Quando i tuoi utenti eseguono l'accesso con un ID federato, i dati dal provider di identità associano dinamicamente i tuoi utenti a un gruppo di accesso in base alle regole da te impostate.
{:shortdesc}

Gli utenti dispongono già di informazioni di identità specifiche all'interno del dominio della tua azienda e, quando accedono con un ID federato, questi dati possono essere passati utilizzando le asserzioni SAML. Le asserzioni SAML o le istruzioni di attributo configurate all'interno del provider di identità forniscono i dati utilizzati per creare ciascuna regola. Ad esempio, potresti avere un'istruzione di attributo true o false che definisce gli utenti come gestore. Queste informazioni possono essere utilizzate per aggiungere tutti gli utenti che sono gestori a un gruppo di accesso specifico per i gestori da te creato nel tuo account {{site.data.keyword.Bluemix_notm}}. Per ulteriori informazioni, vedi la [Regola di esempio](/docs/iam?topic=iam-rules#example).

Solo gli utenti che sono già invitati all'account possono essere associati ai gruppi di accesso utilizzando le regole dinamiche.
{: note}

## Configurazione delle regole
{: #setup_rules}

Le regole dinamiche vengono create impostando le condizioni che devono essere soddisfatte dai dati configurati all'interno del provider di identità e passati con un ID federato dell'utente durante l'accesso. Puoi aggiungere più di una condizione per una regola. Tutte le condizioni impostate nella regola devono essere soddisfatte affinché un utente venga aggiunto a un gruppo di accesso. Per creare una regola, attieniti alla seguente procedura:

1. Dalla barra dei menu, fai clic su **Gestisci** &gt; **Accesso (IAM)** e seleziona **Gruppi di accesso**.
2. Seleziona il nome del gruppo di accesso per cui vuoi creare una regola per aprire la pagina dei dettagli del gruppo.
3. Seleziona la scheda **Regole dinamiche**.
4. Fai clic su **Aggiungi regola**.
5. Immetti le informazioni dal tuo provider di identità che vengono fornite dinamicamente per te nella pagina Aggiungi regola. Il seguente elenco fornisce i dettagli per ogni campo obbligatorio.

<dl>
<dt>Nome</dt>
<dd>Immetti un nome personalizzato per la tua regola che ti aiuti a ricordare quale tipo di utenti stai aggiungendo a un gruppo di accesso.</dd>
<dt>Provider di identità</dt>
<dd>Immetti l'URI per il tuo provider di identità. Questo è il campo "entityId" di SAML, che è a volte indicato come ID emittente, per il provider di identità come parte della configurazione della federazione per l'onboarding con l'ID IBM.</dd>
<dt>Scadenza (in ore)</dt>
<dd>Puoi utilizzare questa opzione per fornire ulteriore sicurezza impostando un limite di tempo per l'accesso assegnato. Ogni utente deve eseguire l'accesso ogni 24 ore per aggiornare il suo accesso ma puoi impostare l'accesso in modo che scada anche entro appena un'ora. L'appartenenza al gruppo viene revocata dopo la scadenza di questo periodo di tempo.</dd>
<dt>Aggiungi utenti quando</dt>
<dd>Il nome dell'istruzione dell'attributo deve essere immesso in questo campo. Questo valore è specifico per il tuo provider di identità.</dd>
<dt>Criteri di confronto</dt>
<dd>Puoi scegliere tra Uguale, Non uguale, Uguale ignorando le differenze tra maiuscolo/minuscolo, Non uguale ignorando le differenze tra maiuscolo/minuscolo, In e Contiene. Utilizza l'opzione Contiene quando l'istruzione dell'attributo ha un tipo array. Puoi inoltre immettere più di un valore da soddisfare utilizzando l'opzione In.</dd>
<dt>Valore</dt>
<dd>Immetti il valore di attributo per l'istruzione di attributo rispetto alla quale la regola sta eseguendo il confronto.</dd>
</dl>

Puoi considerare la regola come una coppia chiave/valore in cui la chiave è ciò che aggiungi nel campo `Aggiungi utenti quando` e il valore è ciò che inserisci nel campo `Valore` per la regola con cui deve essere confrontato in base al criterio di confronto selezionato.
{: tip}

## Regola di esempio
{: #example}

Il seguente esempio include i valori per ciascuno dei campi nella pagina **Aggiungi regola**. In questa regola, gli utenti identificati come gestori all'interno del provider di identità federato vengono associati a un gruppo di accesso {{site.data.keyword.Bluemix_notm}} che dispone di una serie di accessi specifica per i soli gestori.

| Campo | Valore |
|----------|---------|
| Nome | Regola del gruppo gestori |
| Provider di identità | `https://idp.example.org/SAML2` |
| Scadenza (in ore) | 12 |
| Aggiungi utenti quando (nome attributo) | isManager |
| Criteri di confronto | Uguale  |
| Valore |  true |
{: caption="Tabella 1. Regola dinamica di esempio per i gruppi di accesso" caption-side="top"}

---



copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: frequently asked question, faq

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:faq: data-hd-content-type='faq'}
{:note: .note}

# Domande frequenti
{: #iamfaq}

## Cos'è {{site.data.keyword.cloud_notm}} Identity and Access Management?
{: #whatisiam}
{: faq}

IAM (Identity and Access Management) ti consente di autenticare in modo protetto gli utenti per i servizi di piattaforma e di controllare l'accesso alle risorse nella piattaforma {{site.data.keyword.cloud_notm}}. Un insieme di servizi IBM Cloud è abilitato ad utilizzare Cloud IAM per il controllo dell'accesso. Tali servizi sono organizzati in gruppi di risorse all'interno del tuo account per abilitare la concessione agli utenti di un accesso rapido e facile e più di una risorsa per volta. Le politiche di accesso Cloud IAM vengono utilizzate per assegnare agli utenti e agli ID servizio l'accesso alle risorse all'interno del tuo account. Per ulteriori informazioni, vedi [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam?topic=iam-iamoverview#iamoverview).

## Cos'è un servizio abilitato a IAM?
{: #iam-enabled}
{: faq}

Un servizio abilitato a IAM deve trovarsi in un gruppo di risorse e l'accesso al servizio viene concesso utilizzando le politiche di accesso IAM. Quando crei un servizio abilitato a IAM dal catalogo,devi assegnarlo ad un gruppo di risorse. Per ulteriori informazioni, vedi [Che cosa è una risorsa?](/docs/resources?topic=resources-resource#resource)

{{site.data.keyword.containerlong_notm}} è l'unica eccezione; è controllato dall'accesso IAM ma è sempre assegnato al gruppo di risorse predefinito. Pertanto non ti viene offerta l'opzione di sceglierne uno quando lo crei dal catalogo. Non può inoltre essere assegnato a un altro gruppo di risorse


## IAM e Cloud Foundry sono correlati?
{: #iam-cloudfoundry}
{: faq}

Non sono correlati. Cloud Foundry è una piattaforma open source che utilizza le organizzazioni, gli spazi e i ruoli Cloud Foundry per la gestione degli accessi. IAM è il modo sicuro per autenticare gli utenti per i servizi di piattaforma e per controllare l'accesso alle risorse in tutta la piattaforma {{site.data.keyword.cloud_notm}} utilizzando i gruppi di risorse e i ruoli di accesso IAM.

I sistemi di gestione dell'accesso sono completamente diversi. Le risorse IAM appartengono ad un gruppo di risorse e le risorse Cloud Foundry appartengono a un'organizzazione e a uno spazio. Le politiche di accesso IAM vengono utilizzate per fornire l'accesso alle risorse in un gruppo di risorse. I ruoli di organizzazione e spazio di Cloud Foundry sono utilizzati per fornire l'accesso agli utenti alle risorse Cloud Foundry in uno spazio. IAM non ti dà accesso a nulla all'interno degli spazi Cloud Foundry e i ruoli Cloud Foundry non possono concedere l'accesso alle risorse all'interno di un gruppo di risorse.

## Come faccio a scoprire a cosa ho accesso?
{: #iam-access}
{: faq}

Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona il tuo nome nella pagina Utenti. Quindi, a seconda dell'accesso che stai cercando, apri le diverse schede:

* Per determinare l'accesso di cui disponi attraverso i gruppi di accesso che ti sono stati assegnati, seleziona **Gruppi di accesso**.
* Per vedere le politiche di accesso IAM che ti sono state assegnate, seleziona **Politiche di accesso**.
* Per vedere il tuo accesso a Cloud Foundry per tutte le organizzazioni e gli spazi, seleziona **Accesso Cloud Foundry**.


## Come richiedo l'accesso a una risorsa?
{: #request-access}
{: faq}

Il proprietario dell'account può aggiornare il tuo accesso a qualsiasi risorsa nell'account oppure puoi contattare qualsiasi utente a cui è assegnato il ruolo di amministratore sul servizio o sull'istanza del servizio.

## Perché dovrei usare gruppi di risorse e gruppi di accesso?
{: #resource-groups}
{: faq}

Un gruppo di risorse è un contenitore logico per le risorse. Quando viene creata, una risorsa viene assegnata ad un gruppo di risorse e non può essere spostata dopo che è stata aggiunta.

Un gruppo di accesso viene utilizzato per organizzare facilmente un insieme di utenti e ID servizio in una singola entità per rendere facile le assegnazioni dell'accesso. Puoi assegnare una singola politica a un gruppo di accesso per concedere a tutti i membri tali autorizzazioni. Se hai più di un utente o ID servizio che ha bisogno dello stesso accesso, crea un gruppo di accesso invece di assegnare lo stesso accesso più volte per ogni singolo utente o ID servizio.

Utilizzando sia gruppi di risorse che gruppi di accesso, puoi ottimizzare la politica di assegnazione dell'accesso assegnando un numero limitato di politiche. Puoi organizzare tutte le risorse a cui uno specifico gruppo di utenti e ID servizio ha bisogno di accedere in un singolo gruppo di risorse, raggruppare tutti gli utenti o gli ID servizio in un gruppo di accesso e assegnare quindi una singola politica concedendo l'accesso a tutte le risorse nel gruppo di risorse.

Per ulteriori informazioni, consulta [Procedure consigliate per l'assegnazione dell'accesso](/docs/iam?topic=iam-account_setup#account_setup).

## Come faccio a garantire che i miei utenti possano creare risorse all'interno di un gruppo di risorse?
{: #resources}
{: faq}

Per creare una risorsa in un gruppo di risorse, l'utente deve disporre di due politiche di accesso: una assegnata al gruppo di risorse stesso e una assegnata alle risorse nel gruppo. L'accesso al gruppo di risorse stesso è semplicemente l'accesso al contenitore che organizza le risorse e questo tipo di politica consente ad un utente di visualizzare, modificare o gestire l'accesso al gruppo ma non le risorse al suo interno. L'accesso ai servizi all'interno del gruppo di risorse consente ad un utente di gestire le istanze di servizio, il che significa che l'utente può creare un'istanza di servizio.

Quindi, come minimo, l'utente deve disporre del seguente accesso:

* Ruolo visualizzatore o superiore sul gruppo di risorse stesso
* Ruolo editor o superiore sul servizio o su tutti i servizi nel gruppo di risorse


## Di quale accesso ho bisogno per fornire l'accesso ad altri utenti?
{: #user-access}
{: faq}

Per i servizi abilitati a IAM, devi disporre del ruolo di amministratore sul servizio o sulla risorsa in cui vuoi assegnare l'accesso agli utenti. Se vuoi assegnare l'accesso a tutti i servizi o a tutte le risorse nell'account, hai bisogno di una politica su tutti i servizi abilitati per l'accesso e l'identità con il ruolo di amministratore. Inoltre, per assegnare agli utenti l'accesso ai servizi di gestione dell'account, devi avere il ruolo di amministratore sul servizio specifico o su tutti i servizi di gestione dell'account.

Per i servizi Cloud Foundry, devi disporre dei ruoli di gestore organizzazione o gestore spazio Cloud Foundry per fornire l'accesso alle risorse Cloud Foundry.

Per l'infrastruttura classica, devi disporre dell'autorizzazione di gestione utenti dell'infrastruttura classica e le autorizzazioni di categoria di servizio e dispositivo per le risorse a cui vuoi concedere l'accesso utente.

## Qual è la differenza tra fornire l'accesso per gestire un gruppo di risorse rispetto all'accesso alle risorse all'interno di un gruppo di risorse?
{: #providing-access}
{: faq}

Quando disponi dell'accesso per gestire un gruppo di risorse, puoi visualizzare, modificare il nome e gestire l'accesso per il gruppo di risorse stesso a seconda del ruolo assegnato. L'accesso a un gruppo di risorse stesso non dà all'utente l'accesso alle risorse all'interno del gruppo.

Quando disponi dell'accesso alle risorse all'interno di un gruppo di risorse, puoi modificare, eliminare e creare istanze oppure disporre di tutte le azioni di gestione per i servizi specificati all'interno del gruppo di risorse a seconda del ruolo assegnato.

Per un esempio sui ruoli e sulle azioni di gestione della piattaforma per i servizi di gestione dell'account, vedi [Tabella dei ruoli della piattaforma](/docs/iam?topic=iam-userroles#platformrolestable2).

## Chi può rimuovere gli utenti?
{: #remove-users}
{: faq}

Il proprietario dell'account può rimuovere tutti gli utenti dall'account e qualsiasi utente con il seguente accesso può rimuovere gli utenti da un account:

* Una politica IAM per il servizio di gestione account Gestione utenti con il ruolo di amministratore assegnato ed essere il gestore organizzazione Cloud Foundry se l'utente appartiene a un'organizzazione Cloud Foundry.
* Se hai l'infrastruttura classica nel tuo account, un utente deve avere una politica IAM per il servizio di gestione account Gestione utenti con il ruolo di amministratore assegnato, essere il gestore organizzazione Cloud Foundry se l'utente appartiene a un'organizzazione Cloud Foundry ed essere un predecessore dell'utente nella gerarchia di utenti dell'infrastruttura classica con assegnata l'autorizzazione di gestione utenti dell'infrastruttura classica.

## Come richiedo l'autenticazione multifattore dell'ID IBM per il mio account?
{: #multi-factor}
{: faq}

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Impostazioni**.
2. Scegli **Autenticazione multifattore** e fai clic su **Sì, sono sicuro**. Per ulteriori informazioni, vedi [Richiesta di MFA per gli utenti nel tuo account](/docs/iam?topic=iam-enablemfa#enablemfa).

## Qual è la differenza tra i ruoli del servizio e della piattaforma?
{: #service-platform-roles}
{: faq}

I ruoli del servizio e della piattaforma sono due tipi diversi di ruoli:

* I ruoli della piattaforma sono il modo in cui lavori con un servizio all'interno di un account, ad esempio la creazione di istanze, l'esecuzione del bind di istanze e la gestione dell'accesso dell'utente al servizio. Per i servizi della piattaforma, questi ruoli abilitano gli utenti a creare gruppi di risorse e gestire ID servizio, ad esempio. I ruoli della piattaforma sono: amministratore, editor, operatore e visualizzatore.

* I ruoli del servizio definiscono la capacità di eseguire azioni su un servizio e sono specifici per ogni servizio come l'esecuzione di chiamate API o l'accesso all'interfaccia utente. I ruoli del servizio sono: gestore, scrittore e lettore. Per ulteriori informazioni su come si applicano questi ruoli, fai riferimento alla documentazione del servizio specifico.

## Qual è la differenza tra un gruppo di risorse e le organizzazioni e gli spazi Cloud Foundry?
{: #groups-organizations}
{: faq}

Con l'inizio di {{site.data.keyword.Bluemix_notm}}, un servizio di piattaforma open source per il controllo dell'accesso e l'organizzazione di risorse denominato Cloud Foundry era il singolo metodo per organizzare e controllare l'accesso alle risorse. Poiché {{site.data.keyword.Bluemix_notm}} è stato espanso, era necessario un nuovo metodo che potesse essere utilizzato da tutti i tipi di servizi e risorse. I gruppi di risorse sono ora utilizzati per raggruppare e organizzare molti tipi di risorse, e IAM viene utilizzato per controllare in modo uniforme l'accesso ai servizi e alle risorse. Sono già stati adottati numerosi servizi utilizzando gruppi di risorse e IAM e ulteriori servizi passeranno progressivamente al nuovo metodo per l'organizzazione delle risorse e la gestione dell'accesso.

Il controllo dell'accesso e l'organizzazione delle risorse dell'account sono le principali differenze tra i gruppi di risorse le organizzazioni e gli spazi Cloud Foundry. I gruppi di risorse organizzano i servizi abilitati a IBM in un account di cui viene controllato l'accesso utilizzando le politiche IAM. Le organizzazioni e gli spazi sono gestiti utilizzando i ruoli Cloud Foundry per il controllo dell'accesso e le risorse Cloud Foundry sono assegnate agli spazi. Le organizzazioni e gli spazi possono essere utilizzati per organizzare e controllare l'accesso alle risorse solo all'interno dell'ambito Cloud Foundry mentre i gruppi di risorse e IAM possono essere utilizzati per più tipi di risorse in tutto {{site.data.keyword.Bluemix_notm}}.

## Come posso delegare le capacità di amministratore dell'account?  
{: #account-administrator}
{: faq}

Per delegare le capacità di amministratore dell'account, assegna il seguente accesso:

* Una politica IAM con il ruolo di amministratore su tutti i servizi abilitati per l'accesso e l'identità, che consente a un utente di creare istanze del servizio e di assegnare agli utenti l'accesso a tutte le risorse nell'account.
* Una politica IAM con il ruolo di amministratore su tutti i servizi di gestione dell'account, che consente a un utente di completare attività come invito e rimozione di utenti, gestione dei gruppi di accesso, gestione degli ID servizio, gestione delle offerte del catalogo privato e traccia della fatturazione e dell'utilizzo.
* La serie di autorizzazioni Super utente per l'infrastruttura classica
* Gestore di Cloud Foundry per tutte le organizzazioni

Anche con l'accesso precedentemente descritto assegnato, un amministratore dell'account non può modificare l'impostazione MFA per l'account. Solo il proprietario dell'account può modificare questa impostazione.
{: note}

## Qual è la differenza tra un amministratore dell'account e un proprietario dell'account?
{: #owner-administrator}
{: faq}

I proprietari dell'account vengono assegnati automaticamente come amministratore dell'account per {{site.data.keyword.Bluemix_notm}} IAM. Come amministratore dell'account, puoi invitare utenti, assegnare e gestire l'accesso per gli utenti, creare gruppi di risorse, richiedere MFA per tutti gli utenti nell'account e creare istanze del servizio. Se vuoi che altri utenti nel tuo account abbiano il ruolo di amministratore account, assegna loro il seguente accesso:

* Una politica IAM con il ruolo Amministratore su tutti i servizi abilitati per l'accesso e l'identità, che consente a un utente di creare istanze del servizio e di assegnare agli utenti l'accesso a tutte le risorse nell'account.
* Una politica IAM con il ruolo Amministratore su tutti i servizi di gestione dell'account, che consente a un utente di completare attività come l'invito di utenti, la gestione dei gruppi di accesso, la gestione degli ID servizio, la gestione delle offerte del catalogo privato e la traccia della fatturazione e dell'utilizzo.
* La serie di autorizzazioni Super utente per l'infrastruttura classica
* Gestore di Cloud Foundry per tutte le organizzazioni

Anche con l'accesso precedentemente descritto assegnato, un amministratore dell'account non può modificare l'impostazione MFA per l'account. Solo il proprietario dell'account può modificare questa impostazione.
{: note}

## Come assegno l'accesso alle infrastrutture e ai dispositivi?
{: #infrastructure-devices}
{: faq}

1. Vai a **Gestisci** &gt; **Accesso (IAM)** e seleziona **Utenti**.
2. Seleziona il nome di un utente.
3. Fai clic su **Infrastruttura classica**.
4. Assegna le autorizzazioni dalla sezione **Autorizzazioni**, assegna l'accesso ai dispositivi dalla sezione **Dispositivi** e assegna l'accesso alle sottoreti VPN per i dispositivi a cui all'utente è stato assegnato l'accesso dalla sezione **Accesso VPN**.

## Ogni utente nel mio account può vedere tutti gli altri utenti?
{: #users}
{: faq}

Un proprietario di account può visualizzare tutti gli utenti nell'account e scegliere il modo in cui gli utenti possono visualizzare altri utenti nell'account nella pagina Utenti. Un proprietario di account può modificare l'[impostazione di visibilità dell'elenco utenti](/docs/iam?topic=iam-userlistview#userlistview) nella pagina Impostazioni selezionando una delle seguenti opzioni:

* **Visualizzazione non limitata**: tutti gli utenti nel tuo account possono visualizzare tutti gli altri nell'account.
* **Visualizzazione limitata**: limita la possibilità di visualizzare gli utenti nella pagina Utenti solo a coloro ai quali è stato concesso l'accesso esplicito, insieme a coloro che hanno visibilità di altri utenti tramite un'organizzazione Cloud Foundry condivisa o una relazione di gerarchia dell'utente dell'infrastruttura classica.


## Devo assegnare l'accesso a un utente quando lo invito all'account?
{: #account-invite}
{: faq}

Sì. Devi assegnare un accesso utente all'interno di uno dei tre sistemi di gestione degli accessi:

* Una politica di accesso IAM su una risorsa, un gruppo di risorse o servizi di gestione dell'account
* Un ruolo Cloud Foundry per un'organizzazione e uno spazio
* Una serie di autorizzazioni per l'infrastruttura classica


## Come aggiungo l'autenticazione nelle mie applicazioni web e mobili?
{: #appid}
{: faq}

IAM viene utilizzato per gestire l'accesso ai tuoi servizi e alle tue risorse {{site.data.keyword.cloud_notm}}. Con {{site.data.keyword.appid_full_notm}}, puoi portare la sicurezza cloud a un livello superiore aggiungendo l'autenticazione nelle tue applicazioni web e mobili. Con solo poche righe di codice, puoi proteggere facilmente le applicazioni e i servizi nativi cloud che vengono eseguiti su {{site.data.keyword.cloud_notm}}. Pronto per iniziare? [Consulta le documentazioni](/docs/services/appid?topic=appid-gettingstarted#gettingstarted).

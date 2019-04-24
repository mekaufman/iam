---

copyright:

  years: 2017, 2019

lastupdated: "2019-04-02"

keywords: Cloud Foundry roles, Cloud Foundry access, auditor, manager, developer, billing manager

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Accesso Cloud Foundry
{: #cfaccess}

Al momento, non tutti i servizi possono essere gestiti utilizzando Cloud IAM. Puoi continuare a utilizzare i ruoli Cloud Foundry per l'accesso a queste istanze del servizio. Gli utenti vengono aggiunti all'organizzazione e allo spazio a cui l'istanza appartiene con un ruolo Cloud Foundry assegnato.
{:shortdesc}

Il seguente grafico descrive come vengono correlati le organizzazioni, gli spazi e i ruoli Cloud Foundry all'interno di un account. Un account può avere molti utenti, organizzazioni e spazi. Ogni utente può essere assegnato a tutte le organizzazioni e spazi necessari e quando vengono assegnati a un'organizzazione e spazio, puoi configurare il livello di accesso da utilizzare assegnando un ruolo Cloud Foundry.


![Accesso a un account utilizzando le organizzazioni, gli spazi e i ruoli Cloud Foundry](images/cf-diagram.svg "Come funziona l'accesso a un account utilizzando le organizzazioni, gli spazi e i ruoli Cloud Foundry")



## Ruoli Cloud Foundry
{: #cfroles}

I ruoli Cloud Foundry concedono l'accesso alle organizzazioni e agli spazi all'interno dell'account. I ruoli Cloud Foundry non abilitano le autorizzazioni utente per il completamento delle azioni nel contesto di un servizio nell'account.

L'accesso Cloud Foundry viene assegnato aggiungendo un utente a un'organizzazione e spazio e poi assegnando un ruolo organizzazione e spazio. A seconda del tipo di ruolo che viene assegnato, l'utente può completare azioni specifiche per le istanze del servizio che vengono aggiunte a un particolare spazio.

![Accesso Cloud Foundry](images/CF.svg "Assegnazione di un accesso utente a un'organizzazione e spazio Cloud Foundry")

I seguenti ruoli possono essere assegnati a livello dell'organizzazione:

| Ruolo organizzazione | Autorizzazioni |
|-------------------|-------------|
|Gestore | I gestori dell'organizzazione possono creare, visualizzare, modificare o eliminare gli spazi nell'organizzazione, visualizzare l'utilizzo e la quota dell'organizzazione, invitare utenti all'organizzazione, gestire chi ha accesso all'organizzazione e i loro ruoli al suo interno e gestire i domini personalizzati per l'organizzazione. |
|Gestore fatturazione | I gestori fatturazione possono visualizzare le informazioni sull'utilizzo di runtime e servizi per l'organizzazione nella pagina Utilizzo.  |
|Revisore | I revisori organizzazione possono visualizzare il contenuto di applicazioni e servizi nell'organizzazione. I revisori possono anche visualizzare gli utenti nell'organizzazione e i ruoli ad essi assegnati, nonché la quota per l'organizzazione. |
{:caption="Tabella 1. Ruoli e autorizzazioni dell'organizzazione" caption-side="top"}

I seguenti ruoli possono essere assegnati a livello dello spazio:

| Ruolo spazio | Autorizzazioni |
|------------|-------------|
|Gestore | I gestori spazio possono aggiungere utenti esistenti e gestire i ruoli nello spazio. Il gestore spazio può anche visualizzare il numero di istanze, i bind di servizio e l'utilizzo delle risorse per ciascuna applicazione nello spazio. |
|Sviluppatore | Gli sviluppatori spazio possono creare, eliminare e gestire applicazioni e servizi nello spazio. Alcune delle attività di gestione includono la distribuzione di applicazioni, l'avvio e l'arresto di applicazioni, la rinominazione di un'applicazione, l'eliminazione di un'applicazione, la rinominazione di uno spazio, il bind o l'annullamento del bind di un servizio a un'applicazione, la visualizzazione del numero di istanze, i bind di servizi e l'utilizzo di risorse per ciascuna applicazione nello spazio. Inoltre, lo sviluppatore spazio può associare un URL interno o esterno a un'applicazione nello spazio.   |
|Revisore | I revisori spazio hanno un accesso in sola lettura a tutte le informazioni sullo spazio, quali le informazioni sul numero di istanze, i bind di servizio e l'utilizzo di risorse per ciascuna applicazione nello spazio. |
{:caption="Tabella 2. Ruoli e autorizzazioni dello spazio" caption-side="top"}

Gli utenti a cui nello spazio è assegnato il ruolo di gestore o sviluppatore possono accedere alla variabile di ambiente VCAP_SERVICES. Tuttavia, un utente a cui è assegnato il ruolo di revisore non può accedere a VCAP_SERVICES.
{: note}

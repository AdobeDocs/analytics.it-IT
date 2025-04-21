---
description: Dettagli dell’annuncio sulla fine del ciclo di vita dell’API Adobe Analytics 1.4.
title: Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4
feature: Admin Tools
role: Admin
exl-id: 88769032-a7cd-4ca8-958f-3300a4bfe71f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 4%

---

# Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4

Adobe pianifica di ritirare l&#39;API di Adobe Analytics 1.4 il **12 agosto 2026**. Non saranno più accessibili dopo tale data. Questo annuncio ha un impatto diretto sui seguenti elementi:

* API di Adobe Analytics 1.4, escluse le API di inserimento dati
* Autenticazione WSSE di Adobe Analytics

## API 1.4

Le [API di Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/) forniscono un&#39;ampia gamma di azioni, ad esempio reporting, classificazioni, feed di dati e configurazioni della suite di rapporti. Sono stati ritirati a favore delle [API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/). Le API 2.0 ti consentono di eseguire quasi tutte le azioni che possono essere eseguite nell’interfaccia utente di Analytics, ad esempio generare rapporti o gestire componenti come segmenti e metriche calcolate.

Adobe offre un [percorso di migrazione](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) per gli utenti API 1.4. Puoi migrare le integrazioni alle API 2.0 (le stesse API da cui dipende l’applicazione Adobe Analytics) e sfruttare le funzioni più recenti. Tutte le funzionalità disponibili nelle API 1.4 possono essere eseguite utilizzando le [API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Autenticazione WSSE

L’autenticazione WSSE è un protocollo di autenticazione legacy supportato dalle API di Analytics 1.4. È stato sostituito dalle opzioni di autenticazione basate su OAuth fornite in [Adobe Developer Console](https://developer.adobe.com/console/projects). I progetti che utilizzano l’autenticazione WSSE devono aggiornare le proprie credenziali a quelle fornite in Adobe Developer Console. A tale scopo, accedi a [Adobe Developer Console](https://developer.adobe.com/console/projects) per creare un progetto per l&#39;integrazione API di Analytics 2.0. Seleziona il metodo di autenticazione server-to-server OAuth User o OAuth Server-to-Server.

## Domande frequenti

+++**Questo interessa i miei progetti di I/O Adobe esistenti per le API di Analytics?**

Sono interessati tutti i progetti esistenti che utilizzano le API di Analytics 1.4. È necessario eseguire la migrazione di tali integrazioni alle [API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) prima della scadenza della fine del ciclo di vita.

+++

+++**Ho condiviso le mie credenziali di Adobe con un altro prodotto o applicazione che utilizza le API di Analytics. Sono interessati?**

Se tale prodotto o applicazione utilizza le credenziali WSSE e/o chiama le API di Analytics 1.4, ne risente e deve migrare prima della scadenza della fine del ciclo di vita. Rivolgiti al fornitore del prodotto o dell’applicazione per ulteriori dettagli sui piani di migrazione e sulla tempistica.

+++

+++**Come posso determinare quale API utilizza il mio progetto?**

L’URL di base utilizzato dalle chiamate API determina la versione API utilizzata dal progetto. Le API di Adobe Analytics 1.4 utilizzano i seguenti URL:
* `https://api.omniture.com`
* `https://api3.omniture.com`
* `https://api4.omniture.com`
* `https://api5.omniture.com`

Le [API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) utilizzano il seguente URL:

* `https://analytics.adobe.io`

Se uno dei tuoi progetti API utilizza `api*.omniture.com`, utilizza le API di Adobe Analytics 1.4 e deve effettuare la migrazione alle API 2.0.

+++

+++**Questa fine del ciclo di vita influisce sulla raccolta dei dati?**

La fine del ciclo di vita di Adobe Analytics 1.4 non influisce sulle soluzioni di assegnazione tag, come Tag (precedentemente Adobe Launch), Web SDK o AppMeasurement. Tuttavia, se utilizzi le API di origini dati o classificazioni 1.4 per migliorare i dati, devi migrare tali flussi di lavoro alle API di Adobe Analytics 2.0.

L’API di inserimento dati non è interessata da questo annuncio di fine del ciclo di vita. Mentre Adobe prevede di continuare a supportare l&#39;API di inserimento dati, Adobe consiglia di utilizzare l&#39;[API di inserimento dati in blocco](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/).

+++

Per ulteriori domande sull’annuncio di fine ciclo di vita alle quali non viene fornita risposta in questa pagina, contatta il team del tuo account Adobe.

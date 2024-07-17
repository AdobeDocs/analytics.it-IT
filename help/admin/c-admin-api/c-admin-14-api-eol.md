---
description: Collegamento all’API di amministrazione di Adobe Analytics su github.
title: Domande frequenti sulla fine del ciclo di vita delle API di Adobe Analytics 1.4
feature: Admin Tools
role: Admin
source-git-commit: 0aaeb60528f8ff1b1067f059710c9d9fa8e1886f
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 1%

---

# Domande frequenti sulla fine del ciclo di vita delle API di Adobe Analytics 1.4

## Avviso di fine del ciclo di vita (EOL)

**Cosa verrà ritirato?**

* API di Adobe Analytics 1.4

* Autenticazione Adobe Analytics WSSE

**Quando verrà chiuso?**

Questi servizi saranno ritirati il 12 agosto 2026. Non saranno più accessibili dopo tale data.

## API 1.4

**Quali sono questi servizi?**

Le [API di Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/) sono una raccolta di API che forniscono un&#39;ampia gamma di azioni, ad esempio reporting, classificazioni, feed di dati e configurazioni della suite di rapporti.

**Cosa devo fare per eseguire la migrazione?**

Le [API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) offrono un percorso di migrazione in avanti per gli utenti API 1.4. I clienti che attualmente utilizzano le API 1.4 possono migrare le integrazioni alle API 2.0 (le stesse API da cui dipende l’applicazione Adobe Analytics) e sfruttare le funzioni più recenti.

Le API 2.0 ti consentono di eseguire quasi tutte le azioni che possono essere eseguite nell’interfaccia utente di Analytics, ad esempio generare rapporti o gestire componenti come segmenti e metriche calcolate.

**Le API 2.0 offrono le stesse funzionalità delle API 1.4?**
Tutte le funzionalità disponibili nelle API 1.4 possono essere eseguite utilizzando le [API Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/). Alcune funzionalità forniscono le stesse funzionalità disponibili nelle API 1.4 e consentono di eseguire quasi tutte le azioni eseguibili nell’interfaccia utente di Analytics, ad esempio generare rapporti o gestire componenti come segmenti e metriche calcolate.

## Autenticazione WSSE

**Quali sono questi servizi?**

L’autenticazione WSSE è un protocollo di autenticazione legacy supportato dalle API di Analytics 1.4. È stato sostituito dalle opzioni di autenticazione basate su OAuth fornite in [Adobe Developer Console](https://developer.adobe.com/console/projects).

**Cosa devo fare per eseguire la migrazione?**

I clienti WSSE devono aggiornare le proprie autenticazioni per utilizzare le credenziali fornite in Adobe Developer Console. A tale scopo, accedi a [Adobe Developer Console](https://developer.adobe.com/console/projects) per creare un progetto per l&#39;integrazione API di Analytics 2.0. Seleziona tra i metodi di autenticazione Utente OAuth e Server-to-Server OAuth.

## Domande

D: **Questo interessa i miei progetti di I/O Adobe esistenti per le API di Analytics?**

R: saranno interessati tutti i progetti esistenti che utilizzano le API di Analytics 1.4. È necessario eseguire la migrazione di tali integrazioni alle [API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) prima della scadenza della fine del ciclo di vita.

D: **Ho condiviso le mie credenziali di Adobe con un altro prodotto o applicazione che utilizza le API di Analytics. Sono interessati?**

R: Se tale prodotto o applicazione utilizza le credenziali WSSE e/o chiama le API Analytics 1.4, è interessato e dovrà migrare prima della scadenza EOL. Per ulteriori dettagli sui piani di migrazione e sulle tempistiche, contatta il fornitore del prodotto o dell’applicazione.

D: **Non sono sicuro di quale API Adobe Analytics stiamo utilizzando.**

R: Puoi identificare l’API che utilizzi dall’indirizzo chiamato nell’integrazione.

Per accedere alle API di Adobe Analytics 1.4, richiama uno degli URL seguenti:
* https://api.omniture.com
* https://api3.omniture.com
* https://api4.omniture.com
* https://api5.omniture.com

È possibile accedere alle [API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/) chiamando il seguente URL:
* https://analytics.adobe.io

Se utilizzi api*.omniture.com, devi eseguire la migrazione alle [API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/).

D: **Le API di Adobe Analytics 2.0 sono identiche alle API 1.4? In caso contrario, quali sono le differenze maggiori?**

R: Le API di Adobe Analytics 2.0 non sono identiche alle API 1.4, ma offrono funzioni paragonabili, tra cui i seguenti vantaggi:

* Tempi di risposta più rapidi con metodi di query più semplici ed efficienti, eliminando la necessità di polling

* Funzionalità programmatica per query e aggiornamenti dinamici dei rapporti

* Gestione più agevole degli errori

* Funzionalità flessibile per eseguire qualsiasi operazione da Analysis Workspace

* Coerenza e corrispondenza delle chiamate API alle azioni dell’interfaccia utente

* Accesso a tutti i modelli di Attribution IQ utilizzati in Analysis Workspace

* Accesso a tutti gli algoritmi di rilevamento delle anomalie utilizzati in Analysis Workspace

* Capacità di integrazione con altri prodotti di Experience Cloud

* Maggiore capacità per più rapporti di suddivisione

* Accesso alle funzioni di Analytics più recenti

La guida [Migrazione alle API di Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/migration/) illustra le differenze chiave tra le API 1.4 e 2.0. Ulteriori informazioni sono disponibili anche nelle [Domande frequenti sull&#39;API di Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/guides/faq/).

D: **Questo influisce sulla raccolta dei dati?**

R: la fine del ciclo di vita di Adobe Analytics 1.4 non influisce sulle soluzioni di tag, come Tags (precedentemente Adobe Launch), Web SDK o AppMeasurement.js. Tuttavia, se utilizzi le API di Origini dati, Inserimento dati o Classificazioni 1.4 per raccogliere o migliorare i dati, devi migrare tali flussi di lavoro alle API di Adobe Analytics 2.0. Per ulteriori informazioni, consultare la [2.0 API Endpoints guide](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/).

D: **Cosa posso fare se la mia domanda non ha ricevuto risposta in queste domande frequenti?**

R: Se hai ancora delle domande, contatta il rappresentante del tuo account Adobe.


---
description: Le categorie di origine dati identificano diversi tipi di origini dati che forniscono funzionalità simili.
subtopic: Data sources
title: Panoramica dei tipi di dati e categorie
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 90%

---

# Panoramica dei tipi di dati e categorie

Le categorie di origine dati identificano diversi tipi di origini dati che forniscono funzionalità simili.

Le categorie consentono di raggruppare le origini dati dal punto di vista di un utente. Durante la creazione di un’origine dati tramite [!DNL Data Sources] Interfaccia utente, seleziona prima una categoria di origine dati, quindi un tipo di origine dati specifico. Ogni categoria contiene tipi di origini dati che supportano tipi di dati simili. [!DNL Data Sources] fornisce le seguenti categorie di origini dati:

## Utilizzo sito web {#web-usage}

| Origine dati | Tipo di elaborazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Web Server Log Files] | [Registro web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | La maggior parte dei server web genera file di registro che registrano ogni pagina utilizzata. Tramite questa origine dati puoi elaborare i file di registro dalla maggior parte dei dati di server web e aggiungere i dati ai rapporti. |
| [!UICONTROL Advertising Cloud Bulk Upload] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Fornisce caricamenti in serie manuali ed automatizzati da Excel in [!DNL Advertising Cloud]. |
| [!UICONTROL Site-level Traffic Data Source] | [Traffico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importa i dati del traffico per tutto il sito web. Ad esempio, [!UICONTROL Page Views]. |
| [!UICONTROL Breakdown Traffic Data Source] | [Traffico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importa i dati Traffico suddivisi per un&#39;altra variabile del sito web. Ad esempio: [!UICONTROL Page Views] suddivisi per [!UICONTROL Product]. |

## Campagne pubblicitarie {#ad-campaigns}

| Origine dati | Tipo di elaborazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Generic Ad Server] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di integrare impression e altre metriche top-line sulle attività di trasmissione degli annunci dall&#39;ad server ai rapporti di marketing. È l&#39;origine dati ad server generica e deve essere utilizzata se l&#39;ad server specifico non è supportato. |
| [!UICONTROL Generic Email Campaign Server] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di integrare le metriche dal server di campagne e-mail nei rapporti di marketing.  Le metriche incorporate comunemente includono il numero di messaggi inviati, i messaggi consegnati e i messaggi letti. È l&#39;origine dati di campagne e-mail generica e deve essere utilizzata se il server di campagne e-mail specifico non è supportato. |
| [!UICONTROL Generic Pay-Per-Click Service] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di importare i dati sulle prestazioni pay-per-click, inclusi impression, clic e costi.  È l&#39;origine dati pay-per-click generica e deve essere utilizzata se il servizio pay-per-click specifico non è supportato. |

## Gestione delle relazioni con i clienti (CRM) {#crm}

| Origine dati | Tipo di elaborazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Generic Call Center] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di integrare informazioni sul call center nei rapporti di marketing. Le metriche importate più comunemente includono il numero di chiamate, il tempo al telefono, l&#39;agente e le vendite totali.  È l&#39;origine dati call center generica e deve essere utilizzata se il software call center specifico non è supportato. |
| [!UICONTROL Generic Customer Support Application] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di integrare informazioni sul software di assistenze clienti nei rapporti di marketing. Include metriche quali il numero di nuovi incidenti, il numero di incidenti risolti e il tempo impiegato per la risoluzione degli incidenti.  È l&#39;origine dati assistenza clienti generica e deve essere utilizzata se il servizio assistenza clienti specifico non è supportato. |

## Soddisfazione dei clienti {#csat}

| Origine dati | Tipo di elaborazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Generic Survey Data] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di integrare i risultati dei sondaggi da uno strumento di terze parti nei rapporti di marketing e mostra il livello di soddisfazione dei clienti in merito alle interazioni con il sito.  È l&#39;origine dati sondaggio generica e deve essere utilizzata se il servizio dati sondaggio specifico non è supportato. |

## Prestazioni del sito {#performance}

| Origine dati | Tipo di elaborazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Generic Site Download Speed] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di integrare i dati da un&#39;applicazione o servizio che monitora la velocità dei download con i dati. È l&#39;origine dati velocità download e deve essere utilizzata se il software di velocità download specifico non è supportato. |

## Generico {#generic}

| Origine dati | Tipo di elaborazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Generic Data Source (Summary Data Only)] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Utilizza questa origine dati quando non esiste una corrispondenza migliore per il tipo di dati da importare nei reporting e analisi di marketing. |
| [!UICONTROL Generic Data Source (Full Processing)] | Elaborazione completa | Il 31 gennaio 2022, Adobe ha dichiarato obsolete le origini dati a elaborazione completa. [Ulteriori informazioni](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). L’Adobe consiglia di utilizzare il [API di inserimento dati in blocco (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) invece. |
| [!UICONTROL Generic Data Source (Transaction ID)] | <ul><li>ID transazione</li><li>ID visitatore</li></ul> | Consente di collegare qualsiasi evento offline a un evento online. La [!UICONTROL Transaction ID] funge da chiave tra gli eventi offline e online. |

## Acquisti online {#purchases}

| Origine dati | Tipo di elaborazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Product Returns] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di importare i dati dei resi di prodotti da associare a un ID acquisto in modo da identificare motori di ricerca, parole chiave, campagne e altri attributi che genereranno resi con maggiore probabilità. |
| [!UICONTROL Product Cost] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di fornire il costo effettivo dei prodotti acquistati e spediti dal sito Web associando costo o profitto a singoli prodotti in modo da creare rapporti precisi su campagne, parole chiave e promozioni interne più redditizie per il sito Web. |
| [!UICONTROL Order Status] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di utilizzare le metriche per identificare lo stato di ogni ordine effettuato, inclusi gli ordini annullati, spediti, completati o ritenuti fraudolenti. Il reporting dello stato degli ordini può identificare quali metodi di acquisizione generano il tasso di completamento degli ordini più alto. |

## Lead e preventivi {#leads}

| Origine dati | Tipo di elaborazione | Descrizione |
| --- | --- | --- |
| [!UICONTROL Lead Generation] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di caricare le informazioni sui risultati dei lead per ogni lead generato sul sito Web, inclusi i ricavi effettivi generati.  Dopo aver attribuito con precisione i ricavi agli ID lead, puoi identificare le campagne e le promozioni più redditizie. |
| [!UICONTROL Online Quote] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di caricare le informazioni sui risultati dei lead per ogni lead generato sul sito Web, inclusi i ricavi effettivi generati.  Dopo aver attribuito con precisione i ricavi agli ID lead, puoi identificare le campagne e le promozioni più redditizie. |
| [!UICONTROL Call Center Data] | [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Consente di caricare le transazioni del call center in modo da identificare le tattiche (campagne, promozioni e così via) che convincono i clienti a fare una telefonata. |

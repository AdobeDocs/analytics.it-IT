---
title: Panoramica di Report Builder
description: Descrive la funzionalità di Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 29%

---

# Panoramica di Report Builder

Il nuovo componente aggiuntivo JavaScript per Report Builder, inizialmente disponibile solo in Customer Journey Analytics, ora viene introdotto anche in Adobe Analytics. Questa nuova versione offre diversi vantaggi:

- Trova informazioni in Excel in modo più semplice e veloce con flussi di lavoro migliorati per la creazione e la gestione dei blocchi di dati, inclusa una maggiore flessibilità
- Multipiattaforma: non è più possibile accedere alla macchina virtuale per utilizzare Report Builder, in quanto ora sono supportati PC, Mac ed Excel Online
- Meno tempo di attesa per il ritorno dei blocchi di dati, grazie all’aggiornamento API 2.0
- Velocità ottimizzata.

Gli utenti dello strumento Report Builder legacy possono [convertire le cartelle di lavoro legacy](/help/analyze/report-builder/convert-workbooks.md) nel nuovo Report Builder.

Report Builder consente di creare, modificare e aggiornare facilmente i rapporti personalizzati utilizzando i dati di Adobe Analytics. Con l’interfaccia utente di trascinamento semplice e flessibile di Report Builder, puoi creare query di dati complesse e rapporti personalizzati dai dati di Adobe Analytics, il tutto all’interno di Excel.

Con Report Builder è possibile:

- Fare riferimento alle celle del foglio di lavoro esistenti per ottenere l’ordine di riga, l’intervallo di date o il filtro perfetti
- Creare date personalizzate utilizzando calendario, riferimenti di cella o dati matematici della data
- Progettare tabelle e visualizzazioni con i familiari strumenti di formattazione di Excel

## Utilizzo affiancato di versioni precedenti di Report Builder e Report Builder

È comunque possibile utilizzare entrambe le versioni di Report Builder, con le seguenti avvertenze:

- Non utilizzare entrambe le versioni di Report Builder sullo stesso file contemporaneamente. Si escludono a vicenda.
- È comunque possibile utilizzare il Report Builder legacy sulle cartelle di lavoro legacy e il nuovo Report Builder sulle nuove cartelle di lavoro.
- Inoltre, è possibile [convertire automaticamente le cartelle di lavoro legacy](/help/analyze/report-builder/convert-workbooks.md) nel nuovo formato Report Builder. Prima di procedere, duplicare e rinominare il file.

## Funzioni legacy di Report Builder non supportate nel nuovo Report Builder

Confrontando le funzionalità legacy di Report Builder con il nuovo componente aggiuntivo di Report Builder, alcune funzionalità legacy non sono più disponibili:

- Richieste in tempo reale

- Generazione di rapporti percorso/fallout

- Opzione FTP per i rapporti pianificati

- Metriche dei visitatori. Le metriche seguenti verranno tutte convertite in &quot;visitatori univoci&quot;, anche se il risultato del reporting potrebbe non corrispondere esattamente: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` e `visitorsyearly`. Questo vale anche per `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` e `mobilevisitorsyearly`.

## Casi d’uso comuni

- **Estrazione dati**: Adobe Report Builder consente di estrarre dati da Adobe Analytics in Excel. Puoi creare report e query personalizzati per recuperare punti di dati specifici rilevanti per l’analisi.

- **Generazione rapporti personalizzata**: puoi progettare e formattare rapporti personalizzati in Excel in base alle tue esigenze di reporting specifiche. Ciò è particolarmente utile per adattare i rapporti alle diverse parti interessate.

- **Analisi ad hoc**: gli utenti possono generare rapidamente rapporti ad hoc per rispondere a domande specifiche o esplorare le tendenze dei dati senza dover passare attraverso un lungo processo di generazione rapporti.

- **Dashboard**: i dati estratti da CJA possono essere utilizzati per creare dashboard e visualizzazioni basate su Excel per una panoramica di alto livello degli indicatori di prestazioni chiave (KPI, Key Performance Indicators).

- **Condivisione di approfondimenti**: puoi condividere report e informazioni di Excel con i membri del team o gli stakeholder che potrebbero non avere accesso diretto a CJA.

## Video introduttivo

>[!IMPORTANT]
>
>Questo video introduttivo mostra l’interfaccia utente di Report Builder in Customer Journey Analytics. Alcuni termini e l’interfaccia utente sono diversi. In caso contrario, l’esperienza utente è identica.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panoramica di Report Builder](https://video.tv.adobe.com/v/3452588?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

È possibile scaricare Report Builder da [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview).

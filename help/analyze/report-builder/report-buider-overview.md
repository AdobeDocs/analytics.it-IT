---
title: Cos'è la nuova Adobe Report Builder?
description: Descrive la nuova funzionalità del Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: 7e8a25381f2eadafc5dc22a0991060ea475b5d43
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 27%

---

# Informazioni sul nuovo Adobe Report Builder

Il nuovo componente aggiuntivo per Report Builder JavaScript, inizialmente disponibile solo nel Customer Journey Analytics, ora è stato introdotto anche in Adobe Analytics. Questa nuova versione offre diversi vantaggi:

- Trova informazioni in Excel in modo più semplice e veloce con flussi di lavoro migliorati per la creazione e la gestione dei blocchi di dati, inclusa una maggiore flessibilità
- Multipiattaforma: non è più possibile accedere alla macchina virtuale per utilizzare il Report Builder, in quanto sono ora supportati PC, Mac ed Excel Online
- Meno tempo di attesa per il ritorno dei blocchi di dati, grazie all’aggiornamento API 2.0
- Velocità ottimizzata.

>[!NOTE]
>
>La pianificazione della cartella di lavoro per questa versione del Report Builder su Adobe Analytics non è ancora stata rilasciata, ma sarà disponibile all’inizio del 2025. È ora possibile iniziare a utilizzare le cartelle di lavoro che non richiedono la pianificazione.

Gli utenti dello strumento Report Builder legacy possono [convertire le cartelle di lavoro legacy](/help/analyze/report-builder/convert-workbooks.md) nel nuovo Report Builder.

Report Builder consente di creare, modificare e aggiornare facilmente i rapporti personalizzati utilizzando i dati di Adobe Analytics. Con l’interfaccia utente di trascinamento semplice e flessibile del Report Builder, puoi creare query di dati complesse e rapporti personalizzati dai dati di Adobe Analytics, il tutto all’interno di Excel.

Con Report Builder è possibile:

- Fare riferimento alle celle del foglio di lavoro esistenti per ottenere l’ordine di riga, l’intervallo di date o il filtro perfetti
- Creare date personalizzate utilizzando calendario, riferimenti di cella o dati matematici della data
- Progettare tabelle e visualizzazioni con i familiari strumenti di formattazione di Excel

## Utilizzo affiancato di Report Builder legacy e nuovo Report Builder

È comunque possibile utilizzare entrambe le versioni di Report Builder, con le seguenti avvertenze:

- Non utilizzare entrambe le versioni di Report Builder nello stesso file contemporaneamente. Si escludono a vicenda.
- È comunque possibile utilizzare il Report Builder legacy nelle cartelle di lavoro legacy e il nuovo Report Builder nelle nuove cartelle di lavoro.
- Inoltre, è possibile [convertire automaticamente le cartelle di lavoro legacy](/help/analyze/report-builder/convert-workbooks.md) nel nuovo formato di Report Builder. Prima di procedere, duplicare e rinominare il file.

## Funzioni di Report Builder legacy non supportate nel nuovo Report Builder

Quando si confrontano le funzionalità del Report Builder legacy con il nuovo componente aggiuntivo di Report Builder, alcune funzionalità legacy non sono più disponibili:

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
>Questo video introduttivo mostra l’interfaccia utente del Report Builder in Customer Journey Analytics. Alcuni termini e l’interfaccia utente sono diversi. In caso contrario, l’esperienza utente è identica.

>[!VIDEO](https://video.tv.adobe.com/v/337569/?quality=12&learn=on)

È possibile scaricare il Report Builder da [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview).

---
title: Modello di area di lavoro CDA
description: Descrive ciascun campo nel modello CDA in  Analysis Workspace.
translation-type: tm+mt
source-git-commit: 2e7ec3b2e4401b02005b3099dae2bb34c64a6846
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 67%

---


# Modello di area di lavoro CDA

Adobe offre un modello per visualizzare i dati essenziali sulle prestazioni cross-device.

1. Andate a [experience.adobe.com](https://experiencecloud.adobe.com) ed effettuate l&#39;accesso utilizzando le credenziali AdobeID.
1. Fate clic sull&#39;icona a 9 griglie nella parte superiore, quindi fate clic  Analytics.
1. Fate clic [!UICONTROL Workspace] in alto, quindi fate clic su [!UICONTROL Create New Project].
1. Individuare il &quot;IQ del viaggio: Modello multi-dispositivo  Analytics&quot;, quindi fai clic su [!UICONTROL Create].
1. Se richiesto, modificate la suite di rapporti in una che supporti CDA.

Viene creato un progetto Analysis Workspace  che contiene diversi pannelli. Nella parte superiore, viene visualizzato un sommario e un’introduzione che consentono di visualizzare il contesto del rapporto e di passare ai singoli rapporti. Fate clic su un collegamento all’interno del sommario o espandete la struttura di navigazione di un pannello per visualizzarli.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Nota speciale per i membri del Co-op Graph**: mostra quale parte della suite di rapporti contiene i visitatori nelle aree in cui è supportato il grafico Co-op e le aree in cui non è supportato.
* **Identificazione degli utenti**: mostra la frequenza con cui i visitatori del sito vengono identificati utilizzando metodi basati su Cross-Device Analytics.
* **Misurazione della dimensione dell’audience**: mostra un confronto tra “Dispositivi unici” e “Persone”. La proporzione di questi due numeri è nota come “compressione tra dispositivi”, una metrica calcolata visibile in questo pannello. Questa metrica di compressione dipende da un’ampia gamma di fattori:
   * Utilizzo del grafico Co-op o del grafico Private: in generale, le organizzazioni che utilizzano Device Co-op godono di tassi di compressione migliori rispetto alle organizzazioni che utilizzano il grafico Private.
   * Velocità di accesso: Più utenti accedono al sito, più Adobe è in grado di identificare e unire i visitatori tra i dispositivi. I siti con un tasso di accesso basso hanno anche tassi di compressione bassi.
   * Copertura di Experience Cloud ID: è possibile unire solo i visitatori con un ECID. Una percentuale inferiore di visitatori del sito che utilizza un ECID è correlata a tassi di compressione più bassi.
   * Utilizzo di più dispositivi: se i visitatori del sito non utilizzano più dispositivi le percentuali di compressione potrebbero essere più basse.
   * Granularità del reporting: la compressione per giorno è generalmente inferiore della compressione per mese o per anno. Le possibilità che una sola persona utilizzi più dispositivi si riducono maggiormente in un singolo giorno che nell’arco di un mese intero. Segmentazione, filtraggio o utilizzo di dimensioni di suddivisione possono mostrare inoltre un tasso di compressione più basso.
* **Segmenti basati sulle persone**: contiene un elenco a discesa dei segmenti che consente di visualizzare dati specifici per il dispositivo. Questo pannello incoraggia la sperimentazione con i segmenti per vedere in che modo i rapporti possono essere influenzati dall’inclusione o esclusione di tipi di dispositivi.
* **Analisi del percorso tra dispositivi**: fornisce rapporti di flusso e di fallout in base al tipo di dispositivo.
* **Attribuzione tra dispositivi**: combina le funzioni di Journey IQ e Attribution IQ.
* **Altri suggerimenti e trucchi**: argomenti utili che riguardano CDA e permettono di ottenere il massimo dal suo utilizzo.

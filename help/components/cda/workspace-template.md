---
title: Modello di CDA Workspace
description: Descrive ogni campo nel modello CDA in Analysis Workspace.
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/Zui1m27pi3eQnm-dac2akfGRF01IbPaQ0SwLD01iDAE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: e38cbddc-1633-4cd5-bed5-9f289f2a6029id: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 386
ht-degree: 45%

---

# Modello di CDA Workspace

{{available-existing-customers}}

Adobe offre un modello per visualizzare dati vitali sulle prestazioni tra dispositivi.

1. Passa a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e accedi con le credenziali Adobe ID.
1. Fai clic sull’icona della griglia a 9 celle in alto, quindi fai clic su Analytics.
1. Fai clic su [!UICONTROL Workspace] in alto, quindi fai clic su [!UICONTROL Create New Project].
1. Individuare il modello &quot;Cross-Device Analysis&quot;, quindi fare clic su [!UICONTROL Create].
1. Se richiesto, modifica la suite di rapporti impostandola su una che supporti CDA.

Viene creato un progetto Analysis Workspace che contiene diversi pannelli. Nella parte superiore viene visualizzato un sommario e un’introduzione che consentono di contestualizzare il rapporto e di passare a singoli rapporti. Fai clic su un collegamento all’interno del sommario o espandi il pannello a soffietto per visualizzare tali rapporti.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Identificazione degli utenti**: mostra la frequenza con cui i visitatori del sito vengono identificati utilizzando metodi basati su Cross-Device Analytics.
* **Misurazione della dimensione del pubblico**: mostra un confronto tra “Dispositivi univoci” e “Persone”. La proporzione di questi due numeri è nota come “compressione tra dispositivi”, una metrica calcolata visibile in questo pannello. Questa metrica di compressione dipende da un’ampia gamma di fattori:
   * Tasso di accesso: più utenti accedono al sito, più Adobe è in grado di identificare e unire i visitatori tra i dispositivi. I siti con un tasso di accesso basso hanno anche tassi di compressione bassi.
   * Copertura di Experience Cloud ID: è possibile unire solo i visitatori con un ECID. Una percentuale inferiore di visitatori del sito che utilizza un ECID è correlata a tassi di compressione più bassi.
   * Utilizzo di più dispositivi: se i visitatori del sito non utilizzano più dispositivi, le percentuali di compressione potrebbero essere più basse.
   * Granularità del reporting: la compressione per giorno è generalmente inferiore della compressione per mese o per anno. Le possibilità che una sola persona utilizzi più dispositivi si riducono maggiormente in un singolo giorno che nell’arco di un mese intero. Segmentazione, filtraggio o utilizzo di dimensioni di raggruppamento possono mostrare inoltre un tasso di compressione più basso.
* **Segmenti basati sulle persone**: contiene un elenco a discesa dei segmenti che consente di visualizzare dati specifici per il dispositivo. Questo pannello incoraggia la sperimentazione con i segmenti per vedere in che modo i rapporti possono essere influenzati dall’inclusione o esclusione di tipi di dispositivi.
* **Analisi del percorso tra dispositivi**: fornisce rapporti di flusso e di fallout in base al tipo di dispositivo.
* **Attribuzione tra dispositivi**: combina le funzioni di analisi tra dispositivi e attribuzione.
* **Altri suggerimenti e trucchi**: argomenti utili che riguardano CDA e permettono di ottenere il massimo dal suo utilizzo.

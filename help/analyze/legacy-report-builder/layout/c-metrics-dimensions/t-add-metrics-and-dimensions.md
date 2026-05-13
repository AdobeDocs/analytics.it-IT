---
description: Scopri i passaggi per aggiungere metriche e dimensioni a una richiesta.
title: Aggiungere metriche e dimensioni
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
TQID: https://experienceleague.adobe.com/nKf59WLxvtYrcyR-mQ8oM41rUDLl3qpkwbujRDBV27A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 544
ht-degree: 2%

---

# Aggiungere metriche e dimensioni

{{legacy-arb}}

Passaggi per aggiungere metriche e dimensioni a una richiesta.

1. Utilizza il modulo [!UICONTROL Request Wizard: Step 1] per [creare la richiesta di dati](/help/analyze/legacy-report-builder/data-requests/data-requests.md), quindi fai clic su **[!UICONTROL Next]**.
1. Nel modulo [!UICONTROL Request Wizard: Step 2] fare doppio clic sulle metriche o trascinarle nella posizione desiderata.

   ![Schermata che mostra la Richiesta guidata: passaggio 2 con una freccia che punta dall&#39;elenco delle metriche alla sezione di visualizzazione della pagina desiderata.](assets/adding_metrics.png)

   Quando si aggiungono metriche, queste non vengono rimosse dalla scheda [!UICONTROL Metrics], in quanto è possibile visualizzare le metriche più volte all&#39;interno di una richiesta. Ad esempio, puoi visualizzare il subtotale della metrica in aggiunta a ciascun valore. Tuttavia, l’elenco delle metriche disponibili cambia ogni volta che aggiungi o rimuovi una dimensione.

   È possibile aggiungere solo metriche alla sezione di layout [!UICONTROL Metrics]. Le metriche vengono aggiunte al layout [!UICONTROL Column Label] come [!UICONTROL Metric Header]. Se sposti un [!UICONTROL Metric Header] da [!UICONTROL Column Layout] a [!UICONTROL Row Layout], viene visualizzato lì e viene utilizzato come metrica di suddivisione.

   Nella scheda Metriche, immediatamente sopra l’elenco Metriche, viene visualizzata una barra di ricerca.

   ![Schermata che mostra la barra di ricerca delle metriche.](assets/search_bar_metric.png)

## Linee guida

Quando aggiungi metriche e dimensioni, considera le seguenti linee guida.

* Quando inserisci un termine di ricerca, l’elenco viene aggiornato automaticamente in modo da visualizzare le metriche con etichette che corrispondono al termine di ricerca.
* La corrispondenza è senza distinzione tra maiuscole e minuscole ed equivale a una ricerca *contains*.
* Ricerche di parole complete e altri contrassegni di ricerca speciali (inizia con, termina con, E, O, ecc.) non sono supportati.

Il termine di ricerca viene cancellato se si esce dalla Creazione guidata richieste quando si fa clic su [!UICONTROL Finish] o [!UICONTROL Cancel], si torna al Passaggio 1 della Creazione guidata richieste o si modifica la categoria della metrica.

Il termine di ricerca non viene cancellato:

* Quando trascini e rilasci (o fai doppio clic) un elemento metrico dall’elenco, in modo che venga aggiunto al pannello Layout pivot/Metriche layout personalizzate.
* Quando rimuovi uno o più elementi metrici dal pannello Metrica layout pivot/layout personalizzato.
* Quando fai clic sulla scheda Dimension, torna alla scheda Metrica.
* Quando si richiamano altri sottomoduli (modali o non modali) che all&#39;uscita torneranno al Passaggio 2 della Creazione guidata richieste. Esempi di questi moduli sono

   * Dimension Filter Forms
   * Formattazione intervallo di date Forms
   * Modulo opzioni formato
   * Modulo testo pre-pend-postpend
   * Modulo posizione intervallo di output

## Ordinare una richiesta per metrica

Facoltativamente, puoi ordinare una richiesta per metrica.

Per ordinare una richiesta per metrica

1. Fai clic sull’etichetta della metrica.
1. Aggiungere dimensioni. Aggiungere dimensioni nello stesso modo in cui si aggiungono le metriche. Vedere i passaggi 1 e 2 sopra.

   Nella scheda [!UICONTROL Dimensions], il sistema visualizza le dimensioni che si suddividono o sono una classificazione di qualsiasi report di base selezionato in [!UICONTROL Request Wizard: Step 1] e sulla configurazione della suite di rapporti. Quando si rilascia una dimensione nelle griglie di layout, questa viene rimossa dalla vista ad albero e ricalcola l&#39;elenco delle dimensioni rimanenti disponibili.

   La dimensione [!UICONTROL Date] viene aggiunta automaticamente. Le dimensioni data disponibili variano a seconda della granularità selezionata da [!UICONTROL Request Wizard: Step 1]. I valori validi sono:

   * Ora
   * Giorno
   * Settimana
   * Mese
   * Anno
   * Intervallo di date (quando non è specificata alcuna granularità)

1. Modificare le metriche e le dimensioni configurando [opzioni di formato](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md) e filtri.
1. Fai clic su **[!UICONTROL Finish]**.
Nell&#39;esempio seguente, le dimensioni si riferiscono alla metrica [!UICONTROL Page]. La dimensione [!UICONTROL Referring Domain] crea un rapporto di suddivisione tra [!UICONTROL Page] e [!UICONTROL Referring Domain]. La scheda [!UICONTROL Dimension] viene aggiornata con le sole dimensioni che è possibile aggiungere a un report di suddivisione.

   ![Schermata che mostra le dimensioni relative alla metrica.](assets/page_pageview_02.png)

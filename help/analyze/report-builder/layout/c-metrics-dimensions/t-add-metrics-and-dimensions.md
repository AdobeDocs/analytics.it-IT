---
description: Scopri i passaggi per aggiungere metriche e dimensioni a una richiesta.
title: Aggiungere metriche e dimensioni
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# Aggiungere metriche e dimensioni

Passaggi per aggiungere metriche e dimensioni a una richiesta.

1. Utilizza il [!UICONTROL Request Wizard: Step 1] modulo a [Creare la richiesta di dati](/help/analyze/report-builder/data-requests/data-requests.md)  quindi fai clic su **[!UICONTROL Next]**.
1. In [!UICONTROL Request Wizard: Step 2] , fare doppio clic sulle metriche o trascinarle nella posizione desiderata.

   ![Schermata che mostra la Richiesta guidata: passaggio 2 con una freccia che punta dall’elenco delle metriche alla sezione di visualizzazione della pagina desiderata.](assets/adding_metrics.png)

   Le metriche aggiunte non vengono rimosse dal [!UICONTROL Metrics] perché è possibile visualizzare le metriche più volte all’interno di una richiesta. Ad esempio, puoi visualizzare il subtotale della metrica in aggiunta a ciascun valore. Tuttavia, l’elenco delle metriche disponibili cambia ogni volta che aggiungi o rimuovi una dimensione.

   È possibile aggiungere solo metriche al [!UICONTROL Metrics] sezione layout. Le metriche vengono aggiunte al [!UICONTROL Column Label] layout come [!UICONTROL Metric Header]. Se si sposta una [!UICONTROL Metric Header] da [!UICONTROL Column Layout] a [!UICONTROL Row Layout], viene visualizzata e viene utilizzata come metrica di raggruppamento.

   Nella scheda Metriche, immediatamente sopra l’elenco Metriche, viene visualizzata una barra di ricerca.

   ![Schermata che mostra la barra di ricerca Metriche.](assets/search_bar_metric.png)

## Linee guida

Quando aggiungi metriche e dimensioni, considera le seguenti linee guida.

* Quando inserisci un termine di ricerca, l’elenco viene aggiornato automaticamente in modo da visualizzare le metriche con etichette che corrispondono al termine di ricerca.
* La corrispondenza è senza distinzione tra maiuscole e minuscole ed equivale a una *contiene* ricerca.
* Ricerche di parole complete e altri contrassegni di ricerca speciali (inizia con, termina con, E, O, ecc.) non sono supportati.

Il termine di ricerca viene cancellato se si esce dalla Creazione guidata richieste facendo clic su [!UICONTROL Finish] o [!UICONTROL Cancel], o tornare al Passaggio 1 della Creazione guidata richieste o modificare la categoria della metrica.

Il termine di ricerca non viene cancellato:

* Quando trascini e rilasci (o fai doppio clic) un elemento metrico dall’elenco, in modo che venga aggiunto al pannello Layout pivot/Metriche layout personalizzate.
* Quando rimuovi uno o più elementi metrici dal pannello Metrica layout pivot/layout personalizzato.
* Quando fai clic sulla scheda Dimension, quindi torna alla scheda Metrica.
* Quando si richiamano altri sottomoduli (modali o non modali) che all&#39;uscita torneranno al Passaggio 2 della Creazione guidata richieste. Esempi di questi moduli sono

   * Forms filtro Dimension
   * Formattazione intervallo di date Forms
   * Modulo opzioni formato
   * Modulo testo pre-pend-postpend
   * Modulo posizione intervallo di output

## Ordinare una richiesta per metrica

Facoltativamente, puoi ordinare una richiesta per metrica.

Per ordinare una richiesta per metrica

1. Fai clic sull’etichetta della metrica.
1. Aggiunta di dimensioni. Aggiungere dimensioni nello stesso modo in cui si aggiungono le metriche. Vedere i passaggi 1 e 2 sopra.

   Il giorno [!UICONTROL Dimensions] , il sistema visualizza le dimensioni che si suddividono o sono una classificazione di qualsiasi rapporto di base selezionato [!UICONTROL Request Wizard: Step 1]e sulla configurazione della suite di rapporti. Quando si rilascia una dimensione nelle griglie di layout, questa viene rimossa dalla vista ad albero e ricalcola l&#39;elenco delle dimensioni rimanenti disponibili.

   Il [!UICONTROL Date] viene aggiunta automaticamente. Le dimensioni data disponibili variano a seconda della granularità selezionata dall’opzione [!UICONTROL Request Wizard: Step 1]. I valori validi sono:

   * Ora
   * Giorno
   * Settimana
   * Mese
   * Anno
   * Intervallo di date (quando non è specificata alcuna granularità)

1. Modificare metriche e dimensioni tramite la configurazione di [opzioni di formato](/help/analyze/report-builder/layout/t-format-display-headers.md) filtri e.
1. Fai clic su **[!UICONTROL Finish]** (Usa modello di attribuzione non predefinito).
Nell&#39;esempio seguente, le quote si riferiscono al [!UICONTROL Page] metrica. Il [!UICONTROL Referring Domain] crea un rapporto di suddivisione tra [!UICONTROL Page] e [!UICONTROL Referring Domain]. Il [!UICONTROL Dimension] La scheda viene aggiornata con solo le dimensioni che puoi aggiungere a un rapporto di suddivisione.

   ![Schermata che mostra le dimensioni relative alla metrica.](assets/page_pageview_02.png)

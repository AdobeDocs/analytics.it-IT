---
description: Passaggi per aggiungere metriche e dimensioni a una richiesta.
title: Aggiungere metriche e dimensioni
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 3%

---

# Aggiungere metriche e dimensioni

Passaggi per aggiungere metriche e dimensioni a una richiesta.

1. [Creare la richiesta di dati](/help/analyze/report-builder/data-requests/data-requests.md) il [!UICONTROL Request Wizard: Step 1], quindi fai clic su **[!UICONTROL Next]**.
1. Il giorno [!UICONTROL Request Wizard: Step 2], fare doppio clic sulle metriche o trascinarle nella posizione desiderata.

   ![Informazioni sul passaggio](assets/adding_metrics.png)

   Le metriche aggiunte non vengono rimosse dal [!UICONTROL Metrics] perché è possibile visualizzare le metriche più volte all’interno di una richiesta. Ad esempio, puoi visualizzare il subtotale della metrica in aggiunta a ciascun valore. Tuttavia, l’elenco delle metriche disponibili cambia ogni volta che aggiungi o rimuovi una dimensione.

   È possibile aggiungere solo metriche al [!UICONTROL Metrics] sezione layout. Le metriche vengono aggiunte al [!UICONTROL Column Label] layout come [!UICONTROL Metric Header]. Se si sposta una [!UICONTROL Metric Header] da [!UICONTROL Column Layout] a [!UICONTROL Row Layout], viene visualizzata e viene utilizzata come metrica di raggruppamento.

   Nella scheda Metriche, immediatamente sopra l’elenco Metriche, viene visualizzata una barra di ricerca.

   ![](assets/search_bar_metric.png)

   Aspetti da considerare:

   * Quando immetti un termine di ricerca, l’elenco viene aggiornato automaticamente in modo da visualizzare solo le metriche la cui etichetta corrisponde al termine di ricerca.
   * La corrispondenza non distingue tra maiuscole e minuscole ed equivale a una ricerca &quot;contiene&quot;.
   * Ricerche di parole intere o altri contrassegni di ricerca speciali (iniziano con, terminano con, AND, OR, ecc.) non sono supportati.

      Il termine di ricerca verrà cancellato se si esce dalla Creazione guidata richieste (ad esempio, si fa clic su Fine o Annulla), o si torna al Passaggio 1 della Creazione guidata richieste o si modifica la categoria della metrica.

      Il termine di ricerca non verrà cancellato nei seguenti casi:

   * Trascina e rilascia (o fai doppio clic) uno degli elementi metrici dall’elenco, in modo che venga aggiunto al pannello Layout pivot/Metriche layout personalizzate.
   * È possibile rimuovere uno o più elementi di metrica dal pannello Layout pivot/Metrica layout personalizzato.
   * Fai clic sulla scheda Dimension, quindi torna alla scheda Metrica.
   * Richiamare altri sottomoduli (modali o non modali) che all&#39;uscita torneranno al Passaggio 2 della Creazione guidata richieste. Esempi di questi moduli sono

      * Forms filtro Dimension
      * Formattazione intervallo di date Forms
      * Modulo opzioni formato
      * Modulo testo pre-pend-postpend
      * Modulo posizione intervallo di output

1. (Facoltativo) Per ordinare una richiesta per metrica, fai clic sull’etichetta della metrica.
1. Aggiungere dimensioni nello stesso modo in cui si aggiungono le metriche.

Il giorno [!UICONTROL Dimensions] , il sistema visualizza le dimensioni che si suddividono o sono una classificazione di qualsiasi rapporto di base selezionato al passaggio 1 e sulla configurazione della suite di rapporti. Quando si rilascia una dimensione alle griglie di layout, questa viene rimossa dalla vista ad albero e ricalcola l&#39;elenco delle dimensioni rimanenti disponibili.

Il [!UICONTROL Date] viene aggiunta automaticamente. Le dimensioni data disponibili variano a seconda della granularità selezionata dall’opzione [!UICONTROL Request Wizard: Step 1]. (I valori validi sono:

    * Ora
    * Giorno
    * Settimana
    * Mese
    * Anno
    * Intervallo di date (quando non è specificata alcuna granularità)

1. Modificare metriche e dimensioni tramite la configurazione di [opzioni di formato](/help/analyze/report-builder/layout/t-format-display-headers.md) filtri e.
1. Fai clic su **[!UICONTROL Finish]** (Usa modello di attribuzione non predefinito).
Nell&#39;esempio seguente, le quote si riferiscono al [!UICONTROL Page] metrica. Ecco, il [!UICONTROL Referring Domain] crea un rapporto di suddivisione tra [!UICONTROL Page] e [!UICONTROL Referring Domain]. Il [!UICONTROL Dimension] La scheda viene aggiornata con solo le dimensioni che puoi aggiungere a un rapporto di suddivisione.

![](assets/page_pageview_02.png)

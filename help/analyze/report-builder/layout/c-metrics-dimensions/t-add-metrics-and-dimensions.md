---
description: Passaggi per aggiungere metriche e dimensioni a una richiesta.
title: Aggiungere metriche e dimensioni
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
feature: Report Builder
role: User, Admin
exl-id: d4e36b69-b5aa-43e5-b394-3b6d93143f15
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 3%

---

# Aggiungere metriche e dimensioni

Passaggi per aggiungere metriche e dimensioni a una richiesta.

1. [Crea la ](/help/analyze/report-builder/data-requests/data-requests.md) richiesta di dati su  [!UICONTROL Request Wizard: Step 1], quindi fai clic su  **[!UICONTROL Next]**.
1. In [!UICONTROL Request Wizard: Step 2], fai doppio clic sulle metriche o trascinale nella posizione desiderata.

   ![Informazioni sul passaggio](assets/adding_metrics.png)

   Quando aggiungi delle metriche, queste non vengono rimosse dalla scheda [!UICONTROL Metrics] perché puoi visualizzarle più volte all’interno di una richiesta. Ad esempio, puoi visualizzare il subtotale della metrica in aggiunta a ciascun valore. Tuttavia, l’elenco delle metriche disponibili cambia ogni volta che aggiungi o rimuovi una dimensione.

   Puoi aggiungere solo metriche alla sezione di layout [!UICONTROL Metrics] . Le metriche vengono aggiunte al layout [!UICONTROL Column Label] come [!UICONTROL Metric Header]. Se si sposta un [!UICONTROL Metric Header] da [!UICONTROL Column Layout] a [!UICONTROL Row Layout], questo viene visualizzato e viene utilizzato come metrica di suddivisione.

   Una barra di ricerca viene visualizzata nella scheda Metriche, appena sopra l’elenco Metrica .

   ![](assets/search_bar_metric.png)

   Nota bene:

   * Quando si immette un termine di ricerca, l’elenco viene aggiornato automaticamente per visualizzare solo le metriche la cui etichetta corrisponde al termine di ricerca.
   * La corrispondenza non distingue tra maiuscole e minuscole ed equivale a una ricerca &quot;contiene&quot;.
   * Ricerche a parole intere o altri flag di ricerca speciali (inizia con, termina con, AND, OR, ecc.) non sono supportati.

      Il termine di ricerca verrà cancellato se si esce dalla Creazione guidata richieste (ad esempio, fare clic su Fine o Annulla), oppure tornare al Passaggio 1 della Creazione guidata richieste o modificare la categoria Metrica.

      Il termine Ricerca non viene cancellato nei seguenti casi:

   * Trascina e rilascia (o fai doppio clic) uno degli elementi della metrica dall’elenco in modo che venga aggiunto al pannello Metriche di layout pivot/layout personalizzato.
   * È possibile rimuovere un elemento di metrica dal pannello Metrica layout pivot/layout personalizzato.
   * Fai clic sulla scheda Dimension , quindi torna alla scheda Metrica .
   * Si richiamano altri sottomoduli (modali o modelli) che al momento dell&#39;uscita torneranno al Passaggio 2 della Creazione guidata richieste. Esempi di questi moduli sono

      * Dimension Filter Forms
      * Formattazione intervallo date Forms
      * Formato Opzioni
      * Modulo di testo pre-pubblicazione
      * Modulo di posizione dell’intervallo di output

1. (Facoltativo) Per ordinare una richiesta per metrica, fai clic sull’etichetta metrica.
1. Aggiungi le dimensioni nello stesso modo in cui aggiungi le metriche.

Nella scheda [!UICONTROL Dimensions] , il sistema visualizza le dimensioni che si suddividono o sono una classificazione di qualsiasi rapporto di base selezionato al passaggio 1 e sulla configurazione della suite di rapporti. Quando rilasci una dimensione nelle griglie di layout, questa viene rimossa dalla vista ad albero e ricalcola l’elenco delle dimensioni rimanenti disponibili.

La dimensione [!UICONTROL Date] viene aggiunta automaticamente. Le dimensioni della data disponibili variano a seconda della granularità selezionata dal [!UICONTROL Request Wizard: Step 1]. (I valori validi sono:

    * Ora
    * Giorno
    * Settimana
    * Mese
    * Anno
    * Intervallo di date (quando non è specificata alcuna granularità)

1. Modifica metriche e dimensioni configurando [opzioni di formato](/help/analyze/report-builder/layout/t-format-display-headers.md) e filtri.
1. Fai clic su **[!UICONTROL Finish]**.
Nell’esempio seguente, le dimensioni si riferiscono alla metrica [!UICONTROL Page] . In questo caso, la dimensione [!UICONTROL Referring Domain] crea un rapporto di suddivisione tra [!UICONTROL Page] e [!UICONTROL Referring Domain]. La scheda [!UICONTROL Dimension] viene aggiornata con solo le dimensioni che puoi aggiungere a un rapporto di suddivisione.

![](assets/page_pageview_02.png)

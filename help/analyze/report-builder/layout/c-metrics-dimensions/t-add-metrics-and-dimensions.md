---
description: Passaggi per aggiungere metriche e dimensioni a una richiesta.
seo-description: Passaggi per aggiungere metriche e dimensioni a una richiesta.
seo-title: Aggiungere metriche e dimensioni
solution: Analytics
title: Aggiungere metriche e dimensioni
topic: Generatore di report
uuid: 588ce96b-3a2d-42b7-8a8e-7e6f448a0115
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Aggiungere metriche e dimensioni

Passaggi per aggiungere metriche e dimensioni a una richiesta.

1. [Crea la richiesta](/help/analyze/report-builder/data-requests/data-requests.md) di dati sul [!UICONTROL Request Wizard: Step 1], quindi fai clic su **[!UICONTROL Next]**.
1. Fate [!UICONTROL Request Wizard: Step 2]doppio clic sulle metriche o trascinatele nella posizione desiderata.

   ![Informazioni sul passaggio](assets/adding_metrics.png)

   Quando aggiungi delle metriche, queste non vengono rimosse dalla [!UICONTROL Metrics] scheda, perché puoi visualizzare le metriche più volte all'interno di una richiesta. Ad esempio, puoi visualizzare il subtotale della metrica oltre a ciascun valore. Tuttavia, l’elenco delle metriche disponibili cambia ogni volta che aggiungete o rimuovete una dimensione.

   È possibile aggiungere solo metriche alla sezione [!UICONTROL Metrics] del layout. Le metriche vengono aggiunte al [!UICONTROL Column Label] layout come [!UICONTROL Metric Header]. Se spostate un [!UICONTROL Metric Header] oggetto da [!UICONTROL Column Layout] a [!UICONTROL Row Layout], questo viene visualizzato e utilizzato come suddivisione.

   Una barra di ricerca viene visualizzata nella scheda Metriche, appena sopra l’elenco Metrica.

   ![](assets/search_bar_metric.png)

   Nota bene:

   * Quando immetti un termine di ricerca, l'elenco si aggiorna automaticamente per visualizzare solo le metriche la cui etichetta corrisponde al termine di ricerca.
   * La corrispondenza non fa distinzione tra maiuscole e minuscole ed equivale a una ricerca "contains".
   * Ricerche full-word o altri flag di ricerca speciale (inizia con, termina con, AND, OR, ecc.) non sono supportati.

      Il termine di ricerca verrà cancellato se si esce dalla Richiesta guidata (ad esempio, fare clic su Fine o Annulla), oppure tornare al Passaggio 1 della Richiesta guidata oppure modificare la categoria Metrica.

      Il termine di ricerca non verrà cancellato nei seguenti casi:

   * Trascinate e rilasciate (o fate doppio clic) una delle metriche dall’elenco in modo che venga aggiunta al pannello Metriche layout pivot/personalizzato.
   * È possibile rimuovere uno o più elementi della metrica dal pannello Metrica layout pivot/personalizzato.
   * Fai clic sulla scheda Dimensione, quindi torna alla scheda Metrica.
   * È possibile richiamare altri sottomoduli (modali o modelli) che all'uscita torneranno al Passaggio 2 della Richiesta guidata. Esempi di questi moduli sono

      * Moduli filtro dimensioni
      * Moduli di formattazione intervallo date
      * Formato opzioni
      * Modulo testo pre-postpend
      * Modulo posizione intervallo di output

1. (Facoltativo) Per ordinare una richiesta per metrica, fai clic sull’etichetta della metrica.
1. Aggiungi le dimensioni allo stesso modo in cui aggiungi le metriche.

Nella [!UICONTROL Dimensions] scheda, il sistema visualizza le dimensioni che si suddividono o sono una classificazione di qualsiasi rapporto di base selezionato al Passaggio 1 e nella configurazione della suite di rapporti. Quando rilasci una dimensione nelle griglie di layout, questa viene rimossa dalla vista ad albero e ricalcola l’elenco delle dimensioni rimanenti disponibili.

La [!UICONTROL Date] dimensione viene aggiunta automaticamente. Le dimensioni della data disponibili variano in base alla granularità selezionata dall’ [!UICONTROL Request Wizard: Step 1]. (I valori validi sono:

    * Ora
    * Giorno
    * Settimana
    * Mese
    * Anno
    * Intervallo date (quando non è specificata alcuna granularità)

1. Modifica metriche e dimensioni configurando opzioni [e filtri per il](/help/analyze/report-builder/layout/t-format-display-headers.md) formato.
1. Fai clic su **[!UICONTROL Finish]**.
Nell'esempio seguente, le dimensioni si riferiscono alla [!UICONTROL Page] metrica. In questo caso, la [!UICONTROL Referring Domain] dimensione crea un rapporto di suddivisione tra [!UICONTROL Page] e [!UICONTROL Referring Domain]. La [!UICONTROL Dimension] scheda viene aggiornata con solo le dimensioni che è possibile aggiungere a un report dettagliato.

![](assets/page_pageview_02.png)

---
description: Passaggi per aggiungere metriche e dimensioni a una richiesta.
seo-description: Passaggi per aggiungere metriche e dimensioni a una richiesta.
seo-title: Aggiunta di metriche e dimensioni
solution: Analytics
title: Aggiunta di metriche e dimensioni
topic: Generatore di report
uuid: 588 ce 96 b -3 a 2 d -42 b 7-8 a 8 e -7 e 6 f 448 a 0115
translation-type: tm+mt
source-git-commit: 2a37aa64634db50320d149298b467bcc7f954eb6

---


# Aggiunta di metriche e dimensioni

Passaggi per aggiungere metriche e dimensioni a una richiesta.

1. [Create la richiesta dati](../../../../analyze/report-builder/data-requests/data-requests.md#concept_E14C1E6B63C44D02BF8D80021B4B0F89) sulla [!UICONTROL Request Wizard: Step 1], quindi fate clic **[!UICONTROL Next]** su.
1. On the [!UICONTROL Request Wizard: Step 2], double-click metrics, or drag them to the desired position.

   ![Informazioni passo](assets/adding_metrics.png)

   When you add metrics, they are not removed from the [!UICONTROL Metrics] tab, because you can display metrics multiple times within a request. Ad esempio, potete visualizzare la metrica subtotale oltre a ogni valore. Tuttavia, l'elenco delle metriche disponibili cambia ogni volta che aggiungete o rimuovete una dimensione.

   You can add only metrics to the [!UICONTROL Metrics] layout section. Metrics are added to the [!UICONTROL Column Label] layout as a [!UICONTROL Metric Header]. If you move a [!UICONTROL Metric Header] from [!UICONTROL Column Layout] to [!UICONTROL Row Layout], it is displayed there and is used as a metric as a breakdown.

   Nella scheda Metriche, sopra l'elenco Metriche, viene visualizzata una barra di ricerca.

   ![](assets/search_bar_metric.png)

   Nota bene:

   * Quando immetti un termine di ricerca, l'elenco si aggiorna automaticamente per visualizzare solo le metriche la cui etichetta corrisponde al termine di ricerca.
   * La corrispondenza non fa distinzione tra maiuscole e minuscole e equivale a una ricerca "contiene".
   * Ricerche a parola intera o un altro flag di ricerca speciale (con, con, AND, ecc.) non sono supportati.

      Il termine Ricerca verrà cancellato se esci dalla richiesta guidata (ad es., fai clic su Fine o Annulla), oppure torni alla procedura guidata Richiedi 1 oppure cambia la categoria Metrica.

      Il termine Ricerca non verrà cancellato nei casi seguenti:

   * Trascina e rilascia (o fai doppio clic) uno degli elementi della metrica nell'elenco in modo che venga aggiunto al pannello Metriche di layout pivot/personalizzato.
   * Rimuovi un elemento di metrica dal pannello Metriche di layout pivot/layout personalizzato.
   * Fai clic sulla scheda Dimensione, quindi ritorna alla scheda Metrica.
   * Richiamate altri sottomoduli (modali o modali) che all'uscita torneranno alla richiesta guidata richiesta 2. Esempi di questi moduli sono

      * Moduli filtro dimensione
      * Moduli Formattazione intervalli di date
      * Modulo Opzioni formato
      * Premete il modulo Testo preliminare
      * Modulo di posizione intervallo di output

1. (Facoltativo) Per ordinare una richiesta per metrica, fai clic sull'etichetta della metrica.
1. Aggiungi dimensioni nello stesso modo in cui aggiungi le metriche.

On the [!UICONTROL Dimensions] tab, the system displays dimensions that break down or are a classification of any base report you select on Step 1, and on the configuration of the report suite. Quando rilasci una dimensione nelle griglie di layout, questa viene rimossa dalla vista ad albero e ricalcola l'elenco delle dimensioni rimanenti disponibili.

[!UICONTROL Date] La dimensione viene aggiunta automaticamente. Available date dimensions change depending on the selected granularity from the [!UICONTROL Request Wizard: Step 1]. (I valori validi sono:

    * Ora
    * Giorno
    * Settimana
    * Mese
    * Anno * Anno
    * Intervallo di date (quando non è specificata alcuna granularità)

1. Modify metrics and dimensions by configuring [format options](../../../../analyze/report-builder/layout/t-format-display-headers.md#task_45C7C4938C2C47FCB02634A1248AA831) and filters.
1. Fai clic su **[!UICONTROL Finish]**.
In the following example, dimensions relate to the [!UICONTROL Page] metric. Here, the [!UICONTROL Referring Domain] dimension creates a breakdown report between [!UICONTROL Page] and [!UICONTROL Referring Domain]. [!UICONTROL Dimension] La scheda viene aggiornata con solo le dimensioni che puoi aggiungere a un rapporto dettagliato.

![](assets/page_pageview_02.png)
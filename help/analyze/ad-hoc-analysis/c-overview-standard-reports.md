---
description: I report standard mostrano dati per attività di siti Web e visitatori, pattern di traffico, dati di riferimento, campagne pubblicitarie, mantenimento dei visitatori, dati sui prodotti e altro ancora. Puoi eseguire rapporti e quindi accedere agli strumenti per configurare segmenti, metriche e confronti di report.
seo-description: I report standard mostrano dati per attività di siti Web e visitatori, pattern di traffico, dati di riferimento, campagne pubblicitarie, mantenimento dei visitatori, dati sui prodotti e altro ancora. Puoi eseguire rapporti e quindi accedere agli strumenti per configurare segmenti, metriche e confronti di report.
seo-title: Panoramica sui report
solution: Analytics
title: Panoramica sui report
topic: Analisi ad hoc
uuid: 36722 dcd -5 dc 9-4047-8 a 17-16 de 876193 bf
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica sui report

I report standard mostrano dati per attività di siti Web e visitatori, pattern di traffico, dati di riferimento, campagne pubblicitarie, mantenimento dei visitatori, dati sui prodotti e altro ancora. Puoi eseguire rapporti e quindi accedere agli strumenti per configurare segmenti, metriche e confronti di report.

## Reports overview {#concept_41459A705F2048EEA4EFA80F6BD9FFAB}

I report standard mostrano dati per attività di siti Web e visitatori, pattern di traffico, dati di riferimento, campagne pubblicitarie, mantenimento dei visitatori, dati sui prodotti e altro ancora. Puoi eseguire rapporti e quindi accedere agli strumenti per configurare segmenti, metriche e confronti di report.

Potete raccogliere dati personalizzati per creare rapporti specifici per il sito Web. Ad esempio, se si dispone di una funzione di ricerca sul sito Web, è possibile tenere traccia dei termini di ricerca inviati e creare un rapporto che mostra tali termini e i risultati delle ricerche.

Il set di report standard copre argomenti comuni a tutti i siti Web. I rapporti includono (ma non sono limitati):

* Dati sul sito Web
* Dati visitatore
* Pattern di traffico
* Dati di riferimento
* Campagne pubblicitarie
* Mantenimento dei visitatori
* Informazioni prodotto

Se utilizzate reporting e analisi di marketing, i tipi di report e i menu saranno familiari. Analisi ad hoc classifica i rapporti in base ai seguenti tipi:

**Rapporti di riepilogo**

Includes reports such as the [!UICONTROL Totals Report], which shows data designed for quick overviews. Questi sono pensati per i dirigenti che desiderano una panoramica generale dei dati.

**Report conversione**

I rapporti sulla conversione forniscono analisi complete, accurate e dettagliate dell'attività dei clienti. Metriche quali gestione delle campagne, ciclo di vendita, abbandono del cliente e conversione dei clienti consentono di misurare transazioni e-commerce, fonti di vendite, efficacia pubblicitaria, fidelizzazione dei clienti e molto altro.

**Rapporti sul traffico**

I rapporti sul traffico offrono informazioni approfondite sul modo in cui i visitatori interagiscono con il tuo sito web.

* Analizzare aspetti critici del comportamento dei visitatori.
* Monitorare e comprendere i pattern di traffico.
* Determinare il contenuto del sito più diffuso.
* Segmentare i visitatori in base a criteri misurabili.

## Campagne {#concept_A407CDF1D4AA49BAB396A1666E67FC87}

Visualizza informazioni sull'efficacia delle attività pubblicitarie. Potete vedere quali tipi di sforzi pubblicitari forniscono più traffico e quali dei dipendenti hanno la responsabilità di guidare tali sforzi.

<!-- 

c_reports_campaigns.xml

 -->

In genere tali rapporti sono personalizzati e quindi diversi per ogni analista. See [Campaign Manager](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=campaign_manager_admin) in the [!DNL Admin Console] help for more information.

## Statistical Calculations {#concept_83FF70DB7895435E985699FE9012D585}

Potete personalizzare le statistiche predefinite da visualizzare in un report classifica.

<!-- 

c_Statistical_Calculation_ad_hoc.xml

 -->

I calcoli statistici predefiniti aggiuntivi possono essere aggiunti ai report classificati in base alla visualizzazione al momento dell'esecuzione del rapporto, compresi significato, deviazione standard, deviazione standard e altri calcoli matematici valutati in base alle esigenze specifiche di reporting.

**Per aprire i calcoli statistici per Report classifica:**

1. Select **[!UICONTROL Tools]** &gt; **[!UICONTROL Ranked]** from the menu.

1. Select **[!UICONTROL Settings]**.
1. Select **[!UICONTROL Default Statistics]**.

**[!UICONTROL Ignore zeros in statistical calculations]**. Selezionate questa opzione per ignorare gli zero e assicuratevi che l'aggiunta di un'altra metrica non modifichi le medie già calcolate. Tutte le statistiche sono interessate da questa impostazione (anche se per Sum non ha alcun effetto).

| Calcolo | Descrizione |
|--- |--- |
| Max | Identifica il valore massimo su tutte le righe per un set di dati specificato. |
| Min | Identifica il valore minimo su tutte le righe per un set di dati specificato. |
| Sum | Un calcolo di tutti i valori di ogni riga nel set di dati. Ad esempio, la somma aggrega tutte le visite di un visitatore invece di conteggiare una sola volta (indipendentemente dal numero di visite). È un totale complessivo dei punti dati raccolti. |
| Significato | Il significato è la media aritmetica dei valori delle righe in un set di dati, calcolato dalla somma divisa per il conteggio (sum/count). La significato è influenzata dai dati sottostanti, a differenza del median utilizzato generalmente per distribuzioni inclinate. |
| Deviazione standard | La deviazione standard mostra il numero di variazioni presenti nel significato previsto. Una deviazione standard inferiore mostra i punti dati vicini al significato. Una deviazione standard più elevata mostra che i punti dati sono distribuiti su un'ampia gamma di valori. |
| Mediana | Il median è il valore numerico che separa la metà più elevata di un dato dalla metà inferiore per le righe di un set di dati. A differenza del significato, viene generalmente utilizzato per evitare valori non superiori. |
| Quartiles | Un quartile è il set di valori nel set di dati identificati da tre punti che dividono i dati in quattro gruppi uguali, ciascuno dei quali comprende un quarto del set di dati. La prima quartile è il 25 percentile, mentre la terza quartile è il 75 percentile. Il secondo quartile è Median e il quarto quartile è Sum. |
| Count | Restituisce il numero di righe in un set di dati. |

## Example of Mean vs. Metric Total Calculations {#section_7C49196503964FB0A429FA347BC92D09}

La funzione Mean (Significato) è calcolata in modo analogo alle colonne di dati in Microsoft Excel. In particular, this means that the **Mean** of a ratio (such as determining the average bounce rate) would be the average of the ratios, not the ratio of the averages. The ratio of the averages includes the **Total** of the bounce rate metric.

<table id="table_9EC56B15C6A340DA8917CB0DBCAC2355"> 
 <thead> 
  <tr> 
   <th colname="col1" align="center" class="entry"> Data </th> 
   <th colname="col2" align="center" class="entry"> Visite singole </th> 
   <th colname="col3" align="center" class="entry"> Ingressi </th> 
   <th colname="col4" align="center" class="entry"> Bounce Rate </th> 
   <th colname="col5" align="center" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <p>Giugno 2013 </p> <p>Luglio 2013 </p> <p>Agosto 2013 </p> </td> 
   <td colname="col2" align="center"> <p>344 </p> <p>297 </p> <p>41 </p> </td> 
   <td colname="col3" align="center"> <p>1000 </p> <p>1000 </p> <p>1000 </p> </td> 
   <td colname="col4" align="center"> <p>34.4% </p> <p>29.7% </p> <p>41.0% </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1" align="center" valign="middle"><b>Significato</b> </td> 
   <td colname="col2" valign="middle"> (344+297+41)/3 </td> 
   <td colname="col3" valign="middle"> (1000+1000+100)/3 </td> 
   <td colname="col4" valign="middle" align="right"> (34.4 + 29.7 + 41.0) / 3 = <b>35.0</b>% </td> 
   <td colname="col5" valign="middle"><b>Significato dei rapporti</b> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1" align="center" valign="middle"><b>Totale metrica</b> </td> 
   <td colname="col2" valign="middle"> 682 </td> 
   <td colname="col3" valign="middle"> 2100 </td> 
   <td colname="col4" valign="middle" align="right"> 682 / 2100 = <b>32.0</b>% </td> 
   <td colname="col5" valign="middle"><b>Rapporto tra mezzi</b> </td> 
  </tr> 
 </tbody> 
</table>

## Statistical Calculation Overlays {#concept_97E1B32DAC734C7B9F8899717283CEEC}

Analisi ad hoc ora fornisce visualizzazioni sovrapposizioni di calcoli statistici per rapporti che mostrano dati nel tempo (minuti, ore, giorni, settimane).

<!-- 

c_overlay_calculations.xml

 -->

In a report that identifies data over a period of time, the **[!UICONTROL Statistics]** button lets you select calculations that will display as overlays across the report time line.

![](assets/overlay_calculations.png)

In addition to standard [Statistical Calculations](../../analyze/ad-hoc-analysis/c-overview-standard-reports.md#concept_83FF70DB7895435E985699FE9012D585), you can select the 1st, 2nd, and 3rd standard deviations in the overlays.

## Group Manager {#concept_E1433974A61144858E87334C006982B2}

Rather than using a single page in a report, you can group multiple pages and use them as categories for starting, intermediate, or destination location in the [!UICONTROL Fallout] and [!UICONTROL Site Analysis] reports. Potete modificare i gruppi dal menu principale o direttamente dal rapporto. Categories that you have created in marketing reports and analytics also appear in the [!UICONTROL Checkpoint Selector] list.

<!-- 

c_groups.xml

 -->

Click **[!UICONTROL Tools]** &gt; **[!UICONTROL Group Manager]**.

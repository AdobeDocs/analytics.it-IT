---
description: I rapporti standard mostrano i dati per il sito Web e l'attività del visitatore, i pattern di traffico, i dati di riferimento, le campagne pubblicitarie, la conservazione dei visitatori, i dati sui prodotti e altro ancora. Puoi eseguire report e quindi accedere a strumenti per configurare segmenti, metriche e confronti di report.
seo-description: I rapporti standard mostrano i dati per il sito Web e l'attività del visitatore, i pattern di traffico, i dati di riferimento, le campagne pubblicitarie, la conservazione dei visitatori, i dati sui prodotti e altro ancora. Puoi eseguire report e quindi accedere a strumenti per configurare segmenti, metriche e confronti di report.
seo-title: Panoramica sui report
solution: Analytics
title: Panoramica sui report
topic: Analisi ad hoc
uuid: 36722dcd-5dc9-4047-8a17-16de876193bf
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Panoramica sui report

I rapporti standard mostrano i dati per il sito Web e l'attività del visitatore, i pattern di traffico, i dati di riferimento, le campagne pubblicitarie, la conservazione dei visitatori, i dati sui prodotti e altro ancora. Puoi eseguire report e quindi accedere a strumenti per configurare segmenti, metriche e confronti di report.

## Panoramica sui report {#concept_41459A705F2048EEA4EFA80F6BD9FFAB}

I rapporti standard mostrano i dati per il sito Web e l'attività del visitatore, i pattern di traffico, i dati di riferimento, le campagne pubblicitarie, la conservazione dei visitatori, i dati sui prodotti e altro ancora. Puoi eseguire report e quindi accedere a strumenti per configurare segmenti, metriche e confronti di report.

Potete raccogliere dati personalizzati per creare rapporti specifici per il sito Web. Ad esempio, se disponete di una funzione di ricerca nel sito Web, potete tenere traccia dei termini di ricerca inviati e creare un rapporto che mostra questi termini e i risultati delle ricerche.

Il set di rapporti standard include argomenti comuni a tutti i siti Web. I rapporti includono (ma non sono limitati a):

* Dati del sito Web
* Dati visitatore
* Pattern di traffico
* Dati di riferimento
* Campagne pubblicitarie
* Conservazione dei visitatori
* Informazioni prodotto

Se usi i reporting e analisi di marketing, i tipi di report e i menu saranno familiari. L'analisi ad hoc classifica i rapporti in base ai seguenti tipi:

**Report di riepilogo**

Include rapporti come il [!UICONTROL Totals Report], che mostra i dati progettati per le panoramiche rapide. Sono destinati ai dirigenti che desiderano una panoramica generale dei dati.

**Report di conversione**

I rapporti di conversione forniscono un'analisi completa, accurata e dettagliata dell'attività del cliente. Metriche come la gestione delle campagne, il ciclo di vendita, l'abbandono del cliente e la conversione del cliente consentono di misurare le transazioni di e-commerce, le fonti di vendita, l'efficacia della pubblicità, la fedeltà dei clienti e altro ancora.

**Rapporti sul traffico**

I rapporti sul traffico forniscono informazioni approfondite sul modo in cui i visitatori interagiscono con il sito Web.

* Analyze critical aspects of visitor behavior.
* Monitor and understand traffic patterns.
* Consente di determinare il contenuto del sito più popolare.
* Segmenta i visitatori in base a qualsiasi criterio misurabile.

## Campagne {#concept_A407CDF1D4AA49BAB396A1666E67FC87}

Visualizza informazioni sull'efficacia delle attività pubblicitarie. Potete vedere quali tipi di iniziative pubblicitarie forniscono maggior traffico e quale dei vostri dipendenti è responsabile di tali sforzi.

<!-- 

c_reports_campaigns.xml

 -->

Questi report sono generalmente personalizzati e quindi diversi per ogni analista. Per ulteriori informazioni, consulta [Campaign Manager](https://marketing.adobe.com/resources/help/en_US/reference/campaign_manager_admin.html) nella [!DNL Admin Console] guida.

## Calcoli statistici {#concept_83FF70DB7895435E985699FE9012D585}

Potete personalizzare le statistiche predefinite in modo da visualizzarle in un rapporto con classifica.

<!-- 

c_Statistical_Calculation_ad_hoc.xml

 -->

È possibile aggiungere ulteriori calcoli statistici predefiniti ai report con classifica in base alla visualizzazione quando si esegue il report, inclusi i calcoli medi, medi, di deviazione standard e altri calcoli matematici valutati in base alle specifiche esigenze di reporting.

**Per aprire i calcoli statistici per i report con classifica:**

1. Select **[!UICONTROL Tools]** &gt; **[!UICONTROL Ranked]** from the menu.

1. Seleziona **[!UICONTROL Settings]**.
1. Seleziona **[!UICONTROL Default Statistics]**.

**[!UICONTROL Ignore zeros in statistical calculations]**. Selezionate questa opzione per ignorare gli zero e assicuratevi che l’aggiunta di un’altra metrica non modifichi le medie già calcolate. Tutte le statistiche sono influenzate da questa impostazione (anche se per Somma non ha effetto).

| Calcolo | Descrizione |
|--- |--- |
| Max | Identifica il valore massimo tra tutte le righe per un set di dati specificato. |
| Min | Identifica il valore minimo tra tutte le righe per un set di dati specificato. |
| Sum | Un calcolo di tutti i valori per ciascuna riga del set di dati.  Ad esempio, la somma aggrega tutte le visite effettuate da un visitatore anziché conteggiare il visitatore solo una volta (indipendentemente dal numero di visite). Si tratta di un totale completo di punti dati raccolti. |
| Media | La media è la media aritmetica dei valori delle righe di un dataset, calcolata dalla somma divisa per il conteggio (somma/conteggio). La media è influenzata da dati esterni, a differenza della media che viene generalmente utilizzata per le distribuzioni distorte. |
| Deviazione standard | La deviazione standard mostra la quantità di variazione rispetto alla media prevista. Una deviazione standard inferiore mostra i punti dati vicini alla media. Una deviazione standard più elevata indica che i punti dati sono distribuiti su un ampio intervallo di valori. |
| mediano | La mediana è il valore numerico che separa la metà superiore di un dato dalla metà inferiore per le righe di un dataset. A differenza della media, è generalmente utilizzato per evitare valori esterni. |
| Quartiles | Un quartile è l'insieme di valori nel set di dati identificato da tre punti che dividono l'insieme di dati in quattro gruppi uguali, ciascuno dei quali comprende un quarto dell'insieme di dati. Il primo quartile è il 25° percentile, e il terzo quartile è il 75° percentile. (Il secondo quartile è la mediana e il quarto quartile è la Somma.) |
| Count | Restituisce il numero di righe in un dataset. |

## Esempio di calcoli medi rispetto al totale della metrica {#section_7C49196503964FB0A429FA347BC92D09}

La funzione Media è calcolata in modo simile alle colonne di dati in Microsoft Excel. In particolare, ciò significa che la **media** di un rapporto (come la determinazione del tasso di rimbalzo medio) sarebbe la media dei rapporti, non il rapporto delle medie. Il rapporto delle medie include il **totale** della metrica del tasso di rimbalzo.

<table id="table_9EC56B15C6A340DA8917CB0DBCAC2355"> 
 <thead> 
  <tr> 
   <th colname="col1" align="center" class="entry"> Data </th> 
   <th colname="col2" align="center" class="entry"> Visite singole </th> 
   <th colname="col3" align="center" class="entry"> Voci </th> 
   <th colname="col4" align="center" class="entry"> Percentuale non recapitate </th> 
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
   <td colname="col1" align="center" valign="middle"><b>Media</b> </td> 
   <td colname="col2" valign="middle"> (344+297+41)/3 </td> 
   <td colname="col3" valign="middle"> (1000+1000+100)/3 </td> 
   <td colname="col4" valign="middle" align="right"> (34.4 + 29.7 + 41.0) / 3 = <b>35.0</b>% </td> 
   <td colname="col5" valign="middle"><b>Mezzo di rapporto</b> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1" align="center" valign="middle"><b>Totale metrica</b> </td> 
   <td colname="col2" valign="middle"> 682 </td> 
   <td colname="col3" valign="middle"> 2100 </td> 
   <td colname="col4" valign="middle" align="right"> 682 / 2100 = <b>32.0</b>% </td> 
   <td colname="col5" valign="middle"><b>Rapporto dei mezzi</b> </td> 
  </tr> 
 </tbody> 
</table>

## Sovrapposizioni di calcolo statistico {#concept_97E1B32DAC734C7B9F8899717283CEEC}

L'analisi ad hoc ora fornisce visualizzazioni sovrapposte dei calcoli statistici per i rapporti che mostrano i dati nel tempo (minuti, ore, giorni, settimane).

<!-- 

c_overlay_calculations.xml

 -->

In un rapporto che identifica i dati in un periodo di tempo, il **[!UICONTROL Statistics]** pulsante consente di selezionare i calcoli che verranno visualizzati come sovrapposizioni nella linea temporale del rapporto.

![](assets/overlay_calculations.png)

Oltre ai calcoli [](../../analyze/ad-hoc-analysis/c-overview-standard-reports.md#concept_83FF70DB7895435E985699FE9012D585)statistici standard, potete selezionare le deviazioni standard 1, 2 e 3 nelle sovrapposizioni.

## Manager gruppo {#concept_E1433974A61144858E87334C006982B2}

Invece di utilizzare una singola pagina in un rapporto, potete raggruppare più pagine e utilizzarle come categorie per iniziare, intermedia o per la posizione di destinazione nei [!UICONTROL Fallout] rapporti e [!UICONTROL Site Analysis] . Potete modificare i gruppi dal menu principale o dall’interno del rapporto. Nell' [!UICONTROL Checkpoint Selector] elenco vengono visualizzate anche le categorie create nei report di marketing e nelle analisi.

<!-- 

c_groups.xml

 -->

Clic **[!UICONTROL Tools]** &gt; **[!UICONTROL Group Manager]**.

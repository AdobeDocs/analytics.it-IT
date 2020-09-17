---
description: I rapporti standard visualizzano i dati per il sito Web e l'attività del visitatore, i pattern di traffico, i dati di riferimento, le campagne pubblicitarie, la conservazione dei visitatori, i dati sui prodotti e altro ancora. Puoi eseguire report e quindi accedere a strumenti per configurare segmenti, metriche e confronti di report.
title: Panoramica sui report
topic: Ad hoc analysis
uuid: 36722dcd-5dc9-4047-8a17-16de876193bf
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 4%

---


# Panoramica sui report

>[!IMPORTANT]
>
> Adobe si sta muovendo  Ad Hoc Analysis fino alla fine del suo ciclo di vita il 1 marzo 2021. [Ulteriori informazioni](https://adobe.ly/discoverworkspace)

I rapporti standard visualizzano i dati per il sito Web e l&#39;attività del visitatore, i pattern di traffico, i dati di riferimento, le campagne pubblicitarie, la conservazione dei visitatori, i dati sui prodotti e altro ancora. Puoi eseguire report e quindi accedere a strumenti per configurare segmenti, metriche e confronti di report.

## Panoramica sui report {#concept_41459A705F2048EEA4EFA80F6BD9FFAB}

I rapporti standard visualizzano i dati per il sito Web e l&#39;attività del visitatore, i pattern di traffico, i dati di riferimento, le campagne pubblicitarie, la conservazione dei visitatori, i dati sui prodotti e altro ancora. Puoi eseguire report e quindi accedere a strumenti per configurare segmenti, metriche e confronti di report.

Potete raccogliere dati personalizzati per creare rapporti specifici per il sito Web. Ad esempio, se disponete di una funzione di ricerca nel sito Web, potete tenere traccia dei termini di ricerca inviati e creare un rapporto che mostra questi termini e i risultati delle ricerche.

Il set di rapporti standard include argomenti comuni a tutti i siti Web. I rapporti includono (ma non sono limitati a):

* Dati del sito Web
* Dati visitatore
* Pattern di traffico
* Dati di riferimento
* Campagne pubblicitarie
* Conservazione dei visitatori
* Informazioni prodotto

Se utilizzate i marketing reports and analytics, i tipi di rapporto e i menu saranno familiari. L&#39;analisi ad hoc classifica i rapporti in base ai seguenti tipi:

**Report di riepilogo**

Include rapporti come il [!UICONTROL Totals Report], che mostra i dati progettati per le panoramiche rapide. Sono destinati ai dirigenti che desiderano una panoramica generale dei dati.

**Report di conversione**

I rapporti di conversione forniscono un&#39;analisi completa, accurata e dettagliata dell&#39;attività del cliente. Metriche come la gestione delle campagne, il ciclo di vendita, l&#39;abbandono del cliente e la conversione del cliente consentono di misurare le transazioni di e-commerce, le fonti di vendita, l&#39;efficacia della pubblicità, la fedeltà dei clienti e altro ancora.

**Rapporti sul traffico**

I rapporti sul traffico forniscono informazioni approfondite sul modo in cui i visitatori interagiscono con il sito Web.

* Analizzare gli aspetti critici del comportamento dei visitatori.
* Monitorare e comprendere i pattern di traffico.
* Consente di determinare il contenuto del sito più popolare.
* Segmenta i visitatori in base a qualsiasi criterio misurabile.

## Campagne {#concept_A407CDF1D4AA49BAB396A1666E67FC87}

Visualizza informazioni sull&#39;efficacia delle attività pubblicitarie. Potete vedere quali tipi di iniziative pubblicitarie forniscono maggior traffico e quale dei vostri dipendenti è responsabile di tali sforzi.

<!-- 

c_reports_campaigns.xml

 -->

Questi report sono di solito personalizzati e quindi diversi per ogni analista. See the [Admin Console help](https://helpx.adobe.com/it/enterprise/using/admin-console.html) for more information.

## Calcoli statistici {#concept_83FF70DB7895435E985699FE9012D585}

Potete personalizzare le statistiche predefinite in modo da visualizzarle in un rapporto con classifica.

<!-- 

c_Statistical_Calculation_ad_hoc.xml

 -->

È possibile aggiungere ulteriori calcoli statistici predefiniti ai report con classifica in base alla visualizzazione quando si esegue il report, inclusi i calcoli medi, medi, di deviazione standard e altri calcoli matematici valutati in base alle specifiche esigenze di reporting.

**Per aprire i calcoli statistici per i report con classifica:**

1. Select **[!UICONTROL Tools]** > **[!UICONTROL Ranked]** from the menu.

1. Select **[!UICONTROL Settings]**.
1. Select **[!UICONTROL Default Statistics]**.

**[!UICONTROL Ignore zeros in statistical calculations]** (Progetto > scarica CSV). Selezionate questa opzione per ignorare gli zero e assicuratevi che l’aggiunta di un’altra metrica non modifichi le medie già calcolate. Tutte le statistiche sono influenzate da questa impostazione (anche se per Somma non ha effetto).

| Calcolo | Descrizione |
|--- |--- |
| Max | Identifica il valore massimo tra tutte le righe per un set di dati specificato. |
| Min | Identifica il valore minimo tra tutte le righe per un set di dati specificato. |
| Sum | Un calcolo di tutti i valori per ciascuna riga del set di dati.  Ad esempio, la somma aggrega tutte le visite effettuate da un visitatore anziché conteggiare il visitatore solo una volta (indipendentemente dal numero di visite). Si tratta di un totale completo di punti dati raccolti. |
| Mean (Media) | La media è la media aritmetica dei valori delle righe di un dataset, calcolata dalla somma divisa per il conteggio (somma/conteggio). La media è influenzata da dati esterni, a differenza della mediana che viene generalmente utilizzata per le distribuzioni distorte. |
| Deviazione standard | La deviazione standard mostra la quantità di variazione rispetto alla media prevista. Una deviazione standard inferiore mostra i punti dati vicini alla media. Una deviazione standard più elevata indica che i punti dati sono distribuiti su un ampio intervallo di valori. |
| Median (Mediano) | La mediana è il valore numerico che separa la metà superiore di un dato dalla metà inferiore per le righe di un dataset. A differenza della media, è generalmente utilizzato per evitare valori esterni. |
| Quartiles | Un quartile è l&#39;insieme di valori nel dataset identificato da tre punti che dividono l&#39;insieme di dati in quattro gruppi uguali, ciascuno dei quali è composto da un quarto dell&#39;insieme di dati. Il primo quartile è il 25° percentile, e il terzo quartile è il 75° percentile. (Il secondo quartile è la mediana e il quarto quartile è la Somma.) |
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
   <td colname="col1"> <p>Giugno 2013 </p> <p>2013 luglio </p> <p>Agosto 2013 </p> </td> 
   <td colname="col2" align="center"> <p>344 </p> <p>297 </p> <p>41 </p> </td> 
   <td colname="col3" align="center"> <p>1000 </p> <p>1000 </p> <p>1000 </p> </td> 
   <td colname="col4" align="center"> <p>34.4% </p> <p>29.7% </p> <p>41.0% </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1" align="center" valign="middle"><b>Mean (Media)</b> </td> 
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

L&#39;analisi ad hoc ora fornisce visualizzazioni sovrapposte dei calcoli statistici per i rapporti che mostrano i dati nel tempo (minuti, ore, giorni, settimane).

<!-- 

c_overlay_calculations.xml

 -->

In un rapporto che identifica i dati in un periodo di tempo, il **[!UICONTROL Statistics]** pulsante consente di selezionare i calcoli che verranno visualizzati come sovrapposizioni nella linea temporale del rapporto.

![](assets/overlay_calculations.png)

Oltre ai calcoli [](/help/analyze/ad-hoc-analysis/c-overview-standard-reports.md#concept_83FF70DB7895435E985699FE9012D585)statistici standard, potete selezionare le deviazioni standard 1, 2 e 3 nelle sovrapposizioni.

## Manager gruppo {#concept_E1433974A61144858E87334C006982B2}

Invece di utilizzare una singola pagina in un rapporto, potete raggruppare più pagine e utilizzarle come categorie per iniziare, intermedia o per la posizione di destinazione nei [!UICONTROL Fallout] rapporti e [!UICONTROL Site Analysis] . Potete modificare i gruppi dal menu principale o dall’interno del rapporto. Anche le categorie create nei marketing reports and analytics vengono visualizzate nell&#39; [!UICONTROL Checkpoint Selector] elenco.

<!-- 

c_groups.xml

 -->

Fai clic su **[!UICONTROL Tools]** > **[!UICONTROL Group Manager]**.

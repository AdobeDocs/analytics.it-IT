---
description: Data Warehouse fa riferimento alla copia dei dati di Analytics per l'archiviazione e i report personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue precise domande. I report data warehouse vengono inviati via e-mail o tramite FTP e possono richiedere fino a 72 ore di elaborazione. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.
seo-description: Data Warehouse fa riferimento alla copia dei dati di Analytics per l'archiviazione e i report personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue precise domande. I report data warehouse vengono inviati via e-mail o tramite FTP e possono richiedere fino a 72 ore di elaborazione. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.
seo-title: Panoramica di Data Warehouse
solution: Analytics
title: Panoramica di Data Warehouse
topic: Data warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
translation-type: tm+mt
source-git-commit: 506c670e4b2903cc71bb6880cd74c3392bbc751c

---


# Panoramica di Data Warehouse

Data Warehouse fa riferimento alla copia dei dati di Analytics per l'archiviazione e i report personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue precise domande. I report data warehouse vengono inviati via e-mail o tramite FTP e possono richiedere fino a 72 ore di elaborazione. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.

Adobe abilita Data Warehouse solo per gli utenti a livello di amministratore, per suite di rapporti specifiche. Può essere abilitata per le suite di rapporti globali e secondarie, ma non per le suite di rapporti rollup. L'amministratore può creare un gruppo che dispone dell'accesso a Data Warehouse, quindi associare utenti di livello non amministratore a tale gruppo.

Data Warehouse comprime automaticamente qualsiasi file con dimensioni superiori a 1 MB. La dimensione massima per l’allegato e-mail è 10 MB.

Data Warehouse può elaborare un numero illimitato di righe in un'unica richiesta per singoli rapporti pianificati e scaricati.

>[!NOTE]
>
>Data Warehouse segnala il primo valore rilevato nel periodo di reporting.

>[!IMPORTANT]
>
>Quando si suddivide in valori classificati, Analysis Workspace e Data Warehouse gestiscono in modo diverso i valori "non specificati". "Non specificato" in Workspace si riferisce a valori non classificati, mentre "Non specificato" in Data Warehouse fa riferimento a valori classificati come "Non specificato".

## Descrizioni richieste data warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

Nella tabella seguente sono descritti i campi e le opzioni della [!UICONTROL Data Warehouse Request] scheda.

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Request Name (Nome richiesta)</span> </td> 
   <td colname="col2"> Identifica la richiesta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Reporting Date (Data rapporto)</span> </td> 
   <td colname="col2"> <p>Data e granularità della richiesta. </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Personalizzato</span>: Un intervallo di date configurato nel calendario. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Predefinito</span>: Un intervallo predefinito. L’intervallo predefinito è relativo alla data del rapporto. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Granularità</span>: La granularità temporale. I valori validi sono Nessuno, Ora, Giorno, Settimana, Mese, Trimestre e Anno. </li> 
    </ul> <p>Il reporting di Data Warehouse sulle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Available Segments (Segmenti disponibili)</span> </td> 
   <td colname="col2"> <p>Consente di selezionare la parte della popolazione di visitatori da esaminare e generare segmenti complessi. Puoi caricare segmenti preconfigurati, creare nuovi segmenti e archiviare componenti di segmenti in una libreria da utilizzare per la creazione di segmenti aggiuntivi. </p> <p>Ora puoi impilare i segmenti. Quando si selezionano più segmenti, l’area di anteprima, il Gestore richieste e la finestra a comparsa Dettagli richiesta visualizzano un elenco di nomi separati da virgola (ad esempio Segmento1, Segmento2). </p> <p>Per ulteriori informazioni, consulta la <a href="/help/components/c-segmentation/seg-home.md"> guida</a> alla segmentazione. </p> <p>Nota:  Non puoi includere sia un filtro segmento che una suddivisione sullo stesso segmento, nello stesso rapporto Data Warehouse. In questo modo si verificherà un errore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Breakdowns (Suddivisioni)</span> </td> 
   <td colname="col2"> <p>Consente di classificare i dati utilizzando le suddivisioni. Segmenti e suddivisioni differiscono in quanto un segmento filtra i dati da un set di dati, mentre una suddivisione separa i dati da tutti i valori validi per la suddivisione. </p> Puoi anche suddividere un rapporto per uno o più segmenti. Tuttavia, non puoi includere sia un filtro segmento che una suddivisione sullo stesso segmento, nello stesso rapporto Data Warehouse. In questo modo si verificherà un errore. <p> Ad esempio, utilizzare i segmenti per rimuovere un genere dal set di dati e utilizzare una suddivisione per visualizzare i dati separati per genere. </p> <p>Quando una richiesta di data warehouse viene inviata con dimensioni multi-valore (ad esempio, vari rapporti mobili), è possibile generare un numero esponenziale di righe da un singolo hit. Il numero di righe che possono essere emesse da un singolo hit è limitato a 100 (precedentemente 1.000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Metriche</span> </td> 
   <td colname="col2">Consente di aggiungere le metriche su cui si desidera eseguire il rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Ordinamento delle metriche</span> </td> 
   <td colname="col2">Fornisce report dettagliati con classifica, ordinati per valore di metrica decrescente, simili a quanto visualizzato nell'interfaccia utente di Reporting e analisi, Workbench dati e così via. <a href="../../export/data-warehouse/sorting-by-metric.md#concept_7B7BDE3D42E549389DACA1E33B2FC1CC" format="dita" scope="local"> Altro...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Schedule Delivery (Pianifica consegna)</span> </td> 
   <td colname="col2"> <p>Consente di pianificare le richieste di consegna automatica a intervalli selezionati o come rapporto una tantum. Se utilizzate il formato predefinito, il rapporto viene inviato in un messaggio e-mail come file .csv. </p> <p>Per aggiungere l’intervallo di date, includete <span class="filepath"> %R</span> nel nome del file. Questo valore rappresenta i valori data richiesti nel report. Ad esempio, se si richiedono dati dal 1 maggio 2013 al 7 maggio 2013, il <span class="filepath"> %R</span> mostra un nome di file che include l'intervallo di date 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>


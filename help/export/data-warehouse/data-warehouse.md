---
description: Data warehouse si basa sulla copia dei dati di Analytics per l'archiviazione e i rapporti personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue precise domande. I rapporti Data Warehouse vengono inviati via e-mail o inviati mediante FTP e potrebbero essere necessarie fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.
seo-description: Data warehouse si basa sulla copia dei dati di Analytics per l'archiviazione e i rapporti personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue precise domande. I rapporti Data Warehouse vengono inviati via e-mail o inviati mediante FTP e potrebbero essere necessarie fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.
seo-title: Panoramica di Data Warehouse
solution: Analytics
title: Panoramica di Data Warehouse
topic: Data warehouse
uuid: 768557 dd -1644-4 ce 6-bfc 2-8 c 46 dd 6 e 1 cd 1
translation-type: tm+mt
source-git-commit: 15d49195e5d555adcc37366d679d6b971972504b

---


# Panoramica di Data Warehouse

Data Warehouse si basa sulla copia dei dati di Analytics per l'archiviazione e i rapporti personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue precise domande. I rapporti Data Warehouse vengono inviati via e-mail o inviati mediante FTP e potrebbero essere necessarie fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.

Adobe abilita Data Warehouse solo per gli utenti a livello di amministratore, per suite di rapporti specifiche. Può essere attivato per suite di rapporti globali e secondarie, ma non per suite di rapporti di rollup. L'amministratore può creare un gruppo con accesso a Data Warehouse, quindi associare gli utenti a livello non amministratore a tale gruppo.

Data Warehouse è in grado di comporre automaticamente qualsiasi file superiore a 1 MB. La dimensione massima dell'allegato e-mail è di 10 MB.

Data Warehouse può elaborare un numero illimitato di righe in una singola richiesta per i singoli rapporti pianificati e scaricati.

>[!NOTE]
>
>Data Warehouse segnala il primo valore rilevato nel periodo di reporting.

>[!IMPORTANT]
>
>Quando si segmentano i valori classificati, Analysis Workspace e Data Warehouse trattano in modo diverso i valori «non specificati». ' Unspecified'in Workspace (Non specificato) si riferisce a valori non classificati, mentre in Data Warehouse si fa riferimento a valori classificati come "Non specificato".

## Data Warehouse Requests Descriptions {#section_F21C78ED36884C389C852E876AF5CDE8}

This table describes the fields and options on the [!UICONTROL Data Warehouse Request] tab.

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
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Personalizzato</span>: Intervallo di date configurato nel calendario. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Predefinito</span>: Un intervallo di predefiniti. L'intervallo di predefinito è relativo alla data del rapporto. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Granularità</span>: Granularità temporale. I valori validi sono Nessuno, Ora, Giorno, Settimana, Mese, Trimestre e Anno. </li> 
    </ul> <p>La generazione di rapporti di Data Warehouse sulle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Available Segments (Segmenti disponibili)</span> </td> 
   <td colname="col2"> <p>Consente di selezionare la parte della popolazione dei visitatori che si desidera esaminare e generare segmenti complessi. Puoi caricare segmenti preconfigurati, creare nuovi segmenti e memorizzare i componenti dei segmenti in una libreria da utilizzare per la creazione di segmenti aggiuntivi. </p> <p>Ora potete inserire dei segmenti. Quando si selezionano più segmenti, l'area di anteprima, Request Manager (Gestore richieste) e la finestra popup Dettagli richiesta mostrano un elenco di nomi separati da virgola (ad es., Segmento 1, Segmento 2). </p> <p>Per ulteriori informazioni, consultate [Guida alla segmentazione] (/help/components/c-segmentation/seg-home. md). </p> <p>Nota: Nello stesso rapporto di Data Warehouse non puoi includere sia un filtro segmento che una suddivisione sullo stesso segmento. In tal modo si verificherà un errore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Breakdowns (Suddivisioni)</span> </td> 
   <td colname="col2"> <p>Consente di classificare i dati utilizzando le suddivisioni. I segmenti e le suddivisioni differiscono in quanto un segmento filtra dati fuori da un set di dati, mentre una suddivisione suddivisa i dati in tutti i valori validi per la suddivisione. </p> Puoi anche suddividere un rapporto in base a uno o più segmenti. Tuttavia, non puoi includere sia un filtro segmento che una suddivisione sullo stesso segmento nello stesso report Data Warehouse. In tal modo si verificherà un errore. <p> Ad esempio, utilizzate i segmenti per rimuovere un genere dal set di dati e utilizzare una suddivisione per visualizzare i dati separati da genere. </p> <p>Quando una richiesta Data Warehouse viene inviata con dimensioni multi-valore (ad es. vari rapporti mobili), un numero esponenziale di righe può essere generato da un singolo hit. Il numero di righe che possono essere emesse da un singolo hit è limitato a 100 (in precedenza 1,000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Metriche</span> </td> 
   <td colname="col2">Consente di aggiungere metriche sui quali desideri eseguire il rapporto. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Ordinamento metriche</span> </td> 
   <td colname="col2">Fornisce rapporti di suddivisione classificati, ordinati con valore metrica decrescente, simile a quanto visualizzato nell'interfaccia utente Reporting e analisi, Workbench dati e così via. <a href="../../export/data-warehouse/sorting-by-metric.md#concept_7B7BDE3D42E549389DACA1E33B2FC1CC" format="dita" scope="local">Altro...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Schedule Delivery (Pianifica consegna)</span> </td> 
   <td colname="col2"> <p>Consente di pianificare le richieste di consegna automatica a intervalli selezionati o come un rapporto una tantum. Se utilizzi il formato predefinito, il rapporto arriva come file. csv. </p> <p>To add the date range, include <span class="filepath"> %R</span> in the filename. Questo valore rappresenta i valori di data richiesti nel report. For example, if you request data from May 1, 2013 through May 7, 2013, the <span class="filepath"> %R</span> shows a filename including the date range of 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>


---
description: Data warehouse rimanda alla copia dei dati di Analytics per l’archiviazione e i rapporti personalizzati, che puoi eseguire filtrando i dati. È possibile richiedere rapporti per visualizzare relazioni avanzate tra i dati, da dati non elaborati in base a domande specifiche. I rapporti data warehouse vengono inviati tramite e-mail o FTP e la loro elaborazione può richiedere fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.
title: Panoramica di Data Warehouse
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 25%

---

# Panoramica di Data Warehouse

Data Warehouse rimanda alla copia dei dati di Analytics per l’archiviazione e i rapporti personalizzati, che si possono eseguire filtrando i dati. È possibile richiedere rapporti per visualizzare relazioni avanzate tra i dati, da dati non elaborati in base a domande specifiche. I rapporti data warehouse vengono inviati tramite e-mail o FTP e la loro elaborazione può richiedere fino a 72 ore. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.

L’Adobe abilita Data Warehouse solo per gli utenti a livello di amministratore, per suite di rapporti specifiche. Può essere abilitata per le suite di rapporti globali e secondarie, ma non per le suite di rapporti di aggregazione dati. L&#39;amministratore può creare un gruppo con accesso a Data Warehouse e quindi associare al gruppo utenti non amministratori.

Data Warehouse comprime automaticamente qualsiasi file di dimensioni superiori a 1 MB. La dimensione massima dell&#39;allegato e-mail è 10 MB.

Data Warehouse può elaborare un numero illimitato di righe in una singola richiesta per singoli rapporti pianificati e scaricati.

>[!NOTE]
>
>Data Warehouse riporta il primo valore rilevato nel periodo di reporting.

>[!IMPORTANT]
>
>Quando si segmentano valori classificati, Analysis Workspace e Data Warehouse trattano i valori &quot;non specificati&quot; in modo diverso. &#39;Non specificato&#39; in Workspace fa riferimento a valori non classificati, mentre &#39;Non specificato&#39; nella Data Warehouse fa riferimento a valori classificati come &quot;Non specificato&quot;.

## Data Warehouse descrizioni richieste {#section_F21C78ED36884C389C852E876AF5CDE8}

Questa tabella descrive i campi e le opzioni della [!UICONTROL Data Warehouse Request] scheda.

<table id="table_7325A2466866460E8B0AF7D696152713"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nome richiesta</span> </td> 
   <td colname="col2"> Identifica la richiesta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Reporting Date (Data rapporto)</span> </td> 
   <td colname="col2"> <p>Data e granularità della richiesta. </p> 
    <ul id="ul_C00F4529BD9E4113B517A61751B1DD5C"> 
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Personalizzato</span>: intervallo di date configurato nel calendario. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Predefinito</span>: intervallo predefinito. L’intervallo di predefiniti è relativo alla data del rapporto. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Granularità</span>: granularità temporale. I valori validi sono Nessuno, Ora, Giorno, Settimana, Mese, Trimestre e Anno. </li> 
    </ul> <p>Il reporting Data Warehouse sulle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Available Segments (Segmenti disponibili)</span> </td> 
   <td colname="col2"> <p>Consente di selezionare la parte della popolazione di visitatori che desideri esaminare e generare segmenti complessi. Puoi caricare segmenti preconfigurati, creare nuovi segmenti e archiviare i componenti dei segmenti in una libreria da utilizzare per la creazione di segmenti aggiuntivi. </p> <p>Ora puoi impilare i segmenti. Quando si selezionano più segmenti, l’area di anteprima, il Request Manager (Gestore richieste) e la finestra a comparsa Request Detail (Dettagli richiesta) mostrano un elenco di nomi separati da virgole (ad esempio, Segment1, Segment2). </p> <p>Consulta la <a href="/help/components/segmentation/seg-home.md"> Guida alla segmentazione</a> per ulteriori informazioni. </p> <p>Nota: non puoi includere sia un filtro segmento che un raggruppamento sullo stesso segmento nello stesso rapporto Date Warehouse. Procedendo, si verifica un errore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Breakdowns (Suddivisioni)</span> </td> 
   <td colname="col2"> <p>Consente di categorizzare i dati utilizzando raggruppamenti. Segmenti e raggruppamenti differiscono in quanto un segmento filtra i dati al di fuori di un set di dati, mentre un raggruppamento compartimenta i dati tra tutti i valori validi per il raggruppamento. </p> Puoi anche suddividere un rapporto per uno o più segmenti. Tuttavia, non puoi includere sia un filtro segmento che un raggruppamento sullo stesso segmento, nello stesso rapporto di Data Warehouse. Procedendo, si verifica un errore. <p> Ad esempio, utilizza i segmenti per rimuovere un genere dal set di dati e un raggruppamento per visualizzare i dati separati per genere. </p> <p>Quando una richiesta Data Warehouse viene inviata con dimensioni con più valori (ad esempio, vari Report dispositivi mobili), è possibile generare un numero esponenziale di righe da un singolo hit. Il numero di righe che possono essere generate da un singolo hit è limitato a 100 (in precedenza 1.000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Metriche</span> </td> 
   <td colname="col2">Consente di aggiungere metriche sulle quali si desidera creare rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Ordinamento metriche</span> </td> 
   <td colname="col2">Fornisce rapporti con raggruppamenti classificati, ordinati per valore di metrica decrescente, simile a quello visualizzato nell’interfaccia utente di Reports &amp; Analytics, Data Workbench, ecc. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > Altro...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Schedule Delivery (Pianifica consegna)</span> </td> 
   <td colname="col2"> <p>Consente di pianificare le richieste di consegna automatica a intervalli selezionati o come rapporto una tantum. Se utilizzi il formato predefinito, il rapporto arriva tramite e-mail come file .csv. </p> <p>Per aggiungere l’intervallo di date, includi <span class="filepath"> %R</span> nel nome file. Questo valore rappresenta i valori di data richiesti nel rapporto. Ad esempio, se richiedi dati dal 1° maggio 2013 al 7 maggio 2013, il <span class="filepath"> %R</span> mostra un nome file che include l’intervallo di date 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

---
description: Data Warehouse fa riferimento alla copia dei dati di Analytics per l'archiviazione e i report personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue domande specifiche. I report data warehouse vengono inviati via e-mail o tramite FTP e possono richiedere fino a 72 ore per l'elaborazione. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.
title: Panoramica di Data Warehouse
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 7%

---

# Panoramica di Data Warehouse

Data Warehouse si riferisce alla copia dei dati di Analytics per l’archiviazione e i rapporti personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue domande specifiche. I report data warehouse vengono inviati via e-mail o tramite FTP e possono richiedere fino a 72 ore per l&#39;elaborazione. Il tempo di elaborazione dipende dalla complessità della query e dalla quantità di dati richiesti.

L’Adobe abilita la Data Warehouse solo per gli utenti a livello di amministratore, per suite di rapporti specifiche. Può essere abilitata per le suite di rapporti globali e figlio, ma non per le suite di rapporti rollup. L’amministratore può creare un gruppo con accesso a Data Warehouse e quindi associare utenti non amministratori a tale gruppo.

Data Warehouse comprime automaticamente qualsiasi file con dimensioni superiori a 1 MB. La dimensione massima dell’allegato e-mail è di 10 MB.

Data Warehouse può elaborare un numero illimitato di righe in una singola richiesta per singoli rapporti pianificati e scaricati.

>[!NOTE]
>
>Data Warehouse segnala il primo valore rilevato nel periodo di reporting.

>[!IMPORTANT]
>
>Quando si segmentano i valori classificati, Analysis Workspace e Data Warehouse gestiscono i valori &quot;non specificati&quot; in modo diverso. &quot;Non specificato&quot; in Workspace fa riferimento a valori non classificati, mentre &quot;Non specificato&quot; nella Data Warehouse fa riferimento a valori classificati come &quot;Non specificato&quot;.

## Descrizioni delle richieste di Data Warehouse {#section_F21C78ED36884C389C852E876AF5CDE8}

Questa tabella descrive i campi e le opzioni della scheda [!UICONTROL Data Warehouse Request] .

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
     <li id="li_4D7C26812DF94ED7B64F985309541F46"> <span class="wintitle"> Personalizzato</span>: Un intervallo di date configurato nel calendario. </li> 
     <li id="li_2B272087006847148A936350D1B2D523"> <span class="wintitle"> Preimpostazione</span>: Un intervallo predefinito. L’intervallo predefinito è relativo alla data del rapporto. </li> 
     <li id="li_745989965BB94D489FF7046587E13C42"> <span class="wintitle"> Granularità</span>: Granularità temporale. I valori validi sono Nessuno, Ora, Giorno, Settimana, Mese, Trimestre e Anno. </li> 
    </ul> <p>La funzione di reporting Data Warehouse nelle suite di rapporti virtuali supporta il fuso orario alternativo configurato nella suite di rapporti virtuali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Available Segments (Segmenti disponibili)</span> </td> 
   <td colname="col2"> <p>Consente di selezionare la parte della popolazione di visitatori che si desidera esaminare e generare segmenti complessi. Puoi caricare segmenti preconfigurati, creare nuovi segmenti e archiviare componenti di segmenti in una libreria da utilizzare nella creazione di segmenti aggiuntivi. </p> <p>Ora puoi impilare segmenti. Quando si selezionano più segmenti, l’area di anteprima, il Request Manager e il popup Request Detail mostrano un elenco di nomi separati da virgole (ad esempio, Segment1, Segment2). </p> <p>Per ulteriori informazioni, consulta la <a href="/help/components/segmentation/seg-home.md"> Guida alla segmentazione</a> . </p> <p>Nota:  Non puoi includere sia un filtro segmenti che un raggruppamento sullo stesso segmento, nello stesso rapporto di Data Warehouse. In questo modo si verifica un errore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Breakdowns (Suddivisioni)</span> </td> 
   <td colname="col2"> <p>Consente di classificare i dati utilizzando le suddivisioni. Segmenti e suddivisioni sono diversi nel caso in cui un segmento filtra i dati da un set di dati, mentre un raggruppamento separa i dati da tutti i valori validi per la suddivisione. </p> Puoi anche suddividere un rapporto per uno o più segmenti. Tuttavia, non puoi includere sia un filtro segmento che una suddivisione sullo stesso segmento, nello stesso rapporto di Data Warehouse. In questo modo si verifica un errore. <p> Ad esempio, utilizza i segmenti per rimuovere un genere dal set di dati e utilizza un raggruppamento per visualizzare i dati separati per genere. </p> <p>Quando una richiesta di Data Warehouse viene inviata con più dimensioni con più valori (ad esempio, vari rapporti mobili), da un singolo hit può essere generato un numero esponenziale di righe. Il numero di righe che possono essere emesse da un singolo hit è limitato a 100 (precedentemente 1.000). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Metriche</span> </td> 
   <td colname="col2">Consente di aggiungere le metriche sulle quali si desidera creare rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Ordinamento delle metriche</span> </td> 
   <td colname="col2">Fornisce rapporti di suddivisione classificati, ordinati per valore di metrica decrescente, simili a quelli visualizzati nell’interfaccia utente, nella Data Workbench e così via di Reports &amp; Analytics. <a href="/help/export/data-warehouse/sorting-by-metric.md"  > Altro...</a> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle">Schedule Delivery (Pianifica consegna)</span> </td> 
   <td colname="col2"> <p>Consente di pianificare le richieste di consegna automatica a intervalli selezionati o come rapporto una tantum. Se utilizzi il formato predefinito, il rapporto viene inviato tramite e-mail come file .csv. </p> <p>Per aggiungere l’intervallo di date, includi <span class="filepath"> %R</span> nel nome file. Questo valore rappresenta i valori di data richiesti nel rapporto. Ad esempio, se richiedi i dati dal 1° maggio 2013 al 7 maggio 2013, il <span class="filepath"> %R</span> mostra un nome file contenente l’intervallo di date 20130501 - 20130507. </p> </td> 
  </tr> 
 </tbody> 
</table>

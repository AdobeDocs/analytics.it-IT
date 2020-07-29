---
description: Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione in una singola suite di rapporti
subtopic: Classifications
title: Importazione browser
topic: Admin tools
uuid: 56dfbf4c-36e6-49f4-b5cb-8ab714432825
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 3%

---


# Importazione browser

Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione in una singola suite di rapporti

## Importazione browser {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione in una singola suite di rapporti

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**

## Importazione browser classificazioni - Descrizioni dei campi {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Seleziona suite di rapporti </td> 
   <td colname="col2"> <p>La suite di rapporti in cui si desidera importare i dati delle classificazioni. Il file di dati di importazione deve corrispondere al formato del set di dati nella suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Set di dati da classificare </td> 
   <td colname="col2"> <p>Set di dati per la ricezione delle classificazioni. L'elenco a discesa include tutti i rapporti nelle suite di rapporti configurati per le classificazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Selezionare il file da importare </td> 
   <td colname="col2"> <p>Consente di individuare il file di dati di importazione da caricare. </p> <p>Nota:  La dimensione massima per il file di caricamento è 1 MB. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sovrascrivi dati sui conflitti </td> 
   <td colname="col2"> <p>Sovrascrive automaticamente i dati esistenti in conflitto con quelli importati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scarica automaticamente il file di classificazione al termine dell'importazione </td> 
   <td colname="col2"> <p>Scarica automaticamente un file delimitato da tabulazioni che rappresenta il set di dati con i nuovi dati di classificazione caricati.  Adobe genera automaticamente questo file se l’importazione crea degli ID univoci o se si verificano degli errori. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Importa classificazioni tramite il browser {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**.
1. Configurare i **[!UICONTROL Browser Import]** campi.
1. Fai clic su **[!UICONTROL Import File]**.
1. Controlla la finestra di stato per l&#39;elaborazione dei messaggi.
1. (Condizionale) Se avete selezionato **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specificate dove memorizzare il file risultante al termine dell&#39;elaborazione.
>Un&#39;importazione corretta visualizza immediatamente le modifiche appropriate in un&#39;esportazione. Tuttavia, le modifiche ai dati nei rapporti richiedono fino a quattro ore quando si utilizza un&#39;importazione browser e fino a 24 ore quando si utilizza un&#39;importazione FTP.


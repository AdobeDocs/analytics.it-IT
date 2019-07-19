---
description: Potete importare (caricare) i dati classificazioni utilizzando il browser. Questo metodo limita il caricamento di dati di classificazione a una singola suite di rapporti
seo-description: Potete importare (caricare) i dati classificazioni utilizzando il browser. Questo metodo limita il caricamento di dati di classificazione a una singola suite di rapporti
seo-title: Importazione del browser
solution: Analytics
subtopic: Classificazioni
title: Importazione del browser
topic: Strumenti di amministrazione
uuid: 56 dfbf 4 c -36 e 6-49 f 4-b 5 cb -8 ab 714432825
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Importazione del browser

Potete importare (caricare) i dati classificazioni utilizzando il browser. Questo metodo limita il caricamento di dati di classificazione a una singola suite di rapporti

## Browser import {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Potete importare (caricare) i dati classificazioni utilizzando il browser. Questo metodo limita il caricamento di dati di classificazione a una singola suite di rapporti

**[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**

## Classifications Browser Import - Field Descriptions {#section_F628C47081DA4026A4D30E3D3454B1DA}

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
   <td colname="col2"> <p>La suite di rapporti in cui desideri importare i dati di classificazione. Il file di dati Importa deve corrispondere al formato del set di dati nella suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Set di dati da classificare </td> 
   <td colname="col2"> <p>Set di dati per ricevere le classificazioni. L'elenco a discesa include tutti i report nelle suite di rapporti configurati per le classificazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seleziona file da importare </td> 
   <td colname="col2"> <p>Consente di individuare il file di dati da caricare. </p> <p>Nota: Il limite di dimensione del file di caricamento è di 1 MB. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sovrascrivi dati in conflitto </td> 
   <td colname="col2"> <p>Sovrascrive automaticamente i dati esistenti in conflitto con i dati importati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scarica automaticamente file di classificazione dopo l'importazione completata </td> 
   <td colname="col2"> <p>Scarica automaticamente un file delimitato da tabulazioni che rappresenta il set di dati con i dati di classificazione caricati di recente. Adobe genera automaticamente questo file se l'importazione crea ID univoci oppure se si verificano errori. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Import classifications via the browser {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**.
1. Configure the **[!UICONTROL Browser Import]** fields.
1. Fai clic su **[!UICONTROL Import File]**.
1. Visualizza la finestra dello stato per i messaggi di elaborazione.
1. (Conditional) If you selected **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specify where you want to store the resulting file when processing completes.
>Un importazione corretta mostra immediatamente le modifiche apportate in un'esportazione. Tuttavia, le modifiche ai dati nei rapporti possono richiedere fino a quattro ore quando si utilizza un'importazione del browser e fino a 24 ore quando si utilizza un'importazione FTP.


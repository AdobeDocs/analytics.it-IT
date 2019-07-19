---
description: Puoi personalizzare la pianificazione della consegna per i rapporti. Potete interrompere la consegna in un determinato momento o specificare quante volte desiderate inviare un rapporto. Le nuove pianificazioni utilizzano l'intervallo di date definito nel report. Ad esempio, se crei un rapporto per gli ultimi 90 giorni e lo pianifichi a eseguire ogni giorno, riceverai un rapporto per gli ultimi 90 giorni ogni giorno. Se crei un rapporto con un intervallo di date statico dal calendario, vedrai lo stesso rapporto ogni volta che viene inviato.
seo-description: Puoi personalizzare la pianificazione della consegna per i rapporti. Potete interrompere la consegna in un determinato momento o specificare quante volte desiderate inviare un rapporto. Le nuove pianificazioni utilizzano l'intervallo di date definito nel report. Ad esempio, se crei un rapporto per gli ultimi 90 giorni e lo pianifichi a eseguire ogni giorno, riceverai un rapporto per gli ultimi 90 giorni ogni giorno. Se crei un rapporto con un intervallo di date statico dal calendario, vedrai lo stesso rapporto ogni volta che viene inviato.
seo-title: Pianificazione Manager
solution: Analytics
title: Pianificazione Manager
topic: Analisi ad hoc
uuid: 82 a 054 ef -109 d -414 d-a 6 e 1-e 09 ee 57 c 163 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Pianificazione Manager

Puoi personalizzare la pianificazione della consegna per i rapporti. Potete interrompere la consegna in un determinato momento o specificare quante volte desiderate inviare un rapporto. Le nuove pianificazioni utilizzano l'intervallo di date definito nel report. Ad esempio, se crei un rapporto per gli ultimi 90 giorni e lo pianifichi a eseguire ogni giorno, riceverai un rapporto per gli ultimi 90 giorni ogni giorno. Se crei un rapporto con un intervallo di date statico dal calendario, vedrai lo stesso rapporto ogni volta che viene inviato.

## Scheduling Manager {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

Puoi personalizzare la pianificazione della consegna per i rapporti. Potete interrompere la consegna in un determinato momento o specificare quante volte desiderate inviare un rapporto. Le nuove pianificazioni utilizzano l'intervallo di date definito nel report. Ad esempio, se crei un rapporto per gli ultimi 90 giorni e lo pianifichi a eseguire ogni giorno, riceverai un rapporto per gli ultimi 90 giorni ogni giorno. Se crei un rapporto con un intervallo di date statico dal calendario, vedrai lo stesso rapporto ogni volta che viene inviato.

>[!NOTE]
>
>Quando un account utente è disattivato, tutte le consegne pianificate create da tale utente vengono sospese.

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](../../analyze/ad-hoc-analysis/c-tablebuilder.md#concept_664FC77306E148DBA4EA081814943C5E) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>Analisi ad hoc consente di definire e pianificare rapidamente i report per necessità di reporting specifici, puntuali e puntuali. Non è progettato per esportare intere esportazioni di dati con numeri o righe, colonne, valutazioni metriche o interruzioni ampie mediante estratti di dati.
>
>I vincoli pratici per i rapporti pianificati in Analisi ad hoc sono basati su questo principio: Se il report non viene generato entro dieci minuti (il timeout per Analisi ad hoc), il rapporto è probabilmente troppo complesso.
>
>Probabilmente il rapporto contiene troppe metriche, troppe suddivisioni degli elementi dimensione, troppe righe o colonne o altri estremi che rendono troppo lunga un processo di generazione di rapporti per Analisi ad hoc. Questo tipo di rapporto deve essere eseguito in Data Warehouse, una funzionalità Adobe Analytics eseguita per l'estrazione completa dei dati in modalità offline con la generazione dei report, che può richiedere molte ore o giorni.
>
>Ad esempio, Analisi ad hoc può gestire 50,000 righe di dati, ma suddividere quei dati per dieci tipi di browser significa 50,0000 volte 10, un incremento esponenziale che potrebbe essere troppo complesso per uno strumento di reporting ad hoc. Ulteriori suddivisioni aumentano di nuovo le righe di dati esponenziale. La definizione del numero o della riga, delle colonne e delle suddivisioni effettive per la generazione di rapporti Ad Hoc Analysis non può essere definita in termini profondi, ma è una combinazione di tutti questi fattori.

## Schedule a report for delivery {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Procedura che descrive come pianificare un rapporto per la consegna.

<!-- 

t_schedule_delivery.xml

 -->

1. Click **[!UICONTROL Tools]**, then click **[!UICONTROL Schedule Manager]**.
1. On the [!UICONTROL Schedule Manager], click **[!UICONTROL New.]**

## Delivery Options - Definitions {#reference_CA49AC560258471AAE959BCA243F170C}

Definizioni delle impostazioni in Opzioni di consegna.

<!-- 

r_delivery_options.xml

 -->

Potete inviare le informazioni visualizzate nel rapporto selezionato al formato selezionato. Potete inviarlo una volta oppure impostare una pianificazione di consegna e specificare il formato di file desiderato. È possibile creare e inviare una firma digitale per garantire che il destinatario del file sia autentico. Puoi inviare il file a un indirizzo e-mail o caricarlo su un server FTP.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome </p> </td> 
   <td colname="col2"> <p> Nome configurabile del report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Indica l'ID del rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato file </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: Trasmette il rapporto in un foglio di calcolo, incluse tutte le immagini. Modificabile in Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: Trasmette il rapporto in Valori separati da virgola. Modificabile in un semplice editor di testo (ad esempio Blocco note) o un editor di fogli di calcolo (ad esempio Excel). Non contiene immagini. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: Trasmette il rapporto in formato PDF portatile. Non modificabile e visualizzabile in Adobe Acrobat o Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: Trasmette il rapporto in un allegato di linguaggio di marcatura ipertestuale. Questo formato è costituito dalla maggior parte dei siti Web composti. Non modificabile, a meno che non abbiate familiarità con il codice HTML. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word: Trasmette il rapporto in Formato RTF, incluse tutte le immagini. Modificabile in Microsoft Word o wordpad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Advanced </p> </td> 
   <td colname="col2"> <p> See <a href="../../analyze/ad-hoc-analysis/c-schedule.md#reference_F99B65BF7C9746638D8147EED147015B" type="reference" format="dita" scope="local"> Advanced Format Settings</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destinazione file </p> </td> 
   <td colname="col2"> <p>E-mail: Impostazioni da inviare tramite e-mail. </p> <p>FTP: Impostazioni per il caricamento su un server FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo di report e pianificazione consegna </p> </td> 
   <td colname="col2"> <p>Specifica quando distribuire il rapporto. Le nuove pianificazioni utilizzano l'intervallo di date definito nel report. Ad esempio, se crei un rapporto per gli ultimi 90 giorni e lo pianifichi a eseguire ogni giorno, riceverai un rapporto per gli ultimi 90 giorni ogni giorno. Se crei un rapporto con un intervallo di date statico dal calendario, vedrai lo stesso rapporto ogni volta che viene inviato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Advanced Format Settings - Definitions {#reference_F99B65BF7C9746638D8147EED147015B}

Definizioni delle impostazioni in Impostazioni formato avanzate.

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome file </p> </td> 
   <td colname="col2"> <p>Nome file definito dall'utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiungi ID al nome file </p> </td> 
   <td colname="col2"> <p>Aggiunge automaticamente l'ID rapporto al nome del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Aggiungi data al nome del file </p> </td> 
   <td colname="col2"> <p> Aggiunge automaticamente la data del rapporto al nome del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lingua </p> </td> 
   <td colname="col2"> <p> Consente di selezionare una lingua per il rapporto. Potete inviare il rapporto in una delle lingue seguenti, indipendentemente dalla lingua utilizzata </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">English </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">Spagnolo </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">Cinese semplificato </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">Cinese tradizionale </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">Francese </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">Tedesco </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">Giapponese </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">Portoghese </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codifica </p> </td> 
   <td colname="col2"> <p>Specifica un tipo di codifica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Invia rapporto come file compresso </p> </td> 
   <td colname="col2"> <p> Comprime il file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Invia file firma digitale </p> </td> 
   <td colname="col2"> <p>Crea una firma digitale da inviare all'e-mail. </p> </td> 
  </tr> 
 </tbody> 
</table>


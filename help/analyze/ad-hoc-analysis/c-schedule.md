---
description: Potete personalizzare la pianificazione della consegna per i rapporti. È possibile interrompere la consegna a una determinata ora, oppure specificare quante volte si desidera inviare un rapporto. Le nuove pianificazioni utilizzano l'intervallo di date definito nel rapporto. Ad esempio, se create un rapporto per gli ultimi 90 giorni e lo pianificate per l’esecuzione giornaliera, riceverete un rapporto per gli ultimi 90 giorni al giorno. Se crei un rapporto con un intervallo di date statico dal calendario, lo stesso rapporto verrà visualizzato ogni volta che viene inviato.
title: Pianificazione Manager
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 3%

---


# Pianificazione Manager

>[!IMPORTANT]
>
> Adobe sta spostando  Ad Hoc Analysis a fine ciclo di vita il 1 marzo 2021. [Ulteriori informazioni...](https://adobe.ly/discoverworkspace).

Potete personalizzare la pianificazione della consegna per i rapporti. È possibile interrompere la consegna a una determinata ora, oppure specificare quante volte si desidera inviare un rapporto. Le nuove pianificazioni utilizzano l&#39;intervallo di date definito nel rapporto. Ad esempio, se create un rapporto per gli ultimi 90 giorni e lo pianificate per l’esecuzione giornaliera, riceverete un rapporto per gli ultimi 90 giorni al giorno. Se crei un rapporto con un intervallo di date statico dal calendario, lo stesso rapporto verrà visualizzato ogni volta che viene inviato.

## Pianificazione Manager {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

Potete personalizzare la pianificazione della consegna per i rapporti. È possibile interrompere la consegna a una determinata ora, oppure specificare quante volte si desidera inviare un rapporto. Le nuove pianificazioni utilizzano l&#39;intervallo di date definito nel rapporto. Ad esempio, se create un rapporto per gli ultimi 90 giorni e lo pianificate per l’esecuzione giornaliera, riceverete un rapporto per gli ultimi 90 giorni al giorno. Se crei un rapporto con un intervallo di date statico dal calendario, lo stesso rapporto verrà visualizzato ogni volta che viene inviato.

>[!NOTE]
>
>Quando un account utente è disattivato, tutte le consegne programmate dei rapporti create da tale utente vengono sospese.

Per garantire che gli elementi di riga in una suddivisione siano persistenti nei rapporti salvati e pianificati, utilizzate la **[!UICONTROL Edit Items]** funzione in Generatore [di](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) tabelle per creare elenchi di dimensioni fisse nelle suddivisioni.

>[!IMPORTANT]
>
> Ad Hoc Analysis consente di definire e pianificare rapidamente i rapporti per specifiche esigenze di reporting ad hoc, tempestive e specifiche. Non è progettato per l&#39;esportazione completa di dati con un numero o più righe, colonne, valutazioni metriche o dettagliate suddivisioni utilizzando estratti di dati.
>
>I vincoli pratici per i report pianificati in  Ad Hoc Analysis si basano su questo principio: Se il rapporto non viene generato entro dieci minuti (il timeout per  Ad Hoc Analysis), è probabile che sia troppo complesso.
>
>Molto probabilmente il rapporto contiene troppe metriche, troppe suddivisioni di elementi dimensionali, troppe righe o colonne o altri estremi che rendono troppo lungo il processo di generazione dei report per  Ad Hoc Analysis. Questo tipo di report deve essere eseguito in Data Warehouse, una funzionalità Adobe Analytics  realizzata per l&#39;estrazione dati completa in esecuzione offline con generazione di report che può richiedere molte ore o giorni.
>
>Ad esempio,  Ad Hoc Analysis è in grado di gestire 50.000 righe di dati, ma suddividere tali dati per dieci tipi di browser significa 50.000 volte 10, un aumento esponenziale che potrebbe essere troppo complesso per uno strumento di reporting ad hoc. Ulteriori analisi approfondite aumentano di nuovo le righe di dati in modo esponenziale. La definizione del numero o delle righe, colonne e suddivisioni effettivi da vincolare per  report Ad Hoc Analysis non può essere definita in termini netti, ma è una combinazione di tutti questi fattori.

## Pianificazione di un rapporto per la consegna {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Passaggi che descrivono come pianificare un rapporto per la consegna.

<!-- 

t_schedule_delivery.xml

 -->

1. Fai clic su **[!UICONTROL Tools]**, quindi su **[!UICONTROL Schedule Manager]**.
1. On the [!UICONTROL Schedule Manager], click **[!UICONTROL New.]**

## Opzioni di consegna - Definizioni {#reference_CA49AC560258471AAE959BCA243F170C}

Definizioni per le impostazioni in Opzioni consegna.

<!-- 

r_delivery_options.xml

 -->

Potete inviare le informazioni visualizzate nel rapporto attualmente selezionato al formato selezionato. Potete inviarlo una sola volta o impostare un programma di consegna e specificare il formato di file desiderato. È possibile creare e inviare una firma digitale per assicurare al destinatario che il file è autentico. Potete inviare il file a un indirizzo e-mail o caricarlo su un server FTP.

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
   <td colname="col2"> <p>Indica l’ID del rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato file </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: Invia il rapporto in un foglio di calcolo, incluse tutte le immagini. Modificabile in Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: Invia il rapporto in Valori separati da virgole. Modificabile in un semplice editor di testo (come Blocco note) o in un editor di fogli di calcolo (come Excel). Non contiene immagini. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: Invia il rapporto in formato documento portatile. Non modificabile e visualizzabile in  Adobe Acrobat o  Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: Invia il rapporto in un allegato Hypertext Markup Language. Questo è il formato di cui sono composti la maggior parte dei siti Web. Modificabile solo se si ha familiarità con il codice HTML. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word: Invia il rapporto in formato RTF, incluse tutte le immagini. Modificabile in Microsoft Word o WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Advanced </p> </td> 
   <td colname="col2"> <p> See <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   > Advanced Format Settings</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destinazione file </p> </td> 
   <td colname="col2"> <p>E-mail: Impostazioni da inviare via e-mail. </p> <p>FTP: Impostazioni per il caricamento su un server FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervallo report e programma di consegna </p> </td> 
   <td colname="col2"> <p>Specifica quando distribuire il report. Le nuove pianificazioni utilizzano l'intervallo di date definito nel rapporto. Ad esempio, se create un rapporto per gli ultimi 90 giorni e lo pianificate per l’esecuzione giornaliera, riceverete un rapporto per gli ultimi 90 giorni al giorno. Se crei un rapporto con un intervallo di date statico dal calendario, lo stesso rapporto verrà visualizzato ogni volta che viene inviato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impostazioni di formato avanzate - Definizioni {#reference_F99B65BF7C9746638D8147EED147015B}

Definizioni per le impostazioni in Impostazioni formato avanzate.

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
   <td colname="col2"> <p>Un nome di file definito dall'utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiungi ID al nome del file </p> </td> 
   <td colname="col2"> <p>Aggiunge automaticamente l'ID del rapporto al nome del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Aggiungi data al nome del file </p> </td> 
   <td colname="col2"> <p> Aggiunge automaticamente la data del rapporto al nome del file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lingua </p> </td> 
   <td colname="col2"> <p> Consente di selezionare una lingua per il rapporto. Puoi inviare il rapporto in una qualsiasi delle seguenti lingue, indipendentemente dalla lingua utilizzata </p> 
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
   <td colname="col2"> <p>Crea una firma digitale da inviare con il messaggio e-mail. </p> </td> 
  </tr> 
 </tbody> 
</table>


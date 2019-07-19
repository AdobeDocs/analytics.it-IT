---
description: Analisi ad hoc si integra con l'ambiente Segmentazione di Analytics, che consente di creare, condividere, gestire e applicare segmenti di visitatori tra i prodotti Adobe. Analisi ad hoc fornisce un'interfaccia utente basata su Java per il Generatore di segmenti e il Gestore segmenti identico agli strumenti basati su Web utilizzati da altri strumenti Analytics, che corrispondono alle chiamate server e forniscono le stesse funzionalità e funzionalità di una console basata su Java.
seo-description: Analisi ad hoc si integra con l'ambiente Segmentazione di Analytics, che consente di creare, condividere, gestire e applicare segmenti di visitatori tra i prodotti Adobe. Analisi ad hoc fornisce un'interfaccia utente basata su Java per il Generatore di segmenti e il Gestore segmenti identico agli strumenti basati su Web utilizzati da altri strumenti Analytics, che corrispondono alle chiamate server e forniscono le stesse funzionalità e funzionalità di una console basata su Java.
seo-title: Creare segmenti
solution: Analytics
title: Creare segmenti
topic: Analisi ad hoc
uuid: e 14 fb 777-900 a -4700-8 dc 7-56 a 45 c 678 d 29
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Creare segmenti

Analisi ad hoc si integra con l'ambiente Segmentazione di Analytics, che consente di creare, condividere, gestire e applicare segmenti di visitatori tra i prodotti Adobe. Analisi ad hoc fornisce un'interfaccia utente basata su Java per il Generatore di segmenti e il Gestore segmenti identico agli strumenti basati su Web utilizzati da altri strumenti Analytics, che corrispondono alle chiamate server e forniscono le stesse funzionalità e funzionalità di una console basata su Java.

Ad Hoc Analysis includes familiar features for building segments, plus new feature upgrades like the [Segment Manager](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_manage) used to set up a segment management [workflow](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_workflow). As always, you can build and save segments in the [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_build) or [generate segments from a Fallout report](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=t_seg_fallout) from the ad hoc analysis console, and then save the new or extended segments to the audience library for general access and application. ![](assets/seg__overview_ad_hoc.png)

## Unified Segmentation in Ad Hoc Analysis {#section_5FA03A06DE054448AD519CE30C39E294}

For information and instructions on building and managing segments in the Unified Segmentation environment including ad hoc analysis features, see the [Unified Segmentation](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=index) documentation.

* [Nuove funzionalità](../../analyze/ad-hoc-analysis/c-content-ref.md#section_BD58629D1A9346BF879E229FA6BEC7A2)
* [Modifiche alla definizione del segmento](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_definition)
* [Cosa succede ai segmenti esistenti?](../../analyze/ad-hoc-analysis/c-content-ref.md#section_76CF47142D1A4FB6A0718AD9073049FE)
* [Cosa succede alle cartelle dei segmenti esistenti?](../../analyze/ad-hoc-analysis/c-content-ref.md#section_FB04DCF775694E69B761DCA53F301C30)
* [Posso gestire tutti i segmenti di Analytics in Gestione segmenti?](../../analyze/ad-hoc-analysis/c-content-ref.md#section_AF5EDD72C74A4739BD40C4AF125CE489)
* [Cos'è un contenitore hit? Is it different from a Page View Container?](../../analyze/ad-hoc-analysis/c-content-ref.md#section_65BBE60A836C4001938830DDA15DC256)
* [Quali diritti e privilegi sono necessari per utilizzare, creare e gestire i segmenti?](../../analyze/ad-hoc-analysis/c-content-ref.md#section_648DFA3A882146C485A84ED014EEC707)
* [Cosa devo fare con i segmenti duplicati che hanno](../../analyze/ad-hoc-analysis/c-content-ref.md#section_E2C3A1B4B4274D1B86CAA9C0359D049C)
* [In che modo Adobe consiglia di pulire i segmenti?](../../analyze/ad-hoc-analysis/c-content-ref.md#section_3AC2D265F9084557A24C6FB39DC6EE49)
* [Perché non posso eliminare questo segmento?](../../analyze/ad-hoc-analysis/c-content-ref.md#section_0FEB6711031A4ABCA915CDA745ECF38D)
* [Ulteriori informazioni sui segmenti esistenti](../../analyze/ad-hoc-analysis/c-content-ref.md#section_83ACAB256F394DCD8B424D8920BDD853)

## Funzioni {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* [I segmenti](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_overview) sono universali a tutte le suite di rapporti. In precedenza, i segmenti erano specifici della suite di rapporti.
* The [Segment Manager](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_manage) lets you set up [workflows](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_workflow) with segment sharing, tagging, verification, and approval features.

* The [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_build_ui) has been updated to simplify segment creation.
* You can [tag segments](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_tag) to organize and search later instead of using folders. Previously, you used folders (in [!DNL ad hoc analysis]) to organize your segments.

* You can create [Sequential Segments](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_sequential) outside of Ad Hoc Analysis.
* 

>[!NOTE]
>
>In Analisi ad hoc non è possibile aggiungere intervalli di date ai segmenti. Questa funzione è disponibile in Analysis Workspace. In Analisi ad hoc non è inoltre possibile utilizzare la sequenza Solo prima/Solo dopo.

## What happened to my existing segments? {#section_76CF47142D1A4FB6A0718AD9073049FE}

I segmenti esistenti continueranno a funzionare come prima dell'introduzione di Analytics Segmentation. Tutti i rapporti che presentano questi segmenti continueranno a funzionare correttamente.

Most former pre-defined and suite segments will be migrated over as [segment templates](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_templates) into the segment builder. I modelli di segmento vengono utilizzati per creare rapidamente segmenti personalizzati con audience comuni. I modelli di segmento non possono essere applicati direttamente a un rapporto, ma possono essere salvati facilmente in un segmento personalizzato.

## What happened to my existing segment folders? {#section_FB04DCF775694E69B761DCA53F301C30}

Instead of (Ad Hoc Analysis) folders, the Segment Manager uses [tags](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_tag). I nomi delle cartelle vengono automaticamente convertiti in tag e questi tag vengono applicati ai rispettivi segmenti.

## Can I manage all Analytics segments in the Segment Manager? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

In Gestione segmenti Analisi ad hoc, puoi vedere solo i segmenti che appartengono a te (i segmenti creati) e i segmenti che sono stati condivisi con te.

## Cos'è un contenitore hit? Is it different from a Page View Container? {#section_65BBE60A836C4001938830DDA15DC256}

Il contenitore Visualizzazione pagina è stato rinominato nel contenitore Hit per indicare che il contenitore segmenta tutti i tipi di dati e non solo le visualizzazioni di pagina. For example, link tracking calls, and [!DNL trackAction] calls from the mobile SDKs are all included or excluded by the hit container.

Tenete presente che non si verifica una modifica al modo in cui funziona questa contenitore, ma è stata rinominata semplicemente.

## What rights and privileges do I need to use, create, and manage segments? {#section_648DFA3A882146C485A84ED014EEC707}

Tutti gli utenti possono creare e modificare segmenti personali. Questi segmenti possono essere condivisi direttamente con qualsiasi altro utente Analytics.

Admins can edit any segment, and [share segments](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=t_seg_share) with groups and [set rights](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_rights) to access segments for the organization.

## What should I do with duplicate segments that have the same name but may have different definitions? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Poiché i segmenti funzionano in più suite di rapporti, potresti notare che hai più segmenti con lo stesso nome. Consigliamo di:

* Rinominare i segmenti con lo stesso nome, ma diverse definizioni o
* Eliminare i segmenti non più necessari.

## How does Adobe recommend that I clean up segments? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Assegna tag a tutti i segmenti con tag legacy.
* Controlla i segmenti che hai.
* Aggiungili alla libreria segmenti, ove applicabile.
* Approvare segmenti canonici.
* Assegna tag ai segmenti in base alle best practice.

## Why can't I delete this segment? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

If the segment was [published to the Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=t_publish_audience_segment), you cannot delete it or edit it. Tuttavia, potete copiarlo e modificarne la versione copiata.

## More on what happens to your existing segments {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Categoria segmento </th> 
   <th colname="col2" class="entry"> Cosa succede a questi segmenti? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Segmenti preferiti (Analisi ad hoc) </td> 
   <td colname="col2">Questi segmenti di analisi ad hoc vengono visualizzati come segmenti regolari in Adobe Analytics. <p>Non devono essere confusi con la funzione Preferiti in Gestione segmenti che consente di contrassegnare i segmenti come preferiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti preconfigurati: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Visite a pagina singola </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visite da dispositivi mobili </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visite da ricerca naturale </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visite da Paid Search </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visite con cookie ID visitatore </li> 
    </ul> </td> 
   <td colname="col2"> <p>These segments will be migrated over as <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_templates" format="http" scope="external"> segment templates</a> into the segment builder. </p> <p>I rapporti esistenti che presentano questi segmenti continueranno a funzionare correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti di Experience Cloud (Suite): 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Acquirenti non acquirenti </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Acquirenti </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Visite prima visita </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visite da social sites </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visite di oltre 10 minuti * </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visite con 5 + Visite precedenti * </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visite da Facebook * </li> 
    </ul> </td> 
   <td colname="col2"> <p> Most of these segments (except the ones marked with an asterisk *) will be migrated over as <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_templates" format="http" scope="external"> segment templates</a> into the segment builder. Sono stati aggiunti inoltre diversi modelli di segmento. </p> <p>I rapporti esistenti che presentano questi segmenti continueranno a funzionare correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti amministratore <p>(detti anche segmenti "Global") </p> </td> 
   <td colname="col2"> <p> <b>I segmenti di amministratore</b> verranno migrati nella nuova interfaccia del segmento e saranno visualizzati come segmenti condivisi con tutti. </p> <p>Il proprietario di questi segmenti è impostato sull'amministratore con l'account più vecchio nell'elenco degli utenti admin della società di accesso, tuttavia, tutti gli amministratori possono eliminare, modificare e condividere questi segmenti. </p> <p>L'interfaccia di gestione segmenti nell'Admin Console in cui gli amministratori creati e gestiti non sono più disponibili. Adesso, gli amministratori devono usare il nuovo generatore di segmenti per creare segmenti e condividerli con gruppi o singoli gruppi oppure con tutti. </p> </td> 
  </tr> 
 </tbody> 
</table>


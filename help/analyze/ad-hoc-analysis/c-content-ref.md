---
description: ' Ad Hoc Analysis si integra con l''ambiente di segmentazione di Analytics, consentendo di creare, condividere, gestire e applicare segmenti di visitatori tra  prodotti di Adobe.  Ad Hoc Analysis fornisce un''interfaccia utente basata su Java per il Segment Builder e il Segment Manager identico agli strumenti basati sul Web utilizzati da altri strumenti Analytics, alle chiamate dei server corrispondenti e alle stesse funzionalità di una console basata su Java.'
title: Generare segmenti
topic: Ad hoc analysis
uuid: e14fb777-900a-4700-8dc7-56a45c678d29
translation-type: tm+mt
source-git-commit: 42782779a9b9d5f4795b2663ec78678cd3aada02
workflow-type: tm+mt
source-wordcount: '1226'
ht-degree: 1%

---


# Generare segmenti

>[!IMPORTANT]
>
> Adobe si sta muovendo  Ad Hoc Analysis fino alla fine del suo ciclo di vita il 1 marzo 2021. [Ulteriori informazioni](https://adobe.ly/discoverworkspace)

 Ad Hoc Analysis si integra con l&#39;ambiente di segmentazione di Analytics, consentendo di creare, condividere, gestire e applicare segmenti di visitatori tra  prodotti di Adobe.  Ad Hoc Analysis fornisce un&#39;interfaccia utente basata su Java per il Segment Builder e il Segment Manager identico agli strumenti basati sul Web utilizzati da altri strumenti Analytics, alle chiamate dei server corrispondenti e alle stesse funzionalità di una console basata su Java.

 Ad Hoc Analysis include funzionalità familiari per la creazione di segmenti, oltre a nuovi aggiornamenti di funzionalità come [Segment Manager](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-manage.html) utilizzati per impostare un [flusso di lavoro](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html)di gestione segmenti. Come sempre, puoi creare e salvare segmenti nel Generatore [di](/help/components/segmentation/segmentation-workflow/seg-build.md) segmenti o [generare segmenti da un rapporto](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.html) di abbandono dalla console di analisi ad hoc, quindi salvare i segmenti nuovi o estesi nella libreria del pubblico per l’accesso e l’applicazione generali. ![](assets/seg__overview_ad_hoc.png)

## Segmentazione unificata in  Ad Hoc Analysis {#section_5FA03A06DE054448AD519CE30C39E294}

Per informazioni e istruzioni sulla creazione e la gestione di segmenti nell’ambiente di segmentazione unificata, comprese le funzioni di analisi ad hoc, consulta la documentazione relativa alla segmentazione [](/help/components/segmentation/segmentation-workflow/seg-build.md) unificata.

* [Nuove funzionalità](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_BD58629D1A9346BF879E229FA6BEC7A2)
* [Cos&#39;è successo ai segmenti esistenti?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_76CF47142D1A4FB6A0718AD9073049FE)
* [Cos’è successo alle cartelle dei segmenti esistenti?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_FB04DCF775694E69B761DCA53F301C30)
* [Posso gestire tutti i segmenti di Analytics in Segment Manager?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_AF5EDD72C74A4739BD40C4AF125CE489)
* [Cos&#39;è un contenitore Hit? È diverso da un contenitore Visualizzazione pagina?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_65BBE60A836C4001938830DDA15DC256)
* [Quali diritti e privilegi devo utilizzare, creare e gestire i segmenti?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_648DFA3A882146C485A84ED014EEC707)
* [Cosa devo fare con segmenti duplicati che hanno...](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_E2C3A1B4B4274D1B86CAA9C0359D049C)
* [In che modo  Adobe consiglia di ripulire i segmenti?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_3AC2D265F9084557A24C6FB39DC6EE49)
* [Perché non posso eliminare questo segmento?](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_0FEB6711031A4ABCA915CDA745ECF38D)
* [Ulteriori informazioni su ciò che accade ai segmenti esistenti](/help/analyze/ad-hoc-analysis/c-content-ref.md#section_83ACAB256F394DCD8B424D8920BDD853)

## Funzioni {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* [I segmenti](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html) sono universali per tutte le suite di rapporti. Precedentemente, i segmenti erano specifici della suite di rapporti.
* Gestione [](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-manage.html) segmenti consente di impostare [flussi di lavoro](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) con funzioni di condivisione dei segmenti, assegnazione di tag, verifica e approvazione.
* Il Generatore di [segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md) è stato aggiornato per semplificare la creazione dei segmenti.
* Puoi assegnare [tag ai segmenti](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-tag.html) per organizzarli ed effettuare ricerche in un secondo momento, anziché utilizzare le cartelle. Precedentemente, per organizzare i segmenti erano state utilizzate le cartelle (in [!DNL ad hoc analysis]).
* Puoi creare segmenti [](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-sequential-build.html) sequenziali all’esterno di  Ad Hoc Analysis.

   >[!NOTE]
   >
   >In  Ad Hoc Analysis non è possibile aggiungere intervalli di date ai segmenti. Questa funzione è disponibile in  Analysis Workspace. Non è inoltre possibile utilizzare la sequenza Solo prima/Solo dopo in  Ad Hoc Analysis.

## Cos&#39;è successo ai segmenti esistenti? {#section_76CF47142D1A4FB6A0718AD9073049FE}

I segmenti esistenti continueranno a funzionare come prima dell&#39;introduzione della segmentazione di Analytics. Tutti i report a cui sono applicati questi segmenti continueranno a funzionare correttamente.

La maggior parte dei segmenti predefiniti e suite precedenti verranno trasferiti come modelli di segmento nel generatore di segmenti. I modelli di segmento sono utilizzati per creare rapidamente segmenti personalizzati con audience comuni. I modelli di segmento non possono essere applicati direttamente a un report, ma possono essere facilmente salvati in un segmento personalizzato.

## Cos’è successo alle cartelle dei segmenti esistenti? {#section_FB04DCF775694E69B761DCA53F301C30}

Invece di ( Ad Hoc Analysis) cartelle, Segment Manager utilizza [i tag](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-tag.html). I nomi delle cartelle vengono automaticamente convertiti in tag e tali tag vengono applicati ai rispettivi segmenti.

## Posso gestire tutti i segmenti di Analytics in Segment Manager? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

In  Ad Hoc Analysis Segment Manager è possibile visualizzare solo i segmenti che appartengono a te (i segmenti creati) e i segmenti che sono specificamente condivisi con te.

## Cos&#39;è un contenitore Hit? È diverso da un contenitore Visualizzazione pagina? {#section_65BBE60A836C4001938830DDA15DC256}

Il contenitore Visualizzazione pagina è stato rinominato nel contenitore Hit per indicare che questo contenitore segmenta tutti i tipi di dati e non solo le visualizzazioni di pagina. Ad esempio, le chiamate di tracciamento dei collegamenti e [!DNL trackAction] le chiamate dagli SDK per dispositivi mobili sono tutte incluse o escluse dal contenitore degli hit.

Notate che non c&#39;è stata una modifica al modo in cui funziona questo contenitore, è stato semplicemente rinominato.

## Quali diritti e privilegi devo utilizzare, creare e gestire i segmenti? {#section_648DFA3A882146C485A84ED014EEC707}

Tutti gli utenti possono creare e modificare segmenti personali. Questi segmenti possono essere condivisi direttamente con qualsiasi altro utente Analytics.

Gli amministratori possono modificare qualsiasi segmento, [condividere segmenti](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/t-seg-share.html) con gruppi e [impostare diritti](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-rights.html) per accedere ai segmenti dell&#39;organizzazione.

## Cosa devo fare con segmenti duplicati con lo stesso nome ma con definizioni diverse? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Poiché i segmenti funzionano in più suite di rapporti, potresti avere più segmenti con lo stesso nome. È consigliabile

* Rinominare segmenti con lo stesso nome, ma definizioni diverse, oppure
* Elimina segmenti non più necessari.

## In che modo  Adobe consiglia di ripulire i segmenti? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Assegna tag a tutti i segmenti con tag legacy.
* Rivedete i segmenti che avete.
* Aggiungeteli alla libreria dei segmenti, se applicabile.
* Approva segmenti canonici.
* Assegnare tag ai segmenti in base alle best practice.

## Perché non posso eliminare questo segmento? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Se il segmento è stato [pubblicato nel Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html), non è possibile eliminarlo o modificarlo. Tuttavia, potete copiarlo e modificare la versione copiata.

## Ulteriori informazioni su ciò che accade ai segmenti esistenti {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Categoria segmento </th> 
   <th colname="col2" class="entry"> Cosa succede a questi segmenti? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Segmenti preferiti ( Ad Hoc Analysis) </td> 
   <td colname="col2">Questi segmenti  Ad Hoc Analysis vengono visualizzati come segmenti regolari in  Adobe Analytics. <p>Non devono essere confusi con la funzione Preferiti in Segment Manager (Gestore segmenti), che consente di contrassegnare i segmenti come preferiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti pre-configurati: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Visite a pagina singola </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visite da dispositivi mobili </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visite da Ricerca naturale </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visite da ricerca a pagamento </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visite con il cookie ID visitatore </li> 
    </ul> </td> 
   <td colname="col2"> <p>Questi segmenti verranno trasferiti come modelli di segmento nel generatore di segmenti. </p> <p>I rapporti esistenti con questi segmenti continueranno a funzionare correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti di Experienci Cloud (Suite) : 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Non acquirenti </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Acquirenti </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Prima visita </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visite dai siti social </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visite di oltre 10 minuti* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visite con 5+ visite precedenti* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visite da Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> La maggior parte di questi segmenti (tranne quelli contrassegnati con un asterisco *) verrà migrata come modelli di segmento nel generatore di segmenti. Inoltre, sono stati aggiunti diversi nuovi modelli di segmento. </p> <p>I rapporti esistenti con questi segmenti continueranno a funzionare correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti di amministrazione <p>(noti anche come segmenti "globali") </p> </td> 
   <td colname="col2"> <p> <b>I segmenti amministratore</b> verranno migrati nella nuova interfaccia del segmento e visualizzati come segmenti condivisi con tutti. </p> <p>Il proprietario di questi segmenti è impostato sull’amministratore con l’account più vecchio nell’elenco degli utenti di amministrazione della società di accesso. Tuttavia, tutti gli amministratori possono eliminare, modificare e condividere questi segmenti. </p> <p>L'interfaccia di gestione dei segmenti nel Admin Console  in cui gli amministratori hanno creato e gestito questi segmenti globali non è più disponibile. Adesso, gli amministratori devono usare il nuovo generatore di segmenti per creare segmenti e condividerli con gruppi o individui appropriati o con tutti. </p> </td> 
  </tr> 
 </tbody> 
</table>


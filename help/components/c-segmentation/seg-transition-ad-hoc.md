---
description: Se utilizzi il Generatore di segmenti in Analisi ad hoc, questa domanda frequente spiega cosa accade ai segmenti e alle cartelle esistenti e quali azioni devi intraprendere.
keywords: segmentazione; segmenti
seo-description: Se utilizzi il Generatore di segmenti in Analisi ad hoc, questa domanda frequente spiega cosa accade ai segmenti e alle cartelle esistenti e quali azioni devi intraprendere.
seo-title: Guida alla transizione per Analisi ad hoc
solution: Analytics
title: Guida alla transizione per Analisi ad hoc
topic: Segmenti
uuid: d 409 d 71 a-f 8 d 9-42 a 2-add 2-37 d 426 cd 40 d 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Guida alla transizione per Analisi ad hoc

Se utilizzi il Generatore di segmenti in Analisi ad hoc, questa domanda frequente spiega cosa accade ai segmenti e alle cartelle esistenti e quali azioni devi intraprendere.

## Funzioni {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* I segmenti sono universali a tutte le suite di rapporti. In precedenza, i segmenti erano specifici della suite di rapporti.
* Analisi ad hoc include aggiornamenti al Generatore di segmenti e un aggiornamento completo di Gestione segmenti.
* Ora potete assegnare tag ai segmenti per organizzare e cercare in un secondo momento anziché utilizzare le cartelle. Previously, you used folders in [!DNL Ad Hoc Analysis] to organize your segments.

## What happened to my existing segments? {#section_76CF47142D1A4FB6A0718AD9073049FE}

I segmenti esistenti continueranno a funzionare come prima. Tutti i rapporti che presentano questi segmenti continueranno a funzionare correttamente.

La maggior parte dei precedenti segmenti predefiniti e delle suite verranno migrati come modelli di segmento nel generatore di segmenti. I modelli di segmento vengono utilizzati per creare rapidamente segmenti personalizzati con audience comuni. I modelli di segmento non possono essere applicati direttamente a un rapporto, ma possono essere salvati facilmente in un segmento personalizzato.

I modelli di segmento sono contrassegnati con un'icona speciale in Segment Builder (Generatore segmenti).

## What happened to my existing segment folders? {#section_FB04DCF775694E69B761DCA53F301C30}

Invece di cartelle di analisi ad hoc, il Gestore segmenti utilizza i tag. I nomi delle cartelle vengono automaticamente convertiti in tag e questi tag vengono applicati ai rispettivi segmenti.

## What happened to scheduled reports that have segments applied? {#section_81D1B215533C46E99E17BAE7A3376FDF}

I rapporti pianificati continuano a essere eseguiti correttamente con i segmenti definiti.

Quando eliminate un segmento, i report pianificati e le dashboard in cui questo segmento è applicato continuano a funzionare normalmente, ovvero il segmento o il dashboard continua a utilizzare il segmento eliminato.

## Cos'è un contenitore hit? Is it different from a Page View Container? {#section_65BBE60A836C4001938830DDA15DC256}

Il contenitore Visualizzazione pagina è stato rinominato nel contenitore Hit per indicare che il contenitore segmenta tutti i tipi di dati e non solo le visualizzazioni di pagina. Ad esempio, le chiamate di tracciamento dei collegamenti e le chiamate trackaction dagli SDK per dispositivi mobili sono tutte incluse o escluse dal contenitore hit.

Tenete presente che non si verifica una modifica al modo in cui funziona questa contenitore, ma è stata rinominata semplicemente.

## What rights and privileges do I need to use, create, and manage segments? {#section_648DFA3A882146C485A84ED014EEC707}

Tutti gli utenti possono creare e modificare segmenti personali. Questi segmenti possono essere condivisi direttamente con qualsiasi altro utente Analytics. Gli utenti Ad Hoc Analysis possono vedere i segmenti creati e quelli condivisi direttamente con l'utente.

Nella console Web unificazione unificata, gli amministratori possono modificare qualsiasi segmento e condividere segmenti con gruppi e con chiunque nell'organizzazione.

## Can I see all segments in my company? {#section_AC2D328C7410419E80C7C17971CD95B3}

Vengono visualizzati tutti i segmenti di analisi ad hoc che possedete e i segmenti che sono specificamente condivisi con voi.

## Can I manage all Analytics segments in the Segment Manager? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

L'analisi ad hoc visualizza solo i segmenti creati da voi o segmenti condivisi espressamente con voi. Solo per analisi ad hoc, puoi utilizzare Gestione segmenti (Organizza segmenti) per gestire segmenti di analisi ad hoc. Utilizza il Gestore segmenti in Segmentazione unificata per gestire tutti i segmenti di Analytics.

## What should I do with duplicate segments that have the same name but may have different definitions? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Ora che i segmenti funzionano in più suite di rapporti, potresti notare che hai più segmenti con lo stesso nome. Consigliamo di:

* Rinominare i segmenti con lo stesso nome, ma diverse definizioni o
* Eliminare i segmenti non più necessari.

## How does Adobe recommend that I clean up segments? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Assegna tag a tutti i segmenti con tag legacy.
* Controlla i segmenti che hai.
* Aggiungili alla libreria segmenti, ove applicabile.
* Approvare segmenti canonici.

## Why can't I delete this segment? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Se il segmento è stato pubblicato in Experience Cloud, non puoi eliminarlo o modificarlo. Tuttavia, potete copiarlo e modificarne la versione copiata.

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
   <td colname="col1"> Segmenti preferiti in Analisi ad hoc </td> 
   <td colname="col2">Questi segmenti di analisi ad hoc vengono visualizzati come segmenti regolari in Adobe Analytics. <p>Non devono essere confusi con la funzione Preferiti in Gestione segmenti che consente di contrassegnare i segmenti come preferiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti preconfigurati in Analisi ad hoc: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Visite a pagina singola </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visite da dispositivi mobili </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visite da ricerca naturale </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visite da Paid Search </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visite con cookie ID visitatore </li> 
    </ul> </td> 
   <td colname="col2"> <p>Questi segmenti verranno migrati come modelli di segmento nel generatore di segmenti. </p> <p>I rapporti esistenti che presentano questi segmenti continueranno a funzionare correttamente. </p> </td> 
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
   <td colname="col2"> <p> La maggior parte di questi segmenti (eccetto quelli contrassegnati con un asterisco *) verranno migrati come modelli di segmento nel generatore di segmenti. Sono stati aggiunti inoltre diversi modelli di segmento. </p> <p>I rapporti esistenti che presentano questi segmenti continueranno a funzionare correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>


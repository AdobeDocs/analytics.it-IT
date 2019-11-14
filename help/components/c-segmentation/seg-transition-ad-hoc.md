---
description: Se sei abituato a lavorare con Segment Builder (Generatore di segmenti) in Analisi ad hoc, questa domanda frequente spiega cosa accade ai segmenti e alle cartelle esistenti e quali azioni devi intraprendere.
keywords: segmentation;segments
solution: Analytics
title: Guida alla transizione per Ad Hoc Analysis
topic: Segments
uuid: d409d71a-f8d9-42a2-add2-37d426cd40d1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Guida alla transizione per Ad Hoc Analysis

Se sei abituato a lavorare con Segment Builder (Generatore di segmenti) in Analisi ad hoc, questa domanda frequente spiega cosa accade ai segmenti e alle cartelle esistenti e quali azioni devi intraprendere.

## Funzioni {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* I segmenti sono universali per tutte le suite di rapporti. Precedentemente, i segmenti erano specifici della suite di rapporti.
* Analisi ad hoc include aggiornamenti al Generatore di segmenti e un aggiornamento completo del Gestore segmenti.
* Ora puoi assegnare tag ai segmenti per organizzarli ed effettuare ricerche in un secondo momento, anziché utilizzare le cartelle. Precedentemente, per organizzare [!DNL Ad Hoc Analysis] i segmenti si utilizzavano le cartelle.

## Cosa è successo ai segmenti esistenti? {#section_76CF47142D1A4FB6A0718AD9073049FE}

I segmenti esistenti continueranno a funzionare come prima. Tutti i report a cui sono applicati questi segmenti continueranno a funzionare correttamente.

La maggior parte dei segmenti predefiniti e suite precedenti verranno trasferiti come modelli di segmento nel generatore di segmenti. I modelli di segmento sono utilizzati per creare rapidamente segmenti personalizzati con audience comuni. I modelli di segmento non possono essere applicati direttamente a un report, ma possono essere facilmente salvati in un segmento personalizzato.

I modelli di segmento sono contrassegnati da un’icona speciale in Generatore di segmenti.

## Cos'è successo alle cartelle dei segmenti esistenti? {#section_FB04DCF775694E69B761DCA53F301C30}

Invece delle cartelle di analisi ad hoc, Segment Manager utilizza i tag . I nomi delle cartelle vengono automaticamente convertiti in tag e tali tag vengono applicati ai rispettivi segmenti.

## Cos'è successo ai report pianificati con segmenti applicati? {#section_81D1B215533C46E99E17BAE7A3376FDF}

I report pianificati continuano a essere eseguiti correttamente con i segmenti definiti.

Quando eliminate un segmento, i rapporti pianificati e le dashboard a cui è applicato questo segmento continuano a funzionare normalmente, ovvero il segmento o la dashboard continua a utilizzare il segmento eliminato.

## Cos'è un contenitore Hit? È diverso da un contenitore Visualizzazione pagina? {#section_65BBE60A836C4001938830DDA15DC256}

Il contenitore Visualizzazione pagina è stato rinominato nel contenitore Hit per indicare che questo contenitore segmenta tutti i tipi di dati e non solo le visualizzazioni di pagina. Ad esempio, le chiamate di tracciamento dei collegamenti e le chiamate trackAction dagli SDK per dispositivi mobili sono tutte incluse o escluse dal contenitore degli hit.

Notate che non c'è stata una modifica al modo in cui funziona questo contenitore, è stato semplicemente rinominato.

## Quali diritti e privilegi devo utilizzare, creare e gestire i segmenti? {#section_648DFA3A882146C485A84ED014EEC707}

Tutti gli utenti possono creare e modificare segmenti personali. Questi segmenti possono essere condivisi direttamente con qualsiasi altro utente Analytics. Gli utenti di Analisi ad hoc possono vedere i segmenti creati e condivisi direttamente con l'utente.

Nella console Web Segmentazione unificata, gli amministratori possono modificare qualsiasi segmento e condividere i segmenti con i gruppi e con tutti gli utenti dell’organizzazione.

## Posso visualizzare tutti i segmenti nella mia azienda? {#section_AC2D328C7410419E80C7C17971CD95B3}

Vengono visualizzati tutti i segmenti di analisi ad hoc di proprietà e quelli specificamente condivisi con l'utente.

## Posso gestire tutti i segmenti di Analytics in Segment Manager? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

L'analisi ad hoc visualizza solo i segmenti generati dall'utente stesso o quelli condivisi specificatamente con l'utente. Solo per l’analisi ad hoc, puoi usare Segment Manager (Organizza segmenti) per gestire segmenti di analisi ad hoc. Utilizza Segment Manager (Gestore segmenti) in Unified Segmentation per gestire tutti i segmenti di Analytics.

## Cosa devo fare con segmenti duplicati con lo stesso nome ma con definizioni diverse? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Ora che i segmenti funzionano in più suite di rapporti, potresti avere più segmenti con lo stesso nome. È consigliabile

* Rinominare segmenti con lo stesso nome, ma definizioni diverse, oppure
* Elimina segmenti non più necessari.

## In che modo Adobe consiglia di pulire i segmenti? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Assegna tag a tutti i segmenti con tag legacy.
* Rivedete i segmenti disponibili.
* Aggiungeteli alla libreria dei segmenti, se applicabile.
* Approva segmenti canonici.

## Perché non posso eliminare questo segmento? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Se il segmento è stato pubblicato in Experience Cloud, non puoi eliminarlo o modificarlo. Tuttavia, potete copiarlo e modificare la versione copiata.

## Ulteriori informazioni su cosa accade ai segmenti esistenti {#section_83ACAB256F394DCD8B424D8920BDD853}

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
   <td colname="col2">Questi segmenti di Analisi ad hoc vengono visualizzati come segmenti regolari in Adobe Analytics. <p>Non devono essere confusi con la funzione Preferiti in Segment Manager (Gestore segmenti), che consente di contrassegnare i segmenti come preferiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti preconfigurati in Analisi ad hoc: 
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
   <td colname="col1">Segmenti Experience Cloud (Suite): 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Non acquirenti </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Acquirenti </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Prima visita </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visite dai siti social </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visite di oltre 10 minuti* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visite con 5+ visite precedenti* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visite da Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> La maggior parte di questi segmenti (tranne quelli contrassegnati con un asterisco *) verrà migrata come modelli di segmento nel generatore di segmenti. Sono stati inoltre aggiunti diversi nuovi modelli di segmento. </p> <p>I rapporti esistenti con questi segmenti continueranno a funzionare correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>


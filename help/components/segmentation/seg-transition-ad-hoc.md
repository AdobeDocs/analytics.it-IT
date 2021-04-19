---
description: Se utilizzi il Generatore di segmenti in Ad Hoc Analysis, le domande frequenti riportate di seguito spiegano cosa accade ai segmenti e alle cartelle esistenti e quali azioni devi intraprendere.
keywords: segmentazione;segmenti
title: Guida alla transizione per Ad Hoc Analysis
feature: Segmentazione
uuid: d409d71a-f8d9-42a2-add2-37d426cd40d1
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 99%

---


# Guida alla transizione per Ad Hoc Analysis

Se utilizzi il Generatore di segmenti in Ad Hoc Analysis, le domande frequenti riportate di seguito spiegano cosa accade ai segmenti e alle cartelle esistenti e quali azioni devi intraprendere.

## Funzioni {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* I segmenti sono universali per tutte le suite di rapporti. mentre prima erano specifici per una suite di rapporti.
* Ad Hoc Analysis include aggiornamenti al Generatore di segmenti e un aggiornamento completo al Gestore segmenti.
* Ora puoi assegnare tag ai segmenti per organizzarli ed effettuare ricerche in un secondo momento, anziché utilizzare le cartelle. Prima in [!DNL Ad Hoc Analysis] si utilizzavano le cartelle per organizzare i segmenti.

## Cos’è successo ai segmenti esistenti? {#section_76CF47142D1A4FB6A0718AD9073049FE}

I segmenti esistenti continueranno a funzionare come prima. Tutti i rapporti a cui sono applicati questi segmenti continueranno a funzionare correttamente.

La maggior parte dei segmenti predefiniti e dei segmenti delle suite precedenti migreranno e diventeranno modelli nel Generatore di segmenti. I modelli di segmenti sono utilizzati per creare rapidamente segmenti personalizzati con audience comuni. I modelli di segmenti non possono essere applicati direttamente a un rapporto, ma possono essere salvati con facilità in un segmento personalizzato.

I modelli di segmenti sono contrassegnati da un’icona specifica nel Generatore di segmenti.

## Cos’è successo alle cartelle di segmenti esistenti? {#section_FB04DCF775694E69B761DCA53F301C30}

Invece delle cartelle di analisi ad hoc, il Generatore di segmenti utilizza i tag. I nomi delle cartelle vengono automaticamente convertiti in tag, che vengono applicati ai rispettivi segmenti.

## Cos’è successo ai rapporti programmati con segmenti applicati? {#section_81D1B215533C46E99E17BAE7A3376FDF}

I rapporti programmati continuano a essere eseguiti correttamente con i segmenti definiti.

Quando elimini un segmento, i rapporti e le dashboard programmati a cui è applicato il segmento continuano a funzionare normalmente, ovvero il segmento o la dashboard continua a utilizzare il segmento eliminato.

## Cos’è un contenitore Hit? È diverso da un contenitore Visualizzazione pagina? {#section_65BBE60A836C4001938830DDA15DC256}

Il contenitore Visualizzazione pagina è stato rinominato contenitore Hit per indicare che il contenitore segmenta tutti i tipi di dati e non solo le visualizzazioni di pagina. Ad esempio, le chiamate di tracciamento dei collegamenti e le chiamate trackAction dagli SDK per dispositivi mobili sono tutte incluse o escluse dal contenitore Hit.

Nota che il funzionamento del contenitore non è cambiato, il contenitore è stato semplicemente rinominato.

## Quali diritti e privilegi servono per utilizzare, creare e gestire i segmenti? {#section_648DFA3A882146C485A84ED014EEC707}

Tutti gli utenti possono creare e modificare segmenti personali. Questi segmenti possono essere condivisi direttamente con qualsiasi altro utente Analytics. Gli utenti di Ad Hoc Analysis possono vedere i segmenti creati e quelli condivisi direttamente con l’utente.

Nella console web Segmentazione unificata, gli amministratori possono modificare qualsiasi segmento e condividere i segmenti con i gruppi e con tutti gli utenti dell’organizzazione.

## Posso visualizzare tutti i segmenti nella mia azienda? {#section_AC2D328C7410419E80C7C17971CD95B3}

Puoi visualizzare tutti i segmenti di Ad Hoc Analysis che possiedi e quelli condivisi con te.

## Posso gestire tutti i segmenti di Analytics nel Gestore segmenti? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

Ad Hoc Analysis mostra solo i segmenti generati da te o quelli condivisi con te. Solo per analisi ad hoc puoi utilizzare il Gestore segmenti (Organizza segmenti) per gestire segmenti di analisi ad hoc. Utilizza il Gestore segmenti in Segmentazione unificata per gestire tutti i segmenti di Analytics.

## Cosa conviene fare con i segmenti duplicati che hanno lo stesso nome ma definizioni diverse? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Ora che i segmenti funzionano in più suite di rapporti, potresti avere più segmenti con lo stesso nome. Consigliamo di svolgere una delle seguenti azioni:

* Rinominare i segmenti che hanno lo stesso nome ma definizioni diverse, oppure
* Eliminare i segmenti non più necessari.

## Cosa consiglia Adobe per quanto riguarda la pulizia dei segmenti? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Assegna a tutti i segmenti un tag legacy.
* Esamina i tuoi segmenti.
* Aggiungili alla libreria dei segmenti, se applicabile.
* Approva i segmenti canonici.

## Perché non posso eliminare questo segmento? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

Se il segmento è stato pubblicato in Experience Cloud, non è possibile eliminarlo o modificarlo. Tuttavia, puoi copiarlo e modificare la versione copiata.

## Ulteriori informazioni su ciò che accade ai segmenti esistenti {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Categoria di segmenti </th> 
   <th colname="col2" class="entry"> Cosa succede a questi segmenti? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Segmenti preferiti in Ad Hoc Analysis </td> 
   <td colname="col2">Questi segmenti di Ad Hoc Analysis vengono visualizzati come segmenti regolari in Adobe Analytics. <p>Non vanno confusi con la funzione Preferiti nel Gestore segmenti, che consente di contrassegnare i segmenti come preferiti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti preconfigurati in Ad Hoc Analysis: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Visite a pagina singola </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visite da dispositivi mobili </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visite da ricerca naturale </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visite da ricerca a pagamento </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visite con il cookie ID visitatore </li> 
    </ul> </td> 
   <td colname="col2"> <p>Verrà eseguita la migrazione di questi segmenti e diventeranno modelli di segmenti nel Generatore di segmenti. </p> <p>I rapporti esistenti a cui sono applicati questi segmenti continueranno a funzionare correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Segmenti di Experience Cloud (Suite): 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Non acquirenti </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Acquirenti </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">Prime visite </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visite dai siti social </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visite di oltre 10 minuti* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visite con oltre 5 visite precedenti* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visite da Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> La maggior parte di questi segmenti (tranne quelli contrassegnati con un asterisco *) verrà migrata e i segmenti diventeranno modelli nel Generatore di segmenti. Sono stati inoltre aggiunti diversi nuovi modelli di segmenti. </p> <p>I rapporti esistenti a cui sono applicati questi segmenti continueranno a funzionare correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>


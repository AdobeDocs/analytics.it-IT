---
description: Suggerimenti e best practice per i nuovi utenti delle suite di rapporti virtuali.
keywords: Suite di rapporti virtuali
title: Domande frequenti su VRS
feature: Nozioni di base su Reports & Analytics e nozioni di base su Analytics
uuid: 91225743-765a-4145-9ce5-4268e80ea7e8
exl-id: ab961bec-5719-4b90-bc10-c929b63dc923
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 1%

---

# Domande frequenti su VRS

Suggerimenti e best practice per i nuovi utenti delle suite di rapporti virtuali.

<table id="table_4D9DE70984674B65AD7D40E3D1479CD2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Devo consolidare l’implementazione da più suite di rapporti in un’unica suite di rapporti "globale" e quindi utilizzare suite di rapporti virtuali per esporre diversi segmenti di dati ai miei utenti?</b> </td> 
   <td colname="col2"> <p>Forse. Di seguito sono riportate alcune circostanze in cui è necessario <b>continuare con suite di rapporti individuali</b>: </p> 
    <ul> 
     <li>Se disponi di variabili/dimensioni con un numero elevato di valori univoci, il consolidamento in una singola suite di rapporti potrebbe determinare il superamento dei limiti di valore univoci mensili in questa suite globale, con conseguente troncamento ("traffico ridotto" come voce di riga nei rapporti). </li> 
     <li>Se hai bisogno di rapporti in tempo reale o "Dati correnti" per singoli segmenti (ad esempio marchi, unità operative, ecc.) dei tuoi dati. </li> 
     <li>Se le varie suite di rapporti hanno requisiti univoci per il tracciamento (ad esempio, se utilizzano variabili ed eventi di Adobe Analytics in modo molto diverso), il consolidamento in una suite di rapporti globale non ti concederà variabili o eventi aggiuntivi per il tracciamento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quali impostazioni nelle suite di rapporti virtuali vengono ereditate dalla suite di rapporti principale?  </b> </td> 
   <td colname="col2"> <p>Una suite di rapporti virtuale (VRS) eredita la maggior parte dei livelli di servizio della suite di rapporti principale, ad esempio le impostazioni di eVar, le regole di elaborazione, le classificazioni e così via. </p> <p>Le seguenti impostazioni sono ereditate da <b>NOT</b> : </p> 
    <ul> 
     <li>ID suite di rapporti </li> 
     <li>Nome della suite di rapporti </li> 
     <li>Gruppi di autorizzazioni (le suite di rapporti virtuali possono essere assegnate ai rispettivi gruppi di autorizzazioni) </li> 
    </ul> <p>Nota:  Non sono incluse la maggior parte delle entità create dall’utente come segnalibri, dashboard, rapporti pianificati, ecc.; questi elementi non vengono ereditati dalla pagina padre e possono essere creati e utilizzati in modo specifico rispetto alla VRS (più dettaglio nella domanda successiva). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quali sono le differenze tra le operazioni con una suite di rapporti virtuale e quelle con una suite di rapporti di base nell’interfaccia utente di Analytics?</b> </td> 
   <td colname="col2"> <p>Una volta creata, una suite di rapporti virtuale viene trattata come una suite di rapporti di base in tutta l’interfaccia utente ed è generalmente supportata per la maggior parte delle funzioni estese. Ad esempio: </p> 
    <ul> 
     <li>Le suite di rapporti virtuali vengono visualizzate nel selettore Suite di rapporti e possono essere selezionate singolarmente come qualsiasi altra suite di rapporti di base. </li> 
     <li>Report DL, segnalibri, dashboard, destinazioni, avvisi, segmenti, metriche calcolate, ecc. possono essere creati con una suite di rapporti virtuale e comportarsi in modo indipendente dall'elemento padre. </li> 
     <li>Le suite di rapporti virtuali possono essere aggiunte individualmente ai gruppi di autorizzazioni, come qualsiasi altra suite di rapporti. </li> 
     <li>I segmenti possono ancora essere applicati quando si eseguono rapporti nel contesto di una VRS; al momento del recupero dei dati del rapporto, verranno automaticamente sovrapposti ai segmenti della suite di rapporti virtuali. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Come vengono trattate le suite di rapporti virtuali nell’API Admin Console e Admin? Posso salvare le funzionalità rispetto a loro come suite di rapporti di base? </b> </td> 
   <td colname="col2"> <p>No, le suite di rapporti virtuali <b>non sono supportate per la maggior parte delle funzioni amministratore</b>. Come accennato in precedenza, una VRS eredita la maggior parte dei livelli di servizio e delle funzionalità dal padre (ad esempio, impostazioni di eVar, Regole di elaborazione, Classificazioni, ecc.), quindi per apportare modifiche a queste impostazioni ereditate in una VRS, devi modificare la suite di rapporti principale. </p> <p>Di conseguenza, le suite di rapporti virtuali vengono visualizzate nell'interfaccia utente <b>solo qui</b>: </p> 
    <ul> 
     <li>Gestione suite di rapporti virtuale, in cui puoi creare e modificare le VRS. <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics </span> &gt; <span class="uicontrol"> Componenti </span> &gt; <span class="uicontrol"> Suite di rapporti virtuali </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> Interfaccia User Management, in cui puoi modificare i gruppi di autorizzazioni personalizzati. Questo consente di aggiungere gli account VRS a un gruppo di autorizzazioni e può essere utilizzato per creare un gruppo che ha accesso solo alle suite di rapporti virtuali (se l’amministratore desidera negare l’accesso al gruppo principale e consentire solo agli utenti l’accesso a segmenti specifici). <p>( <span class="ignoretag"> <span class="uicontrol"> Amministratore </span> &gt; <span class="uicontrol"> Gestione utente </span> </span>) </p> </li> 
    </ul> <p>Nota:  Quando si utilizza l'API dei servizi Web e si tenta di salvare le impostazioni delle funzioni rispetto a una VRS, viene generata un'eccezione. Le funzionalità possono essere impostate solo su una suite di rapporti di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Ho controllato "inizia una nuova visita al lancio". Perché visualizzo visite ancora più elevate dei lanci?</b> </td> 
   <td colname="col2"> <p> Quando è selezionato "Avvia nuova visita al lancio", il timeout viene comunque applicato. Quindi, se un utente utilizza l’app per dieci minuti con un minuto di pausa tra ciascuna azione, una nuova visita inizia all’avvio, vengono create altre nove visite quando la visita si interrompe. Per mantenere gli avvii e le visite il più vicino possibile quando utilizzi l’opzione "avvia una nuova visita al momento dell’avvio", utilizza un timeout più lungo del timeout di sessione impostato nell’SDK . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Ho impostato "start new visit on launch" e impostato un timeout più lungo del mio SDK. Perché i miei lanci sono ancora molto inferiori alle visite?</b> </td> 
   <td colname="col2"> <p> Se il timeout è superiore al valore impostato nell'SDK, è molto probabile che l'app invii hit in background e questi hit si registrano come nuove visite. Per verificarlo, utilizza la dimensione del tipo di hit nella suite di rapporti principale per verificare se sono presenti hit di background. </p> <p> <p>Nota: Gli hit in background e in primo piano sono differenziati solo nella versione 4.13.6 e successive dell’SDK. Se utilizzi una versione inferiore, tutti gli hit vengono visualizzati in primo piano. Se usi la versione corretta dell’SDK, abilita l’impostazione "Impedisci agli hit di background di avviare una nuova visita". </p> </p> <p> <p>Nota: Se hai disabilitato l’elaborazione legacy per gli hit in background in Admin Console, questi non verranno visualizzati nella suite di rapporti principale ma verranno visualizzati nella suite di rapporti virtuale. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Quale versione dell'SDK devo avere per tenere traccia degli hit di background?</b> </td> 
   <td colname="col2"> <p> Devi avere la versione 4.13.6 o successiva dell'SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>

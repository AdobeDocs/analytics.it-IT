---
description: Suggerimenti e best practice per i nuovi utenti delle suite di rapporti virtuali.
keywords: Virtual Report Suite
solution: Analytics
title: Domande frequenti su VRS
topic: Reports and analytics
uuid: 91225743-765a-4145-9ce5-4268e80ea7e8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
   <td colname="col1"> <b>Devo consolidare la mia implementazione da suite di rapporti multiple in una singola suite di rapporti "globale" e quindi utilizzare suite di rapporti virtuali per esporre diversi segmenti di dati ai miei utenti?</b> </td> 
   <td colname="col2"> <p>Forse. Di seguito sono riportate alcune circostanze in cui è <b>consigliabile continuare con le singole suite</b>di rapporti: </p> 
    <ul id="ul_493454A655DE48E0AF94130014203268"> 
     <li id="li_B37C2651D2804FD1B965286C85A765D5">Se disponete di variabili/dimensioni con un numero elevato di valori univoci, il consolidamento in una singola suite di rapporti potrebbe causare il superamento dei limiti di valori univoci mensili in questa suite globale, causando il troncamento ("Basso traffico" come elemento di riga nei report). </li> 
     <li id="li_87ABC62EC73D4355A9F768AD1949D3C6">Se hai bisogno di un reporting in tempo reale o "Dati correnti" per singoli segmenti (ad esempio marchi, unità aziendali ecc.) dei tuoi dati. </li> 
     <li id="li_7252787B2D4C4756836DAEA0EEC0BF8B">Se le varie suite di rapporti dispongono di requisiti univoci per il tracciamento (ovvero se utilizzano variabili ed eventi di Adobe Analytics in modo molto diverso), tieni presente che il consolidamento in una suite di rapporti globale non ti concederà variabili o eventi aggiuntivi per il tracciamento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quali impostazioni nelle suite di rapporti virtuali vengono ereditate dalla suite di rapporti principale? </b> </td> 
   <td colname="col2"> <p>Una suite di rapporti virtuale (VRS) eredita la maggior parte dei livelli di servizio della suite di rapporti principale, come le impostazioni eVar, le regole di elaborazione, le classificazioni, ecc. </p> <p>Le seguenti impostazioni sono <b>NON</b> ereditate: </p> 
    <ul id="ul_43B0637F095C480B82126C96BFF627FA"> 
     <li id="li_F3DF9D6B0B1A4A46B9D8B1CF2DA09BE3">ID suite di rapporti </li> 
     <li id="li_A735D7BA4DA14DCB8F40D7898A324F1F">Nome suite di rapporti </li> 
     <li id="li_BF66DD426EE7464CBF7F2EB56B0C3075">Gruppi di autorizzazioni (le suite di rapporti virtuali possono essere assegnate ai propri gruppi di autorizzazioni) </li> 
    </ul> <p>Nota:  Non sono incluse la maggior parte delle entità create dall'utente come Segnalibri, Dashboard, Rapporti pianificati, ecc.; questi elementi non vengono ereditati dall'elemento padre e possono essere creati e utilizzati in base alla VRS in modo specifico (maggiori dettagli nella domanda successiva). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>In che modo l'utilizzo di una suite di rapporti virtuale è diverso dall'utilizzo di una suite di rapporti di base nell'interfaccia utente di Analytics?</b> </td> 
   <td colname="col2"> <p>Una volta creata, una suite di rapporti virtuale viene trattata come una suite di rapporti di base nell'interfaccia utente ed è generalmente supportata per la maggior parte delle funzioni estese. Ad esempio: </p> 
    <ul id="ul_D20435FD9B3546DFB611FD09035BACBB"> 
     <li id="li_4A331EB50B7F43E697F67B4A657B4450">Le suite di rapporti virtuali vengono visualizzate nel selettore Suite di rapporti e possono essere selezionate singolarmente come qualsiasi altra suite di rapporti di base. </li> 
     <li id="li_6E8C1E45C68943A1BA7C260FA62C40E0">Rapporti DL, segnalibri, dashboard, destinazioni, avvisi, segmenti, metriche calcolate, ecc. possono essere tutti creati rispetto a una suite di rapporti virtuale e comportarsi in modo indipendente dall'elemento padre. </li> 
     <li id="li_5701D7F60BF8452CBEC8DFA2072CE8C2">Le suite di rapporti virtuali possono essere aggiunte singolarmente ai gruppi di autorizzazioni come qualsiasi altra suite di rapporti. </li> 
     <li id="li_764475FD352C434D92E876E30699F280">I segmenti possono essere ancora applicati quando si eseguono rapporti nel contesto di una VRS; verranno automaticamente sovrapposti ai segmenti della suite di rapporti virtuali al momento del recupero dei dati del rapporto. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Come vengono trattate le suite di rapporti virtuali nell'Admin Console e nell'API di amministrazione? Posso salvare le funzionalità rispetto a loro come suite di rapporti di base? </b> </td> 
   <td colname="col2"> <p>No, le suite di rapporti virtuali <b>non sono supportate per la maggior parte delle funzioni</b>Amministratore. Come già detto, una VRS eredita la maggior parte dei livelli di servizio e delle funzionalità dall'elemento padre (ad esempio, impostazioni eVar, Regole di elaborazione, Classificazioni, ecc.), pertanto per apportare modifiche a queste impostazioni ereditate su una VRS, devi modificare la suite di rapporti principale. </p> <p>Di conseguenza, le suite di rapporti virtuali vengono visualizzate nell’interfaccia utente <b>solo qui</b>: </p> 
    <ul id="ul_64CF126ACF39453A95BD9FC9D2CFA59B"> 
     <li id="li_08EBF87ADF13400C9DD3FFC2695F5CF9">Virtual Report Suite Manager (Gestione suite di rapporti virtuali), dove si creano e si modificano le VRS. <p>( <span class="ignoretag"><span class="uicontrol"> Analytics </span> &gt; <span class="uicontrol"> Componenti </span> &gt; <span class="uicontrol"> Suite di rapporti virtuali </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> Interfaccia di gestione utente, in cui potete modificare i gruppi di autorizzazioni personalizzati. Questo consente agli account VRS di essere aggiunti a un gruppo di autorizzazioni e possono essere utilizzati per creare un gruppo che ha accesso solo alle suite di rapporti virtuali (se l'amministratore desidera negare l'accesso al gruppo principale e consentire solo agli utenti l'accesso a segmenti specifici). <p>( <span class="ignoretag"> <span class="uicontrol"> Admin </span>  &gt; <span class="uicontrol"> User Management </span> </span>) </p> </li> 
    </ul> <p>Nota:  Quando si utilizza l'API dei servizi Web e si tenta di salvare le impostazioni delle funzioni su una VRS, viene generata un'eccezione. Le funzioni possono essere impostate solo su una suite di rapporti di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Le suite di rapporti virtuali sono supportate nell'interfaccia utente di SiteCatalyst 14?</b> </td> 
   <td colname="col2"> <p>No, non esponiamo le suite di rapporti virtuali in SiteCatalyst 14. Non vengono visualizzati per la selezione nel selettore delle suite di rapporti e non possono essere selezionati. Tuttavia, durante la modifica di un gruppo, esponiamo le suite di rapporti virtuali nell’interfaccia utente di Admin Console di SiteCatalyst 14. In questo caso particolare, le suite di rapporti virtuali devono essere rappresentate in modo che non vengano accidentalmente rimosse da un gruppo già esistente che potrebbe già avere accesso a una o più suite di rapporti virtuali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Ho selezionato "Inizia nuova visita al lancio". Perché vedo le visite ancora più in alto rispetto ai lanci?</b> </td> 
   <td colname="col2"> <p> Quando l'opzione <span class="uicontrol"> Avvia nuova visita all'avvio </span> è selezionata, il timeout continua a essere applicato. Pertanto, se un utente utilizza un'app per dieci minuti con un'interruzione di un minuto tra ciascuna azione, una nuova visita inizia all'avvio, quindi vengono create altre nove visite al termine della visita. Per mantenere gli avvii e le visite il più vicino possibile quando si <span class="uicontrol"> utilizza l’opzione Avvia nuova visita all’avvio </span> , devi utilizzare un timeout più lungo del timeout sessione impostato nell’SDK. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Ho impostato "Avvia nuova visita all’avvio" e un timeout più lungo del mio SDK. Perché i miei lanci sono ancora molto più bassi delle visite?</b> </td> 
   <td colname="col2"> <p> Se il timeout è superiore al valore impostato nell’SDK, è molto probabile che l’app invii hit mentre è in background e che questi hit si registrino come nuove visite. Per verificarlo, utilizza la dimensione del tipo di hit nella suite di rapporti principale per verificare se sono presenti hit di sfondo. </p> <p> <p>Nota:  Gli hit in background e in primo piano sono differenziati solo nella versione 4.13.6 e successive dell’SDK. Se usate una versione inferiore, tutti gli hit vengono visualizzati in primo piano. Se utilizzi la versione corretta dell’SDK, devi attivare l’opzione <span class="uicontrol"> Impedisci agli hit in background di avviare una nuova impostazione di visita </span> . </p> </p> <p> <p>Nota:  Se hai disabilitato l’elaborazione legacy per gli hit in background nella console di amministrazione, questi non verranno visualizzati nella suite di rapporti principale ma verranno visualizzati nella suite di rapporti virtuale. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Quale versione dell’SDK devo usare per tenere traccia degli hit in background?</b> </td> 
   <td colname="col2"> <p> È necessario disporre della versione 4.13.6 o successiva dell’SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>


---
description: Suggerimenti e best practice per i nuovi utenti delle suite di rapporti virtuali.
keywords: Suite di rapporti virtuali
seo-description: Suggerimenti e best practice per i nuovi utenti delle suite di rapporti virtuali.
seo-title: Domande frequenti su VRS
solution: Analytics
title: Domande frequenti su VRS
topic: Reports & Analytics
uuid: 91225743-765 a -4145-9 ce 5-4268 e 80 ea 7 e 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
   <td colname="col1"> <b>Posso consolidare la mia implementazione da suite di rapporti multiple in una singola suite di rapporti "globale", e quindi utilizzare suite di rapporti virtuali per esporre diversi segmenti ai miei utenti?</b> </td> 
   <td colname="col2"> <p>Ad esempio. Here are some circumstances under which you should <b>consider continuing with individual report suites</b>: </p> 
    <ul id="ul_493454A655DE48E0AF94130014203268"> 
     <li id="li_B37C2651D2804FD1B965286C85A765D5">Se hai variabili/dimensioni con un numero elevato di valori univoci, il consolidamento in una singola suite di rapporti potrebbe causare la superamento dei limiti mensili univoci del valore in questa suite globale, con conseguente troncamento ("Traffico basso" come elemento di riga nei report). </li> 
     <li id="li_87ABC62EC73D4355A9F768AD1949D3C6">Se hai bisogno di rapporti in tempo reale o di rapporti correnti per singoli segmenti (ad es. marchi, unità aziendali, ecc.) dei dati. </li> 
     <li id="li_7252787B2D4C4756836DAEA0EEC0BF8B">Se le varie suite di rapporti hanno requisiti univoci per il tracciamento (ovvero se usano variabili ed eventi di Adobe Analytics molto diverso), tieni presente che il consolidamento in una suite di rapporti globale non ti darà ulteriori variabili o eventi per il tracciamento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Quali impostazioni delle suite di rapporti virtuali vengono ereditate dalla suite di rapporti principale? </b> </td> 
   <td colname="col2"> <p>Una suite di rapporti virtuale (VRS) eredita la maggior parte dei livelli di servizio della suite di rapporti principale, come le impostazioni evar, le regole di elaborazione, le classificazioni ecc. </p> <p>The following settings are <b>NOT</b> inherited: </p> 
    <ul id="ul_43B0637F095C480B82126C96BFF627FA"> 
     <li id="li_F3DF9D6B0B1A4A46B9D8B1CF2DA09BE3">ID suite di rapporti </li> 
     <li id="li_A735D7BA4DA14DCB8F40D7898A324F1F">Nome suite di rapporti </li> 
     <li id="li_BF66DD426EE7464CBF7F2EB56B0C3075">Gruppi di autorizzazioni (le suite di rapporti virtuali possono essere assegnate a gruppi di autorizzazioni propri) </li> 
    </ul> <p>Nota: Ciò non include la maggior parte delle entità create dall'utente come Segnalibri, Dashboard, Rapporti pianificati ecc.; questi elementi non vengono ereditati dall'elemento padre e possono essere creati e utilizzati in modo specifico rispetto alla VRS (più dettagli nella domanda successiva). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>How does working with a virtual report suite different from working with a basic report suite nell'interfaccia utente di Analytics?</b> </td> 
   <td colname="col2"> <p>Una volta creata, una suite di rapporti virtuale viene gestita come una suite di rapporti di base nell'interfaccia utente ed è generalmente supportata per le funzioni più estese. Ad esempio: </p> 
    <ul id="ul_D20435FD9B3546DFB611FD09035BACBB"> 
     <li id="li_4A331EB50B7F43E697F67B4A657B4450">Le suite di rapporti virtuali vengono visualizzate nel selettore Suite di rapporti e possono essere selezionate singolarmente come qualsiasi altra suite di rapporti base. </li> 
     <li id="li_6E8C1E45C68943A1BA7C260FA62C40E0">Rapporti DL, Segnalibri, Dashboard, Destinazioni, Avvisi, Segmenti, Metriche calcolate, ecc. possono essere create in base a una suite di rapporti virtuale e si comportano in modo indipendente dall'elemento principale. </li> 
     <li id="li_5701D7F60BF8452CBEC8DFA2072CE8C2">Le suite di rapporti virtuali possono essere aggiunte singolarmente a Gruppi di autorizzazioni come qualsiasi altra suite di rapporti. </li> 
     <li id="li_764475FD352C434D92E876E30699F280">I segmenti possono essere applicati durante l'esecuzione di rapporti nel contesto di una VRS; verranno automaticamente impilati con i segmenti della suite di rapporti virtuali quando vengono recuperati i dati del rapporto. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Come sono trattati le suite di rapporti virtuali in Admin Console e nell'API Admin? Can I save features against them like base report suites? </b> </td> 
   <td colname="col2"> <p>No, virtual report suites are <b>not supported for most Admin features</b>. Come indicato sopra, una VRS eredita la maggior parte dei livelli e delle funzionalità del servizio dall'elemento principale (ad esempio, le impostazioni evar, Regole di elaborazione, Classificazioni ecc.), così per apportare una modifica a tali impostazioni ereditate su una VRS, devi modificare la suite di rapporti principale. </p> <p>As a result, virtual report suites are shown in the UI <b>only here</b>: </p> 
    <ul id="ul_64CF126ACF39453A95BD9FC9D2CFA59B"> 
     <li id="li_08EBF87ADF13400C9DD3FFC2695F5CF9">La suite di rapporti virtuali, in cui puoi creare e modificare le VRS. <p>( <span class="ignoretag"> <span class="uicontrol"> Analytics </span>  &gt; <span class="uicontrol"> Components </span>  &gt; <span class="uicontrol"> Virtual Report Suites </span> </span>) </p> </li> 
     <li id="li_E2B3F61A3013402697DCF6E0D32A62DC"> Interfaccia di Gestione utenti, in cui modificate gruppi di autorizzazioni personalizzati. Questo consente l'aggiunta di account VRS a un gruppo di autorizzazioni e può essere utilizzato per creare un gruppo che dispone unicamente dell'accesso alle suite di rapporti virtuali (se l'amministratore desidera negare l'accesso al padre e consentire l'accesso solo agli utenti). <p><span class="ignoretag"><span class="uicontrol"> (Amministratore </span> &gt; <span class="uicontrol"> Gestione </span></span>utente) </p> </li> 
    </ul> <p>Nota: Quando usi l'API Servizi Web e tenti di salvare le impostazioni delle funzionalità rispetto a una VRS, viene generata un'eccezione. Le funzionalità possono essere impostate solo rispetto a una suite di rapporti di base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Le suite di rapporti virtuali sono supportate nell'interfaccia utente di sitecatalyst 14?</b> </td> 
   <td colname="col2"> <p>No, non vengono esposti suite di rapporti virtuali in sitecatalyst 14. Non verranno visualizzati per la selezione nel Selettore suite di rapporti e non possono essere selezionati. Tuttavia, si possono esporre suite di rapporti virtuali nell'interfaccia utente di Sitecatalyst 14 Admin Console quando si modifica un gruppo. In questo caso, le suite di rapporti virtuali virtuali devono essere rappresentate in modo che non vengano rimosse accidentalmente da un gruppo già esistente che può già avere accesso a una o più suite di rapporti virtuali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> I check "start new visit at launch." Why do I see visits still much higher than launches?</b> </td> 
   <td colname="col2"> <p> When the <span class="uicontrol"> start new visit on launch </span> option is checked, the timeout still applies. Pertanto, se un utente utilizza l'app per dieci minuti con un'interruzione di minuto tra ciascuna azione, una nuova visita inizia all'avvio, quindi nove visite aggiuntive vengono create quando la visita scade. To keep launches and visits as close as possible when <span class="uicontrol"> using the start new visit on launch </span> option, you should use a timeout that is longer than the session timeout set in the SDK . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> I set "start new visit at launch" and sets an longer timeout than my SDK. Why are my launches still much lower than visits?</b> </td> 
   <td colname="col2"> <p> Se il timeout è superiore al valore impostato nell'SDK, è molto probabile che l'app stia inviando degli hit mentre in background, e questi hit vengono registrati come nuove visite. Verifica questa opzione utilizzando il tipo di hit nella suite di rapporti principale per verificare se sono presenti hit di sfondo. </p> <p> <p>Nota: Gli hit di sfondo e in primo piano sono differenziati solo nella versione 4.13.6 e successive dell'SDK. Se utilizzi una versione inferiore, tutti gli hit vengono visualizzati come primo piano. If you are on the correct version of the SDK, you should enabled the <span class="uicontrol"> Prevent background hits from starting a new visit </span> setting. </p> </p> <p> <p>Nota: Se hai disattivato l'elaborazione legacy per gli hit in background in Admin Console, questi non vengono visualizzati nella suite di rapporti principale ma saranno visualizzati nella suite di rapporti virtuale. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Quale versione dell'SDK devo tenere traccia degli hit di sfondo?</b> </td> 
   <td colname="col2"> <p> Devi essere nella versione 4.13.6 o successiva dell'SDK. </p> </td> 
  </tr> 
 </tbody> 
</table>


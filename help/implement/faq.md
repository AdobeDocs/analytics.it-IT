---
description: Domande frequenti sull'implementazione e collegamenti a ulteriori informazioni.
keywords: Implementazione di Analytics; faq; domande frequenti; scadenza evar; visibilità evento personalizzata; timestamp; periodo di tolleranza per ID visitatore; ID visitatore; ID visitatore Experience Cloud; ID visitatore di analisi; dtm; heartbeat; cookie; server di tracciamento; prestazioni; javascript; raccolta dati; s_ code version; s_ code debug; tenere traccia dei tipi di collegamento; tracciare video; app per dispositivi mobili; cookie first party; ssl, certificato; scadenza della certificazione; scadenza del certificato; plug-in; api di inserimento dati; 500 errore; 500; Gestisci utente; manage group; utenti; gruppi
seo-description: Domande frequenti sull'implementazione e collegamenti a ulteriori informazioni.
seo-title: Domande frequenti sull'implementazione di Analytics
solution: Analytics
title: Domande frequenti sull'implementazione di Analytics
topic: Sviluppatore e implementazione
uuid: 983 d 759 a-c 4 f 2-4021-84 c 8-0486 dbb 951 b 8
translation-type: tm+mt
source-git-commit: 0143edbcbab3450f6932367f51e9e4c79bc1ae63

---


# Domande frequenti sull'implementazione di Analytics

Domande frequenti sull'implementazione e collegamenti a ulteriori informazioni.

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>domande</b> </td> 
   <td> <b>Risposta</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Come gestisco gli utenti e i gruppi di Analytics? </p> </td> 
   <td colname="col3"> <p>Per informazioni sulla gestione di utenti e gruppi, consulta Gestione <a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html" format="html" scope="external"> di utenti e prodotti </a> nella guida di Adobe Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Evar Expiration - Why are the evar get attributed tò None'nei report? </p> </td> 
   <td colname="col3"> <p> <span class="uicontrol"> Scadenza dopo </span> specifica un periodo di tempo, o un evento, dopo la scadenza del valore evar (non ricevono più crediti per eventi di successo). Se un evento di successo si verifica dopo la scadenza evar, il valore None non riceve credito per l'evento (nessuna evar è attiva). Se selezionate un evento come valore di scadenza, la variabile scade solo se si verifica l'evento. Se l'evento non si verifica, la variabile non scade. <a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Custom Event Visibility (Visibilità evento personalizzata) - Perché Eventi personalizzati non vengono visualizzati nel menu dei report? </p> </td> 
   <td colname="col3"> <p>Nella colonna Visibilità puoi nascondere le metriche standard (integrate), gli eventi personalizzati e gli eventi incorporati in Menu, Metric Selectors (Selettori metriche calcolate), Calculated Metrics Builder (Generatore metriche calcolate) e Segment Builder (Generatore segmenti). Questa impostazione non influisce sulla raccolta dati per la metrica o l'evento; ne incide solo sulla visibilità nell'interfaccia utente. <a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Marca temporale - Cosa devo tenere in considerazione prima di cambiare le impostazioni di marca temporale? </p> </td> 
   <td colname="col3"> <p>Utilizzando la funzione opzionale Marca temporale, potete combinare dati non con marca temporale con dati con marca temporale senza la conseguente perdita di dati. I dati offline con marca temporale generata da un dispositivo mobile possono essere combinati con dati live e non con marca temporale da una pagina Web, oppure integrati con dati provenienti da qualsiasi piattaforma mediante una chiamata di marca temporale lato client. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID visitatore: come funziona il periodo di tolleranza ID visitatore e come è abilitato? </p> </td> 
   <td colname="col3"> <p>Se disponi di più file JavaScript che inviano dati alla stessa suite di rapporti o se utilizzi altre tecnologie sul tuo sito, ad esempio la misurazione video Flash, ti consigliamo di impostare un periodo di tolleranza. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID visitatore: qual è la differenza tra l'ID visitatore Experience Cloud e l'ID visitatore di Analytics? </p> </td> 
   <td colname="col3"> <p>Il Servizio identità assegna un identificatore univoco e costante a tutti i visitatori del sito. Con questo ID, i visitatori e i relativi dati possono essere condivisi tra le altre soluzioni Experience Cloud. Inoltre, questo ID può sostituire o lavorare con ID specifici della soluzione, ad esempio l'ID visitatore di Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-overview.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID visitatore - Come si imposta l'ID visitatore se i cookie sono bloccati? </p> </td> 
   <td colname="col3"> <p>Se il cookie s_ vi standard non è disponibile, viene creato un cookie di fallback sul dominio del sito Web con un ID univoco generato in modo casuale. Questo cookie, denominato s_ fid, è impostato con scadenza di 2 anni e viene utilizzato quando il metodo di identificazione di fallback procede. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Gestione tag dinamica - Perché la mia regola di Gestione dinamica dei tag non viene attivata? </p> </td> 
   <td colname="col3"> <p>Se la regola basata sugli eventi non viene attivata, è probabile che si verifichi un problema con il selettore o la condizione della regola. Individuate l'elemento sul sito in cui si verifica l'azione desiderata, fate clic con il pulsante destro del mouse e selezionate l'elemento Esamina. Ispezionare lo script evidenziato nella casella che si apre e assicurarsi di avere il targeting dell'elemento corretto. <a href="https://marketing.adobe.com/resources/help/en_US/dtm/c_Troubleshooting.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Come si implementa il Tracciamento video Heartbeat? </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/" format="https" scope="external"> Questa sezione </a> contiene istruzioni su come scaricare gli SDK per heartbeat video e guide per sviluppatori per la piattaforma. Assicurati anche di scaricare la guida per sviluppatori presente nella cartella docs quando scaricate l'SDK in quanto contiene le istruzioni di implementazione specifiche per i video heartbeat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Come si aggiungono i cookie al sottodominio corretto? </p> </td> 
   <td colname="col3"> La <span class="varname"> variabile cookiedomainperiod </span> determina il dominio in cui vengono impostati i cookie di Analytics s_ cc e s_ sq determinando il numero di periodi nel dominio dell'URL della pagina. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in. Consultate [Variabili di configurazione] (/help/implementation/js-implementation/c-variables/configuration-variables. md) </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Server di tracciamento - Come posso compilare correttamente il server di tracciamento? </p> </td> 
   <td colname="col3"> <p>Quando configurate un'implementazione per inviare dati ai server Adobe Analytics, dovete inviarli alla posizione corretta. In questo caso, il conteggio dei visitatori aumenta o la perdita di dati. <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Prestazioni - È possibile che il caricamento di Adobe javascript esterno, a causa di connessione Internet, proxy, firewall o interruzione di servizio presso Adobe, comprometta le prestazioni? </p> </td> 
   <td colname="col3"> <p>No. Il file javascript non è ospitato sui server Adobe, pertanto un'interruzione Adobe non influirà sull'esecuzione javascript. Se viene impiegato Gestione tag dinamica, il file javascript è ospitato da Akamai oppure su una posizione server determinata dai clienti. </p> <p>Consulta <i>Gestione tag dinamica per ridurre le prestazioni del sito Web?</i> nelle domande frequenti sulla gestione tag <a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html" format="https" scope="external"> dinamica </a>. </p> <p>Inoltre, se non avete familiarità con la CDN di Akamai, potete ospitare il file di gestione tag dinamica personalizzato. See <a href="https://marketing.adobe.com/resources/help/en_US/dtm/?f=deployment" format="https" scope="external"> Embed Code and Hosting Options </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Prestazioni - Il caricamento di Adobe javascript esterno causa una riduzione delle prestazioni? </p> </td> 
   <td colname="col3"> <p> Il file javascript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti Web, gli utenti possono media più di un paio di visualizzazioni di pagina per sessione, quindi il trasferimento di javascript utilizzato più volte in questo file può comportare meno dati scaricati. </p> <p> Javascript for [! DNL appmeasurement] Compression: Se siete preoccupati dello spessore della pagina (dimensione) del client javascript di Adobe, Adobe consiglia di considerare la compressione del file tramite GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione javascript per comprimere e decomprimere il file <span class="filepath"></span> javascript di base_ code. js. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Prestazioni - L'invio di dati dal browser ai servizi Adobe riduce le prestazioni? </p> </td> 
   <td colname="col3"> <p> Il file Adobe javascript crea un oggetto immagine all'interno della pagina HTML e il browser quindi richiede l'oggetto immagine dai server Adobe. Se i server Adobe dovevano essere lenti o non rispondere, il thread che gestisce la richiesta viene ritardato finché non si verifica un timeout. Poiché i browser gestiscono immagini con più thread, un'interruzione Adobe ha un impatto minimo sul tempo di caricamento della pagina, toccando un thread mentre gli altri continuano a funzionare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Prestazioni - Un evento javascript di Adobe influisce su comportamenti o funzionalità del sistema? </p> </td> 
   <td colname="col3"> <p>No. Consultate le precedenti risposte alle prestazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Come posso modificare i dati raccolti in base a condizioni personali personali? </td> 
   <td colname="col3"> Utilizza le regole di elaborazione per semplificare la raccolta dati e gestire i contenuti quando viene inviato al reporting. <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Qual è la versione più recente del file s_ code? </td> 
   <td> This section contains a release history for [! DNL appmeasurement] da piattaforme Web e mobili. L'ultima versione di ciascuna libreria può essere scaricata in Reporting e analisi &gt; Strumenti di amministrazione &gt; Gestione codici. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/?f=c_release_notes_javascript" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si esegue il debug del file s_ code? </td> 
   <td> Adobe Debugger (precedentemente digitalpulse Debugger) è uno strumento gratuito fornito da Adobe che consente di visualizzare i dati raccolti dal sito in qualsiasi pagina. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=debugger" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si tiene traccia dei diversi tipi di collegamento? </td> 
   <td> I download dei file e i collegamenti di uscita possono essere tracciati automaticamente in base ai parametri impostati in appmeasurement per il file javascript. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=function_tl" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si tiene traccia del video? </td> 
   <td> È possibile utilizzare javascript per tenere traccia di un'ampia gamma di lettori. Per tenere traccia di javascript, aggiungere codice alla pagina Web che contiene il lettore e tenere traccia del lettore utilizzando i gestori di eventi. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si tiene traccia di un'app mobile? </td> 
   <td> In Adobe Mobile Services è possibile generare collegamenti di acquisizione con codici di tracciamento univoci. Quando un utente scarica ed esegue un'app dall'Apple App Store dopo aver fatto clic sul collegamento generato, l'SDK raccoglie e invia automaticamente i dati di acquisizione ad Adobe Mobile Services. <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=acquisition" format="http" scope="external"> iOS </a><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=acquisition" format="http" scope="external"> Android </a> </td> 
  </tr> 
  <tr> 
   <td> Come si implementa il tracciamento video? </td> 
   <td> Potete tenere traccia dei lettori multimediali creando funzioni allegate ai gestori di eventi video player, che consente di chiamare Media. open, Media. play, Media. stop e Media. close ai momenti opportuni. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/?f=video_js_events" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si imposta il cookie First Party? </td> 
   <td> Analytics utilizza i cookie per fornire informazioni su variabili e componenti che non permangono tra richieste di immagini e sessioni del browser. Questi cookie inoffensivi provengono da un dominio ospitato da Adobe, noto come cookie di terze parti. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_cert" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si ottiene un certificato SSL? </td> 
   <td> Stabilite se il sito usa il protocollo https://. In caso contrario, sarà necessario richiedere un CSR e acquistare un certificato SSL. Nota: Non è necessario un certificato SSL se non si dispone di pagine o contenuti protetti. Questo passaggio può essere ignorato se utilizzate solo https:// protocollo sul sito. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_cert" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Dove trovo informazioni sul avviso di scadenza della certificazione? </td> 
   <td> I certificati SSL scadono ogni anno, il che significa che Adobe richiede una richiesta di certificato aggiornata ogni volta che ciò accade. Lo specialista FPC fornisce un avviso sufficiente nel momento in cui si verifica, tuttavia si consiglia di monitorare la scadenza e fornire ad Adobe il certificato aggiornato. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/?f=fpcookies_renewals" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Cosa sono i plug-in? </td> 
   <td> Appmeasurement per i plug-in javascript sono programmi o funzioni che eseguono diverse funzioni avanzate. Questi plug-in estendono le funzionalità del file javascript per offrire ulteriori funzionalità non disponibili con un'implementazione di base. Adobe offre molti altri plug-nell'ambito delle soluzioni avanzate. Contattate l'Account Manager per acquisire i dati utilizzando javascript, ma non assicuratevi di procedere. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=impl_plugins" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Informazioni sull'API di inserimento dati? </td> 
   <td> Adobe ha creato diversi modi per inviare dati in Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=usecase_sending_data_to_sc" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Cos'è un errore 500? </td> 
   <td> Informazioni sull'errore interno del server che ha provocato lo stato di "Errore query 500". <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=pageType" format="http" scope="external">Vedere variabile pagetype </a> </td> 
  </tr> 
 </tbody> 
</table>

| Domanda | Risposta |
|---|---|
| Come gestisco gli utenti e i gruppi di Analytics? | Per informazioni sulla gestione di utenti e gruppi, consulta [Gestione di utenti e prodotti Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html) nella guida dei servizi di base di Adobe Experience Cloud. |
| Evar Expiration - Why are the evar get attributed tò None'nei report? | `Expire After` specifica un periodo di tempo, o un evento, dopo la scadenza del valore evar (non ricevono più crediti per eventi di successo). Se un evento di successo si verifica dopo la scadenza evar, il valore None non riceve credito per l'evento (nessuna evar è attiva). Se selezionate un evento come valore di scadenza, la variabile scade solo se si verifica l'evento. Se l'evento non si verifica, la variabile non scade. [[Altro...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Custom Event Visibility (Visibilità evento personalizzata) - Perché Eventi personalizzati non vengono visualizzati nel menu dei report? | Nella colonna Visibilità puoi nascondere le metriche standard (integrate), gli eventi personalizzati e gli eventi incorporati in Menu, Metric Selectors (Selettori metriche calcolate), Calculated Metrics Builder (Generatore metriche calcolate) e Segment Builder (Generatore segmenti). Questa impostazione non influisce sulla raccolta dati per la metrica o l'evento; ne incide solo sulla visibilità nell'interfaccia utente. [[Altro...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/metric-visibility.html) |
| Marca temporale - Cosa devo tenere in considerazione prima di cambiare le impostazioni di marca temporale? | Utilizzando la funzione opzionale Marca temporale, potete combinare dati non con marca temporale con dati con marca temporale senza la conseguente perdita di dati. I dati offline con marca temporale generata da un dispositivo mobile possono essere combinati con dati live e non con marca temporale da una pagina Web, oppure integrati con dati provenienti da qualsiasi piattaforma mediante una chiamata di marca temporale lato client. [[Altro...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/timestamps-overview.html) |
| ID visitatore: come funziona il periodo di tolleranza ID visitatore e come è abilitato? | Se disponi di più file JavaScript che inviano dati alla stessa suite di rapporti o se utilizzi altre tecnologie sul tuo sito, ad esempio la misurazione video Flash, ti consigliamo di impostare un periodo di tolleranza.  [Altro...](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/grace-period.html) |
| ID visitatore: qual è la differenza tra l'ID visitatore Experience Cloud e l'ID visitatore di Analytics? | Il Servizio identità assegna un identificatore univoco e costante a tutti i visitatori del sito. Con questo ID, i visitatori e i relativi dati possono essere condivisi tra le altre soluzioni Experience Cloud. Inoltre, questo ID può sostituire o lavorare con ID specifici della soluzione, ad esempio l'ID visitatore di Analytics. [Altro...](https://docs.adobe.com/content/help/en/id-service/using/intro/overview.html) |
| ID visitatore - Come si imposta l'ID visitatore se i cookie sono bloccati? | Se il cookie s_ vi standard non è disponibile, viene creato un cookie di fallback sul dominio del sito Web con un ID univoco generato in modo casuale. Questo cookie, denominato s_ fid, è impostato con scadenza di 2 anni e viene utilizzato quando il metodo di identificazione di fallback procede. [Altro...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/unique-visitors/visid-fallback.html) |
| Gestione tag dinamica - Perché la mia regola di Gestione dinamica dei tag non viene attivata? | Se la regola basata sugli eventi non viene attivata, è probabile che si verifichi un problema con il selettore o la condizione della regola. Individuate l'elemento sul sito in cui si verifica l'azione desiderata, fate clic con il pulsante destro del mouse e selezionate l'elemento Esamina. Ispezionare lo script evidenziato nella casella che si apre e assicurarsi di avere il targeting dell'elemento corretto. [Altro...](https://docs.adobe.com/content/help/en/dtm/using/admin/c-troubleshooting.html) |
| Come si implementa il Tracciamento video Heartbeat? | [Questa sezione](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) contiene istruzioni su come scaricare gli SDK per heartbeat video e guide per sviluppatori per la piattaforma. Assicurati anche di scaricare la guida per sviluppatori presente nella cartella docs quando scaricate l'SDK in quanto contiene le istruzioni di implementazione specifiche per i video heartbeat. |
| Come si aggiungono i cookie al sottodominio corretto? | La variabile cookiedomainperiod determina il dominio in cui vengono impostati i cookie di Analytics s_ cc e s_ sq determinando il numero di periodi nel dominio dell'URL della pagina. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in. See [Configuration Variables](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/configuration-variables.html) |
| Server di tracciamento - Come posso compilare correttamente il server di tracciamento? | Quando configurate un'implementazione per inviare dati ai server Adobe Analytics, dovete inviarli alla posizione corretta. In questo caso, il conteggio dei visitatori aumenta o la perdita di dati. [Altro...](https://helpx.adobe.com/analytics/kb/determining-data-center.html) |
| Prestazioni - È possibile che il caricamento di Adobe javascript esterno, a causa di connessione Internet, proxy, firewall o interruzione di servizio presso Adobe, comprometta le prestazioni? | No. Il file javascript non è ospitato sui server Adobe, pertanto un'interruzione Adobe non influirà sull'esecuzione javascript. |
| Prestazioni - Il caricamento di Adobe javascript esterno causa una riduzione delle prestazioni? | Il file javascript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti Web, gli utenti possono media più di un paio di visualizzazioni di pagina per sessione, quindi il trasferimento di javascript utilizzato più volte in questo file può comportare meno dati scaricati. <br>Javascript per la compressione appmeasurement: Se siete preoccupati dello spessore della pagina (dimensione) del client javascript di Adobe, Adobe consiglia di considerare la compressione del file tramite GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione javascript per comprimere e decomprimere il file `s_code.js` javascript di base. |
| Prestazioni - L'invio di dati dal browser ai servizi Adobe riduce le prestazioni? | Il file Adobe javascript crea un oggetto immagine all'interno della pagina HTML e il browser quindi richiede l'oggetto immagine dai server Adobe. Se i server Adobe dovevano essere lenti o non rispondere, il thread che gestisce la richiesta viene ritardato finché non si verifica un timeout. Poiché i browser gestiscono immagini con più thread, un'interruzione Adobe ha un impatto minimo sul tempo di caricamento della pagina, toccando un thread mentre gli altri continuano a funzionare. |
| Prestazioni - Un evento javascript di Adobe influisce su comportamenti o funzionalità del sistema? | No. Consultate le precedenti risposte alle prestazioni. |
| Come posso modificare i dati raccolti in base a condizioni personali personali? | Utilizza le regole di elaborazione per semplificare la raccolta dati e gestire i contenuti quando viene inviato al reporting. ([Altro...](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Qual è la versione più recente del file s_ code? | Questa sezione contiene una cronologia del rilascio per le librerie appmeasurement su piattaforme Web e mobili. L'ultima versione di ciascuna libreria può essere scaricata in Analytics &gt; Amministratore &gt; Gestione codici. [Altro...](/help/implement/appmeasurement-release-notes/c-release-notes-mjs.md) |
| Come si esegue il debug del file s_ code? | Il debugger Experience Cloud è uno strumento gratuito fornito da Adobe che consente di visualizzare i dati raccolti dal sito in qualsiasi pagina. [Altro...](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) |
| Come si tiene traccia dei diversi tipi di collegamento? | I download dei file e i collegamenti di uscita possono essere tracciati automaticamente in base ai parametri impostati in appmeasurement per il file javascript. [Altro...](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/function-tl.html) |
| Come si tiene traccia del video? | È possibile utilizzare javascript per tenere traccia di un'ampia gamma di lettori. Per tenere traccia di javascript, aggiungere codice alla pagina Web che contiene il lettore e tenere traccia del lettore utilizzando i gestori di eventi. [Altro...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| Come si tiene traccia di un'app mobile? | In Adobe Mobile Services è possibile generare collegamenti di acquisizione con codici di tracciamento univoci. Quando un utente scarica ed esegue un'app dall'Apple App Store dopo aver fatto clic sul collegamento generato, l'SDK raccoglie e invia automaticamente i dati di acquisizione ad Adobe Mobile Services. [iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html), [Android](https://docs.adobe.com/content/help/en/mobile-services/android/overview.html) |
| Come si implementa il tracciamento video? | Potete tenere traccia dei lettori multimediali creando funzioni allegate ai gestori di eventi video player, che consente di chiamare Media. open, Media. play, Media. stop e Media. close ai momenti opportuni. [Altro...](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html) |
| Come si imposta il cookie First Party? | Analytics utilizza i cookie per fornire informazioni su variabili e componenti che non permangono tra richieste di immagini e sessioni del browser. Questi cookie inoffensivi provengono da un dominio ospitato da Adobe, noto come cookie di terze parti. [Altro...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| Come si ottiene un certificato SSL? | Stabilite se il vostro sito utilizza il `https://` protocollo. In caso contrario, sarà necessario richiedere un CSR e acquistare un certificato SSL. Nota: Non è necessario un certificato SSL se non si dispone di pagine o contenuti protetti. Questo passaggio può essere ignorato se utilizzate solo `https://` il protocollo sul sito. [Altro...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| Dove trovo informazioni sul avviso di scadenza della certificazione? | I certificati SSL scadono ogni anno, il che significa che Adobe richiede una richiesta di certificato aggiornata ogni volta che ciò accade. Lo specialista FPC fornisce un avviso sufficiente nel momento in cui si verifica, tuttavia si consiglia di monitorare la scadenza e fornire ad Adobe il certificato aggiornato. [Altro...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) |
| Cosa sono i plug-in? | Appmeasurement per i plug-in javascript sono programmi o funzioni che eseguono diverse funzioni avanzate. Questi plug-in estendono le funzionalità del file javascript per offrire ulteriori funzionalità non disponibili con un'implementazione di base. Adobe offre molti altri plug-nell'ambito delle soluzioni avanzate. Contattate l'Account Manager per acquisire i dati utilizzando javascript, ma non assicuratevi di procedere. [Altro...](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) |
| Come trovo informazioni sull'API di inserimento dati? | Adobe ha creato diversi modi per inviare dati in Analytics. [Altro...](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
| Cos'è un errore 500? | Informazioni sull'errore interno del server che ha provocato lo stato di «Errore query 500» nella [variabile pagetype](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables.html#concept_F67870238EF74491B5D3909A33CDB985). |
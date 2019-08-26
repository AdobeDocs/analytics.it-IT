---
description: Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.
keywords: Implementazione di Analytics; faq; domande frequenti; scadenza evar; visibilità evento personalizzata; timestamp; periodo di tolleranza per ID visitatore; ID visitatore; ID visitatore Experience Cloud; ID visitatore analytics; dtm; heartbeat; cookie; server di tracciamento; prestazioni; javascript; raccolta dati; s_ code version; s_ code debug; monitoraggio tipi di collegamento; tracciare video; app per dispositivi mobili; cookie dei siti Web visualizzati; certificato ssl; scadenza della certificazione; scadenza del certificato; plug-in; api di inserimento dati; errore 500; 500; Gestisci utente;gestisci gruppo; utenti; gruppi
seo-description: Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.
seo-title: Domande frequenti sull’implementazione di Analytics
solution: Analytics
title: Domande frequenti sull’implementazione di Analytics
topic: Sviluppatore e implementazione
uuid: 983d759a-c4f2-4021-84c8-0486dbb951b8
translation-type: ht
source-git-commit: 0143edbcbab3450f6932367f51e9e4c79bc1ae63

---


# Domande frequenti sull’implementazione di Analytics

Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.

<table id="table_91790388C2DE4C5E8AEF0B9981AFFE27"> 
 <tbody> 
  <tr> 
   <td> <b>domande</b> </td> 
   <td> <b>Risposta</b> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Come posso gestire utenti e gruppi di Analytics? </p> </td> 
   <td colname="col3"> <p>Per informazioni sulla gestione di utenti e gruppi, consulta <a href="https://marketing.adobe.com/resources/help/en_US/reference/user_management.html" format="html" scope="external"> Gestione di utenti e prodotti </a> nella guida di Adobe Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Scadenza eVar: perché gli eVar vengono attribuiti a "Nessuno" nei rapporti? </p> </td> 
   <td colname="col3"> <p> <span class="uicontrol"> Dopo </span> specifica un periodo di tempo, o un evento, dopo la scadenza del valore eVar (non ricevono più crediti per eventi di successo). Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo). Se selezioni un evento come valore di scadenza, la variabile scade solo se si verifica l’evento. Se l’evento non si verifica, la variabile non scade. <a href="https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Visibilità evento personalizzata: perché gli Eventi personalizzati non vengono visualizzati nel menu rapporti? </p> </td> 
   <td colname="col3"> <p>Nella colonna Visibilità puoi nascondere le metriche standard (integrate), gli eventi personalizzati e gli eventi incorporati in Menu, Selettori metriche, Generatore metriche calcolate e Generatore segmenti. Questa impostazione non influisce sulla raccolta dei dati per quella metrica o evento; influisce solo sulla sua visibilità nell’interfaccia utente. <a href="https://marketing.adobe.com/resources/help/en_US/reference/metric-visibility.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Marca temporale: cosa devo tenere in considerazione prima di cambiare le impostazioni di marca temporale? </p> </td> 
   <td colname="col3"> <p>Utilizzando la funzione facoltativa Marca temporale, puoi combinare dati senza marca temporale con dati con marca temporale senza la conseguente perdita di dati. I dati offline con marca temporale generata da un dispositivo mobile possono essere combinati con dati live e senza marca temporale da una pagina web, oppure integrati con dati provenienti da qualsiasi piattaforma mediante una chiamata di marca temporale lato client. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/timestamps-overview.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID visitatore: come funziona il periodo di tolleranza per il servizio ID visitatore e come è abilitato? </p> </td> 
   <td colname="col3"> <p>Se disponi di più file JavaScript che inviano dati alla stessa suite di rapporti o se utilizzi altre tecnologie sul tuo sito, ad esempio la misurazione video Flash, ti consigliamo di impostare un periodo di tolleranza. <a href="https://marketing.adobe.com/resources/help/it_IT/mcvid/mcvid_grace_period.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID visitatore: qual è la differenza tra l’ID visitatore Experience Cloud e l’ID visitatore Analytics? </p> </td> 
   <td colname="col3"> <p>Il Servizio identità assegna un identificatore unico e permanente a tutti i visitatori del sito. Con questo ID, i visitatori e i loro dati possono essere condivisi tra le altre soluzioni nell’Experience Cloud. Inoltre, questo ID può sostituire o funzionare con ID specifici della soluzione, ad esempio l’ID visitatore Analytics. <a href="https://marketing.adobe.com/resources/help/it_IT/mcvid/mcvid-overview.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>ID visitatore: come si imposta l’ID visitatore se i cookie sono bloccati? </p> </td> 
   <td colname="col3"> <p>Se il cookie s_vi standard non è disponibile, viene creato un cookie di fallback sul dominio del sito web con un ID univoco generato in modo casuale. Questo cookie, denominato s_fid, è impostato con scadenza di 2 anni e viene utilizzato quando il metodo di identificazione di fallback continua. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Dynamic Tag Management: perché la mia regola di Gestione dinamica dei tag non viene attivata? </p> </td> 
   <td colname="col3"> <p>Se la regola basata sugli eventi non viene attivata, è probabile che si verifichi un problema con il selettore o la condizione della regola. Individua l’elemento sul sito in cui si verifica l’azione desiderata, fai clic con il pulsante destro del mouse e seleziona l’elemento Esamina. Esamina lo script evidenziato nella casella che si apre e assicurati di avere il targeting dell’elemento corretto. <a href="https://marketing.adobe.com/resources/help/it_IT/dtm/c_Troubleshooting.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Come si implementa il Tracciamento video Heartbeat? </p> </td> 
   <td colname="col3"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/" format="https" scope="external"> Questa sezione </a> contiene istruzioni su come scaricare gli SDK per heartbeat video e guide per sviluppatori per la piattaforma. Assicurati anche di scaricare la guida per sviluppatori presente nella cartella docs al momento del download dell’SDK in quanto contiene le istruzioni di implementazione specifiche per i video heartbeat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Come si aggiungono i cookie al sottodominio corretto? </p> </td> 
   <td colname="col3"> La variabile <span class="varname">cookieDomainPeriods </span> determina il dominio in cui vengono impostati i cookie di Analytics s_cc e s_sq, determinando il numero di periodi nel dominio dell’URL della pagina. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in. Consulta [Variabili di configurazione](/help/implementation/js-implementation/c-variables/configuration-variables. md) </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Server di tracciamento: come posso compilare correttamente il server di tracciamento? </p> </td> 
   <td colname="col3"> <p>Quando configuri un’implementazione per inviare dati ai server Adobe Analytics, devi inviarli alla posizione corretta. In caso contrario, il conteggio dei visitatori aumenta o si verifica una perdita di dati. <a href="https://helpx.adobe.com/it/analytics/kb/determining-data-center.html" format="https" scope="external"> [Altro...] </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Prestazioni: è possibile che un errore nel caricamento dello JavaScript esterno per Adobe, a causa dell’interruzione della connessione Internet, proxy, firewall o del servizio in Adobe, comprometta le prestazioni? </p> </td> 
   <td colname="col3"> <p>No. Il file JavaScript non è ospitato sui server Adobe, pertanto un’interruzione Adobe non influirà sull’esecuzione di JavaScript. Se viene utilizzata la Dynamic Tag Management, il file JavaScript è ospitato da Akamai oppure su una posizione server determinata dai clienti. </p> <p>Consulta <i>Dynamic Tag Management riduce le prestazioni del sito web?</i> nelle domande frequenti sulla <a href="https://marketing.adobe.com/resources/help/en_US/dtm/faq.html" format="https" scope="external">Dynamic Tag Management </a>. </p> <p>Inoltre, se non hai familiarità con la CDN di Akamai, puoi ospitare il file di Dynamic Tag Management personalizzato. Consulta <a href="https://marketing.adobe.com/resources/help/it_IT/dtm/deployment.html" format="https" scope="external"> Opzioni di hosting e codice di incorporamento </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Prestazioni: il caricamento dello JavaScript esterno di Adobe causa una riduzione delle prestazioni? </p> </td> 
   <td colname="col3"> <p> Il file JavaScript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti web, gli utenti producono in media più di un paio di visualizzazioni di pagina per sessione, quindi il trasferimento di JavaScript utilizzato più volte in questo file può comportare meno dati scaricati. </p> <p> JavaScript per [!DNL AppMeasurement] Compressione: se sei preoccupato del peso della pagina (dimensione) del client JavaScript di Adobe, Adobe consiglia di considerare la compressione del file tramite GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione JavaScript per comprimere e decomprimere il file JavaScript di base <span class="filepath"> s_code.js </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Prestazioni: l’invio di dati dal browser ai servizi Adobe riduce le prestazioni? </p> </td> 
   <td colname="col3"> <p> Il file JavaScript di Adobe crea un oggetto immagine all’interno della pagina HTML e il browser quindi richiede l’oggetto immagine dai server Adobe. Se i server Adobe dovessero essere lenti o non rispondere, la gestione del thread della richiesta verrebbe ritardata fino al ritorno dell’immagine o al verificarsi di un timeout. Poiché i browser gestiscono immagini con più thread, un’interruzione di Adobe avrebbe un impatto minimo sul tempo di caricamento della pagina, bloccando un thread mentre gli altri continuano a funzionare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Prestazioni: un evento JavaScript di Adobe influisce su comportamenti o funzionalità del sistema? </p> </td> 
   <td colname="col3"> <p>No. Consulta le precedenti risposte alle prestazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Come posso modificare i dati raccolti in base a condizioni personali? </td> 
   <td colname="col3"> Utilizza le regole di elaborazione per semplificare la raccolta dati e gestire i contenuti quando viene inviato al reporting. <a href="https://marketing.adobe.com/resources/help/en_US/reference/processing_rules.html" format="https" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Qual è la versione più recente del file s_code? </td> 
   <td> Questa sezione contiene la cronologia delle versioni delle librerie [!DNL AppMeasurement] su piattaforme web e mobile. L’ultima versione di ciascuna libreria può essere scaricata in Reports &amp; Analytics &gt; Strumenti di amministrazione &gt; Codice manager. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/release/c_release_notes_javascript.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si esegue il debug del file s_code? </td> 
   <td> Adobe Debugger (precedentemente DigitalPulse Debugger) è uno strumento gratuito fornito da Adobe che consente di visualizzare i dati raccolti dal sito in qualsiasi pagina. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si tiene traccia dei diversi tipi di collegamento? </td> 
   <td> I download dei file e i collegamenti di uscita possono essere tracciati automaticamente in base ai parametri impostati in AppMeasurement per il file JavaScript. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/function_tl.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si tiene traccia dei video? </td> 
   <td> È possibile utilizzare JavaScript per tenere traccia di un’ampia gamma di lettori. Per tenere traccia di JavaScript, aggiungi codice alla pagina web che contiene il lettore e tieni traccia del lettore utilizzando i gestori di eventi. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si tiene traccia di un’app mobile? </td> 
   <td> In Adobe Mobile Services è possibile generare collegamenti di acquisizione con codici di tracciamento univoci. Quando un utente scarica ed esegue un’app dall’Apple App Store dopo aver fatto clic sul collegamento generato, l’SDK raccoglie e invia automaticamente i dati di acquisizione ad Adobe Mobile Services. <a href="https://marketing.adobe.com/resources/help/it_IT/mobile/ios/acquisition.html" format="http" scope="external"> iOS </a><a href="https://marketing.adobe.com/resources/help/it_IT/mobile/android/acquisition.html" format="http" scope="external"> Android </a> </td> 
  </tr> 
  <tr> 
   <td> Come si implementa il tracciamento video? </td> 
   <td> Puoi tenere traccia dei lettori multimediali creando funzioni allegate ai gestori di eventi del lettore video, che consente di chiamare Media.open, Media.play, Media.stop e Media.close nei momenti opportuni. <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_js_events.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si imposta il cookie di prime parti? </td> 
   <td> Analytics utilizza i cookie per fornire informazioni su variabili e componenti che non permangono tra richieste di immagini e sessioni del browser. Questi cookie innocui che provengono da un dominio ospitato da Adobe, noto come cookie di terze parti. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Come si ottiene un certificato SSL? </td> 
   <td> Stabilisci se il tuo sito usa il protocollo https://. In caso contrario, sarà necessario richiedere un CSR e acquistare un certificato SSL. Nota: non è necessario un certificato SSL se non si dispone di pagine o contenuti protetti. Questo passaggio può essere ignorato se utilizzate solo il protocollo https:// sul sito. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Dove trovo informazioni sull’avviso di scadenza della certificazione? </td> 
   <td> I certificati SSL scadono ogni anno, il che significa che Adobe richiede una richiesta di certificato aggiornata ogni volta che ciò accade. Lo specialista FPC fornisce un avviso sufficiente nel momento in cui si verifica, tuttavia si consiglia di monitorare la scadenza in modo proattivo e fornire ad Adobe il certificato aggiornato. <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_renewals.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Cosa sono i plug-in? </td> 
   <td> AppMeasurement per i plug-in JavaScript sono programmi o funzioni che eseguono diverse funzioni avanzate. Questi plug-in estendono le funzionalità del file JavaScript per offrire ulteriori funzionalità non disponibili con un’implementazione di base. Adobe offre molti altri plug-nell’ambito delle soluzioni avanzate. Contatta l’Account Manager per acquisire i dati utilizzando JavaScript, ma non sei sicuro su come procedere. <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/impl_plugins.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Informazioni sull’API di inserimento dati? </td> 
   <td> Adobe ha creato diverse soluzioni per inviare dati in Analytics. <a href="https://marketing.adobe.com/resources/help/en_US/reference/usecase_sending_data_to_sc.html" format="http" scope="external"> [Altro...] </a> </td> 
  </tr> 
  <tr> 
   <td> Cos’è un errore 500? </td> 
   <td> Informazioni sull’errore interno del server che ha provocato lo stato di "Errore di query 500". <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/pageType.html" format="http" scope="external">Vedi variabile pageType </a> </td> 
  </tr> 
 </tbody> 
</table>

| Domanda | Risposta |
|---|---|
| Come posso gestire utenti e gruppi di Analytics? | Per informazioni sulla gestione di utenti e gruppi, consulta [Gestisci utenti e prodotti Experience Cloud](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html) nella guida dei servizi di base di Adobe Experience Cloud. |
| Scadenza eVar: perché gli eVar vengono attribuiti a "Nessuno" nei rapporti? | `Expire After` specifica un periodo di tempo, o un evento, dopo la scadenza del valore eVar (non riceve più crediti per eventi di successo). Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo). Se selezioni un evento come valore di scadenza, la variabile scade solo se si verifica l’evento. Se l’evento non si verifica, la variabile non scade. [[Altro…](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) |
| Visibilità evento personalizzata: perché gli Eventi personalizzati non vengono visualizzati nel menu rapporti? | Nella colonna Visibilità puoi nascondere le metriche standard (integrate), gli eventi personalizzati e gli eventi incorporati in Menu, Selettori metriche, Generatore metriche calcolate e Generatore segmenti. Questa impostazione non influisce sulla raccolta dei dati per quella metrica o evento; influisce solo sulla sua visibilità nell’interfaccia utente. [[Altro…](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/metric-visibility.html) |
| Marca temporale: cosa devo tenere in considerazione prima di cambiare le impostazioni di marca temporale? | Utilizzando la funzione facoltativa Marca temporale, puoi combinare dati senza marca temporale con dati con marca temporale senza la conseguente perdita di dati. I dati offline con marca temporale generata da un dispositivo mobile possono essere combinati con dati live e senza marca temporale da una pagina Web, oppure integrati con dati provenienti da qualsiasi piattaforma mediante una chiamata di marca temporale lato client. [[Altro…](https://docs.adobe.com/content/help/it-IT/analytics/implementation/javascript-implementation/timestamps-overview.html) |
| ID visitatore: come funziona il periodo di tolleranza per il servizio ID visitatore e come è abilitato? | Se disponi di più file JavaScript che inviano dati alla stessa suite di rapporti o se utilizzi altre tecnologie sul tuo sito, ad esempio la misurazione video Flash, ti consigliamo di impostare un periodo di tolleranza.  [Altro…](https://docs.adobe.com/content/help/it-IT/id-service/using/reference/analytics-reference/grace-period.html) |
| ID visitatore: qual è la differenza tra l’ID visitatore Experience Cloud e l’ID visitatore Analytics? | Il Servizio identità assegna un identificatore unico e permanente a tutti i visitatori del sito. Con questo ID, i visitatori e i loro dati possono essere condivisi tra le altre soluzioni nell’Experience Cloud. Inoltre, questo ID può sostituire o funzionare con ID specifici della soluzione, ad esempio l’ID visitatore Analytics.  [Altro…](https://docs.adobe.com/content/help/it-IT/id-service/using/intro/overview.html) |
| ID visitatore: come si imposta l’ID visitatore se i cookie sono bloccati? | Se il cookie s_vi standard non è disponibile, viene creato un cookie di fallback sul dominio del sito web con un ID univoco generato in modo casuale. Questo cookie, denominato s_fid, è impostato con scadenza di 2 anni e viene utilizzato quando il metodo di identificazione di fallback continua.  [Altro…](https://docs.adobe.com/content/help/it-IT/analytics/implementation/javascript-implementation/unique-visitors/visid-fallback.html) |
| Dynamic Tag Management: perché la mia regola di Gestione dinamica dei tag non viene attivata? | Se la regola basata sugli eventi non viene attivata, è probabile che si verifichi un problema con il selettore o la condizione della regola. Individua l’elemento sul sito in cui si verifica l’azione desiderata, fai clic con il pulsante destro del mouse e seleziona l’elemento Esamina. Esamina lo script evidenziato nella casella che si apre e assicurati di avere il targeting dell’elemento corretto.  [Altro…](https://docs.adobe.com/content/help/it-IT/dtm/using/admin/c-troubleshooting.html) |
| Come si implementa il Tracciamento video Heartbeat? | [Questa sezione](https://docs.adobe.com/content/help/it-IT/media-analytics/using/media-overview.html) contiene istruzioni su come scaricare gli SDK per heartbeat video e guide per sviluppatori per la piattaforma. Assicurati anche di scaricare la guida per sviluppatori presente nella cartella docs al momento del download dell’SDK in quanto contiene le istruzioni di implementazione specifiche per i video heartbeat. |
| Come si aggiungono i cookie al sottodominio corretto? | La variabile cookieDomainPeriods determina il dominio in cui vengono impostati i cookie di Analytics s_cc e s_sq, determinando il numero di periodi nel dominio dell’URL della pagina. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in. Consulta [Variabili di configurazione](https://docs.adobe.com/content/help/it-IT/analytics/implementation/javascript-implementation/variables-analytics-reporting/configuration-variables.html) |
| Server di tracciamento: come posso compilare correttamente il server di tracciamento? | Quando configuri un’implementazione per inviare dati ai server Adobe Analytics, devi inviarli alla posizione corretta. In caso contrario, il conteggio dei visitatori aumenta o si verifica una perdita di dati. [Altro…](https://helpx.adobe.com/it/analytics/kb/determining-data-center.html) |
| Prestazioni: è possibile che un errore nel caricamento dello JavaScript esterno per Adobe, a causa dell’interruzione della connessione Internet, proxy, firewall o del servizio in Adobe, comprometta le prestazioni? | No. Il file JavaScript non è ospitato sui server Adobe, pertanto un’interruzione Adobe non influirà sull’esecuzione di JavaScript. |
| Prestazioni: il caricamento dello JavaScript esterno di Adobe causa una riduzione delle prestazioni? | Il file JavaScript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti web, gli utenti producono in media più di un paio di visualizzazioni di pagina per sessione, quindi il trasferimento di JavaScript utilizzato più volte in questo file può comportare meno dati scaricati. <br>JavaScript per la compressione AppMeasurement: se sei preoccupato del peso della pagina (dimensione) del client JavaScript di Adobe, Adobe consiglia di considerare la compressione del file tramite GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione JavaScript per comprimere e decomprimere il file `s_code.js` JavaScript di base. |
| Prestazioni: l’invio di dati dal browser ai servizi Adobe riduce le prestazioni? | Il file JavaScript di Adobe crea un oggetto immagine all’interno della pagina HTML e il browser quindi richiede l’oggetto immagine dai server Adobe. Se i server Adobe dovessero essere lenti o non rispondere, la gestione del thread della richiesta verrebbe ritardata fino al ritorno dell’immagine o al verificarsi di un timeout. Poiché i browser gestiscono immagini con più thread, un’interruzione di Adobe avrebbe un impatto minimo sul tempo di caricamento della pagina, bloccando un thread mentre gli altri continuano a funzionare. |
| Prestazioni: un evento JavaScript di Adobe influisce su comportamenti o funzionalità del sistema? | No. Consulta le precedenti risposte alle prestazioni. |
| Come posso modificare i dati raccolti in base a condizioni personali? | Utilizza le regole di elaborazione per semplificare la raccolta dati e gestire i contenuti quando viene inviato al reporting.  ([Altro…](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/processing-rules/processing-rules.html) |
| Qual è la versione più recente del file s_code? | Questa sezione contiene una cronologia della versione per le librerie AppMeasurement su piattaforme web e mobili. L’ultima versione di ciascuna libreria può essere scaricata in Analytics &gt; Amministratore &gt; Codice manager. [Altro...](/help/implement/appmeasurement-release-notes/c-release-notes-mjs.md) |
| Come si esegue il debug del file s_code? | Il debugger Experience Cloud è uno strumento gratuito fornito da Adobe che consente di visualizzare i dati raccolti dal sito in qualsiasi pagina. [Altro…](https://docs.adobe.com/content/help/it-IT/analytics/implementation/testing-and-validation/debugger.html) |
| Come si tiene traccia dei diversi tipi di collegamento? | I download dei file e i collegamenti di uscita possono essere tracciati automaticamente in base ai parametri impostati in AppMeasurement per il file JavaScript. [Altro…](https://docs.adobe.com/content/help/it-IT/analytics/implementation/javascript-implementation/function-tl.html) |
| Come si tiene traccia dei video? | È possibile utilizzare JavaScript per tenere traccia di un’ampia gamma di lettori. Per tenere traccia di JavaScript, aggiungi codice alla pagina web che contiene il lettore e tieni traccia del lettore utilizzando i gestori di eventi. [Altro…](https://docs.adobe.com/content/help/it-IT/media-analytics/using/media-overview.html) |
| Come si tiene traccia di un’app mobile? | In Adobe Mobile Services è possibile generare collegamenti di acquisizione con codici di tracciamento univoci. Quando un utente scarica ed esegue un’app dall’Apple App Store dopo aver fatto clic sul collegamento generato, l’SDK raccoglie e invia automaticamente i dati di acquisizione ad Adobe Mobile Services. [iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html), [Android](https://docs.adobe.com/content/help/en/mobile-services/android/overview.html) |
| Come si implementa il tracciamento video? | Puoi tenere traccia dei lettori multimediali creando funzioni allegate ai gestori di eventi del lettore video, che consente di chiamare Media.open, Media.play, Media.stop e Media.close nei momenti opportuni. [Altro…](https://docs.adobe.com/content/help/it-IT/media-analytics/using/media-overview.html) |
| Come si imposta il cookie di prime parti? | Analytics utilizza i cookie per fornire informazioni su variabili e componenti che non permangono tra richieste di immagini e sessioni del browser. Questi cookie innocui che provengono da un dominio ospitato da Adobe, noto come cookie di terze parti. [Altro...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| Come si ottiene un certificato SSL? | Stabilisci se il tuo sito utilizza il protocollo `https://`. In caso contrario, sarà necessario richiedere un CSR e acquistare un certificato SSL. Nota: non è necessario un certificato SSL se non si dispone di pagine o contenuti protetti. Questo passaggio può essere ignorato se utilizzi solo il protocollo `https://` sul sito.  [Altro...](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cert.html) |
| Dove trovo informazioni sull’avviso di scadenza della certificazione? | I certificati SSL scadono ogni anno, il che significa che Adobe richiede una richiesta di certificato aggiornata ogni volta che ciò accade. Lo specialista FPC fornisce un avviso sufficiente nel momento in cui si verifica, tuttavia si consiglia di monitorare la scadenza in modo proattivo e fornire ad Adobe il certificato aggiornato. [Altro…](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html) |
| Cosa sono i plug-in? | AppMeasurement per i plug-in JavaScript sono programmi o funzioni che eseguono diverse funzioni avanzate. Questi plug-in estendono le funzionalità del file JavaScript per offrire ulteriori funzionalità non disponibili con un’implementazione di base. Adobe offre molti altri plug-nell’ambito delle soluzioni avanzate. Contatta l’Account Manager per acquisire i dati utilizzando JavaScript, ma non sei sicuro su come procedere. [Altro...](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) |
| Come trovo informazioni sull’API di inserimento dati? | Adobe ha creato diverse soluzioni per inviare dati in Analytics. [Altro…](https://helpx.adobe.com/it/analytics/kb/data-insertion-api-post-method-adobe-analytics.html) |
| Cos’è un errore 500? | Informazioni sull’errore interno del server che ha provocato lo stato di "Errore di query 500" su [variabile pageType](https://docs.adobe.com/content/help/it-IT/analytics/implementation/javascript-implementation/variables-analytics-reporting/page-variables.html#concept_F67870238EF74491B5D3909A33CDB985). |
---
description: 'La configurazione dell’integrazione DFAE comporta le seguenti attività '
keywords: DFA
title: Integrazione DFA
topic: Data connectors
uuid: 972a9d62-24fd-4463-a34c-5ec0b926e81e
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '2590'
ht-degree: 1%

---


# Integrazione DFA{#dfa-integration}

La configurazione dell’integrazione del DFAE comporta le seguenti attività:

## Configurare l’integrazione DFA{#configure-the-dfa-integration}

Integrazione dei connettori dati del DFA.

Le pagine di configurazione forniscono una panoramica dell&#39;integrazione, insieme a utili collegamenti per ulteriori informazioni. A questa integrazione sono associate sia le tariffe Adobe che DoubleClick. Contatta i rappresentanti di vendita appropriati per entrambe le organizzazioni e assicurati di conoscere la struttura delle tariffe.

1. Accedi a [!DNL Adobe Analytics].
1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Individua **[!UICONTROL DoubleClick DFA]**, quindi fai clic su **[!UICONTROL Add New]**.

   ![Risultato passaggio](assets/wizard-01.png)

   In ogni pagina della procedura guidata di integrazione, fornire le informazioni richieste, quindi fare clic su **[!UICONTROL Next]**. Nella tabella seguente sono illustrate le informazioni necessarie per completare l&#39;integrazione tramite la procedura guidata.

<table id="table_8F6F7F304C36431DA5FD6E5D54F60FC0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina della procedura guidata # </th> 
   <th colname="col2" class="entry"> Campo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Nome integrazione </td> 
   <td colname="col3"> Il nome dell'integrazione visualizzato da Genesis nell'Elenco di integrazione attiva della suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Indirizzo e-mail integrazione </td> 
   <td colname="col3"> L'indirizzo e-mail che riceve tutte le notifiche correlate a questa integrazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Nome utente </td> 
   <td colname="col3"> Il nome utente dell’API DFA da utilizzare con questa integrazione. Per abilitare un utente per l'accesso alle API, controllate l'attributo API nell'interfaccia DFA. Dopo aver attivato l'accesso all'API, viene visualizzato un campo password per fornire una password all'utente. Questa password viene immessa insieme al nome utente nella procedura guidata di autenticazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Password </td> 
   <td colname="col3"> La password dell’API DFA. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> ID inserzionista </td> 
   <td colname="col3"> <p>L’ID dell’inserzionista DFA o l’ID di configurazione del flusso principale. I Connettori dati utilizzano questo ID per identificare l’inserzionista DFA da monitorare (versione 1.5 dell’integrazione). Questo ID inserzionista non viene utilizzato nella versione 2.0 dell'integrazione. L'ID configurazione Floodlight padre verrà cercato e utilizzato. Vedere le istruzioni sullo schermo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> Variabile annuncio DFA </td> 
   <td colname="col3"> L'eVar Analytics  che riceve l'attributo della campagna DFA, le impression e i dati di clic. In genere si tratta dell'eVar del codice di tracciamento ( <span class="varname"> s.campaign </span>), ma potete scegliere qualsiasi eVar disponibile. I Connettori dati aggiungono inoltre le seguenti classificazioni relative al DFA all'eVar selezionata: <p><b>Campagne</b>: Una raccolta di annunci serviti a più siti che contengono messaggi comuni. </p> <p><b>Nome</b>sito: Il sito in cui è stato distribuito l’annuncio. </p> <p><b>Nome</b>annuncio: Il nome dell'annuncio, come definito nel tuo account DFA. </p> <p><b>Nome</b>posizionamento sito: Il sito Web e la pagina in cui è stato distribuito l'annuncio. </p> <p><b>Strumento</b>di consegna: Doppio clic per inserzionisti. </p> <p><b>Canale</b>: Annuncio banner. </p> <p><b>Struttura</b>dei costi: CPM, CPC o Fisso, in base alla struttura dei costi dell’annuncio. </p> <p><b>Nome</b>creativo: Nome del creativo associato a un ID annuncio/posizionamento/creativo. </p> <p><b>DFA &gt; Deduplicazione</b>SearchCenter: Specifica che il DFAE deve inserire i valori nelle variabili del Centro di ricerca quando si verificano click-through DFA o View-through. </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impressioni </td> 
   <td colname="col3"> Evento personalizzato che riceve i dati delle metriche Impression DFA. Impression indica il numero di volte in cui l’annuncio è stato distribuito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Clic </td> 
   <td colname="col3"> Selezionate l’evento personalizzato che riceve i dati delle metriche Clic DFA. I clic indicano il numero di volte in cui i visitatori hanno fatto clic sull’annuncio, misurato dal reindirizzamento del DFAE. La metrica Clicks (Clic) è correlata alla metrica  Click-through di Analytics. <p>Nota:  Clic DFA e  Click-through Analytics potrebbero non corrispondere esattamente a causa delle differenze nelle modalità di raccolta dei dati.  </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Variabile View-Through </td> 
   <td colname="col3"> <p> eVar Analytics che riceve i dati View-Through DFA. La variabile View-Through consente di vedere in che modo le visualizzazioni influiscono sui tassi di conversione sul sito. </p> <p>I Connettori dati aggiungono a questa eVar le stesse classificazioni relative al DFA e alla Variabile annuncio del DFA (vedi sopra). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Ora dall’ultima visualizzazione (variabile periodo fisso vista-through) </td> 
   <td colname="col3"> L'eVar Analytics  che riceve l'ora DFA dall'ultima visualizzazione dei dati. L’indicazione Ora dall’ultima visualizzazione indica il tempo trascorso dall’ultima visualizzazione annuncio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Visualizza-through </td> 
   <td colname="col3"> L’evento personalizzato che riceve i dati delle metriche di visualizzazione DFA attraverso. Utilizzare l'evento View-through con la variabile View-Through per vedere quali campagne non hanno influenzato un click-through diretto, ma hanno avuto un ruolo nel traffico verso il sito in un momento successivo. <p>I Connettori dati rinominano l'evento personalizzato selezionato in "Visualizza attraverso". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Errore query DFA </td> 
   <td colname="col3"> (Facoltativo)  eVar Analytics che riceve tutti i codici messaggio di errore query DFA segnalati. I possibili codici messaggio DFA includono: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: Nessun cookie DoubleClick. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>o</b>: L'utente ha rinunciato. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: Nessuna cronologia delle campagne. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: Errore di query (timeout, inattività del server, ecc.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Evento timeout </td> 
   <td colname="col3"> <p>Il  Analytics Counter Event che aumenta ogni volta che scade il timer <span class="varname"> s.maxDelay </span> e non è stata ricevuta alcuna risposta dai server DFA. Utilizzate questo evento per configurare la <span class="varname"> variabile s.maxDelay Sintonizzazione s.maxDelay </span> </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiornamenti del sito Web per l&#39;integrazione DFA{#web-site-updates-for-the-dfa-integration}

Dopo che Genesis ha configurato la suite di rapporti  Analytics per l&#39;integrazione DFA, devi effettuare le seguenti operazioni per configurare il tuo sito Web e l&#39;ambiente DFA in modo che supporti l&#39;integrazione:

### Verifica spazio cookie sul dominio{#verify-cookie-space-on-the-domain}

L’integrazione dei connettori dati per DFA richiede l’impostazione di un cookie sul dominio della pagina.

Anche se è raro, alcuni domini hanno raggiunto la capacità massima di cookie per alcuni browser Web. Per evitare di influenzare l&#39;esperienza di navigazione di un visitatore sul sito Web, rivolgiti alle operazioni di rete, al team di sviluppo o al gruppo di tecnici per verificare che l&#39;aggiunta di un altro cookie al dominio delle pagine utilizzate per l&#39;integrazione DFAE non influisca sull&#39;esperienza dell&#39;utente. Sarà inoltre necessario selezionare un nome per il cookie.

### Aggiorna il parametro query-stringa DFA{#update-your-dfa-query-string-parameter}

Se hai già eseguito il tracciamento delle campagne pubblicitarie con Adobe  Analytics prima dell&#39;integrazione DFA, è possibile che tutte le campagne (e-mail, ricerca o banner) utilizzino lo stesso parametro della stringa di query per identificare l&#39;ID campagna di provenienza sulla pagina di destinazione.

Per capire quando richiedere dati di visualizzazione e click-through dai dati DFA per le campagne DFA Ad, i Connettori dati devono identificare quando un visitatore ha fatto clic su un banner pubblicitario di campagna DFA. Per rendere possibile questa operazione, devi aggiungere un parametro di stringa di query differenziata all&#39;URL della pagina di destinazione della campagna DFA Ad in modo che i Connettori dati possano distinguere tra le pagine della campagna DFA Ad e altre pagine della campagna pubblicitaria che potresti avere sul tuo sito Web. Il plug- `dfa_overrideParam` in JavaScript utilizzato per il DFA.

>[!CAUTION]
>
>Anche se la variabile Campaign può essere utilizzata per altre campagne, non utilizzarla per le campagne DFA. Se imposti la variabile Campagna su una pagina di destinazione della campagna DFA, Adobe non può collegare impression e clic ai click-through della campagna DFA. Una volta effettuata la visita, i server di raccolta Adobe controllano i server DFA per verificare la presenza di un click-through precedente. Per questo motivo, includete il codice plug-in DFA solo su pagine di destinazione comuni, per evitare reindirizzamenti inutili che possano rallentare i tempi di caricamento delle pagine, in particolare per gli utenti con connessioni Internet più lente.

## Aggiorna il codice di raccolta dati del sito Web{#update-your-web-site-s-data-collection-code}

L’integrazione di Genesis per il DFA sfrutta l’ID di configurazione DFA Floodlight (dfa_SPOTID), che migliora la coerenza dei rapporti tra il DFA e il sistema di raccolta dei dati Adobe.

>[!NOTE]
>
>Il termine Spotlight è stato modificato in Floodlight in una recente release di Google DFA. Il parametro JavaScript `dfa_SPOTID` è stato denominato in base alla terminologia di Spotlight, ma viene utilizzato per entrambe le versioni.

Per abilitare l&#39;integrazione DFA sul sito Web, è necessario aggiornare il codice di raccolta dati JavaScript aggiungendo quanto segue:

* Modulo integrato per DFA
* Aggiunta al codice della raccolta

### Modulo integrato per DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

L’integrazione DFA sfrutta il modulo Adobe Experience Cloud Integrate, che aggiunge funzionalità al codice di raccolta dati JavaScript di base ( `s_code.js`). Il modulo Integrate fa parte del file .zip quando si scarica il codice AppMeasurement per Javascript da Gestione codici. Contatta il tuo Adobe Consultant solo se hai bisogno di ulteriore aiuto per trovarla.

Inserite il codice Modulo integrato nella `Modules` sezione del `s_code.js` file del sito Web.

### Aggiunta al codice della raccolta {#section-8f98c727f1ba414fb8b4f02d696b8791}

In base alle selezioni effettuate durante l&#39;attivazione dell&#39;integrazione DFA nella procedura guidata di integrazione, i Connettori dati generano ed inviano tramite e-mail un&#39;aggiunta personalizzata al codice di raccolta dati JavaScript. Inserire questo codice nella sezione principale del `s_code.js` file (non nella `doPlugins` funzione o in qualsiasi altra funzione).

Il codice di esempio riportato di seguito è solo a scopo illustrativo; utilizzare il codice che ti è stato inviato via e-mail dopo aver completato l&#39;Integrazione guidata Connettori dati.

Il codice della raccolta è costituito dai seguenti componenti:

* Impostazioni di integrazione DFA
* Plug-in richiesti per l&#39;integrazione

**Impostazioni di integrazione DFA**

```
/************************** DFA VARIABLES **************************/ 
var dfaConfig = { 
   CSID:              "1234567", 
   SPOTID:            "29876543", 
   tEvar:             "eVar17", 
   errorEvar:         "eVar59", 
   timeoutEvent:      "event76", 
   requestURL:         "http://fls.doubleclick.net/ 
json?spot=[SPOTID]&src=[CSID]&var=[VAR]&host=integrate.112.2o7.net%2 
Fdfa_echo%3Fvar%3D[VAR]%26AQE%3D1%26A2S%3D1&ord=[RAND]", 
 
   maxDelay:          "1500", 
   visitCookie:       "s_dfa", 
   clickThroughParam: "CID", 
   searchCenterParam: "s_kwcid", 
   newRsidsProp:      undefined 
}; 
/************************ END DFA Variables ************************/ 
```

Il blocco delle impostazioni integrate DFAE imposta le variabili richieste dall’integrazione del DFAE. I valori per ciascuna di queste variabili provengono dalle origini seguenti:

**CSID**: ID lato client. Generato dal DFA una volta completata l&#39;Integrazione guidata. Connettori dati precompila questa variabile con il tuo DFA CS ID e invia anche questo valore nel messaggio e-mail di configurazione dopo il completamento dell&#39;Integrazione guidata. Questa variabile non è necessaria se sul vostro account è abilitato Advanced Ad Serving.

**SPOTID**: Configurazione di Floodlight (precedentemente denominato Spotlight ID). I Connettori dati precompilano questa variabile con l’ID di configurazione DFA Floodlight, in base alle informazioni sull’account DFA specificate nella procedura guidata di integrazione.

**Evar**: Variabile di trasferimento. Connettori dati precompila questa variabile con il nome  variabile Analytics specificato per la variabile View-Through nella procedura guidata di integrazione. Non modificate questo valore senza un&#39;attenta coordinazione con Adobe Engineering o Engineering Services.

**errorEvar**: Variabile di errore. Connettori dati precompila questa variabile con il nome  variabile Analytics specificato per la variabile Errore query DFA nell&#39;Integrazione guidata.

**timeoutEvent**: Evento Timeout. Connettori dati precompila questa variabile con il nome  variabile Analytics specificato per la variabile Evento timeout nella procedura guidata di integrazione.

**requestURL**: Host DFA remoto per richiedere informazioni sugli annunci. Non modificate questo valore a meno che non sia richiesto da Adobe.

**maxDelay**: Specifica il tempo in millisecondi che il codice JavaScript di raccolta dati attende una risposta dal server DFA Floodlight. Adobe consiglia di sperimentare questo valore per trovare il valore ottimale in base al traffico del sito. Ad esempio, se si aumenta questo valore, in genere vengono raccolti più dati DFA, ma aumenta il rischio di perdere i dati del visitatore di base se il visitatore lascia il sito durante il periodo di ritardo. Riducendo questo valore si riduce il rischio di perdita di dati hit, ma si può ridurre la quantità di dati DFA inviati con i dati hit Adobe.

**visitCookie**: Nome del cookie utilizzato per limitare le chiamate DFA a una volta per visita.

**clickThroughParam**: Una stringa di query, solitamente inclusa in tutti gli annunci, che notifica al modulo Integrate che si è appena verificato un clic. La presenza di questo parametro nella stringa di query determina l&#39;esecuzione della richiesta ai server DFA Floodlight, indipendentemente dal fatto che il visitatore sia già stato interrogato negli ultimi 30 minuti.

**newRsidsProp**: (Facoltativo) Mappata a una variabile della proprietà Traffico non utilizzata. L’integrazione DFAE raccoglie e memorizza questo valore nel cookie della visita per identificare le suite di rapporti che hanno raccolto i dati per un particolare visitatore. Questa proprietà è necessaria solo con le implementazioni personalizzate con i servizi tecnici Adobe.

**Plug-in richiesti per l&#39;integrazione**

L&#39;aggiunta del codice di raccolta include plug-in aggiuntivi che migliorano il funzionamento dell&#39;integrazione DFAE:

* Limita le query DFA a una sola visita
* Offre flessibilità per il nome dei cookie. Anche se la maggior parte delle organizzazioni utilizza s_dfa, è possibile utilizzare qualsiasi nome di cookie valido per l&#39;integrazione DFA.
* Elimina i reindirizzamenti non necessari. Poiché i dati di visualizzazione vengono raccolti in tempo reale, i server di raccolta Adobe e il DFA potrebbero potenzialmente scambiare dati su ogni visualizzazione di pagina. Il plug-in blocca questi scambi di dati quando le informazioni non sono necessarie.

>[!CAUTION]
>
>Uno dei meccanismi utilizzati dal plug-in per eliminare le query DFA non necessarie è un cookie di visita basato su dominio. Una suite di rapporti per l&#39;integrazione che si estende su più domini aumenta i dati di click-through e visualizzazione through quando i visitatori attraversano più domini dopo una visualizzazione o un click-through influenzati dal DFA.

## Conferma di un&#39;integrazione DFA di successo{#confirming-a-successful-dfa-integration}

Dopo aver effettuato tutti gli aggiornamenti necessari al sito Web, potete utilizzare un visualizzatore del traffico di rete, come Charles*, Chrome Developer Tools o Firebug*, per confermare che DFA sta comunicando con i server di raccolta Adobe.

Dopo aver distribuito il `s_code.js` file abilitato per il DFA, utilizzate il visualizzatore del traffico di rete per visualizzare le richieste tra il DFA e i server di raccolta dati Adobe, alla ricerca di quanto segue:

* Una richiesta al `fls.doubleclick.net/json` servizio del DFAE. Questo servizio può rispondere in modo diverso a seconda della versione del DFAE in uso. Con la versione 1.5 dell’integrazione DFAE:

   * Reindirizzamento HTTP 302 a [!DNL ad.doubleclick.net]. Verrà inviata una posizione: nella risposta che contiene informazioni sul visitatore dell&#39;annuncio.
   * Questo tag Location causa il reindirizzamento a [!DNL integrate.112.2o7.net/dfa_echo]. Questo servizio traduce le informazioni sul visitatore dell&#39;annuncio in una stringa codificata JSON (JavaScript Object Notati on). Questi dati vengono restituiti con una risposta HTTP di 200 OK.

* Con l&#39;integrazione DFA versione 2.0 (Advanced Ad Serving enabled):

   * [!DNL fls.doubleclick.net] risponderà direttamente con 200 OK.

In entrambi i casi, una richiesta corretta darà luogo a una richiesta ai server di raccolta dati Adobe che contengono il parametro vX, dove X è il numero eVar View-Through. Questo valore di parametro assume la forma: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Questa stringa contiene i dati sull’ultimo clic e l’ultima impressione per il visitatore corrente.

## Tuning s.maxDelay{#tuning-s-maxdelay}

Per ottenere una corretta implementazione DFA è necessario ottimizzare s.maxDelay per il sito specifico.

In generale, la decisione di aumentare o diminuire *`s.maxDelay`* comporta un compromesso tra l’ottenimento di più dati visitatore DFA e la raccolta dei dati dei visitatori Adobe in pericolo. Aumentando *`s.maxDelay`* ottiene più dati visitatore DFA, ma (inseriti eccessivamente alti) potrebbe compromettere la raccolta dei dati visitatore Adobe. La riduzione di s.maxDelay assicura la raccolta dei dati dei visitatori Adobe, ma potrebbe perdere i dati dei visitatori DFA.

*`s.maxDelay`* incapsula più del semplice tempo di comunicazione in rete per contattare il DFAE; rappresenta anche i ritardi del browser per attivare e valutare il codice JavaScript da cui si basano tali comunicazioni. Questo perché il modulo Integrate avvia il *`s.maxDelay`* timer dopo che ha inserito l&#39;elemento HTML nel DOM che estrae i dati dal server DFA Floodlight. Il tempo necessario affinché il browser avvii effettivamente la richiesta HTTP in base a questo nuovo elemento HTML varia in base ad altre immagini o file JavaScript che vengono caricati contemporaneamente, alla velocità del computer dei visitatori e a specifiche implementazioni del browser. Inoltre, quando i dati JSON vengono recuperati dal server DFA Floodlight, JavaScript deve essere valutato dal browser. Anche questa operazione è controllata completamente dal browser e può essere ritardata in caso di grandi quantità di codice JavaScript in esecuzione simultanea o di molte richieste JavaScript asincrone.

A tal fine, *`s.maxDelay`* è necessario impostare la pagina di destinazione in base alla complessità della pagina e al ritardo della rete con il DFAE. In alcuni siti, un modo possibile per ridurre la complessità consiste nell&#39;attivare il codice di raccolta Adobe all&#39;inizio del caricamento della pagina, in modo che il browser non venga utilizzato al momento della richiesta del server Floodlight.

La variabile Timeout è assolutamente necessaria durante l&#39;ottimizzazione *`s.maxDelay`*, perché viene incrementata ogni volta che viene raggiunto il timeout s.maxDelay. Per decidere se aumentare o diminuire *`s.maxDelay`* consigliamo di seguire questo processo:

1. Raccogliere diversi giorni di dati con *`s.maxDelay`* un valore particolare.
1. Eseguire un [!DNL Daily Unique Visitors Report] intervallo di tempo.
1. Eseguite il comando [!DNL Timeout Event Report] per controllare il numero di timeout che stanno arrivando. Ricorda che un timeout viene raccolto solo una volta per ogni visitatore.

Ora con le cifre in mano, calcolare

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

La percentuale di timeout sta prendendo in considerazione tutti i visitatori del sito. Alcuni di questi visitatori non sarebbero stati legati al DFAE, quindi il timeout è fuorviante. Per migliorare questo calcolo, un&#39;altra analisi potrebbe considerare solo i visitatori univoci nelle pagine con il `clickThroughParam` set (ad esempio, `?CID=1`). Questo mostrerà più precisione.

Se la percentuale di timeout è molto bassa, prendete in considerazione la riduzione *`s.maxDelay`*. Se è molto alto, aumentare *`s.maxDelay`*. In caso di diminuzione, *`s.maxDelay`* si desidera ripetere l&#39;operazione per [!DNL Timeout Report] garantire che i timeout non siano aumentati drasticamente. Con *`s.maxDelay`* l&#39;aumento, è necessario eseguire un&#39;operazione [!DNL Page Views Report] per verificare che le visualizzazioni delle pagine non risultino compromesse a causa della perdita di dati. Ogni volta *`s.maxDelay`* viene modificato osservano i dati per diversi giorni al fine di garantire che i dati rappresentino una tendenza, e non solo una fluttuazione giornaliera.

L’impostazione ottimale per *`s.maxDelay`* è il punto in cui la percentuale di timeout viene ridotta a icona mentre le visualizzazioni pagina non vengono eliminate.

I timeout dovrebbero diminuire quando si passa alla versione 2.0 dell&#39;integrazione, a causa delle eliminazioni dei reindirizzamenti 302. Le prime scoperte con i client beta hanno mostrato una consistente riduzione dei timeout, e quindi la raccolta di più dati DFA

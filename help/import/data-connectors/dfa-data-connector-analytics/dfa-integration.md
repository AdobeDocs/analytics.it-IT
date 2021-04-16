---
description: 'La configurazione dell’integrazione DFA comporta le seguenti attività '
keywords: DFA
title: Integrazione DFA
feature: Data Connectors
uuid: 972a9d62-24fd-4463-a34c-5ec0b926e81e
exl-id: 27eb7789-30a5-4f4a-8b23-06e3625996ec
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '2593'
ht-degree: 1%

---

# Integrazione DFA{#dfa-integration}

La configurazione dell’integrazione DFA prevede le seguenti attività:

## Configurare l’integrazione DFA{#configure-the-dfa-integration}

Integrazione dei Data Connectors DFA.

Le pagine di configurazione forniscono una panoramica dell’integrazione, insieme a collegamenti utili per ulteriori informazioni. A questa integrazione sono associate sia le tariffe Adobe che DoubleClick. Contatta i rappresentanti di vendita appropriati per entrambe le organizzazioni e assicurati di conoscere la struttura delle tariffe.

1. Accedi a [!DNL Adobe Analytics].
1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.

   ![](assets/data_connectors.png)

1. Individua **[!UICONTROL DoubleClick DFA]**, quindi fai clic su **[!UICONTROL Add New]**.

   ![Risultato del passaggio](assets/wizard-01.png)

   In ogni pagina dell&#39;Integrazione guidata, fornire le informazioni richieste, quindi fare clic su **[!UICONTROL Next]**. Nella tabella seguente sono illustrate le informazioni necessarie per completare l’integrazione tramite la procedura guidata.

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
   <td colname="col3"> Il nome dell'integrazione visualizzato nel Genesis nell'elenco di integrazione attiva della suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 1 </td> 
   <td colname="col2"> Indirizzo e-mail integrazione </td> 
   <td colname="col3"> Indirizzo e-mail che riceve tutte le notifiche relative a questa integrazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Nome utente </td> 
   <td colname="col3"> Nome utente dell’API DFA da utilizzare con questa integrazione. Per abilitare un utente all’accesso API, controlla l’attributo API nell’interfaccia DFA. Dopo aver abilitato l’accesso API, viene visualizzato un campo password per fornire una password all’utente. Questa password viene immessa insieme al nome utente nella procedura guidata per l'autenticazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> Password </td> 
   <td colname="col3"> Password dell’API DFA. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2 </td> 
   <td colname="col2"> ID inserzionista </td> 
   <td colname="col3"> <p>L’ID dell’inserzionista DFA o l’ID di configurazione del flodlight principale. Data Connectors utilizza questo ID per identificare l’inserzionista DFA da monitorare (versione 1.5 dell’integrazione). Questo ID inserzionista non viene utilizzato nella versione 2.0 dell’integrazione - l’ID di configurazione del flusso padre verrà cercato e utilizzato. Vedere le istruzioni sullo schermo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 3 </td> 
   <td colname="col2"> Variabile annuncio DFA </td> 
   <td colname="col3"> L’eVar di Analytics che riceve l’attributo della campagna DFA, le impression e i dati di clic. In genere si tratta dell’eVar del codice di tracciamento ( <span class="varname"> s.campaign </span>), ma è possibile scegliere qualsiasi eVar disponibile. I Data Connectors aggiungono inoltre le seguenti classificazioni relative al DFA all’eVar selezionato: <p><b>Campagne</b>: Una raccolta di annunci serviti a più siti che includono messaggi comuni. </p> <p><b>Nome</b> sito: Il sito in cui è stato servito l’annuncio. </p> <p><b>Nome</b> annuncio: Il nome dell’annuncio, come definito nel tuo account DFA. </p> <p><b>Nome</b> del posizionamento del sito: Il sito Web e la pagina in cui è stato servito l’annuncio. </p> <p><b>Strumento</b> di consegna: Fare doppio clic per gli inserzionisti. </p> <p><b>Canale</b>: Annuncio banner. </p> <p><b>Struttura</b> dei costi: CPM, CPC o Fisso, in base alla struttura dei costi dell’annuncio. </p> <p><b>Nome</b> creativo: Nome del creativo associato a un ID annuncio/posizionamento/creativo. </p> <p><b>DFA &gt; Deduplicazione</b> SearchCenter: Specifica che DFA deve inserire valori nelle variabili del Centro di ricerca quando si verificano click-through DFA o View-through.  </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Impression </td> 
   <td colname="col3"> L’evento personalizzato che riceve i dati della metrica Impression DFA. Impression indica il numero di volte in cui l’annuncio è stato servito. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 4 </td> 
   <td colname="col2"> Clic </td> 
   <td colname="col3"> Seleziona l’evento personalizzato che riceve i dati della metrica Clic DFA. I clic indicano il numero di volte in cui i visitatori hanno fatto clic sull’annuncio, misurato dal reindirizzamento del DFA. La metrica Clic è correlata alla metrica Click-through di Analytics. <p>Nota:  I clic DFA e i click-through di Analytics potrebbero non corrispondere esattamente a causa delle differenze nella modalità di raccolta dei dati.  </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Variabile view-through </td> 
   <td colname="col3"> <p>L’eVar Analytics che riceve i dati di visualizzazione through DFA. La variabile View-Through consente di vedere in che modo le visualizzazioni influiscono sui tassi di conversione sul sito. </p> <p>I Data Connectors aggiungono a questo eVar le stesse classificazioni relative a DFA che a DFA Ad Variable (vedi sopra). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> Time Since Last View (variabile del periodo fisso di visualizzazione) </td> 
   <td colname="col3"> L’eVar di Analytics che riceve i dati DFA Time Since Last View (Ora DFA dall’ultima visualizzazione). La visualizzazione Ora dall’ultima visualizzazione indica il periodo di tempo trascorso dall’ultima visualizzazione dell’annuncio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 5 </td> 
   <td colname="col2"> View-Throughs </td> 
   <td colname="col3"> L’evento personalizzato che riceve i dati della metrica Visualizzazione DFA attraverso . Utilizza l’evento View-Throughs con la variabile View-Through per vedere quali campagne non hanno influenzato un click-through diretto, ma possono aver avuto un ruolo nell’indirizzare il traffico verso il sito in un momento successivo. <p>I Data Connectors rinomina l’evento personalizzato selezionato in "Visualizza attraverso". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Errore di query DFA </td> 
   <td colname="col3"> (Facoltativo) L'eVar di Analytics che riceve tutti i codici di messaggio per errore di query DFA segnalati. I codici di messaggio DFA possibili sono: 
    <ul id="ul_85FC7FB19F7F4ADF83ABCA6DDB44CE19"> 
     <li id="li_0A3181DED5A149588A0D3F1584E2FE8B"><b>nc</b>: Nessun cookie DoubleClick. </li> 
     <li id="li_D397AA73AD5E4086A18B87F271E4EC14"><b>oo</b>: Utente ha rinunciato. </li> 
     <li id="li_5AC1D0C8049340B4AD857D88E275CBD6"><b>nh</b>: Nessuna cronologia delle campagne. </li> 
     <li id="li_73A8C5E905C54E2BB531A1FCDBC6AA1A"><b>qe</b>: Errore di query (timeout, inattività del server, ecc.) </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 6 </td> 
   <td colname="col2"> Evento timeout </td> 
   <td colname="col3"> <p>L’evento del contatore di Analytics che viene incrementato ogni volta che scade il timer <span class="varname"> s.maxDelay </span> e dai server DFA non è stata ricevuta alcuna risposta. Usa questo evento per configurare la variabile <span class="varname"> s.maxDelay </span> Tuning s.maxDelay </a>.) </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aggiornamenti del sito web per l&#39;integrazione DFA{#web-site-updates-for-the-dfa-integration}

Una volta che Genesis ha configurato la suite di rapporti di Analytics per l’integrazione DFA, è necessario effettuare le seguenti operazioni per configurare il sito Web e l’ambiente DFA per supportare l’integrazione:

### Verifica lo spazio dei cookie sul dominio{#verify-cookie-space-on-the-domain}

L’integrazione dei Data Connectors per DFA richiede di impostare un cookie sul dominio della pagina.

Anche se raramente, alcuni domini hanno raggiunto la capacità massima dei cookie per alcuni browser web. Per evitare di influenzare l’esperienza di navigazione di un visitatore sul sito Web, consulta le operazioni di rete, il team di sviluppo o il gruppo di tecnici per verificare che l’aggiunta di un altro cookie al dominio delle pagine utilizzate per l’integrazione DFA non influisca sull’esperienza utente. Sarà inoltre necessario selezionare un nome per il cookie.

### Aggiorna il parametro DFA Query-String{#update-your-dfa-query-string-parameter}

Se hai già effettuato il tracciamento delle campagne pubblicitarie con Adobe Analytics prima dell’integrazione DFA, è possibile che tutte le campagne (e-mail, ricerca o banner) utilizzino lo stesso parametro della stringa di query per identificare l’ID della campagna di provenienza sulla pagina di destinazione.

Per capire quando richiedere dati di visualizzazione e click-through dai dati DFA per le campagne DFA Ad, i Data Connectors devono identificare quando un visitatore ha fatto clic su un annuncio di un banner della campagna DFA. Per questo motivo, devi aggiungere un parametro di stringa di query differenziato all’URL della pagina di destinazione della campagna DFA Ad in modo che i Data Connectors possano distinguere tra le pagine di campagne DFA Ad e altre pagine di campagne pubblicitarie che potresti avere sul tuo sito Web. Il `dfa_overrideParam` nel plug-in JavaScript utilizzato per DFA.

>[!CAUTION]
>
>Anche se la variabile Campaign può essere utilizzata per altre campagne, non utilizzarla per le campagne DFA. Se imposti la variabile Campaign su una pagina di destinazione della campagna DFA, Adobe non può collegare impression e clic ai click-through di una campagna DFA. Una volta per visita, i server di raccolta Adobe controllano i server DFA per un click-through precedente. Per questo motivo, includi il codice plug-in DFA solo sulle pagine di destinazione comuni per evitare reindirizzamenti non necessari che possano rallentare i tempi di caricamento delle pagine, in particolare per gli utenti con connessioni Internet più lente.

## Aggiorna il codice di raccolta dati del sito Web{#update-your-web-site-s-data-collection-code}

L’integrazione del Genesis per DFA sfrutta l’ID di configurazione DFA Floodlight (dfa_SPOTID), che migliora la coerenza dei rapporti tra il sistema di raccolta dati DFA e Adobe.

>[!NOTE]
>
>Il termine Spotlight è stato modificato in Floodlight in una recente versione di Google DFA. Il parametro JavaScript `dfa_SPOTID` è stato denominato in base alla terminologia Spotlight ma viene utilizzato per entrambe le versioni.

Per abilitare l’integrazione DFA sul sito Web, devi aggiornare il codice di raccolta dati JavaScript aggiungendo quanto segue:

* Modulo integrato per DFA
* Aggiunta del codice di raccolta

### Modulo integrato per DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

L’integrazione DFA sfrutta Adobe Experience Cloud Integrate Module, che aggiunge funzionalità al codice di raccolta dati JavaScript di base ( `s_code.js`). Il modulo Integrate fa parte del file .zip quando scarichi AppMeasurement per il codice Javascript da Code Manager. Contatta il tuo consulente Adobe solo se hai bisogno di ulteriore aiuto per trovarlo.

Inserisci il codice del modulo Integrato nella sezione `Modules` del file `s_code.js` del tuo sito web.

### Aggiunta al codice di raccolta {#section-8f98c727f1ba414fb8b4f02d696b8791}

In base alle selezioni effettuate durante l&#39;attivazione dell&#39;integrazione DFA nell&#39;Integrazione guidata, i Data Connectors generano ed inviano un&#39;aggiunta personalizzata al codice di raccolta dati JavaScript. Inserisci questo codice nella sezione principale del file `s_code.js` (non nella funzione `doPlugins` o in qualsiasi altra funzione).

Il codice di esempio riportato di seguito è solo a scopo illustrativo; utilizzare il codice inviato via e-mail dopo aver completato l&#39;integrazione guidata Data Connectors.

Il codice di raccolta è costituito dai seguenti componenti:

* Impostazioni di integrazione DFA
* Plug-in richiesti per l’integrazione

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

Il blocco delle impostazioni di integrazione DFA imposta le variabili richieste dall’integrazione DFA. I valori di ciascuna di queste variabili provengono dalle seguenti origini:

**CSID**: ID lato client. Generato da DFA una volta completata l&#39;Integrazione guidata. Data Connectors precompila questa variabile con il tuo DFA CS ID e invia anche questo valore nell’e-mail di configurazione dopo aver completato l’Integrazione guidata. Questa variabile non è necessaria se sul tuo account è abilitato Advanced Ad Serving .

**SPOTID**: Configurazione del faro (precedentemente denominato ID riflettore). Data Connectors precompila questa variabile con il tuo ID di configurazione DFA Floodlight, in base alle informazioni dell’account DFA specificate nella procedura guidata di integrazione.

**Evar**: Trasferisci variabile. Data Connectors precompila questa variabile con il nome della variabile di Analytics specificato per la variabile View-Through nella procedura guidata di integrazione. Non modificare questo valore senza un&#39;attenta coordinazione con Adobe Engineering Services o Engineering Services.

**errorEvar**: Variabile di errore. Data Connectors precompila questa variabile con il nome della variabile Analytics specificato per la variabile DFA Query Failure nella procedura guidata di integrazione.

**timeoutEvent**: Evento di timeout. Data Connectors precompila questa variabile con il nome della variabile di Analytics specificato per la variabile Evento di timeout nell&#39;Integrazione guidata.

**requestURL**: Host DFA remoto per eseguire una query per informazioni sugli annunci. Non modificare questo valore a meno che non sia indicato dall&#39;Adobe.

**maxDelay**: Specifica il tempo in millisecondi che il codice di raccolta dati JavaScript attende per una risposta dal server DFA Floodlight. Adobe consiglia di provare questo valore per trovare il valore ottimale in base al traffico del sito. Ad esempio, l’aumento di questo valore generalmente raccoglie più dati DFA, ma aumenta il rischio di perdere i dati del visitatore di base se il visitatore lascia il sito durante il periodo di ritardo. La riduzione di questo valore riduce il rischio di perdita dei dati hit, ma può ridurre la quantità di dati DFA inviati con i dati hit di Adobe.

**visitCookie**: Nome del cookie utilizzato per limitare le chiamate DFA a una volta per visita.

**clickThroughParam**: Una stringa di query, generalmente inclusa in tutti gli annunci, che notifica al modulo Integrate che si è appena verificato un clic. La presenza di questo parametro nella stringa query fa sì che la richiesta si verifichi ai server DFA Floodlight indipendentemente dal fatto che il visitatore sia già stato interrogato negli ultimi 30 minuti.

**newRsidsProp**: (Facoltativo) Mappato a una variabile di proprietà Traffico non utilizzata. L’integrazione DFA raccoglie e memorizza questo valore nel cookie di visita per identificare le suite di rapporti che hanno raccolto i dati per un visitatore specifico. Questa proprietà è necessaria solo con implementazioni personalizzate con i servizi di ingegneria Adobe.

**Plug-in richiesti per l’integrazione**

L’aggiunta del Codice di raccolta incorpora plug-in aggiuntivi che migliorano il funzionamento dell’integrazione DFA:

* Limita le query DFA a una volta per visita
* Offre flessibilità per i nomi dei cookie. Sebbene la maggior parte delle organizzazioni utilizzi s_dfa, puoi utilizzare qualsiasi nome di cookie valido per l’integrazione DFA.
* Elimina i reindirizzamenti non necessari. Poiché i dati view-through vengono raccolti in tempo reale, i server di raccolta Adobe e DFA potrebbero potenzialmente scambiare dati su ogni visualizzazione di pagina. Il plug-in blocca questi scambi di dati quando le informazioni non sono necessarie.

>[!CAUTION]
>
>Uno dei meccanismi utilizzati dal plug-in per eliminare le query DFA non necessarie è un cookie di visita basato su dominio. Una suite di rapporti per l’integrazione che si estende su più domini genera dati click-through e view-through quando i visitatori attraversano più domini dopo un click-through o una visualizzazione influenzata da DFA.

## Conferma di un&#39;integrazione DFA riuscita{#confirming-a-successful-dfa-integration}

Dopo aver effettuato tutti gli aggiornamenti necessari al sito Web, puoi utilizzare un visualizzatore del traffico di rete, come Charles*, Chrome Developer Tools o Firebug*, per confermare che DFA sta comunicando con i server di raccolta di Adobe.

Dopo aver distribuito il file `s_code.js` abilitato per DFA, utilizza il visualizzatore del traffico di rete per visualizzare le richieste tra i server di raccolta dati DFA e Adobe, cercando quanto segue:

* Una richiesta al servizio `fls.doubleclick.net/json` del DFA. Questo servizio può rispondere in modo diverso a seconda della versione di DFA in uso. Con la versione 1.5 dell’integrazione DFA:

   * Un reindirizzamento HTTP 302 a [!DNL ad.doubleclick.net]. Questo invierà una posizione: nella risposta che contiene informazioni sul visitatore dell’annuncio.
   * Questo tag Location (Posizione) causa un reindirizzamento a [!DNL integrate.112.2o7.net/dfa_echo]. Questo servizio traduce le informazioni sul visitatore dell’annuncio in una stringa codificata JSON (JavaScript Object Notati on). Questi dati vengono restituiti con una risposta HTTP da 200 OK.

* Con l’integrazione DFA versione 2.0 (Advanced Ad Serving enabled):

   * [!DNL fls.doubleclick.net] risponderà direttamente con 200 OK.

In entrambi i casi, una richiesta riuscita darà luogo a una richiesta ai server di raccolta dati di Adobe che contiene il parametro vX, dove X è il numero di eVar View-Through. Questo valore di parametro assume la forma di: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX-XXXX Questa stringa contiene i dati relativi all’ultimo clic e all’ultima impression per il visitatore corrente.

## Sintonizzazione s.maxDelay{#tuning-s-maxdelay}

Il successo dell’implementazione DFA comporta l’ottimizzazione di s.maxDelay per il sito specifico.

In generale, la decisione di aumentare o abbassare *`s.maxDelay`* implica un compromesso tra l’ottenimento di più dati visitatore DFA e il rischio di raccolta dei dati dei visitatori Adobi. L’incremento di *`s.maxDelay`* ottiene più dati visitatore DFA, ma (posizionati in modo eccessivamente alto) potrebbe mettere a rischio la raccolta di dati visitatore di Adobe. La diminuzione di s.maxDelay assicura la raccolta dei dati dei visitatori di Adobe, ma potrebbe perdere i dati dei visitatori DFA.

*`s.maxDelay`* incapsula più del tempo necessario per la comunicazione in rete per contattare il DFAE; rappresenta anche i ritardi del browser per attivare e valutare il JavaScript da cui si basano queste comunicazioni. Questo perché il modulo Integrate inizia il timer *`s.maxDelay`* dopo aver inserito l’elemento HTML in nel DOM che richiama i dati dal server DFA Floodlight. Il tempo necessario affinché il browser avvii effettivamente la richiesta HTTP basata su questo nuovo elemento HTML varia in base ad altre immagini o file JavaScript che vengono caricati contemporaneamente, alla velocità del computer dei visitatori e a specifiche implementazioni del browser. Inoltre, quando i dati JSON vengono recuperati dal server DFA Floodlight , il JavaScript deve essere valutato dal browser. Anche questo è controllato completamente dal browser e può essere ritardato se ci sono grandi quantità di codice JavaScript in esecuzione simultanea o molte richieste JavaScript asincrone.

A questo scopo, è necessario impostare *`s.maxDelay`* in base alla complessità della pagina di destinazione e alla quantità di ritardo della rete con DFA. Su alcuni siti, un modo possibile per ridurre la complessità è quello di attivare il codice di raccolta Adobe all&#39;inizio del caricamento della pagina, in modo che ci sia meno in corso nel browser al momento in cui viene richiesto il server Floodlight.

La variabile Timeout è assolutamente necessaria quando si sintonizza *`s.maxDelay`*, perché viene incrementata ogni volta che si raggiunge il timeout s.maxDelay. Per decidere se aumentare o diminuire *`s.maxDelay`* si consiglia di seguire questo processo:

1. Raccogliere diversi giorni di dati con *`s.maxDelay`* impostato su un valore specifico.
1. Esegui un [!DNL Daily Unique Visitors Report] per l&#39;intervallo di tempo.
1. Esegui il [!DNL Timeout Event Report] per controllare il numero di timeout in arrivo. Ricorda che un timeout viene raccolto solo una volta per visitatore.

Con le cifre in mano, calcolare

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

La percentuale di timeout sta effettivamente prendendo in considerazione tutti i visitatori del sito. Alcuni di questi visitatori non sarebbero stati affatto legati al DFA, quindi il timeout è fuorviante. Per migliorare questo calcolo, un’altra analisi potrebbe considerare solo i visitatori univoci nelle pagine con il set `clickThroughParam` (ad esempio, `?CID=1`). Questo mostrerà una maggiore precisione.

Se la percentuale di timeout è molto bassa, considera la riduzione di *`s.maxDelay`*. Se è molto alto, aumenta *`s.maxDelay`*. Quando diminuisci *`s.maxDelay`*, esegui nuovamente il [!DNL Timeout Report] per garantire che i timeout non siano aumentati drasticamente. Quando si aumenta *`s.maxDelay`*, è necessario eseguire un [!DNL Page Views Report] per assicurarsi che le visualizzazioni di pagina non stiano scadendo a causa della perdita di dati. Ogni volta che *`s.maxDelay`* viene modificato si osservano i dati per diversi giorni al fine di garantire che i dati rappresentino una tendenza e non solo una fluttuazione giornaliera.

L’impostazione ottimale per *`s.maxDelay`* è il punto in cui la percentuale di timeout viene ridotta a icona mentre le visualizzazioni pagina non vengono rimosse.

I timeout dovrebbero diminuire quando si passa alla versione 2.0 dell’integrazione, a causa delle eliminazioni dei reindirizzamenti 302. I risultati iniziali con i client beta hanno mostrato una consistente riduzione dei timeout, e quindi la raccolta di più dati DFA

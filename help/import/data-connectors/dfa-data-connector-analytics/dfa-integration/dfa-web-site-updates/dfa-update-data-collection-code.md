---
description: L’integrazione di Genesis per il DFA sfrutta l’ID di configurazione DFA Floodlight (dfa_SPOTID), che migliora la coerenza dei rapporti tra il DFA e il sistema di raccolta dei dati Adobe.
keywords: DFAE
seo-description: L’integrazione di Genesis per il DFA sfrutta l’ID di configurazione DFA Floodlight (dfa_SPOTID), che migliora la coerenza dei rapporti tra il DFA e il sistema di raccolta dei dati Adobe.
seo-title: Aggiorna il codice di raccolta dati del sito Web
solution: Analytics
title: Aggiorna il codice di raccolta dati del sito Web
topic: Connettori dati
uuid: a97d1b62-f883-48b1-9516-4f889e701901
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Aggiorna il codice di raccolta dati del sito Web{#update-your-web-site-s-data-collection-code}

L’integrazione di Genesis per il DFA sfrutta l’ID di configurazione DFA Floodlight (dfa_SPOTID), che migliora la coerenza dei rapporti tra il DFA e il sistema di raccolta dei dati Adobe.

>[!NOTE]
>
>Il termine Spotlight è stato modificato in Floodlight in una recente release di Google DFA. Il parametro JavaScript `dfa_SPOTID` è stato denominato in base alla terminologia Spotlight, ma viene utilizzato per entrambe le versioni.

Per abilitare l'integrazione DFA sul sito Web, è necessario aggiornare il codice di raccolta dati JavaScript aggiungendo quanto segue:

* Modulo integrato per DFA
* Aggiunta al codice della raccolta

## Modulo integrato per DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

L’integrazione DFA sfrutta il modulo Adobe Experience Cloud Integrate, che aggiunge funzionalità al codice di raccolta dati JavaScript di base ( `s_code.js`). Il modulo Integrate fa parte del file .zip quando si scarica il codice AppMeasurement per JavaScript da [Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html). Contatta il tuo Adobe Consultant solo se hai bisogno di ulteriore aiuto per trovarla.

Inserite il codice Modulo integrato nella `Modules` sezione del `s_code.js` file del sito Web.

## Aggiunta al codice della raccolta {#section-8f98c727f1ba414fb8b4f02d696b8791}

In base alle selezioni effettuate durante l'attivazione dell'integrazione DFA nella procedura guidata di integrazione, i Connettori dati generano ed inviano tramite e-mail un'aggiunta personalizzata al codice di raccolta dati JavaScript. Inserire questo codice nella sezione principale del `s_code.js` file (non nella `doPlugins` funzione o in qualsiasi altra funzione).

Il codice di esempio riportato di seguito è solo a scopo illustrativo; utilizzare il codice che ti è stato inviato via e-mail dopo aver completato l'Integrazione guidata Connettori dati.

Il codice della raccolta è costituito dai seguenti componenti:

* Impostazioni di integrazione DFA
* Plug-in richiesti per l'integrazione

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

**CSID**: ID lato client. Generato dal DFA una volta completata l'Integrazione guidata. Connettori dati precompila questa variabile con il tuo DFA CS ID e invia anche questo valore nel messaggio e-mail di configurazione dopo il completamento dell'Integrazione guidata. Questa variabile non è necessaria se sul vostro account è abilitato Advanced Ad Serving.

**SPOTID**: Configurazione di Floodlight (precedentemente denominato Spotlight ID). I Connettori dati precompilano questa variabile con l’ID di configurazione DFA Floodlight, in base alle informazioni sull’account DFA specificate nella procedura guidata di integrazione.

**Evar**: Variabile di trasferimento. Connettori dati precompila questa variabile con il nome della variabile Analytics specificato per la variabile View-Through nella procedura guidata di integrazione. Non modificate questo valore senza un'attenta coordinazione con Adobe Engineering o Engineering Services.

**errorEvar**: Variabile di errore. Connettori dati precompila questa variabile con il nome della variabile Analytics specificato per la variabile Errore query DFA nella procedura guidata di integrazione.

**timeoutEvent**: Evento Timeout. Connettori dati precompila questa variabile con il nome della variabile Analytics specificato per la variabile Evento timeout nella procedura guidata di integrazione.

**requestURL**: Host DFA remoto per richiedere informazioni sugli annunci. Non modificate questo valore a meno che non sia richiesto da Adobe.

**maxDelay**: Specifica il tempo in millisecondi che il codice JavaScript di raccolta dati attende una risposta dal server DFA Floodlight. Adobe consiglia di sperimentare questo valore per trovare il valore ottimale in base al traffico del sito. Ad esempio, se si aumenta questo valore, in genere vengono raccolti più dati DFA, ma aumenta il rischio di perdere i dati del visitatore di base se il visitatore lascia il sito durante il periodo di ritardo. Riducendo questo valore si riduce il rischio di perdita di dati hit, ma si può ridurre la quantità di dati DFA inviati con i dati hit Adobe.

**visitCookie**: Nome del cookie utilizzato per limitare le chiamate DFA a una volta per visita.

**clickThroughParam**: Una stringa di query, solitamente inclusa in tutti gli annunci, che notifica al modulo Integrate che si è appena verificato un clic. La presenza di questo parametro nella stringa di query determina l'esecuzione della richiesta ai server DFA Floodlight, indipendentemente dal fatto che il visitatore sia già stato interrogato negli ultimi 30 minuti.

**newRsidsProp**: (Facoltativo) Mappata a una variabile della proprietà Traffico non utilizzata. L’integrazione DFAE raccoglie e memorizza questo valore nel cookie della visita per identificare le suite di rapporti che hanno raccolto i dati per un particolare visitatore. Questa proprietà è necessaria solo con le implementazioni personalizzate con i servizi tecnici Adobe.

**Plug-in richiesti per l'integrazione**

L'aggiunta del codice di raccolta include plug-in aggiuntivi che migliorano il funzionamento dell'integrazione DFAE:

* Limita le query DFA a una sola visita
* Offre flessibilità per il nome dei cookie. Anche se la maggior parte delle organizzazioni utilizza s_dfa, è possibile utilizzare qualsiasi nome di cookie valido per l'integrazione DFA.
* Elimina i reindirizzamenti non necessari. Poiché i dati di visualizzazione vengono raccolti in tempo reale, i server di raccolta Adobe e il DFA potrebbero potenzialmente scambiare dati su ogni visualizzazione di pagina. Il plug-in blocca questi scambi di dati quando le informazioni non sono necessarie.

>[!CAUTION]
>
>Uno dei meccanismi utilizzati dal plug-in per eliminare le query DFA non necessarie è un cookie di visita basato su dominio. Una suite di rapporti per l'integrazione che si estende su più domini aumenta i dati di click-through e visualizzazione through quando i visitatori attraversano più domini dopo una visualizzazione o un click-through influenzati dal DFA.


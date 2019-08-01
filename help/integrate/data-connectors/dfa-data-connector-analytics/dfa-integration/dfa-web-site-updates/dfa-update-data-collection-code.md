---
description: L'integrazione Genesis per DFA sfrutta l'ID di configurazione DFA floodlight (dfa_ SPOTID), che migliora la coerenza dei report tra il sistema di raccolta dati DFA e Adobe.
keywords: DFA
seo-description: L'integrazione Genesis per DFA sfrutta l'ID di configurazione DFA floodlight (dfa_ SPOTID), che migliora la coerenza dei report tra il sistema di raccolta dati DFA e Adobe.
seo-title: Aggiornare il codice di raccolta dati del sito Web
solution: Analytics
title: Aggiornare il codice di raccolta dati del sito Web
topic: Connettori dati
uuid: a 97 d 1 b 62-f 883-48 b 1-9516-4 f 889 e 701901
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Update Your Web Site's Data Collection Code{#update-your-web-site-s-data-collection-code}

L'integrazione Genesis per DFA sfrutta l'ID di configurazione DFA floodlight (dfa_ SPOTID), che migliora la coerenza dei report tra il sistema di raccolta dati DFA e Adobe.

>[!NOTE]
>
>Il termine Spotlight è stato cambiato in Floodlight in una versione recente di Google DFA. The JavaScript parameter `dfa_SPOTID` was named based on the Spotlight terminology but is used for both versions.

Per abilitare l'integrazione DFA sul sito Web, devi aggiornare il codice di raccolta dati javascript aggiungendo quanto segue:

* Integrare modulo per DFA
* Aggiunta al codice di raccolta

## Integrate Module for DFA {#section-fa00e42a732a4e27a4ab3dfcfeae1a5b}

The DFA integration leverages the Adobe Marketing Cloud Integrate Module, which adds functionality to your core JavaScript data collection code ( `s_code.js`). The Integrate Module comes as part of the .zip file when you download the AppMeasurement for Javascript code from the [Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html). Contatta il tuo Adobe Consulente solo se hai bisogno di ulteriore assistenza per trovarlo.

Insert the Integrate Module code in the `Modules` section of your website's `s_code.js` file.

## Addition to Your Collection Code {#section-8f98c727f1ba414fb8b4f02d696b8791}

In base alle selezioni effettuate quando si attiva l'integrazione DFA nella procedura guidata Integrazione, i connettori dati generano e invia via e-mail un'aggiunta personalizzata al codice di raccolta dati javascript. Insert this code in the main section of the `s_code.js` file (not in the `doPlugins` function or any other function).

Il codice di esempio mostrato di seguito è solo per illustrazione; utilizzare il codice inviato via e-mail dopo aver completato la procedura guidata Integrazione dei connettori dati.

Il codice di raccolta è costituito dai seguenti componenti:

* Impostazioni integrate DFA
* Plug-in necessari per l'integrazione

**Impostazioni integrate DFA**

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

Il blocco impostazioni DFA integra le variabili richieste dall'integrazione DFA. I valori per ciascuna di queste variabili provengono dalle origini seguenti:

**CSID**: ID lato client. Generata da DFA una volta completata la procedura guidata Integrazione. I Connettori dati precompilano questa variabile con l'ID DFA CS e ti inviano anche questo valore nell'e-mail di configurazione dopo aver completato la procedura guidata Integrazione. Questa variabile non è necessaria se l'opzione Ad Serving Server è abilitata sul vostro account.

**SPOTID**: Configuration Dlight Configuration (in precedenza denominato Spotlight ID). I Connettori dati precompilano questa variabile con l'ID di configurazione DFA floodlight, in base alle informazioni sull'account DFA specificate nella procedura guidata Integrazione.

**Tevar**: Trasferimento variabile. I Connettori dati precompilano questa variabile con il nome della variabile Analytics specificato per la variabile View-Through nella procedura guidata Integrazione. Non modificatelo senza un particolare coordinamento con Adobe Engineering o Engineering Services.

**Errorevar**: Variabile errore. I Connettori dati precompilano questa variabile con il nome della variabile Analytics specificato per la variabile Query Query Failure (Errore DFA) nella procedura guidata Integrazione.

**Timeoutevent**: Evento Timeout. I Connettori dati precompilano questa variabile con il nome della variabile Analytics specificato per la variabile Evento Timeout nella procedura guidata Integrazione.

**Requesturl**: L'host remoto DFA per richiedere informazioni sull'annuncio. Non modificate questo valore, se richiesto da Adobe.

**Maxdelay**: Specifica il tempo di attesa del codice di raccolta dati javascript per una risposta dal server DFA Floodlight, in millisecondi. Adobe consiglia di sperimentare con questo valore per trovare il valore ottimale basato sul traffico del sito. Ad esempio, l'aumento di questo valore raccoglie in genere più dati DFA, ma aumenta il rischio di perdere i dati dei visitatori di base se il visitatore lascia il sito durante il periodo di ritardo. La riduzione di questo valore riduce il rischio di perdita dei dati di hit, ma può ridurre la quantità di dati DFA inviati con i dati di hit Adobe.

**Visitcookie**: Il nome del cookie utilizzato per limitare le chiamate DFA a una volta per visita.

**Clickthroughparam**: Una stringa di query, generalmente inclusa in tutti gli annunci, che notifica al modulo Integrazione che si è verificato un clic. La presenza di questo parametro nella stringa query causa la richiesta della richiesta ai server DFA Floodlight, indipendentemente dal fatto che il visitatore sia già stato interrogato negli ultimi 30 minuti.

**Newrsidsprop**: (Facoltativo) Mappato su una variabile di proprietà Traffico inutilizzato. L'integrazione DFA raccoglie e memorizza questo valore nel cookie delle visite per identificare le suite di rapporti che raccolgono i dati per un particolare visitatore. Questa proprietà è necessaria solo con le implementazioni personalizzate con i servizi Adobe Engineering.

**Plug-in necessari per l'integrazione**

L'aggiunta del codice raccolta incorpora plug-in aggiuntivi che migliorano il funzionamento dell'integrazione DFA:

* Limita le query DFA a una volta per visita
* Fornisce flessibilità dei nomi dei cookie. Sebbene la maggior parte delle organizzazioni utilizzino s_ dfa, puoi utilizzare qualsiasi nome di cookie valido per l'integrazione DFA.
* Elimina i reindirizzamenti inutili. Dato che i dati di visualizzazione vengono raccolti in tempo reale, i server di raccolta Adobe e DFA potrebbero scambiare dati in ogni visualizzazione di pagina. Il plug-in blocca questi scambi di dati quando le informazioni non sono necessarie.

>[!CAUTION]
>
>Uno dei meccanismi utilizzati dal plug-in per eliminare query DFA non necessarie è un cookie per visita basato su dominio. Una suite di rapporti per l'integrazione che si espande su più domini aumenta i dati click-through e view-through quando i visitatori attraversano i domini dopo una vista-through o click-through influenzati da DFA.


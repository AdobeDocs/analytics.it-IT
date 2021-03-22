---
title: getTimeBetweenEvents
description: Misura il tempo tra due eventi.
translation-type: tm+mt
source-git-commit: e8c6f4bbc72f7edfd966d698b8e4678e5eaa739e
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 0%

---


# Plug-in di Adobe: getTimeBetweenEvents

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `getTimeBetweenEvents` consente di tenere traccia del periodo di tempo tra due eventi di Analytics, inclusi carrello acquisti ed eventi personalizzati. È utile per tenere traccia del tempo necessario al completamento di un processo di pagamento o di qualsiasi altro processo che si desidera misurare. Questo plug-in non è necessario se non disponi di processi di conversione che desideri misurare quanto tempo impiegano.

## Installare il plug-in utilizzando l’estensione Adobe Experience Platform Launch

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza getTimeBetweenEvents
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato di Launch

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi il [!UICONTROL Configure tracking using custom code] pannello a soffietto, che mostra il pulsante [!UICONTROL Open Editor] .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/* Adobe Consulting Plugin: getTimeBetweenEvents v3.0 (AppMeasurement highly recommended) */
function getTimeBetweenEvents(ste,rt,stp,res,cn,etd,fmt,bml,rte){var v=ste,B=rt,x=stp,C=res,k=cn,m=etd,E=fmt,F=bml,p=rte;if("-v"===v)return{plugin:"getTimeBetweenEvents",version:"3.0"};var q=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();if("undefined"!==typeof q&&(q.contextData.getTimeBetweenEvents="3.0",window.cookieWrite=window.cookieWrite||function(c,b,d){if("string"===typeof c){var n=window.location.hostname,f=window.location.hostname.split(".").length-1;if(n&&!/^[0-9.]+$/.test(n)){f=2<f?f:2;var l=n.lastIndexOf(".");if(0<=l){for(;0<=l&&1<f;)l=n.lastIndexOf(".",l-1),f--;l=0<l?n.substring(l):n}}g=l;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var e=new Date;e.setTime(e.getTime()+6E4*d)}else e=d;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+e.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof window.cookieRead)?window.cookieRead(c)===b:!1}},window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,d=b.indexOf(" "+c+"="),e=0>d?d:b.indexOf(";",d);return(c=0>d?"":decodeURIComponent(b.substring(d+2+c.length,0>e?b.length:e)))?c:""},window.formatTime=window.formatTime||function(c,b,d){function e(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(!("undefined"===typeof c||isNaN(c)||0>Number(c))){var f="";"string"===typeof b&&"d"===b||("string"!==typeof b||!e("h,m,s",b))&&86400<=c?(b=86400,f="days",d=isNaN(d)?1:b/(d*b)):"string"===typeof b&&"h"===b||("string"!==typeof b||!e("m,s",b))&&3600<=c?(b=3600,f="hours",d=isNaN(d)?4:b/(d*b)):"string"===typeof b&&"m"===b||("string"!==typeof b||!e("s",b))&&60<=c?(b=60,f="minutes",d=isNaN(d)?2:b/(d*b)):(b=1,f="seconds",d=isNaN(d)?.2:b/d);f=Math.round(c*d/b)/d+" "+f;0===f.indexOf("1 ")&&(f=f.substring(0,f.length-1));return f}},window.inList=window.inList||function(c,b,d,e){if("string"!==typeof b)return!1;if("string"===typeof c)c=c.split(d||",");else if("object"!==typeof c)return!1;d=0;for(a=c.length;d<a;d++)if(1==e&&b===c[d]||b.toLowerCase()===c[d].toLowerCase())return!0;return!1},"string"===typeof v&&"undefined"!==typeof B&&"string"===typeof x&&"undefined"!==typeof C)){k=k?k:"s_tbe";m=isNaN(m)?1:Number(m);var r=!1,t=!1,y=v.split(","),z=x.split(",");p=p?p.split(","):[];for(var u=window.cookieRead(k),w,D=new Date,A=D.getTime(),h=new Date,e=0;e<p.length;++e)if(window.inList(q.events,p[e])){h.setDate(h.getDate()-1);window.cookieWrite(k,"",h);return}h.setTime(h.getTime()+864E5*m);for(e=0;e<y.length&&!r&&(r=window.inList(q.events,y[e]),!0!==r);++e);for(e=0;e<z.length&&!t&&(t=window.inList(q.events,z[e]),!0!==t);++e);1===y.length&&1===z.length&&v===x&&r&&t?(u&&(w=(A-u)/1E3),window.cookieWrite(k,A,m?h:0)):(!r||1!=B&&u||window.cookieWrite(k,A,m?h:0),t&&u&&(w=(D.getTime()-u)/1E3,!0===C&&(h.setDate(h.getDate()-1),window.cookieWrite(k,"",h))));return w?window.formatTime(w,E,F):""}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `getTimeBetweenEvents` utilizza i seguenti argomenti:

* **`ste`** (obbligatorio, stringa): Avvia gli eventi timer. Una stringa delimitata da virgole di eventi di Analytics per &quot;avviare il timer&quot;.
* **`rt`** (obbligatorio, booleano): Riavvia l&#39;opzione del timer. Impostare su `true` se si desidera riavviare il timer ogni volta che la variabile `events` contiene un evento timer di avvio. Impostare su `false` se non si desidera che il timer si riavvii quando viene visualizzato un evento timer di avvio.
* **`stp`** (obbligatorio, stringa): Arresta gli eventi timer. Una stringa delimitata da virgole di eventi di Analytics che &quot;interrompe il timer&quot;.
* **`res`** (obbligatorio, booleano): Opzione Ripristina timer. Impostare su `true` se si desidera registrare l&#39;ora dall&#39;avvio del timer E reimpostare il timer dopo l&#39;arresto. Impostare su `false` se si desidera registrare l&#39;ora ma non arrestare il timer. Se è impostato su `false`, il timer continua a essere eseguito dopo che la variabile eventi registra un evento di arresto.

   >[!TIP]
   >
   >Se si imposta questo argomento su `false`, si consiglia vivamente di impostare l&#39;argomento `rte` riportato di seguito.
* **`cn`** (facoltativo, stringa): Il nome del cookie in cui viene memorizzata l&#39;ora del primo evento. Predefinito su `"s_tbe"`.
* **`etd`** (facoltativo, numero intero): Il tempo di scadenza del cookie in giorni. Imposta su `0` per scadere alla fine della sessione del browser. Se non è impostato, viene impostato su 1 giorno.
* **`fmt`** (facoltativo, stringa): Il formato dell&#39;ora in cui viene restituito il numero di secondi (impostazione predefinita: nulla)
   * `"s"` per secondi
   * `"m"` per minuti
   * `"h"` per ore
   * `"d"` per giorni
   * Se non è impostato, il formato del valore restituito si basa sulle regole seguenti:
      * Qualsiasi valore inferiore a un minuto viene arrotondato al valore di riferimento più vicino di 5 secondi. Ad esempio, 10 secondi, 15 secondi
      * Qualsiasi valore compreso tra un minuto e un&#39;ora viene arrotondato al valore di riferimento più vicino di 1/2 minuti. Ad esempio, 30,5 minuti e 31 minuti
      * Qualsiasi valore compreso tra un’ora e un giorno viene arrotondato al valore di riferimento di trimestre più vicino. Ad esempio, 2,25 ore, 3,5 ore
      * Qualsiasi valore maggiore di un giorno viene arrotondato al valore di riferimento del giorno più vicino. Ad esempio, 1 giorno, 3 giorni, 9 giorni
* **`bml`** (facoltativo, numero): Lunghezza del valore di riferimento per l&#39;arrotondamento in base al formato dell&#39; `fmt` argomento. Ad esempio, se l’argomento `fmt` è `"s"` e questo argomento è `2`, il valore restituito viene arrotondato al valore di riferimento più vicino di 2 secondi. Se l&#39;argomento `fmt` è `"m"` e questo argomento è `0.5`, il valore restituito viene arrotondato al valore di riferimento di mezzo minuto più vicino.
* **`rte`** (facoltativo, stringa): Stringa delimitata da virgole degli eventi di Analytics che rimuovono o eliminano il timer. Non ha valore predefinito.

Una chiamata a questo metodo restituisce un numero intero che rappresenta il periodo di tempo tra l&#39;evento del timer di avvio e l&#39;evento del timer di arresto nel formato desiderato.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...è configurato in modo da comportarsi come segue:

* Il timer si avvia quando s.events contiene event1.
* Il timer si riavvia ogni volta che s.events contiene event1
* Il timer si interrompe quando s.events contiene event2
* Il timer viene reimpostato (ovvero passa a 0 secondi) ogni volta che s.events contiene event2
* Il timer viene reimpostato anche quando s.events contiene event3 O se il visitatore chiude il browser
* Quando si registra un tempo effettivo tra event1 e event2, il plug-in imposta eVar1 in modo uguale al numero di secondi tra i due eventi impostati, arrotondato al valore di riferimento più vicino (ad esempio 0 secondi, 2 secondi, 4 secondi, 10 secondi, 184 secondi, ecc.)
* Se s.events contiene event2 prima dell&#39;avvio di un timer, eVar1 non verrà impostato affatto.

### Esempio n. 3

Codice seguente...

```js
s.eVar1 = getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...è configurato in modo da comportarsi come segue:

* Il timer si avvia quando s.events contiene event1.
* Il timer NON si riavvia ogni volta che s.events contiene event1, ma il timer originale continua a funzionare
* Il timer NON si interrompe quando s.events contiene event2, ma il plug-in registra l&#39;ora dalla registrazione dell&#39;impostazione originale event1
* Il timer viene memorizzato in un cookie denominato &quot;s_20&quot;
* Il timer viene reimpostato solo quando s.events contiene event3 OR se sono trascorsi 20 giorni dall&#39;avvio del timer
* Quando viene registrato un intervallo tra (l&#39;originale) event1 e event2, il plug-in imposta eVar1 in modo pari al numero di ore tra i due eventi impostati, arrotondato al valore di riferimento di 1/2 ore più vicino (ad esempio 0 ore, 1,5 ore, 3 ore, 7,5 ore, 478,5 ore, ecc.)

### Esempio n. 3

Codice seguente...

```js
s.eVar1 = getTimeBetweenEvents("event1", true, "event2", true);
```

...produrrà risultati simili al primo esempio di cui sopra; tuttavia, il valore di eVar1 viene restituito in secondi, minuti, ore o giorni, a seconda della lunghezza finale del timer.  Inoltre, il timer scade 1 giorno dopo che è stato impostato per la prima volta invece che al momento in cui il visitatore chiude il browser.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.1 (26 maggio 2018)

* Riprende le modifiche apportate alla nuova versione del plug-in `formatTime`.

### 2.0 (6 aprile 2018)

* Riscrittura/rianalisi completa del plug-in.

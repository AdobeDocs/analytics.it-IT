---
title: getTimeBetweenEvents
description: Misurare il tempo tra due eventi.
translation-type: tm+mt
source-git-commit: a492de4ccbcd6f3f8ca81c9fecbcca4780e0f589
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 0%

---


#  plug-in di Adobe: getTimeBetweenEvents

>[!IMPORTANT]
>
>Questo plug-in è fornito da  Adobe Consulting come una cortesia per aiutarvi a ottenere più valore da  Adobe Analytics. &#39;Assistenza clienti di Adobe non fornisce supporto con questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getTimeBetweenEvents` plug-in consente di tenere traccia del tempo trascorso tra due eventi Analytics , inclusi gli eventi del carrello e personalizzati. È utile per tenere traccia del tempo necessario al completamento di un processo di checkout o di qualsiasi altro processo da misurare. Questo plug-in non è necessario se non si dispone di processi di conversione che si desidera misurare quanto tempo impiegano.

## Installare il plug-in utilizzando l&#39;estensione Adobe Experience Platform Launch 

 Adobe offre un&#39;estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in Analytics  comuni
   * Tipo azione: Initialize getTimeBetweenEvents
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe Analytics .
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche nell’estensione Analytics .

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata un&#39;istanza dell&#39;oggetto di tracciamento Analytics  (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenendo i commenti e i numeri di versione del codice nell’implementazione,  Adobe può risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeBetweenEvents v2.1 (Requires formatTime and inList plug-ins) */
s.getTimeBetweenEvents=function(ste,rt,stp,res,cn,etd,fmt,bml,rte){var s=this;if("string"===typeof ste&&"undefined"!==typeof rt&&"string"===typeof stp&&"undefined"!==typeof res){cn=cn?cn:"s_tbe";etd=isNaN(etd)?1:Number(etd);var f=!1,g=!1,n=!1, p=ste.split(","),q=stp.split(",");rte=rte?rte.split(","):[];for(var h=s.c_r(cn),k,v=new Date,r=v.getTime(),c=new Date,a=0; a<rte.length;++a)s.inList(s.events,rte[a])&&(n=!0);c.setTime(c.getTime()+864E5*etd);for(a=0;a<p.length&&!f&&(f=s.inList(s.events,p[a]),!0!==f);++a);for(a=0;a<q.length&&!g&&(g=s.inList(s.events,q[a]),!0!==g);++a);1===p.length&&1===q.length&&ste===stp&&f&&g?(h&&(k=(r-h)/1E3),s.c_w(cn,r,etd?c:0)):(!f||1!=rt&&h||s.c_w(cn,r,etd?c:0),g&&h&&(k=(v.getTime()-h)/1E3,!0===res&&(n=!0)));!0===n&&(c.setDate( c.getDate()-1),s.c_w(cn,"",c));return k?s.formatTime(k,fmt,bml):""}};

/* Adobe Consulting Plugin: formatTime v1.1 (Requires inList plug-in) */
s.formatTime=function(ns,tf,bml){var s=this;if(!("undefined"===typeof ns||isNaN(ns)||0>Number(ns))){if("string"===typeof tf&&"d"===tf||("string"!==typeof tf||!s.inList("h,m,s",tf))&&86400<=ns){tf=86400;var d="days";bml=isNaN(bml)?1:tf/(bml*tf)} else"string"===typeof tf&&"h"===tf||("string"!==typeof tf||!s.inList("m,s",tf))&&3600<=ns?(tf=3600,d="hours", bml=isNaN(bml)?4: tf/(bml*tf)):"string"===typeof tf&&"m"===tf||("string"!==typeof tf||!s.inList("s",tf))&&60<=ns?(tf=60,d="minutes",bml=isNaN(bml)?2: tf/(bml*tf)):(tf=1,d="seconds",bml=isNaN(bml)?.2:tf/bml);ns=Math.round(ns*bml/tf)/bml+" "+d;0===ns.indexOf("1 ")&&(ns=ns.substring(0,ns.length-1));return ns}};

/* Adobe Consulting Plugin: inList v2.1 */
s.inList=function(lv,vtc,d,cc){if("string"!==typeof vtc)return!1;if("string"===typeof lv)lv=lv.split(d||",");else if("object"!== typeof lv)return!1;d=0;for(var e=lv.length;d<e;d++)if(1==cc&&vtc===lv[d]||vtc.toLowerCase()===lv[d].toLowerCase())return!0;return!1};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getTimeBetweenEvents` metodo utilizza i seguenti argomenti:

* **`ste`** (obbligatorio, stringa): Avviate gli eventi timer. Una stringa delimitata da virgole di eventi  Analytics per &quot;avviare il timer&quot;.
* **`rt`** (obbligatorio, booleano): Riavvia timer. Impostare su `true` se si desidera riavviare il timer ogni volta che la `events` variabile contiene un evento timer di avvio. Impostare su `false` se non si desidera che il timer venga riavviato quando viene visualizzato un evento timer di avvio.
* **`stp`** (obbligatorio, stringa): Arrestate gli eventi timer. Una stringa delimitata da virgole di eventi  Analytics che &quot;arrestano il timer&quot;.
* **`res`** (obbligatorio, booleano): Opzione Reimposta timer. Impostare su `true` se si desidera registrare l&#39;ora dall&#39;avvio del timer E reimpostare il timer dopo l&#39;arresto. Impostare su `false` se si desidera registrare l&#39;ora ma non arrestare il timer. Se impostato su `false`, il timer continua a essere eseguito dopo che la variabile degli eventi ha registrato un evento stop.
   >[!TIP] Se si imposta questo argomento su `false`, è consigliabile impostare l&#39; `rte` argomento seguente.
* **`cn`** (facoltativo, stringa): Il nome del cookie in cui è memorizzata l&#39;ora del primo evento. Il valore predefinito è `"s_tbe"`.
* **`etd`** (facoltativo, numero intero): Tempo di scadenza per il cookie in giorni. Impostato `0` per scadere alla fine della sessione del browser. Il valore predefinito è 1 giorno se non è impostato.
* **`fmt`** (facoltativo, stringa): Formato del tempo in cui viene restituito il numero di secondi (impostazione predefinita: niente)
   * `"s"` in secondi
   * `"m"` per minuti
   * `"h"` per ore
   * `"d"` per giorni
   * Se non è impostato, il formato del valore restituito è basato sulle regole seguenti:
      * Qualsiasi valore inferiore a un minuto viene arrotondato al valore di riferimento di 5 secondi più vicino. Ad esempio, 10 secondi, 15 secondi
      * Qualsiasi valore compreso tra un minuto e un&#39;ora viene arrotondato al valore di riferimento più vicino di 1/2 minuti. Ad esempio, 30,5 minuti, 31 minuti
      * Qualsiasi valore compreso tra un&#39;ora e un giorno viene arrotondato al valore di riferimento del trimestre più vicino. Ad esempio, 2,25 ore, 3,5 ore
      * Qualsiasi valore maggiore di un giorno viene arrotondato al valore di riferimento del giorno più vicino. Ad esempio, 1 giorno, 3 giorni, 9 giorni
* **`bml`** (facoltativo, numero): Lunghezza del parametro di riferimento per l&#39;arrotondamento in base al formato dell&#39; `fmt` argomento. Ad esempio, se l&#39; `fmt` argomento è `"s"` e questo argomento è `2`, il valore restituito viene arrotondato al valore di riferimento di 2 secondi più vicino. Se `fmt` l&#39;argomento è `"m"` e questo è `0.5`, il valore restituito viene arrotondato al valore di riferimento di mezzo minuto più vicino.
* **`rte`** (facoltativo, stringa): Stringa delimitata da virgole di eventi  Analytics che rimuovono o eliminano il timer. Il valore predefinito è Nothing.

Se si chiama questo metodo, viene restituito un numero intero che rappresenta la quantità di tempo tra l&#39;evento timer di avvio e l&#39;evento timer di arresto nel formato desiderato.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true, "", 0, "s", 2, "event3");
```

...è configurato in modo da funzionare come segue:

* Il timer viene avviato quando s.events contiene event1.
* Il timer si riavvia ogni volta che s.events contiene event1
* Il timer si interrompe quando s.events contiene event2
* Il timer viene reimpostato (ad es. va a 0 secondi) ogni volta che s.events contiene event2
* Il timer viene ripristinato anche quando s.events contiene event3 O se il visitatore chiude il browser
* Quando viene registrato un tempo effettivo tra event1 e event2, il plug-in imposta  eVar1 uguale al numero di secondi tra i due eventi impostati, arrotondato al valore di riferimento più vicino (ad esempio 0 secondi, 2 secondi, 4 secondi, 10 secondi, 184 secondi, ecc.)
* Se s.events contiene event2 prima dell&#39;avvio di un timer,  non verrà impostato alcun eVar1.

### Esempio n. 2

Codice seguente...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", false, "event2", false, "s_20", 20, "h", 1.5, "event3");
```

...è configurato in modo da funzionare come segue:

* Il timer viene avviato quando s.events contiene event1.
* Il timer NON verrà riavviato ogni volta che s.events contiene event1, ma il timer originale continuerà a essere in esecuzione
* Il timer NON si interrompe quando s.events contiene event2, ma il plug-in registrerà l&#39;ora dalla registrazione dell&#39;impostazione originale event1
* Il timer viene memorizzato in un cookie denominato &quot;s_20&quot;
* Il timer viene reimpostato solo quando s.events contiene event3 O se sono trascorsi 20 giorni dall&#39;avvio del timer
* Quando viene registrato un intervallo tra (l&#39;originale) event1 e event2, il plug-in imposta  eVar1 uguale al numero di ore tra i due eventi impostati, arrotondato al valore di riferimento di 1/2 ore più vicino (ad esempio 0 ore, 1,5 ore, 3 ore, 7,5 ore, 478,5 ore, ecc.)

### Esempio n. 3

Codice seguente...

```js
s.eVar1 = s.getTimeBetweenEvents("event1", true, "event2", true);
```

...produrrà risultati simili al primo esempio di cui sopra; tuttavia, il valore di  eVar1 viene restituito in secondi, minuti, ore o giorni, a seconda della lunghezza finale del timer.  Inoltre, il timer scade 1 giorno dopo che è stato impostato per la prima volta invece che al momento in cui il visitatore chiude il browser.

## Cronologia versioni

### 2.1 (26 maggio 2018)

* Riprende le modifiche apportate alla nuova versione del `formatTime` plug-in.

### 2.0 (6 aprile 2018)

* Riscrittura/rianalisi completa del plug-in.

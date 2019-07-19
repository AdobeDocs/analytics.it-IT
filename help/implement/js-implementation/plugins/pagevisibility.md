---
description: Registra quanti secondi è la pagina attiva all'interno del browser e trascina tale valore in una metrica nella visualizzazione pagina successiva.
keywords: Implementazione di Analytics
seo-description: Registra quanti secondi è la pagina attiva all'interno del browser e trascina tale valore in una metrica nella visualizzazione pagina successiva.
seo-title: Getpagevisibility
solution: Analytics
title: Getpagevisibility
topic: Sviluppatore e implementazione
uuid: 3891 e 2 aa-d 5 c 1-4 a 2 b -8522-eb 2 bae 39 ea 2 e
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Getpagevisibility

Registra quanti secondi è la pagina attiva all'interno del browser e trascina tale valore in una metrica nella visualizzazione pagina successiva.

>[!NOTE]
>
>Si tratta di una versione beta del plug-in, e potrebbero essere disponibili aggiornamenti aggiuntivi.

This plug-in requires [getVisitStart](../../../implement/js-implementation/plugins/getvisitstart.md#concept_1C3CD25A87094A498A1D8A455963FBD8).

Questo plug-in registra anche il secondi totale in cui la pagina si trovava all'interno del browser (sia il tempo di visualizzazione attivo che passivo). È necessario utilizzare il plug-in getpreviousvalue per tenere traccia del nome della pagina precedente associato agli eventi di visibilità della pagina. Il tracciamento di questi valori consente di comprendere meglio il coinvolgimento dei visitatori e di monitorare con maggiore precisione il comportamento dei visitatori sui tuoi siti.

È necessario utilizzare il plug-in getpreviousvalue per tenere traccia del nome della pagina precedente associato agli eventi di visibilità della pagina. Il tracciamento di questi valori consente di comprendere meglio il coinvolgimento dei visitatori e di monitorare con maggiore precisione il comportamento dei visitatori sui tuoi siti.

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. Questo può influenzare la raccolta di dati sul sito e deve essere fatta solo da uno sviluppatore con esperienza utilizzando e implementando Analytics. This plug-in is compatible only with [!DNL AppMeasurement] tracking libraries.

## Required Supporting Plug-ins {#section_0CA7624F4A7B4B5F851A4300937887AD}

* Appendlist
* Getpreviousvalue
* Getvisitstart

## Plug-in Code and Implementation {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**Sezione di configurazione**

The `s.pvel` variable should contain the three events you wish to use:

| Evento | Definizione |
|---|---|
| Totale secondi di visibilità pagina (numerico) | Il tempo di attivazione della pagina nel browser |
| Secondi pagina totale (numerico) | Il tempo di caricamento della pagina nel browser, indipendentemente dallo stato di visibilità |
| Istanze totale di visibilità pagina (contatore) | Il numero totale di volte in cui è stato registrato un valore per i due eventi precedenti |

**Chiamate di esempio**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 
```

**Sezione doplugins**

To initialize the plug-in, two lines of code are required in the `doPlugins` section of your s_code, preferably after you have designated the `s.pageName` variable.

**Chiamate di esempio**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 
```

**Sezione plug-in**

```
/* Page Visibility Plugin 0.1 (BETA) */ 
s.getPageVisibility=new Function("","" 
+"var s=this;if(s.getVisitStart()){s.Util.cookieWrite('s_pvs','');s.U" 
+"til.cookieWrite('s_tps','');}if(s.Util.cookieRead('s_pvs')&&s.pvt<1" 
+"){if(parseInt(s.Util.cookieRead('s_pvs'))<=parseInt(s.Util.cookieRe" 
+"ad('s_tps'))){s.pve=s.pvel.split(',');s.events=s.apl(s.events,s.pve" 
+"[0]+'='+(parseInt(s.Util.cookieRead('s_pvs'))),',',2);s.Util.cookie" 
+"Write('s_pvs','');s.events=s.apl(s.events,s.pve[1]+'='+(parseInt(s." 
+"Util.cookieRead('s_tps'))),',',2);s.Util.cookieWrite('s_tps','');s." 
+"events=s.apl(s.events,s.pve[2],',',2);}}s.pvi=setInterval(s.pvx,100" 
+"0);s.wpvi=setInterval(s.wpvc,5000);"); 
s.gbp=new Function("","" 
+"if('hidden'in document){return null;}var bp=['moz','ms','o','webkit" 
+"'];for(var i=0;i<bp.length;i++){var p=bp[i]+'Hidden';if(p in docume" 
+"nt){return bp[i];}}return null;"); 
s.hp=new Function("p","" 
+"if(p){return p+'Hidden';}else{return'hidden';}"); 
s.vs=new Function("p","" 
+"if(p){return p+'VisibilityState';}else{return'visibilityState';}"); 
s.ve=new Function("p","" 
+"if(p){return p+'visibilitychange';}else{return'visibilitychange';}"); 
s.pvx=new Function("","" 
+"s.pvt+=1;"); 
s.wpvc = function(){var tempDate = Date.now();s.Util.cookieWrite('s_tps', 
Math.ceil((tempDate - s.totalTime)/1000));s.Util.cookieWrite('s_pvs', s.pvt)} 
document.addEventListener('visibilitychange',function(event){if(document.hidden){s.visibility = false;clearTimeout(s.pvi);}else{s.visibility=true;s.pvi=setInterval(s.pvx,1000);}});s.totalTime=new Date();s.pvt=0;s.prefix=s.gbp;s.hidden=s.hp(s.prefix);s.visibility=true;s.visibilityState=s.vs(s.prefix);s.visibilityEvent=s.ve(s.prefix); 
```

## Note {#section_47964BB9D0A24BFEB4B2498A41D8B017}

* Verifica sempre le installazioni dei plug-in per garantire che la raccolta dati sia come previsto prima della distribuzione in un ambiente di produzione.
* Poiché il plug-in passa i secondi della visibilità della pagina e i secondi totali in cui sono associati alla pagina precedente, i dati non vengono raccolti per la visualizzazione finale della pagina della visita.
* Questo plug-in si basa sulla capacità di impostare cookie nel browser Web dell'utente. Se l'utente non accetta cookie di prime parti, il plug-in non passa dati in Analytics.
* The plug-in creates its own first-party cookies named `s_tps` and `s_pvs`.

* Una percentuale molto piccola di utenti non passa la percentuale di dati visualizzati a causa dei limiti del browser e la logica è contenuta nel plug-in per garantire che i dati non vengano distorti come risultato. Questo plug-in è stato tuttavia testato correttamente in IE, Firefox, Chrome e Safari.
* A causa del modo in cui il plug-in misura i secondi totali e lo associa al nome della pagina precedente, ci sono differenze tra il tempo predefinito impiegato per le metriche della pagina e le metriche totali dei secondi.
* [!UICONTROL Calculated Metrics] può essere creato per semplificare il riepilogo e comprendere il comportamento dei visitatori associati a queste metriche:

   * ** Rapporto visibilità pagina** (Totale secondi della visibilità pagina/Totale pagina secondi)
   * ** Totale secondi nascosti** (Totale secondi di pagina - Totale secondi di visibilità pagina)
   * ** Secondi media visibilità pagina** (Totale secondi di visibilità pagina/Totale istanze di visibilità pagina)
   * **Secondi** nascosti pagina ((Secondi totali pagina - Secondi totali di visibilità pagina)/Istanze totale di visibilità pagina)

* A causa del modo in cui il plug-in viene arrotondato ai secondi, potrebbe esserci una seconda differenza di 1-2 tra i secondi totali della visibilità delle pagine e i secondi totali, con secondi totali superiori. (da risolvere in un aggiornamento futuro)
* L'utilizzo del plug-in getvisitstart deve tenere conto dei visitatori che hanno una nuova visita dopo un periodo di 30 + minuti di inattività. Questa funzione non funziona correttamente; Tuttavia, se includeremo il «totale secondi attivi» in un'iterazione futura del plug-in, probabilmente troverai una soluzione alternativa.

## Domande frequenti {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

** Questo plug-in effettua chiamate aggiuntive al server? **

Il plug-in registra solo i valori di visibilità della pagina nelle chiamate di server di visualizzazione successive. Non vengono utilizzate chiamate server aggiuntive in combinazione con essa.

** Se non desidero acquisire i secondi totali di pagina o le istanze totale di visibilità delle pagine, posso lasciarli fuori dall'elenco degli eventi? **

Sì, i secondi di pagina totali e le istanze di visibilità totale sono eventi facoltativi e possono essere lasciati fuori dall'elenco, se necessario.

** Gli eventi acquisiti hanno senso se li uso in rapporti diversi da Nome pagina precedente? **

Poiché i valori dei record dei plug-plugin nell'immagine successiva richiedono solo altre evar acquisite in un contesto dì pagina precedentè, vale a dire «URL pagina precedente».

**Il plug-in invia il tempo di visibilità su una chiamata s. tl () o su una chiamata s. t ()?**

Il tempo di visibilità viene registrato solo con le chiamate s. t ().

---
description: Registra il numero di secondi in cui la pagina era la scheda attiva nel browser e trasmette tale valore in una metrica nella visualizzazione pagina successiva.
keywords: Implementazione di Analytics
seo-description: Registra il numero di secondi in cui la pagina era la scheda attiva nel browser e trasmette tale valore in una metrica nella visualizzazione pagina successiva.
seo-title: getPageVisibility
solution: Analytics
title: getPageVisibility
topic: Sviluppatore e implementazione
uuid: 3891e2aa-d5c1-4a2b-8522-eb2bae39ea2e
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# getPageVisibility

Registra il numero di secondi in cui la pagina era la scheda attiva nel browser e trasmette tale valore in una metrica nella visualizzazione pagina successiva.

> [!NOTE] Questa è una versione beta del plugin, e ulteriori aggiornamenti potrebbe essere disponibile.

Questo plug-in richiede [getVisitStart](../../../implement/js-implementation/plugins/getvisitstart.md#concept_1C3CD25A87094A498A1D8A455963FBD8).

Questo plug-in registra anche i secondi totali in cui la pagina si trovava all’interno del browser (tempo di visualizzazione attivo e passivo). È necessario utilizzare il plug-in getPreviousValue per tenere traccia del nome di pagina precedente associato agli eventi di visibilità della pagina. Il tracciamento di questi valori consente di comprendere meglio il coinvolgimento dei visitatori e di monitorare più accuratamente il comportamento dei visitatori sui siti.

È necessario utilizzare il plug-in getPreviousValue per tenere traccia del nome di pagina precedente associato agli eventi di visibilità della pagina. Il tracciamento di questi valori consente di comprendere meglio il coinvolgimento dei visitatori e di monitorare più accuratamente il comportamento dei visitatori sui siti.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza che utilizza e implementa Analytics. Questo plug-in è compatibile solo con le librerie di [!DNL AppMeasurement] tracciamento.

## Plug-in di supporto richiesti {#section_0CA7624F4A7B4B5F851A4300937887AD}

* appendList
* getPreviousValue
* getVisitStart

## Codice plug-in e implementazione {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**Sezione di configurazione**

La `s.pvel` variabile deve contenere i tre eventi da utilizzare:

| Evento | Definizione |
|---|---|
| Secondi Visibilità Totale Pagina (Numerico) | Il tempo di attivazione della pagina nel browser |
| Secondi pagina totali (numerici) | Il tempo di caricamento della pagina nel browser, indipendentemente dal suo stato di visibilità |
| Totale istanze di visibilità pagina (contatore) | Numero totale di volte in cui un valore è stato registrato per i due eventi precedenti |

**Chiamate di esempio**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 
```

**sezione doPlugins**

Per inizializzare il plug-in, nella `doPlugins` sezione s_code sono necessarie due righe di codice, preferibilmente dopo aver designato la `s.pageName` variabile.

**Chiamate di esempio**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 
```

**Sezione Plug-in**

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

* Verificate sempre le installazioni dei plug-in in modo da garantire che la raccolta dei dati avvenga come previsto prima della distribuzione in un ambiente di produzione.
* Poiché il plug-in supera i secondi di visibilità della pagina e i secondi totali associati alla pagina precedente, i dati non vengono raccolti per la visualizzazione della pagina finale della visita.
* Questo plug-in si basa sulla capacità di impostare i cookie nel browser Web dell'utente. Se l'utente non accetta i cookie di prime parti, il plug-in non trasmette dati ad Analytics.
* Il plug-in crea i propri cookie di prime parti denominati `s_tps` e `s_pvs`.

* Una percentuale molto ridotta di utenti non trasmetterà la percentuale di dati di pagina visualizzati a causa delle limitazioni del browser, e la logica è contenuta all'interno del plug-in per garantire che i dati non vengano distorti come risultato. Tuttavia, questo plug-in è stato testato con successo in IE, Firefox, Chrome e Safari.
* A causa del modo in cui il plug-in misura i secondi totali e associa tale valore al nome della pagina precedente, ci saranno differenze tra il tempo predefinito impiegato sulle metriche della pagina e i secondi totali.
* [!UICONTROL Calculated Metrics] può essere creato per riepilogare e comprendere il comportamento dei visitatori associati a queste metriche:

   * **Rapporto** di visibilità della pagina (totale secondi di visibilità della pagina / totale secondi di pagina)
   * **Secondi** Nascosti Totale (Secondi Pagina Totale - Secondi Visibilità Pagina Totale)
   * **Secondi** Di Visibilità Media Delle Pagine (Secondi Di Visibilità Totale Delle Pagine/Istanze Di Visibilità Totale Delle Pagine)
   * **Secondi** Nascosti Di Pagina Media (Secondi Totale Di Pagina - Secondi Di Visibilità Totale Della Pagina)/Istanze Di Visibilità Totale Della Pagina)

* A causa del modo in cui il plug-in arrotonda i secondi, può verificarsi una differenza di 1-2 secondi tra i secondi totali di visibilità della pagina e i secondi totali, con secondi totali superiori. (Da risolvere in un aggiornamento futuro)
* L'utilizzo del plug-in getVisitStart deve tenere conto dei visitatori che hanno un nuovo inizio dopo un periodo di oltre 30 minuti di inattività. Non funziona come previsto; tuttavia, potrebbe verificarsi una soluzione alternativa quando si incorporano i "secondi attivi totali" in una futura iterazione del plug-in.

## Domande frequenti {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

**Il plug-in eseguirà chiamate server aggiuntive?**

Il plug-in registrerà solo i valori di visibilità della pagina nelle chiamate server di visualizzazione pagina successive. Non vengono utilizzate chiamate server aggiuntive insieme ad essa.

**Se non si desidera acquisire i secondi totali di pagina o le istanze totali di visibilità della pagina, è possibile uscire dall'elenco eventi?**

Sì, i secondi totali delle pagine e le istanze di visibilità totali sono eventi facoltativi e, se necessario, possono essere esclusi dall’elenco.

**Gli eventi acquisiti avranno senso se li uso in rapporti diversi da Nome pagina precedente?**

Poiché il plug-in registra i valori nella richiesta di immagine successiva, è possibile applicare solo altre eVar acquisite in un contesto di "pagina precedente", ovvero 'URL pagina precedente'.

**Il plug-in invierà l’ora di visibilità su una chiamata s.tl() o solo su una chiamata s.t()?**

Il tempo di visibilità viene registrato solo con chiamate s.t().

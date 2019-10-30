---
description: Questo plug-in funziona utilizzando l'API JavaScript di temporizzazione navigazione per misurare con precisione le prestazioni sul Web. Questo fornisce un metodo nativo per ottenere statistiche precise e dettagliate sui tempi di caricamento delle pagine e sui tempi di caricamento delle risorse. Precedentemente, misurazioni di questo tipo hanno utilizzato l'oggetto Date JavaScript per le metriche di temporizzazione, oppure un'estrapolazione rudimentale delle metriche di navigazione. Entrambe le metodologie, anche se forniscono alcuni dati con tendenze per i tempi di caricamento delle pagine, non sono affidabili.
keywords: Implementazione di Analytics
seo-description: Questo plug-in funziona utilizzando l'API JavaScript di temporizzazione navigazione per misurare con precisione le prestazioni sul Web. Questo fornisce un metodo nativo per ottenere statistiche precise e dettagliate sui tempi di caricamento delle pagine e sui tempi di caricamento delle risorse. Precedentemente, misurazioni di questo tipo hanno utilizzato l'oggetto Date JavaScript per le metriche di temporizzazione, oppure un'estrapolazione rudimentale delle metriche di navigazione. Entrambe le metodologie, anche se forniscono alcuni dati con tendenze per i tempi di caricamento delle pagine, non sono affidabili.
seo-title: performanceTiming
solution: Analytics
title: performanceTiming
topic: Sviluppatore e implementazione
uuid: ab2a6c51-8791-41e7-9bea-c1ce8d312de8
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# performanceTiming

Questo plug-in funziona utilizzando l'API JavaScript di temporizzazione navigazione per misurare con precisione le prestazioni sul Web. Questo fornisce un metodo nativo per ottenere statistiche precise e dettagliate sui tempi di caricamento delle pagine e sui tempi di caricamento delle risorse. Precedentemente, misurazioni di questo tipo hanno utilizzato l'oggetto Date JavaScript per le metriche di temporizzazione, oppure un'estrapolazione rudimentale delle metriche di navigazione. Entrambe le metodologie, anche se forniscono alcuni dati con tendenze per i tempi di caricamento delle pagine, non sono affidabili.

## Azioni Di Questo Plug-In {#section_4E0771B959FD4F86B4B91BD18CA01DF1}

>[!IMPORTANT]
>
>Questa è una versione beta del plugin, e ulteriori aggiornamenti potrebbe essere disponibile.

Questo plug-in utilizza i seguenti eventi dettagliati per tenere traccia dei singoli componenti di temporizzazione di un caricamento di pagina:

| Evento | Nome | Calcolato da |
|---|---|---|
| 1 | Tempo di reindirizzamento | fetchStart - navigationStart |
| 2 | Tempo cache app | domainLookupStart - fetchStart |
| 3 | Tempo DNS | domainLookupEnd - domainLookupStart |
| 4 | Tempo TCP | connectEnd - connectStart |
| 5 | Tempo richiesta | responseStart - connectEnd |
| 6 | Tempo di risposta | responseEnd - responseStart |
| 7 | Tempo di elaborazione | loadEventStart - domLoading |
| 8 | tempo di caricamento | loadEventEnd - loadEventStart |
| 9 | Tempo di caricamento totale pagina | loadEventEnd - navigationStart |
| 10 | Istanze prestazioni |  Contatore |

Il grafico seguente illustra gli attributi di temporizzazione definiti dall'interfaccia PerformanceTiming e dall'interfaccia PerformanceNavigation rispettivamente con o senza reindirizzamento.

![](assets/timing-attributes.png)

Per informazioni dettagliate sull'oggetto Tempo di navigazione, consultate:

[https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface](https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface)

Inoltre, il plug-in può utilizzare facoltativamente l'oggetto performanceEntries per registrare il nome della risorsa, l'inizio del tempo di caricamento della risorsa e i dettagli della durata del tempo di caricamento della risorsa per ogni singola risorsa caricata su una determinata pagina. Con questo plug-in viene registrata una grande quantità di informazioni e, di conseguenza, l'oggetto di memorizzazione DOM è abilitato per memorizzare le informazioni di caricamento della pagina tra le visualizzazioni della pagina. Accertatevi che l'informativa sulla privacy della società consenta l'utilizzo dell'oggetto di archiviazione DOM prima di abilitare questa funzionalità. Richiede inoltre l'utilizzo di un listVar per tenere traccia di tutte le risorse.

## Plug-in di supporto richiesti {#section_B6447EB6548942EFBC219AEFDC245639}

* appendList
* getPreviousValue

## Codice e implementazione plug-in {#section_564D77E1CF0E445586D95AD9769CE57D}

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e deve essere eseguita solo da uno sviluppatore con esperienza che utilizza e implementa Adobe Analytics. Questo plug-in è compatibile solo con le librerie di [!DNL AppMeasurement] tracciamento.

**Sezione di configurazione (prima di doPlugins):**

`s.pte`: Elenco separato da virgole di eventi contenenti i 10 eventi che si desidera utilizzare - i singoli componenti evento temporizzazione (eventi 1 - 8), il tempo di caricamento totale della pagina (evento 9) e le istanze di prestazioni totali (evento 10) - in tale ordine specifico.

`s.ptc`: Impostate questa opzione per determinare se eseguire o meno il plug-in all'interno di doPlugins. Sempre impostato su false.

*Chiamate di esempio*

```
s.pte = 'event10,event11,event12,event13,event14,event15,event16,event17,event18,event19' 
//[--------------------------- 1 to 8 ---------------------------][-- 9 --][- 10 -] 
s.ptc = false; 
```

**sezione doPlugins:**

Per inizializzare il plug-in, è necessaria una riga di codice nella `doPlugins` sezione s_code, preferibilmente dopo aver designato la `s.pageName`variabile. Se desiderate utilizzare la funzionalità del tempo di caricamento delle risorse all'interno del plug-in, dovete immettere il nome della variabile di elenco da utilizzare. In caso contrario, solo le voci relative ai tempi di prestazione verranno tracciate negli eventi precedentemente specificati nella `s.pte` variabile.

> [!NOTE] Per correlare le voci temporali delle prestazioni con le pagine del sito, è necessario inizializzare il `getPreviousValue` plug-in. È consigliabile confrontare queste voci delle prestazioni con il nome della pagina precedente o con il valore dell'URL della pagina precedente.

*Chiamate di esempio*

```
/* Performance Timing */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.performanceTiming('list2')  
```

**Sezione Plugins:**

Infine, aggiungete il plug-in stesso all'implementazione JavaScript.

```
/* Plugin: Performance Timing Tracking - 0.11 BETA */ 
s.performanceTiming=new Function("v","" 
+"var s=this;if(v)s.ptv=v;if(typeof performance!='undefined'){if(perf" 
+"ormance.timing.loadEventEnd==0){s.pi=setInterval(function(){s.perfo" 
+"rmanceWrite()},250);}if(!s.ptc||s.linkType=='e'){s.performanceRead(" 
+");}else{s.rfe();s[s.ptv]='';}}"); 
s.performanceWrite=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";try{if(s.c_r('s_ptc')==''&&performance.timing.loadEventEnd>0){try{" 
+"var pt=performance.timing;var pta='';pta=s.performanceCheck(pt.fetc" 
+"hStart,pt.navigationStart);pta+='^^'+s.performanceCheck(pt.domainLo" 
+"okupStart,pt.fetchStart);pta+='^^'+s.performanceCheck(pt.domainLook" 
+"upEnd,pt.domainLookupStart);pta+='^^'+s.performanceCheck(pt.connect" 
+"End,pt.connectStart);pta+='^^'+s.performanceCheck(pt.responseStart," 
+"pt.connectEnd);pta+='^^'+s.performanceCheck(pt.responseEnd,pt.respo" 
+"nseStart);pta+='^^'+s.performanceCheck(pt.loadEventStart,pt.domLoad" 
+"ing);pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.loadEventStart" 
+");pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.navigationStart);" 
+"s.c_w('s_ptc',pta);if(sessionStorage&&navigator.cookieEnabled&&s.pt" 
+"v!='undefined'){var pe=performance.getEntries();var tempPe='';for(v" 
+"ar i=0;i<pe.length;i++){tempPe+='!';tempPe+=pe[i].name.indexOf('?')" 
+">-1?pe[i].name.split('?')[0]:pe[i].name;tempPe+='|'+(Math.round(pe[" 
+"i].startTime)/1000).toFixed(1)+'|'+(Math.round(pe[i].duration)/1000" 
+").toFixed(1)+'|'+pe[i].initiatorType;}sessionStorage.setItem('s_pec" 
+"',tempPe);}}catch(err){return;}}}catch(err){return;}"); 
s.performanceCheck=new Function("a","b","" 
+"if(a>=0&&b>=0){if((a-b)<60000&&((a-b)>=0)){return((a-b)/1000).toFix" 
+"ed(2);}else{return 600;}}"); 
s.performanceRead=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";var cv=s.c_r('s_ptc');if(s.pte){var ela=s.pte.split(',');}if(cv!='" 
+"'){var cva=s.split(cv,'^^');if(cva[1]!=''){for(var x=0;x<(ela.lengt" 
+"h-1);x++){s.events=s.apl(s.events,ela[x]+'='+cva[x],',',2);}}s.even" 
+"ts=s.apl(s.events,ela[ela.length-1],',',2);}s.linkTrackEvents=s.apl" 
+"(s.linkTrackEvents,s.pte,',',2);s.c_w('s_ptc','',0);if(sessionStora" 
+"ge&&navigator.cookieEnabled&&s.ptv!='undefined'){s[s.ptv]=sessionSt" 
+"orage.getItem('s_pec');sessionStorage.setItem('s_pec','',0);}else{s" 
+"[s.ptv]='sessionStorage Unavailable';}s.ptc=true;"); 
/* Remove from Events 0.1 - Performance Specific,  
removes all performance events from s.events once being tracked. */ 
s.rfe=new Function("","" 
+"var s=this;var ea=s.split(s.events,',');var pta=s.split(s.pte,',');" 
+"try{for(x in pta){s.events=s.rfl(s.events,pta[x]);s.contextData['ev" 
+"ents']=s.events;}}catch(e){return;}"); 
/* Plugin Utility - RFL (remove from list) 1.0*/ 
s.rfl=new Function("l","v","d1","d2","ku","" 
+"var s=this,R=new Array(),C='',d1=!d1?',':d1,d2=!d2?',':d2,ku=!ku?0:" 
+"1;if(!l)return'';L=l.split(d1);for(i=0;i<L.length;i++){if(L[i].inde" 
+"xOf(':')>-1){C=L[i].split(':');C[1]=C[0]+':'+C[1];L[i]=C[0];}if(L[i" 
+"].indexOf('=')>-1){C=L[i].split('=');C[1]=C[0]+'='+C[1];L[i]=C[0];}" 
+"if(L[i]!=v&&C)R.push(C[1]);else if(L[i]!=v)R.push(L[i]);else if(L[i" 
+"]==v&&ku){ku=0;if(C)R.push(C[1]);else R.push(L[i]);}C='';}return s." 
+"join(R,{delim:d2})"); 
```

## Note {#section_131C5D97A0094880AFC3A2BBE0BC9DE4}

* Verificate sempre le installazioni dei plug-in in modo da garantire che la raccolta dei dati avvenga come previsto prima della distribuzione in un ambiente di produzione.
* Poiché il plug-in trasmette i dati delle prestazioni come sono associati alla pagina precedente, i dati non vengono raccolti per la visualizzazione della pagina finale della visita.
* Se tenete traccia dei tempi delle risorse, questo plug-in si basa sulla capacità di impostare valori di memorizzazione DOM nel browser Web dell'utente. Se l'utente non accetta i cookie e l'archiviazione DOM è abilitata, il plug-in non trasmette dati ad Analytics.
* Una percentuale molto ridotta di utenti non trasmetterà i dati temporali di navigazione a causa delle limitazioni del browser, e la logica è contenuta all'interno del plug-in per garantire che i dati non vengano distorti come risultato - in particolare con una piccola parte dei browser mobili. Tuttavia, questo plug-in è stato testato con successo in IE, Firefox, Chrome e Safari.
* [!UICONTROL Calculated Metrics] devono essere creati per riepilogare e comprendere il comportamento dei visitatori associati a queste metriche:

   * Tempo medio di reindirizzamento (tempo di reindirizzamento/tempi di prestazioni)
   * Tempo medio della cache delle app (occorrenze tempo cache app/durata prestazioni)
   * Tempo DNS medio (istanze di tempo DNS/tempo prestazioni DNS)
   * Tempo TCP medio (istanze di temporizzazione/durata prestazioni TCP)
   * Tempo medio richieste (tempo richieste/istanze di tempo prestazioni)
   * Tempo medio di risposta (tempo di risposta/tempi di prestazioni)
   * Tempo medio di elaborazione (tempo di elaborazione/istanze di durata delle prestazioni)
   * Tempo medio onLoad (istanze di temporizzazione/durata prestazioni onLoad)
   * Tempo medio di caricamento delle pagine (tempo totale di caricamento delle pagine/tempi di prestazioni)


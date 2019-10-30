---
title: PWA per Analytics
seo-title: PWA per Analytics
description: App Web progressive per Adobe Analytics
seo-description: Utilizzare PWA con Analytics
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# PWA per Analytics

Questa guida descrive come utilizzare Adobe Analytics con le app Web progressive (PWA).

## Introduzione

I file PWA possono fornire un’esperienza app nativa e funzionalità offline per un sito Web. Di solito le PWA includono un service worker, disposizioni di caching e un file manifesto, il tutto in grado di fornire assistenza con tempi di caricamento più rapidi, navigazione più semplice e un comportamento reattivo.

Adobe Analytics funziona perfettamente con le PWA come con i siti Web tradizionali. Sebbene i PWA abbiano alcuni requisiti in più per comportarsi progressivamente all'interno e all'esterno di se stessi, non creano barriere o limitazioni sul modo in cui Analytics raccoglie o segnala i dati da tali siti in modo diverso rispetto ai siti Web tradizionali. Infatti, poiché Analytics già include funzionalità di tracciamento offline, le PWA possono aiutarti a sfruttare questa funzionalità integrata più facilmente che con i siti Web tradizionali.

## Ottenimento dei dati PWA Analytics

Per raccogliere e analizzare i dati PWA con Analytics, non è necessario apportare modifiche alla configurazione. Analytics fornisce automaticamente tutte le stesse funzionalità e funzionalità di un sito Web tradizionale.

## Aggiunta del tracciamento offline per aumentare l'efficacia del PWA

Puoi aumentare l’efficacia del tuo PWA utilizzando le funzionalità [di tracciamento](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) offline di Analytics. Per impostazione predefinita, questa funzione è disattivata, ma potete aggiungere la seguente proprietà al file AppMeasurement.js per attivarla: `s.trackOffline=true;`.

Ad esempio, nel seguente file AppMeasurement.js, la proprietà viene aggiunta alla fine del `CONFIG SECTION`:

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.trackOffline=true
***
    
```


Per ulteriori informazioni sulla modifica del file AppMeasurement.js, vedi [Inserimento di codice nel file](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)AppMeasurement.js.

Per esempi di configurazioni nel file AppMeasurement.js, consultate [Configurazione del file](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)AppMeasurement.js.

Per ulteriori informazioni sulle caratteristiche del file AppMeasurement.js, consulta la panoramica [sull’implementazione di](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)Javascript.

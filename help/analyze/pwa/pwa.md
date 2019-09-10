---
title: Pwas for Analytics
seo-title: Pwas for Analytics
description: App Web progressive per Adobe Analytics
seo-description: Utilizzo di pera con Analytics
translation-type: tm+mt
source-git-commit: f64e5d9977bebd0e9db4af0f7118e9e64978c1c7

---


# Pwas for Analytics

Questa guida descrive come utilizzare Adobe Analytics con le app Web progressive (PER).

## Introduzione

Gli PER possono fornire un'esperienza app nativa e funzionalità offline per un sito Web. In genere, PERA include un worker di servizi, le clausole di caching e un file manifesto, il che può facilitare il tempo di caricamento, la navigazione più semplice e il comportamento reattivo.

Adobe Analytics funziona perfettamente con pera, come accade con i siti Web tradizionali. Anche se gli PAVA hanno un numero di requisiti più elevato per il comportamento progressivo e di se stessi, non creano barriere o limitazioni su come Analytics raccoglie o segnala i dati da loro in modo diverso rispetto ai siti Web tradizionali. Infatti, poiché Analytics include già funzionalità di tracciamento offline, per può aiutarti a sfruttare in modo più semplice la funzionalità integrata rispetto ai siti Web tradizionali.

## Ottenimento dei dati di analisi PWA

Per raccogliere e analizzare i dati PWA con Analytics, non devi apportare alcuna modifica alla configurazione. Analytics fornisce automaticamente le stesse funzionalità e funzionalità di un sito Web tradizionale.

## Aggiunta di tracciamento offline per aumentare l'efficacia PWA

Puoi aumentare l'efficacia del tuo PWA utilizzando le funzionalità di tracciamento [offline di Analytics](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) . Per impostazione predefinita, questa funzione è disattivata, ma puoi aggiungere la seguente proprietà al file appmeasurement. js per attivarla: `s.trackOffline=true;`.

Ad esempio, nel seguente file appmeasurement. js, la proprietà viene aggiunta alla fine di `CONFIG SECTION`:

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


Per ulteriori informazioni sulla modifica del file appmeasurement. js, vedi [Inserimento del codice nel file appmeasurement. js](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

Per esempi di configurazioni nel file appmeasurement. js, consulta [Configurazione del file appmeasurement. js](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7).

Per ulteriori informazioni sulle caratteristiche del file appmeasurement. js, consulta la panoramica sull'implementazione [Javascript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

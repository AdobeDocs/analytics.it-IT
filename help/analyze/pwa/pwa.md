---
title: PWA per Analytics
description: App web progressive per Adobe Analytics
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 87%

---


# PWA per Adobe Analytics

Questa pagina descrive come utilizzare Adobe Analytics con le app web progressive (PWA).

## Introduzione

Le PWA possono offrire l’esperienza di un’app nativa e funzionalità offline per un sito web. Di solito le PWA includono un service worker, sistemi di caching e un file manifest, grazie ai quali è possibile fornire assistenza con tempi di caricamento più rapidi e una navigazione più semplice e responsive.

Adobe Analytics funziona perfettamente con le PWA, proprio come con i siti web tradizionali. Sebbene le PWA prevedano alcuni requisiti in più per svilupparsi progressivamente, non creano barriere o limitazioni diverse nella raccolta o reporting dei dati di tali siti da parte di Analytics rispetto ai siti web tradizionali. Infatti, poiché Analytics già include il tracciamento offline, puoi sfruttare questa funzionalità più facilmente con le PWA che con i siti web tradizionali.

## Ottenere i dati PWA Analytics

Per raccogliere e analizzare i dati di PWA con [!UICONTROL Analytics], non è necessario apportare alcuna modifica alla configurazione. [!UICONTROL Analytics] presenta automaticamente le stesse funzionalità e caratteristiche di un sito web tradizionale.

## Aggiungere il tracciamento offline per aumentare l’efficacia della PWA

Puoi aumentare l’efficacia del tuo PWA utilizzando le funzionalità di tracciamento offline di Adobe Analytics [e ](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/functions/forceoffline.translate.html). Per impostazione predefinita, questa funzione è disattivata, ma puoi aggiungere la seguente proprietà al file AppMeasurement.js per attivarla: `s.trackOffline=true;`.

Ad esempio, nel seguente file AppMeasurement.js, la proprietà viene aggiunta alla fine della `CONFIG SECTION`:

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

Per ulteriori informazioni sulla modifica del file AppMeasurement.js, consulta [Inserimento di codice nel file AppMeasurement.js](https://docs.adobe.com/content/help/it-IT/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.translate.html).

Per esempi di configurazioni nel file AppMeasurement.js, consulta [Configurazione del file AppMeasurement.js](https://docs.adobe.com/content/help/it-IT/analytics/implementation/js/overview.translate.html#section_042412C29CC249E298F19B2BC2F43CE7).

Per ulteriori informazioni sulle caratteristiche del file AppMeasurement.js, consulta la [Panoramica sull’implementazione di JavaScript](https://docs.adobe.com/content/help/it-IT/analytics/implementation/js/migrate-from-hcode.translate.html).

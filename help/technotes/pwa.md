---
title: PWA per Analytics
description: App web progressive per Adobe Analytics
role: User, Admin
feature: Progressive Web Apps
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 62%

---

# PWA per Adobe Analytics

Questa pagina descrive come utilizzare Adobe Analytics con le app web progressive (PWA).

## Introduzione

Le PWA possono offrire l’esperienza di un’app nativa e funzionalità offline per un sito web. Di solito le PWA includono un service worker, sistemi di caching e un file manifest, grazie ai quali è possibile fornire assistenza con tempi di caricamento più rapidi e una navigazione più semplice e responsive.

Adobe Analytics funziona perfettamente con i PWA come con i siti web tradizionali. Sebbene le PWA prevedano alcuni requisiti in più per svilupparsi progressivamente, non creano barriere o limitazioni diverse nella raccolta o reporting dei dati di tali siti da parte di Analytics rispetto ai siti web tradizionali. Infatti, poiché Analytics già include il tracciamento offline, puoi sfruttare questa funzionalità più facilmente con le PWA che con i siti web tradizionali.

## Ottenere i dati PWA Analytics

Per raccogliere e analizzare i dati PWA con [!UICONTROL Analytics], non è necessario apportare modifiche alla configurazione. [!UICONTROL Analytics] fornisce automaticamente tutte le funzionalità e le caratteristiche che offre un sito Web tradizionale.

## Aggiungere il tracciamento offline per aumentare l’efficacia della PWA

Puoi aumentare l&#39;efficacia del tuo PWA utilizzando le [funzionalità di tracciamento offline](/help/implement/vars/config-vars/trackoffline.md) di Adobe Analytics. Per impostazione predefinita, questa funzione è disattivata, ma puoi aggiungere la seguente proprietà al file AppMeasurement.js per attivarla: `s.trackOffline=true;`.

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

Per ulteriori informazioni sulla configurazione del file AppMeasurement.js, vedere [Panoramica delle variabili di configurazione](/help/implement/vars/config-vars/configuration-variables.md) e le singole pagine specifiche delle variabili nello stesso sottocapitolo.

Per ulteriori informazioni sulle caratteristiche del file AppMeasurement.js, consulta la [Panoramica sull&#39;implementazione di JavaScript](/help/implement/js/overview.md).

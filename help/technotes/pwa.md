---
title: PWA per Analytics
description: App web progressive per Adobe Analytics
role: User, Admin
feature: Progressive Web Apps
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
TQID: 'https://experienceleague.adobe.com/IKf2D1AqfbD6qurNczyJWaZIOzQyOTURfJFSJNDucnU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b9fe5dd8-e052-4fb5-86db-a5f6ced5bbb8
    internal-label: Progressive web apps
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 62%
---
# PWA per Adobe Analytics

Questa pagina descrive come utilizzare Adobe Analytics con le app web progressive (PWA).

## Introduzione

Le PWA possono offrire l’esperienza di un’app nativa e funzionalità offline per un sito web. Di solito le PWA includono un service worker, sistemi di caching e un file manifest, grazie ai quali è possibile fornire assistenza con tempi di caricamento più rapidi e una navigazione più semplice e responsive.

Adobe Analytics funziona perfettamente con le PWA, come con i siti web tradizionali. Sebbene le PWA prevedano alcuni requisiti in più per svilupparsi progressivamente, non creano barriere o limitazioni diverse nella raccolta o reporting dei dati di tali siti da parte di Analytics rispetto ai siti web tradizionali. Infatti, poiché Analytics già include il tracciamento offline, puoi sfruttare questa funzionalità incorporata più facilmente con le PWA che con i siti web tradizionali.

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

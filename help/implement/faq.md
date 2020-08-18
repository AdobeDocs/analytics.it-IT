---
title: Domande frequenti sull’implementazione di Analytics
description: Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: ht
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35
workflow-type: ht
source-wordcount: '412'
ht-degree: 100%

---


# Domande frequenti sull’implementazione di Analytics

Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.

**Qual è la differenza tra allocazione variabile e scadenza?**

L’allocazione e la scadenza sono entrambe impostazioni che puoi applicare alle variabili personalizzate. *L’allocazione* si attua quando si dispone di un valore di variabile persistente e di un nuovo valore di variabile. Determina se mantenere il valore precedente o quello nuovo. *La scadenza* si applica quando non si desidera che il valore di una variabile continui a persistere.

**Qual è la differenza tra l’ID visitatore Experience Cloud e l’ID visitatore Analytics?**

Identity Service assegna un identificatore univoco e permanente che può essere condiviso tra le altre soluzioni Experience Cloud. L’ID visitatore di Analytics è utilizzato solo da Analytics. Adobe consiglia di utilizzare il servizio ID visitatori di Experience Cloud per la tua implementazione.

**Come viene impostato un ID visitatore se i cookie sono bloccati?**

Se il cookie standard `s_vi` non è disponibile, viene creato un cookie di fallback sul dominio del sito web con un ID univoco generato in modo casuale. Questo cookie, denominato `s_fid`, è impostato con scadenza di 2 anni e viene utilizzato quando il metodo di identificazione di fallback continua.

**Come si implementa il Tracciamento video Heartbeat?**

Vedi la sezione [Misurazione di audio e video in Adobe Analytics](https://docs.adobe.com/content/help/it-IT/media-analytics/using/media-overview.html).

**Un’interruzione del servizio Adobe può influire sulle prestazioni?**

No. Il file JavaScript non è ospitato sui server Adobe, pertanto un’interruzione da parte di Adobe non influirà sulla libreria AppMeasurement. Se utilizzi Adobe Experience Platform Launch, il file JavaScript è ospitato da Akamai o in una posizione server determinata dalla tua organizzazione.

**L’invio di dati dal browser ai servizi Adobe riduce le prestazioni?**

AppMeasurement crea un oggetto immagine all’interno della pagina HTML e il browser quindi richiede l’oggetto immagine ai server di raccolta dati Adobe. Se i server di raccolta dati dovessero essere lenti o non rispondere, la gestione del thread della richiesta verrebbe ritardata fino al ritorno dell’immagine o al verificarsi di un timeout. Poiché i browser gestiscono immagini con più thread, un’interruzione di Adobe avrebbe un impatto minimo sul tempo di caricamento della pagina, bloccando un thread mentre gli altri continuano a funzionare.

**Come si tiene traccia di un’app mobile?**

Puoi usare l’SDK di Adobe Experience Platform. Per ulteriori informazioni, consulta la sezione [Panoramica dell’SDK di Adobe Experience Platform](https://aep-sdks.gitbook.io/docs/).

**Cosa sono i plug-in?**

I plug-in sono snippet di codice che eseguono funzioni avanzate. Estendono le caratteristiche di AppMeasurement per fornire ulteriori funzionalità alla tua implementazione.

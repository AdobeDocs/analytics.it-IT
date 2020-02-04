---
title: Domande frequenti sull’implementazione di Analytics
description: Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.
keywords: Analytics Implementation;faq;frequently asked questions;evar expiration;custom event visibility;timestamp;visitor id grace period;visitor id;Experience Cloud visitor id;analytics visitor id;dtm;heartbeat;cookies;tracking server;performance;javascript;data collection;s_code version;s_code debug;track link types;track video;track mobile app;first party cookie;ssl certificate;certification expiration;certificate expiration;plugins;data insertion api;500 error;500;Manage user;manage group;users;groups
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Domande frequenti sull’implementazione di Analytics

Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.

**Qual è la differenza tra allocazione variabile e scadenza?**

L&#39;allocazione e la scadenza sono entrambe impostazioni che potete applicare alle variabili personalizzate. *L&#39;allocazione* viene riprodotta quando si dispone di un valore di variabile persistente e di un nuovo valore di variabile. Determina se mantenere il valore precedente o il nuovo valore. *La scadenza* viene riprodotta quando non si desidera che il valore di una variabile continui a persistere.

**Qual è la differenza tra l’ID visitatore di Experience Cloud e l’ID visitatore di Analytics?**

Il servizio identità assegna un identificatore univoco e permanente che può essere condiviso tra le altre soluzioni Experience Cloud. L’ID visitatore di Analytics è utilizzato solo da Analytics. Adobe consiglia di utilizzare il servizio ID visitatori di Experience Cloud per la tua implementazione.

**Come viene impostato un ID visitatore se i cookie sono bloccati?**

If the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2-year expiration and is used as the fallback identification method going forward.

**Come posso implementare il tracciamento video heartbeat?**

See [Measuring audio and video in Adobe Analytics](https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html).

**Un&#39;interruzione del servizio in Adobe può influire sulle prestazioni?**

No. Il file JavaScript non è ospitato sui server Adobe, pertanto un&#39;interruzione Adobe non influisce sulla libreria AppMeasurement. Se utilizzate Adobe Experience Platform Launch, il file JavaScript è ospitato da Akamai o in una posizione server determinata dalla vostra organizzazione.

**L&#39;invio di dati dal browser ai servizi Adobe può ridurre le prestazioni?**

AppMeasurement crea un oggetto immagine all&#39;interno della pagina HTML, quindi il browser richiede l&#39;oggetto immagine dai server di raccolta dati Adobe. Se i server di raccolta dati fossero lenti o non reattivi, la gestione del thread della richiesta verrebbe posticipata fino al ritorno dell&#39;immagine o al verificarsi di un timeout. Poiché i browser gestiscono immagini con più thread, un’interruzione di Adobe avrebbe un impatto minimo sul tempo di caricamento della pagina, bloccando un thread mentre gli altri continuano a funzionare.

**Come si tiene traccia di un&#39;app mobile?**

Puoi usare l’SDK di Adobe Experience Platform. Per ulteriori informazioni, consulta [Panoramica](https://aep-sdks.gitbook.io/docs/) dell’SDK di Adobe Experience Platform.

**Cosa sono i plug-in?**

I plug-in sono frammenti di codice che eseguono funzioni avanzate. Estendono le funzionalità di AppMeasurement per fornire ulteriori funzionalità nell&#39;implementazione.

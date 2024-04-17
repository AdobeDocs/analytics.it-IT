---
title: Inviare dati ad Adobe Analytics utilizzando la libreria JavaScript dell’SDK per web
description: Inizia con un’implementazione pulita di Web SDK per inviare dati ad Adobe Analytics utilizzando la libreria JavaScript.
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Inviare dati ad Adobe Analytics utilizzando la libreria JavaScript dell’SDK per web

Questo percorso di implementazione comporta una nuova installazione di Web SDK utilizzando la libreria JavaScript di Web SDK. Altri percorsi di implementazione sono trattati in pagine separate:

* [Estensione tag Web SDK](web-sdk-tag-extension.md): nuova installazione di Web SDK tramite l’estensione tag Web SDK. Simile all’approccio per la libreria JavaScript dell’SDK web (questa pagina), tranne per il fatto che gestisci l’implementazione utilizzando i tag in Raccolta dati di Adobe Experience Platform. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.
* [Estensione Analytics per estensione Web SDK](analytics-extension-to-web-sdk.md): adotta un approccio fluido e sistematico per passare dall’estensione tag Adobe Analytics all’estensione tag Web SDK. Questo approccio elimina la necessità di utilizzare XDM fino a quando l’organizzazione non è pronta a utilizzare i servizi Adobe Experience Platform, come il Customer Journey Analytics. Utilizza il `data` oggetto invece del `xdm` oggetto per inviare dati ad Adobe.
* [AppMeasurement della libreria JavaScript di Web SDK](appmeasurement-to-web-sdk.md): approccio fluido e metodico per la migrazione all’SDK web, con la differenza che non utilizza i tag. È invece possibile rimuovere manualmente la libreria di raccolta dati di Adobe Analytics (`AppMeasurement.js`) e sostituirla con la libreria JavaScript di Web SDK (`alloy.js`).

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo della libreria JavaScript dell’SDK web per inviare dati ad Adobe Analytics presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Approccio diretto**: questo percorso di implementazione è più semplice degli approcci che spostano le implementazioni Adobe Analytics esistenti. Se non hai un’implementazione Adobe Analytics corrente da preoccupare, compila i campi XDM dell’SDK per web applicabili.</li><li>**Schema predefinito**: se per la tua organizzazione non è necessario un tuo schema, puoi semplicemente utilizzare lo schema orientato verso Adobe Analytics. Questo concetto si applica anche quando ci si sposta verso il Customer Journey Analytics; il concetto di prop e eVar non si applica al Customer Journey Analytics, ma puoi continuare a utilizzare prop ed eVar come semplici dimensioni personalizzate.</li></ul> | <ul><li>**Le modifiche all’implementazione richiedono l’intervento degli sviluppatori**: se desideri apportare modifiche all’implementazione dell’SDK web, devi collaborare con il team di sviluppo per modificare il codice sul sito. L&#39;approccio che utilizza [Estensione tag Web SDK](web-sdk-tag-extension.md) evita questo svantaggio.</li><li>**Bloccato in utilizzando uno schema specifico**: quando l’organizzazione passa al Customer Journey Analytics, devi scegliere di continuare a utilizzare lo schema Adobe Analytics o di eseguire la migrazione allo schema della tua organizzazione (che sarebbe un set di dati separato). Se la tua organizzazione desidera evitare sia lo schema Adobe Analytics che la migrazione a un set di dati separato durante il passaggio al Customer Journey Analytics, Adobe consiglia uno dei due metodi seguenti:</li><ul><li>Utilizza il `data` oggetto: `data` object consente di inviare dati ad Adobe Analytics senza essere conforme a uno schema XDM. Una volta creato lo schema dell’organizzazione, puoi utilizzare la mappatura dello stream di dati per eseguire la mappatura `data` campi oggetto in XDM. Entrambe [Estensione Analytics per estensione Web SDK](analytics-extension-to-web-sdk.md) e [AppMeasurement della libreria JavaScript di Web SDK](appmeasurement-to-web-sdk.md) utilizza questo `data` oggetto.</li><li>Ignora completamente Adobe Analytics: se implementi l’SDK web, puoi inviare tali dati a un set di dati in Adobe Experience Platform per l’utilizzo in Customer Journey Analytics. Puoi utilizzare qualsiasi schema desiderato; Adobe Analytics non è coinvolto in questo flusso di lavoro e pertanto non richiede il gruppo di campi Adobe Analytics ExperienceEvent. Questo metodo si assume la minore quantità di debito tecnico, ma lascia anche completamente fuori dal quadro generale Adobe Analytics.</li></ul></ul> |

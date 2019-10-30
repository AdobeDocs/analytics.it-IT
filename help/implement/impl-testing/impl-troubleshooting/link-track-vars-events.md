---
description: La chiave per una corretta implementazione del tracciamento dei collegamenti è comprendere le variabili s.linkTrackVars e s.linkTrackEvents. Questo consente di trasmettere valori di variabili personalizzate alle azioni dell'utente.
keywords: Implementazione di Analytics
seo-description: La chiave per una corretta implementazione del tracciamento dei collegamenti è comprendere le variabili s.linkTrackVars e s.linkTrackEvents. Questo consente di trasmettere valori di variabili personalizzate alle azioni dell'utente.
seo-title: Utilizzo di s.linkTrackVars e s.linkTrackEvents
solution: Analytics
title: Utilizzo di s.linkTrackVars e s.linkTrackEvents
topic: Sviluppatore e implementazione
uuid: f6b7019b-987b-4b7d-a446-80205f7cc36c
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Utilizzo di s.linkTrackVars e s.linkTrackEvents

La chiave per una corretta implementazione del tracciamento dei collegamenti è comprendere le variabili s.linkTrackVars e s.linkTrackEvents. Questo consente di trasmettere valori di variabili personalizzate alle azioni dell'utente.

Se state implementando il tracciamento dei collegamenti personalizzato e state impostando [!UICONTROL custom] variabili e *`events`*, accertatevi che la [!UICONTROL s.linkTrackVars] variabile contenga un elenco separato da virgole di tutte le variabili che state passando, inclusa la *`events`* variabile. Accertatevi che [!UICONTROL s.linkTrackEvents] includa un elenco separato da virgole di tutti gli eventi che state passando.

Impostando [!UICONTROL s.linkTrackVars] e [!UICONTROL s.linkTrackEvents] non impostando tali variabili/eventi, si prepara solo il [!DNL Analytics] codice. È comunque necessario impostare manualmente le variabili, come illustrato nell'esempio seguente:

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 
```

Gli eventi sono elencati nella [!UICONTROL s.linkTrackVars] variabile. I singoli eventi che possono essere passati sono inclusi nella [!UICONTROL s.linkTrackEvents] variabile e sono inclusi anche in un [!UICONTROL s.events] secondo momento nella funzione. Ciascuna delle variabili che vengono passate è elencata in [!UICONTROL s.linkTrackVars] prima che venga compilata successivamente nella funzione. Inoltre, "event9″ è stato incluso in [!UICONTROL s.linkTrackEvents], ma non è stato incluso in [!UICONTROL s.events]. Non viene registrato, ma potrebbe essere registrato se l'utente ha scelto di impostare s.events="event5,event9."

Il download automatico dei file e il tracciamento [!UICONTROL Exit] dei collegamenti funzionano in modo diverso. I [!UICONTROL s.linkTrackVars] e [!UICONTROL s.linkTrackEvents] sono inclusi nel file standard [!DNL s_code.js] e entrambi sono impostati su none. Queste variabili vengono in genere lasciate impostate su none nel [!DNL s_code.js] file, in modo che il tracciamento automatico dei collegamenti, a differenza [!UICONTROL custom link tracking], utilizzi i valori [!UICONTROL s.linkTrackVars] e [!UICONTROL s.linkTrackEvents] impostati nel file JavaScript globale. Trasmettono inoltre tutti i valori esistenti di tali variabili ogni volta che viene registrato il download o il [!UICONTROL Exit] collegamento di un file.

Considerate l’esempio dove s.channel="Home" quando la pagina viene caricata e dove s.linkTrackVars="channel" nel [!DNL s_code.js] file. Se un utente fa clic per scaricare un file, il tracciamento automatico del download dei file passa i dati in [!DNL Analytics], incluso il valore di [!UICONTROL s.channel] quello impostato per il caricamento della pagina. "Home" viene passato una seconda volta, portando l'inflazione nei dati della visualizzazione pagina per questo valore nel [!UICONTROL Site Sections] rapporto.

Adobe consiglia vivamente di lasciare l' [!UICONTROL s.linkTrackVars] e [!UICONTROL s.linkTrackEvents] impostarlo su "none" nel file JavaScript globale e impostarlo in modo esplicito, se necessario, con l' [!UICONTROL custom link tracking] implementazione.

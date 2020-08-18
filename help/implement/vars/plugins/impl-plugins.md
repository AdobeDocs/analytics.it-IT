---
title: Panoramica sui plug-in
description: Incolla il codice sul sito per introdurre nuove funzionalità.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 9%

---


# Panoramica sui plug-in

I plug-in sono frammenti di codice che eseguono diverse funzioni avanzate per facilitare l&#39;implementazione di Analytics. Questi plug-in estendono le funzionalità del file JavaScript per offrire ulteriori funzionalità non disponibili con un’implementazione di base. Adobe offre molti altri plug-nell’ambito delle soluzioni avanzate.

>[!IMPORTANT]
>
>I plug-in sono forniti da  Adobe Consulting come una cortesia per aiutarti a ottenere più valore da  Adobe Analytics. &#39;Assistenza clienti di Adobe non fornisce supporto per questi plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con un plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

 Adobe offre diversi modi per installare un determinato plug-in:

1. Utilizzare l&#39;estensione &#39;Common Analytics Plugins&#39; con  Adobe Experience Platform Launch
2. Incolla il codice del plug-in utilizzando l&#39;editor di codice personalizzato Launch
3. Incolla il codice del plug-in nel `AppMeasurement.js` file

Ogni organizzazione ha esigenze di implementazione diverse, pertanto puoi decidere come includerle nella tua implementazione. Quando includete il codice nel sito, accertatevi di soddisfare i seguenti criteri:

1. Creare innanzitutto un&#39;istanza dell&#39;oggetto di tracciamento di Analytics (che utilizza [`s_gi`](../functions/s-gi.md)).
   * Avvia crea automaticamente un&#39;istanza dell&#39;oggetto di tracciamento quando  Adobe Analytics viene caricato.
   * Le implementazioni che utilizzano in `AppMeasurement.js` genere inizializzano l&#39;oggetto di tracciamento nella parte superiore del file JavaScript.
2. Includi codice plug-in secondo.
   * L&#39;estensione &#39;Common Analytics Plugins&#39; ha una configurazione di azione in cui è possibile inizializzare i plug-in.
   * Se non desiderate utilizzare l&#39;estensione, potete incollare il codice plug-in nell&#39;editor di codice personalizzato durante la configurazione dell&#39;estensione Analytics.
   * Se l’implementazione non utilizza Launch, puoi incollare il codice plug-in in ovunque dopo aver creato un’istanza dell’oggetto di tracciamento `AppMeasurement.js` in oggetto.
3. Chiamate il plug-in terzo.
   * Tutte le implementazioni, sia all&#39;interno che all&#39;esterno di Launch, utilizzano JavaScript per chiamare i plug-in. Chiamate il plug-in utilizzando il formato documentato nella pagina del plug-in.
4. Convalidate l’implementazione e pubblicate.

Molte organizzazioni chiamano i plug-in utilizzando la [`doPlugins`](../functions/doplugins.md) funzione. Anche se questa funzione non è necessaria,  Adobe ritiene che sia una procedura consigliata. AppMeasurement chiama questa funzione appena prima di compilare e inviare una richiesta di immagine, il che è ideale in quanto diversi plug-in dipendono da altre variabili Analytics.

## Utilizzare i plug-in con oggetti di tracciamento non standard

Per impostazione predefinita, i plug-in non funzionano con oggetti di tracciamento diversi da `s`. Tuttavia, potete modificare il codice del plug-in per adattarlo all&#39;oggetto di tracciamento personalizzato. All&#39;interno di un determinato plug-in, sostituite tutti i riferimenti a `s` con l&#39;oggetto di tracciamento desiderato.

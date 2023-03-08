---
title: Panoramica sui plug-in
description: Incolla il codice sul tuo sito per introdurre nuove funzionalità.
feature: Variables
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 10%

---

# Panoramica sui plug-in

I plug-in sono snippet di codice che eseguono diverse funzioni avanzate per facilitare l’implementazione di Analytics. Questi plug-in estendono le funzionalità del file JavaScript per offrire ulteriori funzionalità non disponibili con un’implementazione di base. Adobe offre molti altri plug-nell’ambito delle soluzioni avanzate.

>[!IMPORTANT]
>
>I plug-in vengono forniti da Adobe Consulting per consentirti di trarre più valore da Adobe Analytics. Adobe L’Assistenza clienti non fornisce supporto per nessuno di questi plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto per un plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare un incontro con un consulente per ricevere assistenza.

Adobe offre diversi modi per installare un determinato plug-in:

<!--1. Use the 'Common Analytics Plugins' extension using the Web SDK or the Adobe Analytics extension-->
1. Incollare il codice del plug-in utilizzando l’editor di codice personalizzato
1. Incolla il codice del plug-in nel tuo `AppMeasurement.js` file

Ogni organizzazione ha esigenze di implementazione diverse, per cui puoi decidere come includerle nell’implementazione. Assicurati di soddisfare i seguenti criteri quando includi il codice sul sito:

1. Crea un&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)) innanzitutto.
   * Il sito abilitato ai tag crea automaticamente un’istanza dell’oggetto di tracciamento al caricamento di Adobe Analytics.
   * Implementazioni con `AppMeasurement.js` in genere, inizializza l’oggetto di tracciamento nella parte superiore del file JavaScript.
2. Includi codice plug-in al secondo.
   * L’estensione Common Analytics Plugins dispone di una configurazione delle azioni in cui è possibile inizializzare i plug-in.
   * Se non desideri utilizzare l’estensione, puoi incollare il codice del plug-in nell’editor di codice personalizzato durante la configurazione dell’estensione Analytics.
   * Se l’implementazione non utilizza i tag in Adobe Experience Platform, puoi incollare il codice del plug-in in `AppMeasurement.js` ovunque dopo aver creato un&#39;istanza dell&#39;oggetto di tracciamento.
3. Chiamare il terzo plug-in.
   * Tutte le implementazioni, sia all’interno che all’esterno di un sito abilitato ai tag, utilizzano JavaScript per chiamare i plug-in. Chiama il plug-in utilizzando il formato documentato nella pagina del plug-in.
4. Convalida l’implementazione e pubblica.

Molte organizzazioni chiamano i plug-in utilizzando [`doPlugins`](../functions/doplugins.md) funzione. Anche se questa funzione non è richiesta, Adobe la considera una best practice da utilizzare. AppMeasurement chiama questa funzione appena prima di compilare e inviare una richiesta di immagine, il che è ideale poiché diversi plug-in dipendono da altre variabili di Analytics.

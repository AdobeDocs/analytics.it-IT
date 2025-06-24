---
title: Panoramica sui plug-in
description: Incolla il codice sul tuo sito per introdurre nuove funzionalità.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 8%

---

# Panoramica sui plug-in

I plug-in sono snippet di codice che eseguono diverse funzioni avanzate per facilitare l’implementazione di Analytics. Questi plug-in estendono le funzionalità del file JavaScript per offrire ulteriori funzionalità non disponibili con un’implementazione di base. Adobe offre una serie di altri plug-in come parte delle soluzioni avanzate.

{{plug-in}}

Adobe offre diversi modi per installare un determinato plug-in:

* Utilizzare l’estensione &quot;Common Analytics Plugins&quot; tramite l’estensione Adobe Analytics
* Incollare il codice del plug-in utilizzando l’editor di codice personalizzato
* Incolla il codice del plug-in nel file `AppMeasurement.js`

Ogni organizzazione ha esigenze di implementazione diverse, per cui puoi decidere come includerle nell’implementazione. Assicurati di soddisfare i seguenti criteri quando includi il codice sul sito:

1. Creare prima un&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)).
   * Il sito abilitato ai tag crea automaticamente un’istanza dell’oggetto di tracciamento al caricamento di Adobe Analytics.
   * Le implementazioni che utilizzano `AppMeasurement.js` in genere inizializzano l&#39;oggetto di tracciamento nella parte superiore del file JavaScript.
2. Includi codice plug-in al secondo.
   * L’estensione Common Analytics Plugins dispone di una configurazione delle azioni in cui è possibile inizializzare i plug-in.
   * Se non desideri utilizzare l’estensione, puoi incollare il codice del plug-in nell’editor di codice personalizzato durante la configurazione dell’estensione Analytics.
   * Se l&#39;implementazione non utilizza i tag in Adobe Experience Platform, puoi incollare il codice del plug-in in `AppMeasurement.js` in qualsiasi punto dopo aver creato un&#39;istanza dell&#39;oggetto di tracciamento.
3. Chiamare il terzo plug-in.
   * Tutte le implementazioni, sia all’interno che all’esterno di un sito abilitato ai tag, utilizzano JavaScript per chiamare i plug-in. Chiamare il plug-in utilizzando il formato documentato nella pagina del plug-in.
4. Convalida l’implementazione e pubblica.

Molte organizzazioni chiamano i plug-in utilizzando la funzione [`doPlugins`](../functions/doplugins.md). Anche se questa funzione non è richiesta, Adobe la considera una best practice da utilizzare. AppMeasurement richiama questa funzione subito prima di compilare e inviare una richiesta di immagine, il che è ideale poiché diversi plug-in dipendono da altre variabili di Analytics.

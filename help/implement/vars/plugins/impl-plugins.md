---
title: Panoramica sui plug-in
description: Incolla il codice sul sito per introdurre nuove funzionalità.
feature: Variables
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
source-git-commit: f3c656b0b631d655159ae89d4622990937cf84ef
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 12%

---

# Panoramica sui plug-in

I plug-in sono snippet di codice che eseguono diverse funzioni avanzate per facilitare l’implementazione di Analytics. Questi plug-in estendono le funzionalità del file JavaScript per offrire ulteriori funzionalità non disponibili con un’implementazione di base. Adobe offre molti altri plug-nell’ambito delle soluzioni avanzate.

{{plug-in}}

Adobe offre diversi modi per installare un determinato plug-in:

* Utilizza l’estensione &quot;Common Analytics Plugins&quot; utilizzando l’estensione Adobe Analytics
* Incolla il codice plug-in utilizzando l’editor di codice personalizzato
* Incolla il codice del plug-in nel tuo `AppMeasurement.js` file

Ogni organizzazione ha esigenze di implementazione diverse, quindi puoi decidere come includerle nell’implementazione. Assicurati di soddisfare i seguenti criteri quando includi il codice sul tuo sito:

1. Creare un&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)).
   * Il sito abilitato per i tag crea automaticamente un&#39;istanza dell&#39;oggetto di tracciamento al caricamento di Adobe Analytics.
   * Implementazioni che utilizzano `AppMeasurement.js` in genere, inizializza l&#39;oggetto di tracciamento nella parte superiore del file JavaScript.
2. Includi il codice plug-in secondo.
   * L’estensione Common Analytics Plugins dispone di una configurazione di azione che consente di inizializzare i plug-in.
   * Se non desideri utilizzare l&#39;estensione, puoi incollare il codice plug-in nell&#39;editor di codice personalizzato durante la configurazione dell&#39;estensione Analytics.
   * Se l&#39;implementazione non utilizza tag in Adobe Experience Platform, puoi incollare il codice plug-in in `AppMeasurement.js` ovunque dopo aver istanziato l&#39;oggetto di tracciamento.
3. Chiama il plug-in terzo.
   * Tutte le implementazioni, sia all&#39;interno che all&#39;esterno di un sito abilitato per i tag, usano JavaScript per chiamare i plug-in. Chiama il plug-in utilizzando il formato documentato nella pagina del plug-in.
4. Convalida l’implementazione e pubblica.

Molte organizzazioni chiamano i plug-in utilizzando [`doPlugins`](../functions/doplugins.md) funzione . Anche se questa funzione non è necessaria, l’Adobe considera come best practice da utilizzare. AppMeasurement chiama questa funzione immediatamente prima di compilare e inviare una richiesta di immagine, il che è ideale perché diversi plug-in dipendono da altre variabili di Analytics.

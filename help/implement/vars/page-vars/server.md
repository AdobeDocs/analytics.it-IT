---
title: server
description: Popolare la dimensione "Server".
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---

# server

La `server` in genere memorizza il nome host del sito. Viene comunemente utilizzato nelle suite di rapporti che contengono dati di più domini. È funzionalmente identico a un prop.

## Server che utilizza l’SDK per web

Server [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) nel campo XDM `web.webPageDetails.server`.

## Server che utilizza l’estensione Adobe Analytics

Puoi impostare il server sia durante la configurazione dell’estensione Analytics (variabili globali) sia in base alle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Server] sezione .

Puoi impostare il server su qualsiasi valore stringa o elemento dati.

## s.server in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.server` è una stringa che in genere contiene il nome host del sito. ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

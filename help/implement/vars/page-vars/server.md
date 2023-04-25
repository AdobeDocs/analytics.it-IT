---
title: server
description: Popolare la dimensione "Server".
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 36%

---

# server

La `server` in genere memorizza il nome host del sito. Viene comunemente utilizzato nelle suite di rapporti che contengono dati di più domini. È funzionalmente identico a un prop.

## Server che utilizza l’SDK per web

Server [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `web.webPageDetails.server`.

## Server che utilizza l’estensione Adobe Analytics

Puoi impostare il server sia durante la configurazione dell’estensione Analytics (variabili globali) sia in base alle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta la [!UICONTROL Extension] elenco a discesa in Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Server].

Puoi impostare il server su qualsiasi valore stringa o elemento dati.

## s.server in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.server` è una stringa che in genere contiene il nome host del sito. Può avere un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

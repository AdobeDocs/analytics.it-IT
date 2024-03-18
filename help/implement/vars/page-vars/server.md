---
title: server
description: Popolare la dimensione "Server".
feature: Variables
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 26%

---

# server

Il `server` La variabile in genere memorizza il nome host del sito. Viene comunemente utilizzato nelle suite di rapporti che contengono dati provenienti da più domini. È funzionalmente identica a una prop.

## Server che utilizza il Web SDK

Il server è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.server`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.server`

## Server che utilizza l’estensione Adobe Analytics

Puoi impostare il server sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta il [!UICONTROL Extension] in Adobe Analytics e nella sezione [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Server].

Puoi impostare il server su qualsiasi valore stringa o elemento dati.

## s.server in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.server` variabile è una stringa che in genere contiene il nome host del sito. Ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```

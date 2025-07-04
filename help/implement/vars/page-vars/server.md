---
title: server
description: Popolare la dimensione "Server".
feature: Appmeasurement Implementation
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 26%

---

# server

La variabile `server` in genere memorizza il nome host del sito. Viene comunemente utilizzato nelle suite di rapporti che contengono dati provenienti da più domini. È funzionalmente identica a una prop.

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
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Server].

Puoi impostare il server su qualsiasi valore stringa o elemento dati.

## s.server in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.server` è una stringa che in genere contiene il nome host del sito. Ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
